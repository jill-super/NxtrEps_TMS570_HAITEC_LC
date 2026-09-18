---
title: "TorqueCmdScaling Module Design Document"
description: "Converted from TorqueCmdScaling_MDD.doc"
---

> **Source document:** `MtrCtrl_CM/doc/TorqueCmdScaling_MDD.doc`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: legacy Word document (`.doc`).

> **Note:** the original file is a legacy binary Word document (`.doc`) which cannot be converted with full fidelity in this environment. The text below was recovered automatically and may be out of order in places; tables and figures are not preserved. See the original file for the authoritative content.

bjbjBrBr

## Module -- Torque Command Scaling

## High-Level Description

The Torque Command Scale module multiplies the Torque_Command_MRF input signal by a calibration which is set during a manufacturing EOL calibration process. This calibration is provided to reduce overall system output torque variation. This scaled version of the torque command is used by all other sub functions within motor control which have a torque dependent component.

## Figures

## Diagram

## Function Data Sharing

This diagram shows all data that is shared between functions within the module.

## Diagram

## Function (Name)

This diagram describes the functional characteristics and data flow of a given function.

(Note

This is not mandatory, only used where a graphical representation helps explain the function. It is left to the author

s discretion. New headers of this level (Level 3) should be created for each function.

## Variable Data Dictionary

For details on module input / output variable, refer to the Data Dictionary for the application. Input / output variable names are listed here for reference.

(Note: Full variable names required in table.)

(Note: All global variables including End Of Line data used should be shown here)

## Module Inputs (Global Variable Name)

## Module Outputs (Global Variable Name)

MRFMtrTrqCmd_MtrNm_f32

MRFMtrTrqCmdScl_MtrNm_f32

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

k_MinTrqCmdScl_Uls_f32

k_MaxTrqCmdScl_Uls_f32

TorqueCmdSF_Uls_f32 (NVM)

## Program(fixed) Constants

## Embedded Constants

All embedded constants whose values are provided in Eng units will be evaluated to the equivalent counts by using the FPM_InitFixedPoint_m() macro within the #define statement.

## Local

## Constant Name

## Resolution

## Value

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

Limit_m()

## Data Hiding Functions

## The data hiding functions / macros used in this module are identified below,

Rte_Call_TrqCmdScl_WriteBlock()

Rte_Pim_TorqueCmdSF_Uls_f32()

## Local Functions/Macros Used by this MDD only

(Note if they are defined in another source file, then reference the appropriate header file)

## The local functions/macros in this module are identified below,

## Software Module Implementation

## Periodic Functions

Per: TrqCmdScl_Per1

## Design Rationale

## Program Flow Start

Rte_Call_TrqCmdScl_Per1_CP0_CheckpointReached()

## Store Module Inputs to Local copies

MRFMtrTrqCmd_MtrNm_T_f32 = Rte_IRead_TrqCmdScl_Per1_MRFMtrTrqCmd_MtrNm_f32()

TorqueCmdSF_Uls_T_f32 = *Rte_Pim_TorqueCmdSF_Uls_f32()

## Apply Torque Command Scaling

EMBED Visio.Drawing.11

## Store Local copy of outputs into Module Outputs

Rte_IWrite_TrqCmdScl_Per1_MRFMtrTrqCmdScl_MtrNm_f32(MRFMtrTrqCmdScl_MtrNm_T_f32)

## Program Flow End

Rte_Call_TrqCmdScl_Per1_CP1_CheckpointReached()

## Flow End

Scomm: TrqCmdScl_SCom_Get

## Design Rationale

## Program Flow Start

## Store Module Inputs to Local copies

## Get Torque Command Scaling

EMBED Visio.Drawing.11

## Store Local copy of outputs into Module Outputs

## Program Flow End

Scomm: TrqCmdScl_SCom_Set

## Design Rationale

## Program Flow Start

## Store Module Inputs to Local copies

## Set Torque Command Scaling

EMBED Visio.Drawing.11

## Store Local copy of outputs into Module Outputs

## Program Flow End

## Local Function/Macro Definitions

If these are numerous and defined in a separate source file then reference the source file only.

## Function

## Function Name

UTP Tol.

## Arguments Passed

## Return Value

## Execution Requirements

## Execution Sequence of the Module

TrqCmdScl_Per1 must be executed in the forward path before quadrant detection, the voltage command numerator, phase advance, voltage command denominator, and Modulation Index.

## Execution Rates for sub-modules called by the Scheduler

## This table serves as reference for the Scheduler design

## Function Name

## Calling Frequency

## System State(s)

TrqCmdScl_Per1

## Execution Requirements for Serial Communication Functions

## Function Name

## Sub-Module called by (Serial Comm Function Name)

TrqCmdScl_Scom_Get()

TrqCmdScl_Scom_Set()

## Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in this module.

## Name of Sub Module

## Software Segment

TrqCmdScl_Per1

## Local Functions

This table identifies the software segments for local functions identified in this module.

## Name of Sub Module

## Software Segment

## Known Issues / Limitations With Design

## Revision Control Log

Item #

Rev #

## Change Description

## Author Initials

## Document creation and initial release for the component

29NOV11

## Corrections to assign EOL scaling factor to temporary variable

## Added checkpoints and memmap software segment is updated for static variables

26Sep12

## Selva

## Heading and format corrected

21Nov12

## Selva

## SOFTWARE MODULE DESIGN SPECIFICATION

Title:

## Hand Wheel Torque

Gen II+ EPS

Revision:

Product:

Rev. Date:

2620-SepNov-2012

Group:

Originator:

## Selva Sengottaiyan

Page:

## NUMPAGES

## Delphi

## CONFIDENTIAL

S/W module design template, Rev 2.2b

ytzx-

gdmo#

~z~s~^C~5

gdmo#

ufZfZfZSu

gdI+X

gd7"~

xrxgxrx

gdmo#

IDATx^

hb)4n

43KI~

;Wnl+

SL#}uJ!

oFc)4U;/

4tFCE!

@h*`a

!`G@y

3lj#Q

NOoGAsz{p

t\B`7

H\w,[s

is)+zm

}^l.w

V~ZA`

+YA`*

{$N:E51D$]sz

ytzx-

9svw2d

## Root Entry

## Data

## WordDocument

## ObjectPool

_1384061874

## EPRINT

## CompObj

## Microsoft Visio Drawing

Visio 11.0 Shapes

Visio.Drawing.11

## Vishal Kema

EMF+0@

eCs=bA

eCr=bA

eCq=bA

eCr=bA

eCq=bA

)Cq=bA

Cl=bA

EMF+*@

Cq=bA

## ARIAL

## Start

## Arial

## Start

EMF++@

EMF+*@

#*C6@

## MRFMtrTrqCmdScl

EMF++@

#*C6@

EMF++@

#*C6@

## MtrNm

EMF++@

#*C6@

EMF++@

#*C6@

EMF++@

#*C6@

EMF++@

#*C6@

EMF++@

#*C6@

EMF++@

#*C6@

EMF++@

#*C6@

## MRFMtrTrqCmd

=>0J#@

## MRFMtrTrqCmd

EMF++@

#*C6@

EMF++@

#*C6@

## MtrNm

=>P1K@

## MtrNm

EMF++@

#*C6@

EMF++@

#*C6@

EMF++@

#*C6@

EMF++@

#*C6@

EMF++@

#*C6@

EMF++@

#*C6@

=> "q@

EMF++@

#*C6@

## TorqueCmdSF

EMF++@

#*C6@

EMF++@

#*C6@

EMF++@

#*C6@

EMF++@

#*C6@

EMF++@

#*C6@

EMF++@

#*C6@

EMF++@

#*C6@

EMF++@

EMF+*@

## TorqueCmdSF

EMF++@

## Limit

EMF++@

## TorqueCmdSF

]>p\(@

]>P=2@

## TorqueCmdSF

EMF++@

## MinTrqCmdScl

EMF++@

## MaxTrqCmdScl

>Py&@

## MaxTrqCmdScl

EMF++@

EMF+*@

#lC6@

"b>@|

EMF++@

EMF+*@

## ARIAL

## MRFMtrTrqCmd

## Arial

## MRFMtrTrqCmd

EMF++@

## MtrNm

EMF++@

is float

EMF++@

## MRFMtrTrqCmdScl

EMF++@

## MtrNm

EMF++@

is float

EMF++@

## TorqueCmdSF

EMF++@

is float

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

"usV"i2*b

i!]#S-S

$g0",

g th

["`?C

pyri

])} 2

0P06} uM<0c:0o

s40IfB231r60o1aB0

0 :8s

2Ueb0e:0v

## PobmH

31sB0

m d. l

a& i" ,

l w" hR r

"f rB a

s "i|*b. U!

$]gz",

g on

yA wi

02g26

MM0cA oO0o

2{1r~0

i|0nY0

0dY0p0

@33\F\F

ioa8e

!k+H9

&PVPV

0p04"

7bBct

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

%"si"iO*b

uP'"|!p#f-S

$gM",

g on

## Copy

U0|06p0Mh0cf0

s`0fn2_1r

1an0i`0n

0U f8s

Tm!#

5N|24

oFoFP

|oW*R

`4A-#H5#

g th

Vis_

SFB.

Tm!#

r, gT

(: )k 2

M, ca oN. o

fi"Z!r]

!ai i[ n8

"e. ea v

Xm74G

"oEbc

ZW4IA

h}r&lf(@=q

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

C:\P

m Fi

/-/?/Q/

?C=88

8sU+A

ICl@nhPe

@tl@r

Re_"T

*x@TrRq

uTlP"

## ZGhMa

o0oBo

Uf?x?

8Ey@d$

@cJq@gG@oK@M

CE@=lEB

/"/u'

RW@M";@r

L&O8OJGT

eeFF}@U

o@s}O

## Daose

c}bll

-_?_Q_c_u_

_S Hl

o*iHl

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

nami

xtPo

rmin

{H%a/.

## Vishal Kema

## Microsoft Visio

## Nexteer

Page-1

## Terminator

## Decision

Predefined process.3

## Predefined process

Terminator.5

## DocumentSummaryInformation

_1384062686

## EPRINT

ess.6

## Dynamic connector

## Pages

## Masters

_PID_LINKBASE

_VPID_ALTERNATENAMES

## Microsoft Visio Drawing

Visio 11.0 Shapes

Visio.Drawing.11

EMF+0@

AK#vC

@N#vC

EMF+*@

## ARIAL

## TrqCmdScl

## Arial

## TrqCmdScl

EMF++@

## SCom

'>@-O?

## SCom

EMF++@

)C_sEB

5_BR8&CJ

C{TEC

B}TEC)

B|TEC)

B{TEC)

EMF+*@

EMF++@

EMF+*@

5_B6@

EMF++@

5_B6@

EMF++@

5_B6@

EMF++@

5_B6@

EMF++@

5_B6@

EMF++@

5_B6@

EMF++@

5_B6@

EMF++@

5_B6@

EMF++@

5_B6@

EMF++@

5_B6@

EMF++@

5_B6@

EMF++@

5_B6@

## TorqueCmdSF

EMF++@

5_B6@

EMF++@

5_B6@

EMF++@

5_B6@

EMF++@

5_B6@

EMF++@

5_B6@

EMF++@

5_B6@

EMF++@

BR8&C

## CompObj
