---
title: "PICurrentContrl"
description: "Converted from PICurrentContrl.doc"
---

> **Source document:** `MtrCtrl_CM/doc/PICurrentContrl.doc`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: legacy Word document (`.doc`).

> **Note:** the original file is a legacy binary Word document (`.doc`) which cannot be converted with full fidelity in this environment. The text below was recovered automatically and may be out of order in places; tables and figures are not preserved. See the original file for the authoritative content.

## Module -- PICurrCntrl

## High-Level Description

Non-AUTOSAR PI driver required to perform EPS motor control PWM profiles.

## Figures

## Diagram

## Function Data Sharing

This diagram shows all data that is shared between functions within the module.

## Module Inputs and Outputs

For details on module input / output variable, refer to the Data Dictionary for the application. Input / output variable names are listed here for reference.

(Note: Full variable names required in table.)

(Note: All global variables including End Of Line data used should be shown here)

## Module Inputs (Global Variable Name)

## Module Outputs (Global Variable Name)

MtrCurrQax_Amp_f32

EstKe_VpRadpS_f32

MtrCurrDax_Amp_f32

MtrCurrQaxFinalRef_Amp_f32

MtrCurrQaxRef_Amp_f32

MtrDaxVoltage_Volt_f32

MtrCurrDaxRef_Amp_f32

MtrQaxVoltage_Volt_f32

PIDaxIntegralGain_Uls_f32

ModIdx_Uls_u16p16

PIDaxPropotionalGain_Uls_f32

PhaseAdvanceFinal_Rev_u0p16

PIQaxIntegralGain_Uls_f32

CommOffset_Cnt_u16

PIQaxPropotionalGain_Uls_f32

MtrVolt_Volt_f32

ElecPosDelayComp_Rad_f32

MtrCurrDaxIntg_Volt_f32

MtrVoltDaxFF_Volt_f32

MtrCurrQaxIntg_Volt_f32

MtrVoltQaxFF_Volt_f32

DervLambdaAlphaDiag_Volt_T_f32MtrVoltFinalVChk_Volt__f32

Vecu_Volt_f32

DervLambdaBetaDiag_Volt_T_f32MtrVoltInt_Volt__f32

ModIdxSrlComSvcDft_Cnt_lgc

SlowDataAccessBufIndex_Cnt_M_u16

SysState_Cnt_Enum

MtrCurrOffComOffset_Cnt_u16

MtrCurrQaxRpl_Amp_M_f32

MtrCurrQaxCog_Amp_M_f32

MRFMtrVel_MtrRadpS_f32

MtrVoltDaxInt_Volt_f32

MtrVoltQaxInt_Volt_f32

MtrVolt_Volt_f32

MtrVoltDaxFF_Volt_f32

MtrVoltQaxFF_Volt_f32

MtrCurrQaxRpl_Amp_f32

FastDataAccessBufIndex_Cnt_M_u16

EstKe_VpRadpS_f32

CorrMtrPosElec_Rev_f32

EstR_Ohm_f32

## Module Internal Variables

This section identifies the name, range and resolutions for module specific data created by this module. If there are no range restrictions on the variable, the term

is placed into the table for legal range.

(Note: If no module specific variables are used by the design, place the text

in the first Variable Name cell in the table)

## Variable Name

## Resolution

## Legal Range

(min)

## Legal Range

(max)

## Software Segment

MtrCurrQaxPrevIntg_Volt_M_f32

single precision float

PICURRCNTRL_START_SEC_VAR_CLEARED_32

MtrCurrDaxPrevIntg_Volt_M_f32

single precision float

PICURRCNTRL_START_SEC_VAR_CLEARED_32

MtrVoltQaxPrevFinalLimit_Volt_M_f32

single precision float

PICURRCNTRL_START_SEC_VAR_CLEARED_32

MtrVoltPrevDaxFinal_Volt_M_f32

single precision float

PICURRCNTRL_START_SEC_VAR_CLEARED_32

MtrCurrQaxError_Amp_D_f32

single precision float

PICURRCNTRL_START_SEC_VAR_CLEARED_32

MtrCurrDaxError_Amp_D_f32

single precision float

PICURRCNTRL_START_SEC_VAR_CLEARED_32

MtrVoltQaxFinal_Volt_D_f32

single precision float

PICURRCNTRL_START_SEC_VAR_CLEARED_32

MtrVoltQaxFinalLimit_Volt_D_f32

single precision float

PICURRCNTRL_START_SEC_VAR_CLEARED_32

MtrVoltDaxFinal_Volt_D_f32

single precision float

PICURRCNTRL_START_SEC_VAR_CLEARED_32

MtrVoltQaxProp_Volt_D_f32

single precision float

PICURRCNTRL_START_SEC_VAR_CLEARED_32

MtrVoltDaxProp_Volt_D_f32

single precision float

PICURRCNTRL_START_SEC_VAR_CLEARED_32

MtrVoltQaxInt_Volt_D_f32

single precision float

PICURRCNTRL_START_SEC_VAR_CLEARED_32

MtrVoltDaxInt_Volt_D_f32

single precision float

PICURRCNTRL_START_SEC_VAR_CLEARED_32

PICurrCntrl_MtrCurrQax_Amp_D_f32

single precision float

PICURRCNTRL_START_SEC_VAR_CLEARED_32

PICurrCntrl_MtrCurrDax_Amp_D_f32

single precision float

PICURRCNTRL_START_SEC_VAR_CLEARED_32

MtrVoltDax_Volt_M_f32[2]

single precision float

## See data Dictionary

PICURRCNTRL_START_SEC_VAR_CLEARED_32

MtrVoltQax_Volt_M_f32[2]

single precision float

## See data Dictionary

PICURRCNTRL_START_SEC_VAR_CLEARED_32

MtrCurrQaxFinalRef_Amp_M_f32[2]

single precision float

## See data Dictionary

PICURRCNTRL_START_SEC_VAR_CLEARED_32

PICurrCntrl_DervLambdaQax_Volt_D_f32

single precision float

## See data Dictionary

PICURRCNTRL_START_SEC_VAR_CLEARED_32

PICurrCntrl_DervLambdaDax_Volt_D_f32

single precision float

## See data Dictionary

PICURRCNTRL_START_SEC_VAR_CLEARED_32

## User defined typedef definition/declaration

This section documents any user types uniquely used for the module.

## Variable Name

## Typedef Name

## Storage Type

## Safety Critical Classification

## Constant Data Dictionary

## Calibration Constants

This section lists the calibrations used by the module. For details on calibration constants, refer to the Data Dictionary for the application.

(Note: If no calibrations are used by the design, place the text

in the first location in the table)

## Constant Name

k_PiSamplingTs_Sec_f32

t_CommOffsetTblX_Uls_u3p13[2]

t_CommOffsetTblY_Cnt_u16[2]

k_NoofPoles_Uls_f32

## Program(fixed) Constants

## Embedded Constants

All embedded constants whose values are provided in Eng units will be evaluated to the equivalent counts by using the FPM_InitFixedPoint_m() macro within the #define statement.

## Local

## Constant Name

## Resolution

## Units

## Value

D_SCALERADTOCNTS_ULS_F32

## Single Precision Float

## Unitless

10430.3783505F

D_REVWITHROUND_ULS_F32

## Single Precision Float

## Unitless

65536.5F

D_ROUND_ULS_F32

## Single Precision Float

## Unitless

D_DEG2RAD_ULS_F32

## Single Precision Float

## Unitless

0.0174532925199F

D_GAIN_ULS_F32

## Single Precision Float

## Unitless

D_VECUMAX_VOLTS_F32

## Single Precision Float

## Volts

D_SQRT3OVR2_ULS_F32

## Single Precision Float

## Unitless

0.866025403784

## Global

This section lists the global constants used by the module. For details on global constants, refer to the Data Dictionary for the application.

## Constant Name

D_ZERO_ULS_F32

D_VECUMIN_VOLTS_F32

## Module specific Lookup Tables Constants

(This is for lookup tables (arrays) with fixed values, same name as other tables)

## Constant Name

## Resolution

## Value

## Software Segment

## Functions/Macros used by the Sub-Modules

## Library Functions / Macros

The library functions / Macros that are called by the various sub modules are identified below,

IntplVarXY_u16_u16Xu16Y_Cnt_m()

FPM_FloatToFixed_m

Sign_f32_m

## Sqrtf

## Data Hiding Functions

## The data hiding functions / macros used in this module are identified below,

Rte_ModeType_StaMd_Mode

MtrCntrl_Read_MtrCurrQax_Amp_f32

MtrCntrl_Read_MtrCurrDax_Amp_f32

MtrCntrl_Read_Vecu_Volt_f32

MtrCntrl_Read_ModIdxSrlComSvcDft_Cnt_lgc

MtrCntrl_Read_SysState_Cnt_Enum

MtrCntrl_Read_MtrCurrOffComOffset_Cnt_u16

MtrCntrl_Read_MtrElecPol_Cnt_s8

MtrCntrl_Read_MtrPosElec_Rev_u0p16

MtrCntrl_Write_MtrCurrQaxFinalRef_Amp_f32

MtrCntrl_Write_MtrDaxVoltage_Volt_f32

MtrCntrl_Write_MtrQaxVoltage_Volt_f32

MtrCntrl_Write_ModIdx_Uls_u16p16

MtrCntrl_Write_PhaseAdvanceFinal_Rev_u0p16

MtrCntrl_Write_CommOffset_Cnt_u16

## Local Functions/Macros Used by this MDD only

Header file: Ap_MtrCntrl_Cfg.h

## Software Module Implementation

## Initialization Functions

None.

## Periodic Functions

Per: PICurrCntrl_Per1

## Design Rationale

This function is responsible for calculating the amount of current to be supplied to the motor. To control the PWM profiles generated for the motor. FastDataAccessBufIndex allows the buffer synchronization between data calculated on slower periodic loop time(2 milli seconds) and are read by faster periodic run time (ie 0.125ms)

## Store Module Inputs to Local copies

MtrCntrl_Read_MtrCurrQax_Amp_f32(&MtrCurrQax_Amp_T_f32);

MtrCntrl_Read_MtrCurrDax_Amp_f32(&MtrCurrDax_Amp_T_f32);

MtrCntrl_Read_Vecu_Volt_f32(&Vecu_Volt_T_f32);

MtrCntrl_Read_ModIdxSrlComSvcDft_Cnt_lgc(&ModIdxSrlComSvcDft_Cnt_T_lgc);

MtrCntrl_Read_SysState_Cnt_Enum(&SysState_Cnt_T_Enum);

FwdDataAcessBuffer_Cnt_T_u16= (ActWriteAccBufIndex_Cnt_T_u16)

MtrCurrQaxRef_Amp_T_f32=MtrCurrQaxRef_Amp_M_f32[FwdDataAcessBuffer_Cnt_T_u16];

MtrCurrDaxRef_Amp_T_f32=MtrCurrDaxRef_Amp_M_f32[FwdDataAcessBuffer_Cnt_T_u16];

PIDaxIntegralGain_Uls_T_f32=MtrDaxIntegralGain_Uls_M_f32[FwdDataAcessBuffer_Cnt_T_u16];

PIDaxPropotionalGain_Uls_T_f32=MtrDaxPropotionalGain_Uls_M_f32[FwdDataAcessBuffer_Cnt_T_u16]

PIQaxIntegralGain_Uls_T_f32=MtrQaxIntegralGain_Uls_M_f32[FwdDataAcessBuffer_Cnt_T_u16];

PIQaxPropotionalGain_Uls_T_f32=MtrQaxPropotionalGain_Uls_M_f32[FwdDataAcessBuffer_Cnt_T_u16]

ElecPosDelayComp_Rad_T_f32=MtrPosComputationDelay_Rad_M_f32[FwdDataAcessBuffer_Cnt_T_u16]

MtrVoltDaxFF_Volt_T_f32=MtrVoltDaxFF_Volt_M_f32[FwdDataAcessBuffer_Cnt_T_u16]MtrVoltQaxFF_Volt_T_f32=MtrVoltQaxFF_Volt_M_f32[FwdDataAcessBuffer_Cnt_T_u16];

Vecu_Volt_T_f32 = Limit_m(Vecu_Volt_T_f32, D_VECUMIN_VOLTS_F32, D_VECUMAX_VOLTS_F32)

## Program Flow Start

EMBED Visio.Drawing.11

## Store Local copy of outputs into Module Outputs

MtrCntrl_Write_MtrCurrQaxFinalRef_Amp_f32(MtrCurrQaxFinalRef_Amp_T_f32)

MtrCntrl_Write_MtrDaxVoltage_Volt_f32(MtrDaxVoltage_Volt_T_f32)

MtrCntrl_Write_MtrQaxVoltage_Volt_f32(MtrQaxVoltage_Volt_T_f32)

MtrCntrl_Write_ModIdx_Uls_u16p16(FPM_FloatToFixed_m(ModIdx_Uls_T_u16p16))

MtrCntrl_Write_PhaseAdvanceFinal_Rev_u0p16(PhaseAdvanceFinal_Rev_T_u0p16)

MtrCntrl_Write_CommOffset_Cnt_u16(CommOffset_Cnt_T_u16)

MtrCntrl_Write_MtrVolt_Volt_f32(MtrVoltCmdFinal_Volt_T_f32)

MtrCntrl_Write_MtrCurrDaxIntg_Volt_f32(MtrCurrDaxIntg_Volt_T_f32)

MtrCntrl_Write_MtrCurrQaxIntg_Volt_f32(MtrCurrQaxIntg_Volt_T_f32)

MtrCurrQaxFinalRef_Amp_M_f32[SlowDataAccessBufIndex_Cnt_M_u16]= MtrCurrQaxFinalRef_Amp_T_f32;

MtrVoltDax_Volt_M_f32[SlowDataAccessBufIndex_Cnt_M_u16] = MtrDaxVoltage_Volt_T_f32;

MtrVoltQax_Volt_M_f32[SlowDataAccessBufIndex_Cnt_M_u16] = MtrQaxVoltage_Volt_T_f32

## Program Flow End

## Periodic Functions

Per: PICurrCntrl_Per2

## Design Rationale

This function is responsible for calculating the amount of current to be supplied to the motor. To control the PWM profiles generated for the motor.

SlowDataAccessBufIndex allows the buffer synchronization between data calculated on faster periodic loop time(125 micro seconds) and are read by slower periodic run time (ie 2ms)

## Store Module Inputs to Local copies

ReadBuffer_Cnt_T_u16 = SlowDataAccessBufIndex_Cnt_M_u16

WriteBuffer_Cnt_T_u16 = (ReadBuffer_Cnt_T_u16 & 1U) ^ 1U

SlowDataAccessBufIndex_Cnt_M_u16 = WriteBuffer_Cnt_T_u16

EstKe_VpRadpS_T_f32= Rte_IRead_PICurrCntrl_Per2_EstKe_VpRadpS_f32();

EstR_Ohm_T_f32 = Rte_IRead_PICurrCntrl_Per2_EstR_Ohm_f32();

MRFMtrVel_MtrRadpS_T_f32 = Rte_IRead_PICurrCntrl_Per2_MRFMtrVel_MtrRadpS_f32();

CorrMtrPosElec_Rev_T_f32 = Rte_IRead_PICurrCntrl_Per2_CorrMtrPosElec_Rev_f32();

MtrCurrDaxRef_Amp_T_f32 = Rte_IRead_PICurrCntrl_Per2_MtrCurrDaxRef_Amp_f32();

MtrVoltDax_Volt_T_f32 = MtrVoltDax_Volt_M_f32[ReadBuffer_Cnt_T_u16];

MtrVoltQax_Volt_T_f32 = MtrVoltQax_Volt_M_f32[ReadBuffer_Cnt_T_u16];

MtrCurrQaxFinalRef_Amp_T_f32 = MtrCurrQaxFinalRef_Amp_M_f32[ReadBuffer_Cnt_T_u16];EstLq_Henry_T_f32= Rte_IRead_PICurrCntrl_Per2_EstLq_Henry_f32()

EstR_Ohm_T_f32 = Rte_Iread_PICurrCntrl_Per2_EstR_Ohm_f32()

MRFMtrVel_MtrRadpS_T_f32 = Rte_Iread_PICurrCntrl_Per2_MRFMtrVel_MtrRadpS_f32()

MtrVoltDaxInt_Volt_T_f32 = MtrCurrDaxIntg_Volt_M_f32[ReadBuffer_Cnt_T_u16]

MtrVoltQaxInt_Volt_T_f32 = MtrCurrQaxIntg_Volt_M_f32[ReadBuffer_Cnt_T_u16]

MtrCurrQaxRpl_Amp_T_f32 = MtrCurrQaxRpl_Amp_M_f32[ReadBuffer_Cnt_T_u16]

MtrVolt_Volt_T_f32 = MtrVolt_Volt_M_f32[ReadBuffer_Cnt_T_u16]

MtrVoltQaxFF_Volt_T_f32 = Rte_Iread_PICurrCntrl_Per2_MtrVoltQaxFF_Volt_f32()

MtrVoltDaxFF_Volt_T_f32 = Rte_Iread_PICurrCntrl_Per2_MtrVoltDaxFF_Volt_f32()

## Program Flow Start

Rte_Call_PICurrCntrl_Per2_CP0_CheckpointReached()

## Processing

EMBED Visio.Drawing.11

## Store Local copy of outputs into Module Outputs

Rte_Iwrite_PICurrCntrl_Per2_MtrVoltFinalVChk_Volt_f32(MtrVoltFinalVChk_Volt_T_f32) Rte_Iwrite_PICurrCntrl_Per2_MtrVoltInt_Volt_f32(MtrVoltInt_Volt_T_f32)

Rte_IWrite_PICurrCntrl_Per2_DervLambdaAlphaDiag_Volt_f32(DervLambdaAlphaDiag_Volt_T_f32);

Rte_IWrite_PICurrCntrl_Per2_DervLambdaBetaDiag_Volt_f32(DervLambdaBetaDiag_Volt_T_f32);

## Program Flow End

Rte_Call_PICurrCntrl_Per2_CP1_CheckpointReached()

## Execution Requirements

## Execution Sequence of the Module

## Execution Rates for sub-modules called by the Scheduler

## This table serves as reference for the Scheduler design

## Function Name

## Calling Frequency

## System State(s) in which the function is called

PICurrCntrl_Per1

0.125ms

PICurrCntrl_Per2

## Execution Requirements for Serial Communication Functions

## Function Name

## Sub-Module called by (Serial Comm Function Name)

## Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in this module.

## Name of Sub Module

## Software Segment

PICurrCntrl_Per1

PICurrCntrl_CODE

PICurrCntrl_Per2

RTE_START_SEC_AP_PICURRCNTRL_APPL_CODE

## Local Functions

This table identifies the software segments for local functions identified in this module.

- Denotes functions that are vector call-backs only included to avoid compiler errors.

## Name of Sub Module

## Software Segment

## Known Issues / Limitations With Design

The computation of commoffset and ModIndex service defeat part of FDD15D is implemented in this component inaddition to 99B requirements

The reason for the implementation is to keep the sine voltage driver common across components

## Revision Control Log

Item #

Rev #

## Change Description

## Author Initials

## Initial release with changes for IPM

6/12/2012

## AD/KPIT

## Changes for memap statements added

11/20/2012

## Selva

Updated for SF99B

v8 with only changes needed for voltage command

integrity check for torque reasonableness

02/24/2013

## Selva

34.0,

Updated for SF99B

03/21/2013

## Selva

Corrected for SF99B

04/19/2013

## Selva

Updated for SF99B

21-Oct-13

## Selva

Updated for SF99B

7-Nov-13

## Selva

Updated for V12 of FDD SF99

27-Nov-13

## Selva

## NEXT GENERATION SOFTWARE DESIGN

## MODULE DESIGN SPECIFICATION

Title:

## PICurrCntrl

Gen II Plus - EA3.0

Revision:

Product:

Rev. Date:

27-Nov-13

Group:

Originator:

## Selva Sengottaiyan

Page:

## NUMPAGES

## DELPHI CONFIDENTIAL

S/W module design template, Rev 2.2

gdH's

juju^W

tgZM@M

th\h{XT{

}qjcTMIMjM

|uqm_Xm

gd]/e

}y}qm

gd4!S

gd]/e

k_k_[M

`uQuQu

_WSWSWSWSN

IDATx^

_ 8TT1n

N*4fzO

5E2T7

(1t2G

}UEbe

## WYsIl

eY3[0

]&mQt'

w-O,p

-\#Af

u-O,p

'IDATx^

rgXnw~

fDHpVhi%

,ZC(B

?qYS4

oxw?w

I>Sw_C

BdH]9

5$_fC

6vYzH

oujrzQ

p4dD$

t:O :h

)E-Jq

8knLn

}klyz

z?4jg

u/S}h~

)2XG_

P%. .k

;jQMn

HO;By

DH,X!T

yv}3A

fJY{n

|=y{K

N554G

DH|l!Y

r8BJv

<|~}f

## Root Entry

## Data

## WordDocument

## ObjectPool

_1425901662

## EPRINT

## CompObj

## Microsoft Visio Drawing

Visio 11.0 Shapes

Visio.Drawing.11

EMF+0@

EMF+*@

## ARIAL

## Arial

EMF++@

float

>@0;?

float

EMF++@

## AUTOMATIC

EMF++@

## MtrCurrQax

EMF++@

float

EMF++@

## AUTOMATIC

EMF++@

## MtrCurrDax

EMF++@

float

n(?@`+?

float

EMF++@

n(?@uz?

EMF++@

## AUTOMATIC

EMF++@

## MtrCurrQaxRef

n(?`j

n(?@l

## MtrCurrQaxRef

EMF++@

float

EMF++@

## AUTOMATIC

EMF++@

## MtrCurrDaxRef

EMF++@

float

EMF++@

## AUTOMATIC

EMF++@

## MtrCurrIPMQaxRef

EMF++@

float

EMF++@

l:? j

>J? j

EMF++@

## AUTOMATIC

EMF++@

## MtrCurrIPMDaxRef

?p(#@ j

## MtrCurrIPMDaxRef

EMF++@

0"%@ j

EMF++@

float

E ? {

float

EMF++@

sg? {

Zo? {

EMF++@

## AUTOMATIC

Aw? {

## AUTOMATIC

EMF++@

## PIDaxIntegralGain

."@ {

## PIDaxIntegralGain

EMF++@

"&@ {

EMF++@

:/@ {

EMF++@

\4@ {

EMF++@

0Q8@ {

EMF++@

float

EMF++@

## AUTOMATIC

EMF++@

## PIDaxPropotionalGain

?`O(@@

## PIDaxPropotionalGain

EMF++@

@80@@

EMF++@

float

EMF++@

## AUTOMATIC

@wv?@

## AUTOMATIC

EMF++@

## PIQaxIntegralGain

?0a"@@

## PIQaxIntegralGain

EMF++@

float

EMF++@

## AUTOMATIC

EMF++@

## PIQaxPropotionalGain

EMF++@

float

EMF++@

## AUTOMATIC

EMF++@

## ElecPosDelayComp

EMF++@

@E+@`

?`\4@`

EMF++@

@E<@`

EMF++@

PtN@`

EMF++@

float

?@rX?`

float

EMF++@

@Y`?`

EMF++@

## AUTOMATIC

EMF++@

## MtrVoltDaxFF

EMF++@

## Volt

EMF++@

float

EMF++@

## AUTOMATIC

EMF++@

## MtrVoltQaxFF

EMF++@

## Volt

?ps,@

## Volt

EMF++@

float

EMF++@

## AUTOMATIC

EMF++@

## Vecu

EMF++@

## Volt

EMF++@

P\$@@

EMF++@

float

EMF++@

## AUTOMATIC

EMF++@

## MtrCurrQaxError

EMF++@

@p#F@

EMF++@

float

EMF++@

## AUTOMATIC

EMF++@

## MtrCurrDaxError

EMF++@

@.!@P
