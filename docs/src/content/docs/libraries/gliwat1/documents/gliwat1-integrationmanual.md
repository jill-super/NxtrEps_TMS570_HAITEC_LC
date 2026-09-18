---
title: "GliwaT1 IntegrationManual"
description: "Converted from GliwaT1_IntegrationManual.doc"
---

> **Source document:** `GliwaT1/doc/GliwaT1_IntegrationManual.doc`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: legacy Word document (`.doc`).

> **Note:** the original file is a legacy binary Word document (`.doc`) which cannot be converted with full fidelity in this environment. The text below was recovered automatically and may be out of order in places; tables and figures are not preserved. See the original file for the authoritative content.

bjbj$

## Module Design Document

GliwaT1

Note: Quick Start guide at end of document provides integration overview.

Document Identifier: <Project_id>_<Config Id>

VERSION: GliwaT1_01.00

DATE: May 19, 2014

Prepared By:

## Core Software,

## Nexteer Automotive,

## Saginaw, MI, USA

Location: The official version of this document is stored in the Nexteer Configuration Management System and is uniquely identified by: <Project_ID>_<Config Id>

## Revision History

Sl. No.

## Description

## Author

## Version

## Initial Version

## Blake Latchford

May 19, 2014

Updates per review with Michale Story.

## Blake Latchford

July 14, 2014

## Table of Contents

## Abbrevations And Acronyms

## References

## Dependencies

## Global Functions(Non RTE) to be provided to Integration Project

## Configuration

## Build Time Config

## Configuration Files to be provided by Integration Project

## Da Vinci Parameter Configuration Changes

## DaVinci Interrupt Configuration Changes

## Manual Configuration Changes

## Integration

## Required Global Data Inputs

## Required Global Data Outputs

## Specific Include Path present

## Runnable Scheduling

## Memory Mapping

## Mapping

## Usage

## Non RTE NvM Blocks

## RTE NvM Blocks

## Compiler Settings

## Preprocessor MACRO

## Optimization Settings

## Appendix

## Abbrevations And Acronyms

## Abbreviation

## Description

## Design functional diagram

## Module design Document

## References

This section Lists the title & version of all the documents that are referred for development of this document

Sr. No.

## Title

## Version

<Add if more available>

## Dependencies

## Module

## Required Feature

## Metrics

Must be removed from integration project.

## Global Functions(Non RTE) to be provided to Integration Project

T1_TraceStartNoSusp

For use in motor control ISR.

T1_TraceStopNoSusp

For use in motor control ISR.

Metrics_TaskStart

For use inAllows backwards compaitibilty with existing Metrics configuration. Also to be used when interrupt disabling is required.

Metrics_TaskStop

Same as Metrics_TaskStart, but for the end of the task.

## Configuration

## Build Time Config

## Modules

## Notes

## Configuration Files to be provided by Integration Project

Examples of the following configuration options can be found in the GliwaT1\utp\Example_Tools_GliwaT1\config\ folder. This folder contains data intended to go in the project path Tools directory (not the component).

config

These files configure the Gliwa provided PERL scripts that generate various files when integration is performed. Some of the values more likely to change between projects are called out below.

T1_Cfg.inv

txCycle

Time in ms between calls to T1_AppHandler.

t1ScopeOverheadNs

Overhead to be filled in as called out in Overhead_Calculation.xlsx (Can be found in component tools directory) .

t1FlexOverheadNs

Overhead to be filled in as called out in Overhead_Calculation.xlsx.

T1_OsCfg.inv

## Shouldn

t change per project.

T1_UserCfg.inv

projectName

Name of the program (C1xx, LWR, UKL, etc.)

traceBufferEntries

Size of the trace buffer. This number determines how much RAM is required to store trace events. A minimum for this number on a typical system would be in the range of 300-400 entries. If more space is added to this buffer then each trace download will be able to show a larger picture. If this buffer is made too small then data will be lost, resulting in errors and incomplete data collection.

## Da Vinci Parameter Configuration Changes

## Parameter

## Notes

## DaVinci Interrupt Configuration Changes

## ISR Name

VIM #

## Priority Dependency

## Notes

Isr_MtrCtrl

Add T1_TraceStartNoSusp(T1_Isr_MtrCtrl_ID) and T1_TraceStopNoSusp(T1_Isr_MtrCtrl_ID) calls to the beginning and end of the ISR.

## Any other ISR

Add Metrics_TaskStart(<ID>) and Metrics_TaskEnd(<ID>) to the beginning and end of each ISR. ID will be a symbol generated from the .ecuc.arxml file.

## Manual Configuration Changes

## Constant

## Notes

<Additional configuration changes>Messages need to be added to the .dbc file.

GENy must be updated.

Gliwa communicates on CAN via a custom protocol on the CAN bus. It uses IDs that must be distinct from other IDs already in use. By default these are 0x7FA and 0x7CB. They can be reconfigured if a program intends to use these identifiers for a different purpose.

## Target to Host

The 0x7FA message is used to transmit data from the target (ECU) to the host (PC). In the example provided this is done by use of the CanMsgTransmit() API. If the program supports this API it will likely need to be turned on via the Low Level Transmission.

If this API is unavailable, adding a spontaneous message to the database may be used as an alternative. Once that is completed the standard spontaneous message transmission methods for a SIP can be used. An example of this spontaneous messages is shown below.

## Host To Target

The 0x7CB message is used by default to transmit data from the host (PC) to the target (ECU). This message must be added to the database file to ensure that the hardware doesn

t filter out the message. AN example of the message configuration for this message is shown below.

## Integration

## Required Global Data Inputs

<Mention any global variable that this component requires for other components>

## Required Global Data Outputs

<Mention any global variable that this component requires for other components>

## Specific Include Path present

## Runnable Scheduling

This section specifies the required runnable scheduling.

## Scheduling Requirements

## Trigger

T1_AppInit

As early as possible. Recommend the beginning of the main function.

## Runnable

## Scheduling Requirements

## Trigger

T1_AppHandler

10ms (alternatively, the time called out by txCycle)

Manually scheduled.

T1_AppBgHandler

## Background

Background task.

## Memory Mapping

Memory mapping for this component is performed directly through the linker command file. The following sections must be defined.

.T1_bss

This section should be placed somewhere in RAM. No assumptions are made about the initialization of this memory. This memory is only accessed from a trusted application.

.T1_traceBuffer

This is similar to .T1_bss, but is sepearated for flexibility of placement due to its large size. It contains the ring buffer for logged trace events.

.T1_code

Should be placed similarly to the existing .text section. Application flash is the recommended location.

.T1_const

Expects to be initialized. Application flash is the recommended location.

.T1_codeFast

Code that needs to execute quickly. It has been shown that execution from RAM has minimal impact, though for consistent overhead measurements the following sections should be aligned to a 16 byte flash boundary.

.T1_codeFast:T1_TraceEventNoSusp_

.T1_codeFast:T1_GetTraceTime

.T1_codeFast:T1_TraceEventFast_

## Mapping

## Memory Section

## Contents

## Notes

* Each

START_SEC

constant is terminated by a

STOP_SEC

constant as specified in the AUTOSAR Memory Mapping requirements.

## Usage

## Feature

## Table

SEQ Table \* ARABIC

: ARM Cortex R4 Memory Usage

## Non RTE NvM Blocks

## Block Name

## RTE NvM Blocks

## Block Name

## Compiler Settings

## Preprocessor MACRO

T1_ENABLE will be defined after the integration script is run. If this does not occur then something went wrong in the overlay of T1_AppInterface.h. This can be debugged by viewing the text output of the PerformOverlay.bat file.

## Optimization Settings

## Appendix

## Gliwa Repository

For updates to the Gliwa T1 library or any additional files Gliwa has provided an Xfer server for access by Nexteer employees.

https://gliwa.com/xfer

Username: nexteer

Password: la7Feje7

## Files to be provided by the integration project

Examples of these files can be found in the folder GliwaT1/utp/Example_Integration_Specific

T1_Appinterface_Cfg.c

This file provides an interface for the reception and transmission of messages on the CAN bus in order to communicate with the host PC. Since messages are handled differently depending on the Vector SIP provided, a wrapper must exist for this functionality.

On reception of a message from the host PC, the target ECU must call the T1_RxCallback function. The buffer passed to this function is processed in the T1_AppHandler call. Therefore the buffer most remain valid constantly. A temporary buffer declared at the beginning of the fuction is not sufficient. Furthermore the function must swtich to privldiged mode to permit acces to T1 RAM.

T1_Trasmit is called by T1_AppHandler when T1 needs to transmit a message. The application is responsible for ensuring that this data is put on the bus in the correct order, and before the next call to T1_AppHandler. Any switch to supervisor mode would be redundant as it is already performed in the handler.

T1_Appinterface_Cfg.h

This file contains several constants for backwards compatilbity. D_I2CNXT_CNT_U08, D_SPINXT1_CNT_U08, and D_SPINXT2_CNT_U08 must be included if either of these Nexteer the SpiNxt or I2cNxt components are included. They should be redefined to use the T1 generated constants rather than using a literal. For example if the I2C component is included the following can be used to alias the Identifier.

#define D_I2CNXT_CNT_U08 T1_Isr_I2c_ID

The PollT1HostToTarget function like macro should be defined if the application uses polling to handle messages. If any headers are required to poll for the message they should be included in T1_Appinterface_Cfg.h.

D_GLIWAT1_SWITCHTOPRIVMODE_CNT_LGC should be set to STD_ON if the target application uses MPU regions. This puts all memory accesses by T1 into privlidged mode, so its memory can be allocated anywhere.

D_GLIWAT1_SLOWWAITSTATES_CNT_LGC should be set to STD_ON if the standard wait states of 3dws and 1aws are used. If seto STD_OFF it is assumed that there are 2dws and 0aws. If this is set incorrectly there will be an increase in measurement overhead.

## Executable Scripts

Two batch files are provided in the UTP/Example_Tools_GliwaT1 folder. Perform integration copies the overlay onto the file system, and perfroms the necessary generation steps. The remove integration batch file removes the overlay from the working directory. They are both intended to run from the projects Tools/GliwaT1 folder.

These scripts expect that Perl has been installed locally, and the AsrToOil utility has been installed in the Tools folder of the integration project. Active Perl has been used in the past, but any windows implementation of Perl should work. No modules other than those provided by Gliwa are required to run these scripts.

## Overlay

The point of the overlay is to change files that cannot be modified for an official build. Examples of this include the OS, and vector provided ISRs. The overlay should contain a duplicate of the files contained which are intended to be changed. Since the many of the most important files to be replaced are provided by the Vector SIP, different SIPs will have to tailor their overlay folder to their project.

For ISRs that execute in an non-trusted application it is recommended that the Metrics_TaskStart and Metrics_TaskEnd interface is used. This interface ensures that the events are logged in a privlidged mode. The ID provided should be the ID generated by the Gliwa Perl scripts.

## Basic Test Guidelines

## Minimum Conditions for a Valid Test

## Merged with calibrations traceable to eCalNet

Any modifications should be noted in the report comments.

Every serial communications message that EPS receives being transmitted on all busses.

Controller enters operate state without any defeats enabled.

Turn on all conditionally enabled functionality.

Examples include Lane Keeping Assist on GM C1xx, and Black Box functionality on Ford S550.

Gliwa T1 configuration

Overheads should be re-calculated using Overhead_Calculation.xlsx which is located in the component

s tools directory.

All ISRs must be instrumented, with the exception of any that do not return.

## Required Measurements

## Overall average CPU usage

Appears on report as average CPU use from T1.cont

## Task core execution time

## Task chain time

Time from the activation of the first task executed at a periodic rate, to completion of the last task in that periodic rate.

## Additional Measurements

Motor Control ISR function execution times.

## Task chain thresholds

Add T1_Delay calls to the end of each task, and increase the delay until a failure occurs.

## Quick Start Guide

Remove any existing traces of the old Metrics Component. This includes the component, and any configuration files (likely within the GenData directory).

Add GliwaT1 component to Synergy

## Copy the contents of the Gliwa component

s utp/Example_Tools_GliwaT1 directory to the project

s Tools directory in a new GliwaT1 folder.

Modify the Overlay directory to conform to the expected layout of the project.

The GM_C1XX_EPS_TMS570 folder at the highest level in the Overlay directory will have to be renamed to the name of the project.

All interrupts must be instrumented. See section

. If the OS has changed since integration int C1xx, the OS files will have to be updated appropriately. If significant changes to the OS have occurred then Gliwa support may be required.

Add the two messages to allow the host (PC) software to communicate with the target (ECU).

## See section

## Nexteer Automotive Confidential Proprietary Information

## Do Not Copy/Distribute Without Prior Permission

## Module Design Document Template

Version: <Version> Date: DD-MMM-YYYY

Document identifier: <Project_id>_<Config id>

## Nexteer Automotive

|pgp|p|

_P_>P_P

aWaJWaW

~X~SIS<

xRxMCM

bXbKXbX

qSqH9H

aWaJWaW

of]TG:-

~qmfm]OmH

vi_SG

r''d&

i_U_UK:

r''d&

ylhdWlhIhB8h

gd_@'

|skfka[R[L

xoxoxid

r''d&

gxSIxgx

r''d&

xqf]qYS

gdd<O

phfff

gdd<O

r''d&

r''yt

_Toc387219713

_Toc387219714

_Toc387219715

_Toc387219716

_Toc387219717

_Toc387219718

_Toc387219719

_Toc387219720

_Toc387219721

_Toc387219722

_Toc387219723

_Toc387219724

_Toc387219725

_Toc387219726

_Toc387219727

_Toc387219728

_Toc387219729

_Toc387219730

_Toc387219731

_Toc387219732

_Toc387219733

_Toc387219734

_Toc387219735

_Toc387219736

_Toc387219737

Picture 1

IDATx^

M0&AFm%H

)us\&

ifO'{

-ZTYY

Bt!k$

veUb3(G

I++,\l

"*,Y=&

UE{%E

{!AeCw

uged7

.N29}

x/u_w

L#j&I

6,5'X|

2HmHL

d5Jo<

/NHv\P

<OG!*

z&AcR;

M_E1X#

u%$1dS

eJNIYaO

n?#[3

K(pQ{

v}FiRO

0)!-Y

,iF2Q

## ZUJHH

q"p2h

n!yvIBZ

|r#f=

T$(/!!5

Gb<O#

pDRk!

aTP7OK

rDr%$

sgO[o

)<B9j

}#1;v

9gO_+,

Ug=cF?

H^!$'I

_9gMj

BDxy[j

-3k{U

U&"z,

"t;[#

%zOW`0

AIn?nr

(HKwf

~V/4#

X'Kz:

c\/$V^%oQ

8PNkS

6\[<{

47UyR

ME~1mV

)km)sx

7A7}s\

LS9EX7

yV(%z

C~)3z

ez9&+

[M0IaS3

%lxZx

$>n<\l

_J*sP

myP\i

0)^2[

$>${%-pl8

$|Ae{

rO'iLO~I#

f[H|6

Mk(M.

1G(dF

y;9(qaU

O-I'g

I8.y7

W/__FFRR

0)DyB'

CrN7!

?T6U^Z

#=eN?

[(D0O

H`_J&\

hg9KE:

O=\56

eJ.o0

iLHeE

q/s3t2

D?;yK

L6VR7hOi

}<bd.n[

"YBCP?

BO-$o

xfb_O

'Dgcl

q1sI5

G;R!w

Myrr[UD

Pr^zL

Cy/E_q

pD2jN

s\x7M

r`G"q+

!7H_$+|

/b$$7

)l&cSn

h9H*:Z+

v)2ce;

## YBdO hO

M4.:+

(e4oT#0

=\]t!

9$O*yH

-)&__

V#uU"[Q

aFuY^

3NR-!

z$WkD%.

zHfUQ

## SD)oR

7%h$nE

S~!IYazV

Lq<9I

Y>5F8

QU"j|

n%IRO

d_):K

JH\CAa(

Eo*%!

[%M[Wq

u{]7Q

8m!8|

.47##c

[ yWA39

h]\^,

.KO~i

5C*=@

O=mT[+!

IJH5O

/Xyoo}

gE[V}

Ra':&z

lKHr-m

v[rL;

a^XU{B

k[hUF

T*OL`

STRF3

VG2krS

3Z&gs

gBD=z

s'IH$

F{!9_9FHH

4 *)Z

\EPWDj

## ZMijz

<n|HvA

N}(.iIYSh

lXkE|

{U$w5

oEm10

rHfkJ

8<aMLd

)(INJ

kz-$[

[5;KE"

FT1SM

[v{"[L

y-$)!

e9A[6

g-$s*

#RsIH

GYM0k

## ZHrEmg

@j.^v@

%m\[BJ

aC{/9

[BBck

]FIHx

H$!i/$

[oYP'

.]h9w

.~W7?

Q$"Fkj

^r;Gz

h%:5^

^Hz%"

\q(<e

%jV<H

jjl=z

MHH3IB

&$KHt

*!u`D(

9r$KH_

S6N: y6Rp

## ZQSSQ

Hr#!i_=)H

X)"95[

h%}Y[

\h-$R

grrA*

+s*x*

4NJ"lE

-V8s9

|R(5kWm

FRH"Q

H<b9J

1M= ,

{)XAA

## UWWSc

hr~~>

?t<!u

;SN&&

Xn)9g

xdv2G

X>DG6

[X8s9

)2HU:

M`axquD

VTW9e

mYX2o

'L`')

## TbNyC

## KCCCp

<N.Ht

^riAA

## JuuuLc

I?by(f

gUU1-\S4

## UTQCv

Jn@B(

## KgWJy

p&*_c

.{ _!

{)XAA

(KvA:

;w.$$

@[ @2

3CWN|

8M;V(

jMy&3rA

%)vkio

Y;n00

~D6W9e

Hf"\QE

Yj4u.

2>4el

^riAA

## UVVFM

[8s9D

_-<O-

i?Vm^

4VBJbk{

;.t"[

Kah0Z

j|$4_

VbD$- 9u

AnG%rh>s

## JJAP/

t^HI0

S;sc-MkS

N}}C=

dVEE+

d!m;L

2eJccc}}C=

"#-i=H

+;jcC

63O.d

&$Z,[

D~L,G

N~N,qL[-<

@aEMM

6{FM7

)a]GMX

P\>P6

e%P4p

&`--7

## SkT/A

Obz=m

Vdb%"

(;_(MZ

)2-P6$

,63YMHH

H]DudWA

GLW9b

K^H9+A

K.-((

-yCGH

V[]\1u

i=%^J

{)XAA

## JHQze

f]X)[V8

bQ}B,r

HXO;I

IM)N+

H}!G-zM

Oy9;+I

,QSlN

E,H^:{

:\:}m
