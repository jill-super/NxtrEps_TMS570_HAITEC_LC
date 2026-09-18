---
title: "CurrCmd Module Design Document"
description: "Converted from CurrCmd_MDD.doc"
---

> **Source document:** `MtrCtrl_CM/doc/CurrCmd_MDD.doc`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: legacy Word document (`.doc`).

> **Note:** the original file is a legacy binary Word document (`.doc`) which cannot be converted with full fidelity in this environment. The text below was recovered automatically and may be out of order in places; tables and figures are not preserved. See the original file for the authoritative content.

## Module -- CurrCmd

## High-Level Description

This Module generates the current command and the voltage reference for the current control.

## Diagram

## Function Data Sharing

## Diagram

## Function (Name)

## Variable Data Dictionary

For details on module input / output variable, refer to the Data Dictionary for the application. Input / output variable names are listed here for reference.

## Module Inputs

## Module Outputs

MRFTrqCmdScl_MtrNm_f32

DaxIntegralGain_Uls_f32

MRFMtrVel_MtrRadpS_f32

DaxPropotionalGain_Uls_f32

EstKe_VpRadpS_f32

QaxIntegralGain_Uls_f32

EstR_Ohm_f32

QaxPropotionalGain_Uls_f32

EstLd_Henry_f32

MtrCurrDaxRef_Amp_f32

EstLq_Henry_f32

MtrCurrQaxRef_Amp_f32

VehSpd_Kph_f32

MtrVoltDaxFF_Volt_f32

MtrQuad_Cnt_u08

MtrVoltQaxFF_Volt_f32

FastDataAccessBufIndex_Cnt_M_u16

MtrCurrAngle_Rev_f32

CurrentGainSvc_Cnt_lgc

MtrTrqCmdSign_Cnt_s16

MtrPosComputationDelay_Rad_f32

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

MtrVelFiltFFSV_MtrRadpS_M_s11p20

0.00000095367431640625

-1118

CURRCMD_START_SEC_VAR_CLEARED_32

MtrVelFiltPISV_MtrRadpS_M_s11p20

0.00000095367431640625

-1118

CURRCMD_START_SEC_VAR_CLEARED_32

MtrVelFilt_RadpSec_D_f32

## Single Precision Float

-1118

CURRCMD_START_SEC_VAR_CLEARED_32

MtrMaxCurrDaxRef_Amps_D_f32

## Single Precision Float

CURRCMD_START_SEC_VAR_CLEARED_32

MtrCurrQaxRef_Amp_D_f32

## Single Precision Float

CURRCMD_START_SEC_VAR_CLEARED_32

MtrCurrDaxRef_Amp_D_f32

## Single Precision Float

CURRCMD_START_SEC_VAR_CLEARED_32

PeakTorque_MtrNm_D_f32

## Single Precision Float

CURRCMD_START_SEC_VAR_CLEARED_32

MRFMtrVelFiltPI_MtrRadpS_D_f32

## Single Precision Float

-1118

CURRCMD_START_SEC_VAR_CLEARED_32

ElecPosDelayComp_Rad_D_f32

## Single Precision Float

-2*pi

CURRCMD_START_SEC_VAR_CLEARED_32

KpqGain_Uls_D_f32

## Single Precision Float

CURRCMD_START_SEC_VAR_CLEARED_32

KiqGain_Uls_D_f32

## Single Precision Float

CURRCMD_START_SEC_VAR_CLEARED_32

KpdGain_Uls_D_f32

## Single Precision Float

CURRCMD_START_SEC_VAR_CLEARED_32

KidGain_Uls_D_f32

## Single Precision Float

CURRCMD_START_SEC_VAR_CLEARED_32

IdMin_Amp_D_f32

## Single Precision Float

CURRCMD_START_SEC_VAR_CLEARED_32

IqMin_Amp_D_f32

## Single Precision Float

CURRCMD_START_SEC_VAR_CLEARED_32

IqMax_Amp_D_f32

## Single Precision Float

CURRCMD_START_SEC_VAR_CLEARED_32

IdMax_Amp_D_f32

## Single Precision Float

CURRCMD_START_SEC_VAR_CLEARED_32

ImSqMin_AmpSq_D_f32

## Single Precision Float

\96800

CURRCMD_START_SEC_VAR_CLEARED_32

LimitedMRFMtrTrqCmd_MtrNm_D_f32

## Single Precision Float

CURRCMD_START_SEC_VAR_CLEARED_32

PhsAdvPeak_Rad_D_f32

## Single Precision Float

-2*pi

CURRCMD_START_SEC_VAR_CLEARED_32

CosDelta_Cnt_M_f32

## Single Precision Float

CURRCMD_START_SEC_VAR_CLEARED_32

SinDelta_Cnt_M_f32

## Single Precision Float

CURRCMD_START_SEC_VAR_CLEARED_32

EstKe_VpRadpS_M_f32

## Single Precision Float

0.025

0.075

CURRCMD_START_SEC_VAR_CLEARED_32

TermXq_Uls_M_f32

## Single Precision Float

CURRCMD_START_SEC_VAR_CLEARED_32

TermXd_Uls_M_f32

## Single Precision Float

CURRCMD_START_SEC_VAR_CLEARED_32

TermEgR_Amp_M_f32

## Single Precision Float

-4050

CURRCMD_START_SEC_VAR_CLEARED_32

TermVR2_AmpSq_M_f32

## Single Precision Float

CURRCMD_START_SEC_VAR_CLEARED_32

TermEgRZ_Amp_M_f32

## Single Precision Float

CURRCMD_START_SEC_VAR_CLEARED_32

TermVRZ_Amp_M_f32

## Single Precision Float

CURRCMD_START_SEC_VAR_CLEARED_32

TermVR_Amp_M_f32

## Single Precision Float

CURRCMD_START_SEC_VAR_CLEARED_32

Reluctance_Henry_M_f32

## Single Precision Float

0.0002

0.0005

CURRCMD_START_SEC_VAR_CLEARED_32

LocateMinImNIter_Cnt_D_u16

CURRCMD_START_SEC_VAR_CLEARED_16

LocateTrqExNIter_Cnt_D_u16

CURRCMD_START_SEC_VAR_CLEARED_16

CurrCmd_IdBoostAmount_Amp_D_f32

## Single Precision Float

## See Data Dictionary

CURRCMD_START_SEC_VAR_CLEARED_32

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

k_a0IdSlope_Uls_f32

k_a1IdSlope_Uls_f32

k_a2IdSlope_Uls_f32

k_MtrVelFiltFFKn_Cnt_u16

k_MtrVelFiltPIKn_Cnt_u16

k_MtrMaxCurr_AmpsSq_f32

k_IdrefMtrVelOffset_RadpSec_f32

k_K2Slope_RadpSecpNm_f32

k_K3VelIntercep_RadpSec_f32

k_NoofPoles_Uls_f32

k_PIGainVspdCutoff_kph_f32

t_KpqGainX_MtrRadpSec_u12p4[8]

t_KpqGainY_Uls_u6p10[8]

t_KiqGainX_MtrRadpSec_u12p4[8]

t_KpdGainX_MtrRadpSec_u12p4[8]

t_KpdGainY_Uls_u6p10[8]

t_KidGainX_MtrRadpSec_u12p4[8]

t_KidGainY_Uls_u10p6[8]

t_RefDeltaPoints_Rad_f32[8]

t_Q13VltgSchedXTbl_MtrRadpS_u12p4[10]

t_Q13VltgSchedYTbl_Volt_u5p11[10]

t_Q24VltgSchedXTbl_MtrRadpS_u12p4[10]

t_Q24VltgSchedYTbl_Volt_u5p11[10]

k_IdqRefTrqTol_Rad_f32

k_IdqRefTrqNIter_Cnt_u16

k_IdqRefIminTol_Amp_f32

k_IdqRefLocateRefNIter_Cnt_u16

k_deadtimeVScale_Uls_f32

k_IdBoostGain_Uls_f32

k_IdBoostVRThreshScl_Uls_f32

t_IdBoostTrqCmdX_MtrNm_u4p12

t_IdBoostTrqCharSclY_Uls_u1p15

## Program(fixed) Constants

## Embedded Constants

All embedded constants whose values are provided in Eng units will be evaluated to the equivalent counts by using the FPM_InitFixedPoint_m() macro within the #define statement.

## Local

## Constant Name

## Resolution

## Units

## Value

D_SQRT3OVR2_ULS_F32

## Single Precision Float

0.866025403784

D_MTRPOLESDIV2_CNT_F32

## Single Precision Float

D_2OVRSQRT3_ULS_F32

## Single Precision Float

1.15470053837925

D_NEG2OVRSQRT3_ULS_F32

## Single Precision Float

-1.15470053837925F

D_ROUND_ULS_F32

## Single Precision Float

D_NEGROUND_ULS_F32

## Single Precision Float

D_NEG_ULS_F32

## Single Precision Float

D_MAXCURRENT_AMP_F32

## Single Precision Float

D_SIZERDLTAPOINTS_CNT_U16

TableSize_m(t_RefDeltaPoints_Rad_f32)

D_MAXDELTAPOINTSSIZE_CNT_U16

D_SIZERDLTAPOINTS_CNT_U16

D_PIPLUSPIOVER4_ULS_F32

## Single Precision Float

D_PI_ULS_F32+( D_2PI_ULS_F32/4)

D_VECUMAX_VOLTS_F32

## Single Precision Float

## Volts

31.0F

## Global

This section lists the global constants used by the module. For details on global constants, refer to the Data Dictionary for the application.

## Constant Name

D_ZERO_ULS_F32

D_180OVRPI_ULS_F32

D_ONE_ULS_F32

D_QUADRANT3_CNT_U8

D_QUADRANT1_CNT_U8

D_2PI_ULS_F32

D_ZERO_CNT_U16

D_VECUMIN_VOLTS_F32

## Module specific Lookup Tables Constants

(This is for lookup tables (arrays) with fixed values, same name as other tables)

## Constant Name

## Resolution

## Value

## Software Segment

## Functions/Macros used by the Sub-Modules

## Library Functions / Macros

The library and functions / Macros that are called by the various sub modules are identified below,

FPM_FloatToFixed_m

LPF_SvUpdate_s16InFixKTrunc_m

LPF_OpUpdate_s16InFixKTrunc_m

FPM_FixedToFloat_m

## Sqrtf

Abs_f32_m

atan2f

IntplVarXY_u16_u16Xu16Y_Cnt

## Data Hiding Functions

## Global Functions/Macros Defined by this Module

## Local Functions/Macros Used by this MDD only

Local Function #1

## Function Name

## ParabolicInterpolation

UTP Tol.

## Arguments Passed

IntpolPoints_Uls_T_f32[6]

Float32

## Return Value

ParaIntpol_Uls_T_f32

Float32

## Description

EMBED Visio.Drawing.11

Local Function #2

## Function Name

## CalculateImVSIdq

UTP Tol.

## Arguments Passed

IdRef_Amp_T_f32

Float32

+220-

IqRef_Amp_T_f32

Float32

+220-

## Return Value

ImVSIdq_AmpSq_T_f32

Float32

## Description

EMBED Visio.Drawing.11

Local Function #3

## Function Name

## CalculateIq

UTP Tol.

## Arguments Passed

Torquecmd_MtrNm_T_f32

Float32

IdRef_Amp_T_f32

Float32

## Return Value

IqRefTmp_Amp_T_f32

Float32

## Description

EMBED Visio.Drawing.11

Local Function #4

## Function Name

## CurrtoVoltTest

UTP Tol.

## Arguments Passed

IqRef_Amp_T_f32

Float32

IdRef_Amp_T_f32

Float32

*VqR_Amp_T_f32

Float32

*VdR_Amp_T_f32

Float32

## Return Value

VoltTest_Uls_T_lgc

## Boolean

## False

## Description

EMBED Visio.Drawing.11

Local Function #5

## Function Name

## CalcTorque

UTP Tol.

## Arguments Passed

CosDelta_Cnt_T_f32

Float32

SinDelta_Cnt_T_f32

Float32

*IdMax_Amp_T_f32

Float32

## Return Value

TorqueCalc_MtrNm_T_f32

Float32

## Description

EMBED Visio.Drawing.11

Local Function #6

## Function Name

## LocateTrqExtremese

UTP Tol.

## Arguments Passed

MtrTrqCmd_MtrNm_T_f32

Float32

*IdMax_Amp_T_f32

Float32

*PhsAdvPeak_Rad_T_f32

Float32

-2*pi

+2*pi

## Return Value

TorqueState_MtrNm_T_f32

Float32

## Description

EMBED Visio.Drawing.11

Local Function #7

## Function Name

## LocateMinimumIm

UTP Tol.

## Arguments Passed

MtrTrqCmd_MtrNm_T_f32

Float32

* IdMin_Amp_T_f32

Float32

* IqMin_Amp_T_f32

Float32

## Return Value

ImSqrMin_AmpSq_T_f32

Float32

## Description

EMBED Visio.Drawing.11

## Software Module Implementation

## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but controlled by the RTE. After RTE initialization, the data in this table will contain these values.

## Value

Rte_InitValue_DaxIntegralGain_Uls_f32

Rte_InitValue_DaxPropotionalGain_Uls_f32

Rte_InitValue_EstKe_VpRadpS_f32

Rte_InitValue_EstLd_Henry_f32

Rte_InitValue_EstLq_Henry_f32

Rte_InitValue_EstR_Ohm_f32

Rte_InitValue_MRFMtrVel_MtrRadpS_f32

Rte_InitValue_MRFTrqCmdScl_MtrNm_f32

Rte_InitValue_MtrCurrAngle_Rev_f32

Rte_InitValue_MtrCurrDaxRef_Amp_f32

Rte_InitValue_MtrCurrQaxRef_Amp_f32

Rte_InitValue_MtrPosComputationDelay_Deg_f32

Rte_InitValue_MtrTrqCmdSign_Cnt_s16

Rte_InitValue_MtrVoltDaxFF_Volt_f32

Rte_InitValue_MtrVoltQaxFF_Volt_f32

Rte_InitValue_QaxIntegralGain_Uls_f32

Rte_InitValue_QaxPropotionalGain_Uls_f32

Rte_InitValue_VehSpd_Kph_f32

## FastDataAccessBufIndex

## Initialization Functions

CurrCmd_Init

## Program Flow Start

Rte_Call_CurrCmd_Per1_CP0_CheckpointReached()

## Processing

EMBED Visio.Drawing.11

## Periodic Functions

Per: CurrCmd_Per1

## Design Rationale

## Program Flow Start

Rte_Call_CurrCmd_Per1_CP0_CheckpointReached()

## Store Module Inputs to Local copies

WriteAccessBufIndex_Cnt_T_u16= (FastDataAccessBufIndex_Cnt_M_u16&1)^1;

MRFMtrTrqCmd_MtrNm_T_f32=Rte_Iread_CurrCmd_Per1_MRFTrqCmdScl_MtrNm_f32

MRFMtrVel_MtrRadpS_T_f32=Rte_Iread_CurrCmd_Per1_MRFMtrVel_MtrRadpS_f32

EstKe_VpRadpS_T_f32=Rte_Iread_CurrCmd_Per1_EstKe_VpRadpS_f32

EstR_Ohm_T_f32=Rte_Iread_CurrCmd_Per1_EstR_Ohm_f32

EstLd_Henry_T_f32=Rte_Iread_CurrCmd_Per1_EstLd_Henry_f32

EstLq_Henry_T_f32=Rte_Iread_CurrCmd_Per1_EstLq_Henry_f32

VehSpd_Kph_T_f32=Rte_Iread_CurrCmd_Per1_VehSpd_Kph_f32

MtrQuad_Cnt_T_u8 = Rte_Iread_CurrCmd_Per1_MtrQuad_Cnt_u08

CurrentGainSvc_Cnt_T_lgc = Rte_IRead_CurrCmd_Per1_CurrentGainSvc_Cnt_lgc()

Vecu_Volt_T_f32 = Limit_m(Vecu_Volt_T_f32, D_VECUMIN_VOLTS_F32, D_VECUMAX_VOLTS_F32)

EMBED Visio.Drawing.11

## Store Local copy of outputs into Module Outputs

MtrDaxIntegralGain_Uls_M_f32[WriteAccessBufIndex_Cnt_T_u16] = KidGain_Uls_T_f32

MtrDaxPropotionalGain_Uls_M_f32[WriteAccessBufIndex_Cnt_T_u16] = KpdGain_Uls_T_f32

MtrQaxIntegralGain_Uls_M_f32[WriteAccessBufIndex_Cnt_T_u16] = KiqGain_Uls_T_f32

MtrQaxPropotionalGain_Uls_M_f32[WriteAccessBufIndex_Cnt_T_u16] = KpqGain_Uls_T_f32

MtrCurrQaxRef_Amp_M_f32[WriteAccessBufIndex_Cnt_T_u16] = MtrCurrQaxRef_Amp_T_f32

MtrCurrDaxRef_Amp_M_f32[WriteAccessBufIndex_Cnt_T_u16] = MtrCurrDaxRef_Amp_T_f32

Rte_Iwrite_CurrCmd_Per1_MtrCurrDaxRef_Amp_f32(MtrCurrDaxRef_Amp_T_f32)

Rte_Iwrite_CurrCmd_Per1_MtrCurrQaxRef_Amp_f32(MtrCurrQaxRef_Amp_T_f32)

MtrVoltDaxFF_Volt_M_f32[WriteAccessBufIndex_Cnt_T_u16]=MtrVoltDaxFF_Volt_T_f32

MtrVoltQaxFF_Volt_M_f32[WriteAccessBufIndex_Cnt_T_u16]=MtrVoltQaxFF_Volt_T_f32

Rte_Iwrite_CurrCmd_Per1_MtrVoltDaxFF_Volt_f32(MtrVoltDaxFF_Volt_T_f32)

Rte_Iwrite_CurrCmd_Per1_MtrVoltQaxFF_Volt_f32(MtrVoltQaxFF_Volt_T_f32)

Rte_Iwrite_CurrCmd_Per1_MtrCurrAngle_Rev_f32(MtrCurrElecAngle_Rev_T_f32)

Rte_Iwrite_CurrCmd_Per1_MtrTrqCmdSign_Cnt_s16(Sign_f32_m(MRFMtrTrqCmd_MtrNm_T_f32))

MtrPosComputationDelay_Rad_M_f32[WriteAccessBufIndex_Cnt_T_u16] = ElecPosDelayComp_Rad_T_f32

## Program Flow End

Rte_Call_CurrCmd_Per1_CP1_CheckpointReached()

## Fault Recovery Functions

## Shutdown Functions

## Interrupt Functions

## Serial Communication Functions

## Execution Requirements

## Execution Sequence of the Module

(Describe in words relevant details about the execution sequence of the different sub modules.)

## Execution Rates for sub-modules called by the Scheduler

## This table serves as reference for the Scheduler design

## Function Name

## Calling Frequency

## System State(s) in which the function is called

CurrCmd_Per1

CurrCmd_Init

## At init

## Execution Requirements for Serial Communication Functions

## Function Name

## Sub-Module called by (Serial Comm Function Name)

## Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in this module.

## Name of Sub Module

## Software Segment

CurrCmd_Per1

RTE_START_SEC_AP_CURRCMD_APPL_CODE

CurrCmd_Init

RTE_START_SEC_AP_CURRCMD_APPL_CODE

## Local Functions

This table identifies the software segments for local functions identified in this module.

## Name of Sub Module

## Software Segment

## ParabolicInterpolation

RTE_START_SEC_AP_CURRCMD_APPL_CODE

## CalculateIq

RTE_START_SEC_AP_CURRCMD_APPL_CODE

## CalculateImVSIdq

RTE_START_SEC_AP_CURRCMD_APPL_CODE

## CurrtoVoltTest

RTE_START_SEC_AP_CURRCMD_APPL_CODE

## CalcTorque

RTE_START_SEC_AP_CURRCMD_APPL_CODE

## LocateTrqExtremes

RTE_START_SEC_AP_CURRCMD_APPL_CODE

## LocateMinimumIm

RTE_START_SEC_AP_CURRCMD_APPL_CODE

## Known Issues / Limitations With Design

## Global Macro

s are not unit tested.

## Revision Control Log

Item #

Rev #

## Change Description

## Author Initials

## Initial version

15th-May-12

## KPIT-RT

Partial implementation of SF-99B v004

20-Sep-12

## Checkpoints and memmap statements added

20-Nov-12

## Selva

4.0,5.0

Implementation of SF99 v8

23-Mar-13

19-Apr-13

## Selva

Corrected for A5883. Corrected LocateMinimumIm

21-Oct-13

## Selva

Updated for v11 FDD99B

6-Nov-13

## Selva

Corrected for NewDelta calculation / Updated for v11 FDD99B UTP fixes

8-Nov-13

## Selva

Updated for V12 of FDD SF99

26-Nov-13

## Selva

## SOFTWARE MODULE DESIGN SPECIFICATION

Title:

## CurrCmd

Gen II+ EPS EA3

Revision:

Product:

Rev. Date:

DATE \@ "d-MMM-yy"

27-Nov-13

Group:

Originator:

## Selva Sengottaiyan

Page:

## NUMPAGES

## Nexteer

## CONFIDENTIAL

MDD Template EA3, Rev 1.1

yt)9<

~rngcgT

yt)9<

gd)9<

gd/v9

gd)9<

jfZVJZ:ZVf

gd)9<

gd/v9

yt$:k

gd$:k

gd/v9

zn^K@51

gd/v9

gdQ?.

{ococ

gdQ?.

zvkczv

xqjc_XQ

gd21k

}yrykrk`X`

jh}@V

wf_[WK[?K[

}q}q}q}m[I

{t{l{l{l{bU{

gd/v9

IDATx^

XN#1K

[ZsZS

$9f9qW\^

0<{O7

siHwK

sM{o~b

)BtsC

>v[G_

#,tVX

.zQ/v

}fW7X

`98P|

\nU[z

fh@@Vf

_0(h!

## ZZodH

$B%@ k

Rz!fGS5

xCg@ Q

TT,[Y

Pm[ET

!!cV/

ksj|C

R{We_

g^EX`l

F\le)7

ts`B}

(DfgG

4Vyen

[[[tCe

#GT0N_

`98P|

yt)9<
