---
title: "MotorVelocity3 Module Design Document"
description: "Converted from MotorVelocity3_MDD.doc"
---

> **Source document:** `MtrVel_Digi/doc/MotorVelocity3_MDD.doc`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: legacy Word document (`.doc`).

> **Note:** the original file is a legacy binary Word document (`.doc`) which cannot be converted with full fidelity in this environment. The text below was recovered automatically and may be out of order in places; tables and figures are not preserved. See the original file for the authoritative content.

## Module -- Motor Velocity

## High-Level Description

## Figures

## Diagram

## Function Data Sharing

This diagram shows all data that is shared between functions within the module.

## No Shared Data

## Variable Data Dictionary

For details on module input / output variable, refer to the Data Dictionary for the application. Input / output variable names are listed here for reference.

(Note: Full variable names required in table.)

(Note: All global variables including End Of Line data used should be shown here)

## Module Inputs (Global Variable Name)

## Module Outputs (Global Variable Name)

MechMtrPos1_Rev_u0p16

MechMtrPos1SampleTTimeStamp1_uS_u32

## Module Internal Variables

This section identifies the name, range and resolutions for module specific data created by this module. If there are no range restrictions on the variable, the term

is placed into the table for legal range.

## Variable Name

## Resolution

## Legal Range

(min)

## Legal Range

(max)

## Software Segment

MtrVel3_PosBuffer_Rad_M_u0p16f32

2^-16

6.283089433380357147216796875

MTRVEL3_START_SEC_VAR_CLEARED_1632

MtrVel3_TimeBuffer_uS_M_u16p0

MTRVEL3_START_SEC_VAR_CLEARED_16

MtrVel3_OsBufPos_Cnt_M_u08

MTRVEL3_START_SEC_VAR_CLEARED_8

* Note: These ranges are based on the range of the normalized sine and cosine global inputs, which in turn are based on the maximum amount of signal variation that can be caused by temperature changes on the MSB signals.

## User defined typedef definition/declaration

This section documents any user types uniquely used for the module.

## Typedef Name

## Element Name

## User Defined Type

## Legal Range

(min)

## Legal Range

(max)

## Constant Data Dictionary

## Calibration Constants

This section lists the calibrations used by the module. For details on calibration constants, refer to the Data Dictionary for the application.

## Constant Name

## Program(fixed) Constants

## Embedded Constants

All embedded constants whose values are provided in Eng units will be evaluated to the equivalent counts by using the FPM_InitFixedPoint_m() macro within the #define statement.

## Local

## Constant Name

## Resolution

## Value

D_BUFFERMASK_CNT_U08

D_MTRVELOSBUFSZ_CNT_U08 - 1

## Global

This section lists the global constants used by the module. For details on global constants, refer to the Data Dictionary for the application.

## Constant Name

## Module specific Lookup Tables Constants

(This is for lookup tables (arrays) with fixed values, same name as other tables)

## Constant Name

## Resolution

## Value

## Software Segment

## Functions/Macros used by the Sub-Modules

## Library Functions / Macros

The library functions / Macros that are called by the various sub modules are identified below,

## Data Hiding Functions

## The data hiding functions / macros used in this module are identified below,

## Local Functions/Macros Used by this MDD only

(Note if they are defined in another source file, then reference the appropriate header file)

## The local functions/macros in this module are identified below,

## Software Module Implementation

## Initialization Functions

Init: MtrVel3_Init1

## Design Rationale

## Module Outputs

## Module Internal

MtrVel_Read_MechMtrPos1_Rev_u0p16(&MtrPos_MechMtrPos_Rev_T_u0p16)

MtrVel_Read_MechMtrPos1SampleTime_uS_u32(&MtrPos_SampleTime_uS_T_u32) MtrVel_Read_SampleTime1_uS_u32(&MtrPos_SampleTime_uS_T_u32);

MtrVel_PosBuffer_Rad_T_f32 =(FPM_FixedToFloat_m(MtrPos_MechMtrPos_Rev_T_u0p16, u0p16_T))*D_2PI_ULS_F32

## Description

EMBED Visio.Drawing.11

## Periodic Functions

Per: MtrVel3_Per1

## Design Rationale

## Program Flow Start

## Store Module Inputs to Local copies

MtrVel_Read_MechMtrPos1_Rev_u0p16 MtrVel_Read_MechMtrPos1_Rev_u0p16(&MtrPos_MechMtrPos_Rev_T_u0p16);

MtrVel_Read_MechMtrPos1TimeStamp_uS_u32 MtrVel_Read_SampleTime1_uS_u32(&MtrPos_SampleTime_uS_T_u32);

## Populate Sample Buffers

EMBED Visio.Drawing.11

## Store Local copy of outputs into Module Outputs

## Program Flow End

## Fault Recovery Functions

## Shutdown Functions

## Interrupt Functions

## Serial Communication Functions

## Local Function/Macro Definitions

If these are numerous and defined in a separate source file then reference the source file only.

## Execution Requirements

## Execution Sequence of the Module

(Describe in words relevant details about the execution sequence of the different sub modules.)

## Execution Rates for sub-modules called by the Scheduler

## This table serves as reference for the Scheduler design

## Function Name

## Calling Frequency

## System State(s) in which the function is called

MtrVel3_Init1

## ALL STATES

MtrVel3_Per1

## Motor Control ISR

## ALL STATES

## Execution Requirements for Serial Communication Functions

## Function Name

## Sub-Module called by (Serial Comm Function Name)

## Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in this module.

## Name of Sub Module

## Software Segment

MtrVel3_Per1

RTE_SA_MTRVEL3_APPL_CODE

## Known Issues / Limitations With Design

The range limits are not applied to task running at Motor Control ISR. As the limiting adds few more instruction cycles, the ranges for those variables should be applied at 2ms N/A

## Revision Control Log

Item #

Rev #

## Change Description

## Author Initials

Initial release for FDD v01

6-03 -13

## Updated the Port name from Motor Pos to Motor Velocity

7-30-13

## Selva

## Updated Port interface name to match the FDD

8-22-13

## Selva

## SOFTWARE MODULE DESIGN SPECIFICATION

Title:

Motor Velocity 3

Gen II+ EPS

Revision:

Product:

Rev. Date:

223-JuneAug-13

Group:

Originator:

## Selva

Page:

## NUMPAGES

## NEXTEER CONFIDENTIAL

S/W module design template, Rev 3.1b

ubRbRbRb

gd`-^

yt`-^

oZHZH

{le]YNF]B;7;B7

zvzvzvzvqmiem]m]Y]m

xqxqx

yt`-^

## Root Entry

## Data

## WordDocument

## ObjectPool

_1438682462

## EPRINT

## CompObj

## Microsoft Visio Drawing

Visio 11.0 Shapes

Visio.Drawing.11

kzshz2

EMF+0@

EMF+*@

## ARIAL

## Start

## Arial

## Start

EMF++@

EMF+*@

EMF++@

EMF+*@

EMF++@

EMF+*@

## MtrVel

EMF++@

## OsBufPos

EMF++@

## MTRVELOSBUFSZ

>Pd8@

>P><@

## MTRVELOSBUFSZ

EMF++@

>@"M@

EMF++@

EMF+*@

EMF++@

EMF+*@

## MtrVel

EMF++@

## TimeBuffer

EMF++@

## MtrPos

EMF++@

## SampleTime

EMF++@

EMF+*@

EMF++@

EMF+*@

EMF++@

EMF+*@

EMF++@

## MTRVELOSBUFNUM

Y>@}A?

Y>@Zm?

Y>@bz?

## MTRVELOSBUFNUM

EMF++@

EMF+*@

EMF++@

EMF+*@

EMF++@

## MTRVELOSBUFNUM

Y>@}A?

Y>@Zm?

Y>@bz?

## MTRVELOSBUFNUM

EMF++@

EMF+*@

## MtrVel

EMF++@

## PosBuffer

EMF++@

## MtrPos

EMF++@

## MechMtrPos

>@5#@

## MechMtrPos

EMF++@

> aG@

EMF++@

EMF+*@

EMF++@

EMF+*@

E]C6@

EMF++@

## ObjInfo

## VisioDocument

## VisioInformation

## SummaryInformation

## Visio (TM) Drawing

#/8/?M

>S@#B:

iz4}1

,3Y&4Y&5

?%?7?I?[;

SEn%cO

_!_3_E_W_

4/F/?

o o2oDo

"+z1c

1/C/U/g/y/

1?C?U?g?y?

<ONO`OrO

>_P_<b_os

o&o8oJo\o

jHB/T/

f/x.m

$?6?H?Z?l?~?

O#OFa1:BQ

q[\OnO

_%_7_I_

o*o<oNo

(0_B_

?/qd/

56rCD?

mina

,%"usi"iO*b

|!p#f-S

$gM",

g on

opyr

M`0c^0o

%sX0ff2W1rZ0

1uaf0iX0n

0 ^8Us

0e^0v

_O*J y

EHgA^_R

0euXojf

W15sYR

Dq!X(b

uQuQ"2

## U wM h

tY bu R!cY uiW fU r

tS&j%,

"aJY pw oM ^!sY

!ew ,

-SO xY 6

0OY G9

(E?W?

)!4)!2

g th

opyr

&K?hL

#5#0O

E2Zo.u

m1"uI

g th

## Tt (

(sT"e

vf dY

Tm!#

Rf"o*

PU0%!p

s& ,& wu

m d. l>"Wb

a& i" ,

Ul w" hR r8 U,

"f rB a8"Io

"i|*b. U!

g on

y9 Wi

(S0u)s

ME0uc9 oG0o

2Rs1rv0

0it0unQ0 s

0U z8s

2eG0e9 Ev

0dQ0h0

"u$mV

n]4i&E2IoG

+25Qq#

%`#p$"

`@mP!

0h0,"

&#V=3

"i*:Ab

4g(2,

ag t

]W7c:&

w"`?C

)@2U@0

`m!#

1}23$

A;a"`

T.(Ph

09qo4P

$\v}5

_$UF_

s co

} fV6

Tm!#

U ?D1f@M)@c<0

fdBUArTX@

Aad@iV@n3@] f@A

@ \HUs

Be+@e<0v

d3@J@

SV6U8

c0xo)

W,_74b

:\Pr

\BAS

/>?P?C

!&j6E

4!&<F

!&ZFM

P#NSp+NS

1X]`;NS

ANS<ANSZANSxANS

'xsUiq

!z!>! !

2VirU

rmKU\

.o@ms

!32,r

}O7/I/[/m/H

?!?3?

OW?i?{?

_$_6_r

Jo\o(/:/

F*r0Z

O!O3OEOWO

/_A_S_e_w_

o+o=o

=b_@t_

/&/8/J/

## MtrV

?!?3?E?

W?i?{?9O

_._@_

@/R/d/v%

#hA/S

? ?2?D?~

O.O@OROdOvO

8oJo\o

_:_LZ{

@~U@@

0&DBNs

o(o:of

$X!Jq

U]ippAr]u`=u`80s@s

/`#R-9

O*Fp!U4{/

?+?}_

__OqO

e3/E/

_1_C_U_g_>

?S/e/w/

?/?A?

S?e?w?

q/e%u

P8d"O

'_9_D

sWGrq

<p@z3

7!A+yG1pG53?I?[4

uOp`u

/).&WA

&7oIj

O*O<G

_-_oaC_

vEUU0

/$/6/

`Bu6Mp`u

0_B_T_f_xU

o/oAoSoeowo

[lpQo

-@KqEX

c_u_lP

HUf9^

/)/;/M-

?]?o?

;OMO_OqO

_-_?_

/(&F#

qP/b/t/

L?^?p?

6OHOZO

_1_C_U_Jg[

%o7oIo[o

?@U`?b

4By1fE

(?:?L?^?p6

o.o@oRodovo

maxGO

rial

ymbo

## Ming

## S PG

othi

tran

gelo

rind

hrut

ordi

a Ne

## S Fa

imes

## Guide

rmin

## Cost

rati

sour

Row_1

tiSc

rmin

nami

xtPo

Row_2

Row_3

Row_4

Row_5

-pag

*j'"D

nzt9hv

## Microsoft Visio

## Nexteer

Page-1

## Terminator

## Decision

## Process

## Predefined process

Off-page reference.5

## Dynamic conn

## DocumentSummaryInformation

_1432575440

## CompObj

ector

## Pages

## Masters

_PID_LINKBASE

_VPID_ALTERNATENAMES

## Microsoft Visio Drawing

Visio 11.0 Shapes

Visio.Drawing.11

## ObjInfo

## VisioDocument

## VisioInformation

## SummaryInformation

## Visio (TM) Drawing

#/8/?M

>S@#B:

iz4}1

,3Y&4Y&5

?%?7?I?[;

SEn%cO

_!_3_E_W_

4/F/?

o o2oDo

"+z1c

1/C/U/g/y/

1?C?U?g?y?

<ONO`OrO

>_P_<b_os

o&o8oJo\o

jHB/T/

f/x.m

$?6?H?Z?l?~?

O#OFa1:BQ

q[\OnO

_%_7_I_

o*o<oNo

(0_B_

?/qd/

56rCD?

mina

,%"usi"iO*b

|!p#f-S

$gM",

g on

opyr

M`0c^0o

%sX0ff2W1rZ0

1uaf0iX0n

0 ^8Us

0e^0v

_O*J y

EHgA^_R

0euXojf

W15sYR

Dq!X(b

uQuQ"2

## U wM h

tY bu R!cY uiW fU r

tS&j%,

"aJY pw oM ^!sY

!ew ,

-SO xY 6

0OY G9

(E?W?

)!4)!2

g th

opyr

&K?hL

#5#0O

E2Zo.u

m1"uI

g th

## Tt (

(sT"e

vf dY

Tm!#

Rf"o*

PU0%!p

s& ,& wu

m d. l>"Wb

a& i" ,

Ul w" hR r8 U,

"f rB a8"Io

"i|*b. U!

g on

y9 Wi

(S0u)s

ME0uc9 oG0o

2Rs1rv0

0it0unQ0 s

0U z8s

2eG0e9 Ev

0dQ0h0

"u$mV

n]4i&E2IoG

+25Qq#

%`#p$"

`@mP!

0h0,"

&#V=3

"i*:Ab

4g(2,

ag t

]W7c:&

w"`?C

)@2U@0

`m!#

1}23$

A;a"`

T.(Ph

09qo4P
