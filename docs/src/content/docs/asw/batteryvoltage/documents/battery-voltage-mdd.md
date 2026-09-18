---
title: "Battery Voltage Module Design Document"
description: "Converted from Battery_Voltage_MDD.doc"
---

> **Source document:** `BatteryVoltage/doc/Battery_Voltage_MDD.doc`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: legacy Word document (`.doc`).

> **Note:** the original file is a legacy binary Word document (`.doc`) which cannot be converted with full fidelity in this environment. The text below was recovered automatically and may be out of order in places; tables and figures are not preserved. See the original file for the authoritative content.

## Module -- Battery Voltage

## High-Level Description

This module is responsible for applying voltage and time based hysteresis to the battery voltage to determine over voltage and low voltage faults.

## Figures

## Diagram

## Function Data Sharing

This diagram shows all data that is shared between functions within the module.

## Variable Data Dictionary

For details on module input / output variable, refer to the Data Dictionary for the application. Input / output variable names are listed here for reference.

(Note: Full variable names required in table.)

(Note: All global variables including End Of Line data used should be shown here)

## Module Inputs (Global Variable Name)

## Module Outputs (Global Variable Name)

Batt_Volt_f32

VswitchClosed_Cnt_lgc

BattSwitched_Volt_f32

Vecu_Volts_f32

SysCVSwitch_Volt_f32

SysC_Vecu_Volt_f32

## Module Internal Variables

This section identifies the name, range and resolutions for module specific data created by this module. If there are no range restrictions on the variable, the term

is placed into the table for legal range.

## Variable Name

## User Defined Type

## Resolution

## Legal Range

(min)

## Legal Range

(max)

## Software Segment

Vecu_Volts_M_f32

## Volts

BATTERYVOLTAGE_START_SEC_VAR_CLEARED_32

VswitchClosed_Cnt_M_lgc

## FALSE

BATTERYVOLTAGE_START_SEC_VAR_CLEARED_BOOLEAN

VswitchCorrLimDiff_Volts_D_f32

## Volts

BATTERYVOLTAGE_START_SEC_VAR_CLEARED_32

VecuVbatCorrLimDiff_Volts_D_f32

## Volts

BATTERYVOLTAGE_START_SEC_VAR_CLEARED_32

VswitchCorrErrAcc_Cnt_M_u16

BATTERYVOLTAGE_START_SEC_VAR_CLEARED_16

VecuVbatCorrErrAcc_Cnt_M_u16

BATTERYVOLTAGE_START_SEC_VAR_CLEARED_16

Vbatt_Volts_M_f32

## Volts

BATTERYVOLTAGE_START_SEC_VAR_CLEARED_32

OvervoltageFaultSet_Cnt_M_lgc

boolean

## FALSE

BATTERYVOLTAGE_START_SEC_VAR_CLEARED_BOOLEAN

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

k_MaxSwitchedVolt_Volts_f32

k_MaxBattVoltDiff_Volts_f32

k_VswitchCorrLim_Cnt_Str

k_VecuCorrLim_Cnt_Str

k_VecuVbatCorrLim_Volts_f32

k_VswitchCorrLim_Volts_f32

## Program(fixed) Constants

## Embedded Constants

All embedded constants whose values are provided in Eng units will be evaluated to the equivalent counts by using the FPM_InitFixedPoint_m() macro within the #define statement.

## Local

## Constant Name

## Resolution

## Value

D_VSWITCHEDTHRESH_ULS_F32

## Single precision floating point

D_VECUMAX_VOLTS_F32

## Single precision floating point

## Global

This section lists the global constants used by the module. For details on global constants, refer to the Data Dictionary for the application.

## Constant Name

D_VECUMIN_VOLTS_F32

BC_BATTERYVOLTAGE_FAULTINJECTIONPOINT

FLTINJ_VECU_BATTERYVOLTAGE

## Module specific Lookup Tables Constants

(This is for lookup tables (arrays) with fixed values, same name as other tables)

## Constant Name

## Resolution

## Value

## Software Segment

## Functions/Macros used by the Sub-Modules

## Library Functions / Macros

The library functions / Macros that are called by the various sub modules are identified below,

FPM_FloatToFixed_m()

## Data Hiding Functions

## The data hiding functions / macros used in this module are identified below,

Rte_Call_NxtrDiagMgr_SetNTCStatus()

Rte_Call_Batt_Batt_V_f32()

Rte_Call_BattSwitched_BattSwitched_V_f32

Rte_Call_SysC_Vswitch_BattSwitched_V_f32

Rte_Call_BatteryVoltage_Per1_CP0_CheckpointReached

Rte_Call_BatteryVoltage_Per1_CP1_CheckpointReached

Rte_Call_BatteryVoltage_Per2_CP0_CheckpointReached

Rte_Call_BatteryVoltage_Per2_CP1_CheckpointReached

Rte_Pim_OvervoltageData()

Rte_Call_OvervoltageData_SetRamBlockStatus()

## Local Functions/Macros Used by this MDD only

(Note if they are defined in another source file, then reference the appropriate header file)

## The local functions/macros in this module are identified below,

## Software Module Implementation

## Initialization Functions

Module state variables are initialized to 0 at start-up by RAM init.

Init: BatteryVoltage_Init1

## Design Rationale

## Program Flow Start

## Store Module Inputs to Local copies

EMBED Visio.Drawing.11

## Store Local copy of outputs into Module Outputs

## Program Flow End

## Periodic Functions

Per: BatteryVoltage_Per1

## Design Rationale

See FDD 08B.

## Program Flow Start

Rte_Call_BatteryVoltage_Per1_CP0_CheckpointReached()

## Store Module Inputs to Local copies

Vbatt_Volts_T_f32 = Rte_IRead_BatteryVoltage_Per2_Batt_Volt_f32()

Vswitched_Volts_T_f32 = Rte_IRead_BatteryVoltage_Per1_BattSwitched_Volt_f32()

## Perform Over and Low Voltage Diagnostics

EMBED Visio.Drawing.11

## Store Local copy of outputs into Module Outputs

Vecu_Volts_M_f32 = Vecu_Volts_T_f32

Vbatt_Volts_M_f32 = Vbatt_Volts_T_f32

Rte_IWrite_BatteryVoltage_Per1_ VswitchClosed _Cnt_lgc(VswitchClosed_Cnt_T_lgc)

Rte_IWrite_BatteryVoltage_Per1_ Vecu _Volts_f32(Vecu_Volts_T_f32)

Rte_IWrite_BatteryVoltage_Per1_SysC_Vecu_Volt_f32(Vecu_Volts_M_f32)

## Program Flow End

Rte_Call_BatteryVoltage_Per1_CP1_CheckpointReached()

Per: BatteryVoltage_Per2

## Design Rationale

None.

## Program Flow Start

Rte_Call_BatteryVoltage_Per2_CP0_CheckpointReached()

## Store Module Inputs to Local copies

VecuVbatCorrLimDiff_Volts_T_f32 =0

NTCSysFailCtrlV_T_lgc = FALSE

Vswitched_Volts_T_f32 = Rte_IRead_BatteryVoltage_Per2_BattSwitched_Volt_f32()

SysCVswitch_Volts_T_f32 = Rte_IRead_BatteryVoltage_Per2_SysCVSwitch_Volt_f32()

## VSwitch and Vecu cross correlation diagnostics

EMBED Visio.Drawing.11

## Store Local copy of outputs into Module Outputs

VswitchCorrLimDiff_Volts_D_f32 = VswitchCorrLimDiff_Volts_T_f32

VecuVbatCorrLimDiff_Volts_D_f32 = VecuVbatCorrLimDiff_Volts_T_f32

## Program Flow End

Rte_Call_BatteryVoltage_Per2_CP1_CheckpointReached()

## Fault Recovery Functions

## Shutdown Functions

## Interrupt Functions

NoneIsr: Isr_OvervoltThresh

## Design Rationale

## Description

EMBED Visio.Drawing.11

## Serial Communication Functions

SCom: BatteryVoltage_SCom_ClearTransOvData

## Function Name

BatteryVoltage_SCom_ClearTransOvData

UTP Tol.

## Arguments Passed

## Return Value

## Design Rationale

## Program Flow Start

## Store Module Inputs to Local Copies

## Clear Transient Overvoltage Data Service

EMBED Visio.Drawing.11

## Store Local Copy of outputs into Module Outputs

## Program Flow End

BatteryVoltage_SCom_ReadTransOvData

## Function Name

BatteryVoltage_SCom_ReadTransOvData

UTP Tol.

## Arguments Passed

*OvervoltageCounter_Cnt_u16

Uint16

*MaxBattVoltage_Volts_f32

Float32

## Return Value

## Design Rationale

## Program Flow Start

## Store Module Inputs to Local Copies

## Read Transient Overvoltage Data Service

EMBED Visio.Drawing.11

## Store Local Copy of outputs into Module Outputs

## Program Flow End

## Local Function/Macro Definitions

If these are numerous and defined in a separate source file then reference the source file only.

## Execution Requirements

## Execution Sequence of the Module

(Describe in words relevant details about the execution sequence of the different sub modules.)

## Execution Rates for sub-modules called by the Scheduler

## This table serves as reference for the Scheduler design

## Function Name

## Task List

## Calling Frequency

## System State(s) in which the function is called

BatteryVoltage_Init1

## On Init

## WARM INIT

BatteryVoltage_Per1

BatteryVoltage_Per2

## OPERATE

Isr_OvervoltThresh

## On Event

## Execution Requirements for Serial Communication Functions

## Function Name

## Sub-Module called by (Serial Comm Function Name)

BatteryVoltage_SCom_ClearTransOvData

EPS_DiagSrvc

BatteryVoltage_SCom_ReadTransOvData

EPS_DiagSrvc

## Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in this module.

## Name of Sub Module

## Software Segment

BatteryVoltage_Init1

RTE_AP_BATTERYVOLTAGE_APPL_CODE

BatteryVoltage_Per1()

RTE_AP_BATTERYVOLTAGE_APPL_CODE

BatteryVoltage_Per2()

RTE_AP_BATTERYVOLTAGE_APPL_CODE

BatteryVoltage_SCom_ClearTransOvData()

RTE_AP_BATTERYVOLTAGE_APPL_CODE

BatteryVoltage_SCom_ReadTransOvData()

RTE_AP_BATTERYVOLTAGE_APPL_CODE

Isr_OvervoltThresh

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

Initial AutoSAR release.

07-Feb-11

Updated to meet FDD 08B rev 02 Ecu Voltage

28-Mar-11

Updated to meet FDD 08B rev 02 Ecu Voltage

30-Mar-11

## Corrected execution states for periodic

07-Apr-11

## Updated NTC

s to global constants

02-Dec-11

## Updated NTC

s global constants names per latest NTC definitions

11-Jan-12

Updated as per FDD Ver 004

17-Oct-12

changed from client server port type to Sender/Receiver port

29 -Oct-12

## MDD updates for UTP catchups

30-Jan-13

## Checked in the right version of the MDD into synergy

28-Mar-13

Updated to FDD Ver 005

16-APR-13

## Jared

Updated to FDD Ver 006 and anomaly 5138 correction

26-Jun-13

Added missing ISR function for overvoltage diagnostic (A5789)

3-Jan-14

## Jared

Add BATTERYVOLTAGE_REPORTERRORSTATUS for program specific integration.

8-Jan-14

## SOFTWARE MODULE DESIGN SPECIFICATION

Title:

## Battery Voltage

Gen II+ EPS

Revision:

Product:

Rev. Date:

83-Jan-1426-Jun-13

Group:

Originator:

## Jared Julien

Page:

## NUMPAGES

## Nexteer CONFIDENTIAL

S/W module design template, Rev 3.0a

sgsgsgs

uiuiu

thYhJh

&ytNB

rngncn\XnQMQ

gdA8=

gd!/!

gdA8=

gd!/!

jLB\V

n_S@_S@.

od_oX

IDATx^

y2-*S2}

WL~c)|

.5avn

,Ki4z

## TnVpR

Lfo!S

Slf6(Dt

'7Yl6X

&ytNB

## Root Entry

## Data

## WordDocument

## ObjectPool

_1450258673

## EPRINT

## CompObj

## Microsoft Visio Drawing

Visio 11.0 Shapes

Visio.Drawing.11

kzshz2

EMF+0@

lCY2jBKz

CY2jB$

C]2jB

bCV2jB+

lCY2jB

EMF+*@

## ARIAL

## Start

## Arial

tpOPu

## Start

EMF++@

EMF+*@

EMF++@

EMF+*@

## OvervoltageFaultSet

>@B\?

>@)d?

## OvervoltageFaultSet

EMF++@

## FALSE

EMF++@

EMF+*@

EMF++@

## Call

"r>@T

## Call

EMF++@

## NxtrDiagMgr

"r>@&v?

## NxtrDiagMgr

EMF++@

## SetNTCStatus

"r>@x

"r> a

## SetNTCStatus

EMF++@

## BattTransOverVolt

"r>@S1@

"r>pA7@

"r>0;9@

"r>@sX@

## BattTransOverVolt

EMF++@

"r> 3}@

EMF++@

## STATUS

"r>P;

"r>Pg

## STATUS

EMF++@

## PASSED

"r>@o

"r>p-

## PASSED

EMF++@

CY2jBq=

EMF+*@

C"C6@

EMF++@

EMF+*@

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

Uhk rQ ,+"f

r[ aQ"o- t',4%

)S+ x

g on

XY.c

@2`?C

@MV@cr0oNX@o

BeX@er0v

5.3>4

(M!M!

LV@n@

@{@~2

p/E/E

@zAFR

@{@SR

`+ A+

A{@4QVE

O^@UK

v1bX"A

D).^@

7T%2H

=!a/s-*

~ynqf

\Pro

## File

?'?9?K?]?o?

O#O5OGOYOkO}O

_#_5_G_

Y_k_}_

o1oCoUogo yo

??}4xw

A.!$!

"/4,q

F4zo_5

UV\aBM

AB6e~

aj0T\OnO

rv!e3

QXA$\1

`uX `

qpmCi

X [@z

Y%FEi/{ 1

I ]4_0

s<V;RV

V/)'n/

@?R?d?v?

Af!%O

Cjo|o

Ea?3e

U@(!h

/!/3/E.

8?J=%

&dCOIAYHN

_oqon

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

nami

xtPo

rmin

tiSc

bpro

## Owner
