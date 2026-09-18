---
title: "Damping Firewall Module Design Document"
description: "Converted from Damping_Firewall_MDD.doc"
---

> **Source document:** `DampingFirewall/doc/Damping_Firewall_MDD.doc`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: legacy Word document (`.doc`).

> **Note:** the original file is a legacy binary Word document (`.doc`) which cannot be converted with full fidelity in this environment. The text below was recovered automatically and may be out of order in places; tables and figures are not preserved. See the original file for the authoritative content.

bjbj$

`vd5^

## Module

## Damping Firewall

## High-Level Description

This module regulates the damping command according to safety specifications.

## Figures

## Component Diagram

## Variable Data Dictionary

For details on module input / output variable, refer to the Data Dictionary for the application. Input / output variable names are listed here for reference.

## Module Inputs

## Module Outputs

AsstFirewallActive_Uls_f32

CombinedDamping_MtrNm_f32

DampingCmd_MtrNm_f32

HwTorque_HwNm_f32

InertiaComp_MtrNm_f32

MtrVelCRF_MtrRadpS_f32

VehicleSpeed_Kph_f32

BaseAssistCmd_MtrNm_f32

WIRCmdAmpBlnd_MtrNm_f32

FreqDepDmpSrlComSvcDft_Cnt_lgc

VehicleLonAccel_KphpS_f32

Defeat_Damping_Svc_Cnt_lgc

MEC_Counter_Cnt_enum

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

DampFWVBICErrFiltSv_M_str

LPF32KSV_Str

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_UNSPECIFIED

DampFWActiveKSV_M_str

LPF32KSV_Str

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_UNSPECIFIED

DampFWUprBoundKSV_M_str

LPF32KSV_Str

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_UNSPECIFIED

DampFWLwrBoundKSV_M_str

LPF32KSV_Str

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_UNSPECIFIED

DampFWUprBoundFilt_MtrNm_D_f32

## Single Precision Float

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_32

DampFWLwrBoundFilt_MtrNm_D_f32

## Single Precision Float

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_32

DampFWUprBound_MtrNm_D_f32

## Single Precision Float

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_32

DampFWLwrBound_MtrNm_D_f32

## Single Precision Float

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_32

DampFWAddedDamp_MtrNm_D_f32

## Single Precision Float

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_32

DampFWAddedDampAFW_MtrNm_D_f32

## Single Precision Float

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_32

DampFWAddedDampDFW_MtrNm_D_f32

## Single Precision Float

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_32

DampFWTbarVelFiltSv_M_str

LPF32KSV_Str

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_UNSPECIFIED

DampFWSatDamp_MtrNm_D_f32

## Single Precision Floating Point

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_32

DampFWPrevTbarAng_HwDeg_M_s6p9

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_16

DampFWPrev1SclDrvVel_MtrRadpS_M_s14p1

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_16

DampFWPrev2SclDrvVel_MtrRadpS_M_s14p1

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_16

DampFWPrev1PreAttnComp_MtrNm_M_s9p6

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_16

DampFWPrev2PreAttnComp_MtrNm_M_s9p6

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_16

DampFWOverBound_Uls_D_lgc

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_BOOLEAN

ReducedPerfSV_Cnt_M_lgc

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_BOOLEAN

DampFWVBICOverThresh_Cnt_D_lgc

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_BOOLEAN

DampFWVBICReducedPerfSV_Cnt_M_lgc

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_BOOLEAN

DampFWDiverseVBIC_MtrNm_D_f32

## Single Precision Floating Point

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_32

DampFWDefltDamp_MtrNm_D_f32

## Single Precision Floating Point

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_32

DampFWDampActive_Uls_D_f32

## Single Precision Floating Point

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_32

DampFWLimitedVBIC_MtrNm_D_f32

## Single Precision Floating Point

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_32

DampFWInrtCmpPNStatus_Cnt_M_lgc

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_BOOLEAN

DampFWPNCountStatus_Cnt_M_lgc

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_BOOLEAN

InrtCmpPNAccum_Cnt_M_u16

UINT16

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_16

DampPNAcc_Cnt_M_u16

UNIT16

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_16

PNAcc_Cnt_M_u16

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_16

DampFWOverBound_Cnt_D_lgc

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_BOOLEAN

LimitedDamp_MtrNm_D_f32

## Single Precision Floating Point

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_32

DriverVel_MtrRadpSec_D_s24p7

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_32

PrevDecelGain_Uls_M_u5p11

2^-11

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_16

PrevRawDecelGain_Uls_M_u5p11

2^-11

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_16

FiltFreq_RadpS_D_s10p5

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_16

ScaledDriverVel_MtrRadpS_D_s14p1

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_16

OutputAtten_Uls_D_u8p8

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_16

RawDecelGain_Uls_D_u5p11

2^-11

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_16

DecelGain_Uls_D_u5p11

2^-11

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_16

ADDCoefCalc_MtrNmSpRad_D_u0p16

2^-16

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_16

InertiaCompCalc_MtrNm_D_u9p7

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_16

PreFiltVBICError_MtrNm_D_f32

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_32

PostFiltVBICError_MtrNm_D_f32

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_32

DampFWPrev1PreAttnComp_MtrNm_M_s20p11

2^-11

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_32

DampFWPrev2PreAttnComp_MtrNm_M_s20p11

2^-11

see Data Dictionary

DAMPINGFIREWALL_START_SEC_VAR_CLEARED_32

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

k_DampFWInpLimitDamp_MtrNm_f32

k_DampFWVBICLPF_Hz_f32

k_DampFWFWActiveLPF_Hz_f32

k_DampFWTbarVelLPFKn_Hz_f32

k_DmpBoundLPFKn_Hz_f32

k_DampFWMtrVelScale_Uls_f32

t_DampFWEstCompTblX_Kph_u9p7[]

t_DampFWTbarVelScaleY_Uls_u2p14[]

k_DampFWFilkKn_Hz_f32

t_DampFWEstCompHPF_Hz_u7p9[]

t_DampFWEstCompGain_MtrNmpMtrRadpS_u1p15[]

t_DampFWVehSpd_Kph_u9p7[]

t2_DampFWUprBoundX_MtrRadpS_s10p5[][]

t2_DampFWUprBoundY_MtrNm_s4p11[][]

t_DampFWAddDampX_MtrRadpS_u11p5[]

t_DampFWAddDampY_MtrNm_u5p11[]

t_DampFWDefltDampX_MtrRadpS_u11p5[]

t_DampFWDefltDampY_MtrNm_u5p11[]

k_DampFWErrThresh_MtrNm_f32

t_DampFWDampInrtCmpPNThesh_Cnt_u16[]

k_DampFWInCmpPStep_Cnt_u16

k_DampFWInCmpNStep_Cnt_u16

k_InrtCmp_TBarVelLPFKn_Hz_f32

k_DampFWPstep_Cnt_u16

k_DampFWNstep_Cnt_u16

t_DampFWPNstepThresh_Cnt_u16[]

k_InrtCmp_MtrInertia_KgmSq_f32

t_InrtCmp_ScaleFactorTblY_Uls_u9p7[]

t_InrtCmp_TBarVel_ScaleFactorTblY_Uls_u9p7[]

k_InrtCmp_MtrVel_ScaleFactor_Uls_f32

t_InrtCmp_VehSpdTblX_Kph_u15p1[]

t_FDD_ADDStaticTblY_MtrNmpRadpS_um1p17[]

t2_FDD_ADDRollingTblYM_MtrNmpRadpS_um1p17[][]

t_FDD_BlendTblY_Uls_u8p8[]

t_FDD_FreqTblYM_Hz_u12p4[]

t_FDD_AttenTblX_MtrRadpS_u12p4[]

t_FDD_AttenTblY_Uls_u8p8[]

t_WIRBlndTblX_MtrNm_u8p8[]

t_RIAstWIRBlndTblY_Uls_u2p14[]

t_DmpFiltKpWIRBlndY_Uls_u2p14[]

k_CmnTbarStiff_NmpDeg_f32

t_DmpADDCoefX_MtrNm_u4p12[10]

k_DmpGainOnThresh_KphpS_f32

k_DmpGainOffThresh_KphpS_f32

k_DmpDecelGain_Uls_f32

k_DmpDecelGainFSlew_UlspS_f32

t_DmpDecelGainSlewX_MtrRadpS_f32[]

t_DmpDecelGainSlewY_UlspS_f32[]

k_CmnSysKinRatio_MtrDegpHwDeg_f32

## Program (fixed) Constants

## Embedded Constants

All embedded constants whose values are provided in Eng units will be evaluated to the equivalent counts by using the FPM_InitFixedPoint_m() macro within the #define statement.

## Local

## Constant Name

## Resolution

## Units

## Value

D_ONEOVR2MS_SEC_U9P7

500.0

D_2MS_SEC_U0P16

2^-16

0.002

D_2MS_SEC_U2P14

2^-14

0.002

D_PIOVR180_ULS_S4P11

2^-11

## Unitless

0.0174532925199

D_ONE_ULS_U2P14

2^-14

## Unitless

D_ONE_ULS_U8P8

## Unitless

D_ONE_ULS_U5P11

2^-11

## Unitless

D_TWO_ULS_S2P13

2^-13

## Unitless

D_2PI_ULS_U2P13

2^-13

## Unitless

6.2831853071796

D_TBARVELFILTVAL_HWDEGPSEC_S15P16

2^-16

## HwDegpSec

1024.0

D_TBARVELFILTVAL_HWDEGPSEC_S15P16

2^-16

## HwDegpSec

2047.9375

D_TERMA_MTRRADPSEC_S20P11

2^-11

## MtrRadpS

4095.875

D_EIGHT_ULS_U10P6

## Unitless

D_SCALEDDRIVERVEL_MTRRADPS_S17P14

2^-14

## MtrRadpS

10000.0

D_COMPENSATIONLIMIT_MTRNM_S11P20

2^-20

## MtrNm

D_INERTIACOMPCALCLIMIT_MTRNM_U15P1

## MtrNm

D_FOUR_ULS_S3P12

2^-12

## Unitless

D_ADDCOEFCALCHILIMIT_MTRNMSPRAD_U1P15

2^-15

## MtrNmSpRad

D_ADDCOEFCALCHILIMIT_MTRNMSPRAD_U3P13

2^-13

## MtrNmSpRad

D_ABSSCALEDRIVERVELHI_MTRRADPS_U15P1

## MtrNmSpRad

4095. 5

VEHICLELONACCEL_MIN_F32

Float32

## KphpS

-64.0

VEHICLELONACCEL_MAX_F32

Float32

## KphpS

63.99804

D_ONE_ULS_U11P21

Uint32

## Unitless

## Global

This section lists the global constants used by the module. For details on global constants, refer to the Data Dictionary for the application.

## Constant Name

D_2MS_SEC_F32

D_PIOVR180_ULS_F32

D_ZERO_ULS_F32

D_FALSE_CNT_LGC

D_2PI_ULS_F32

D_MTRTRQCMDHILMT_MTRNM_F32

D_ONE_ULS_F32

## Module specific Lookup Tables Constants

## Constant Name

## Resolution

## Value

## Software Segment

## Functions/Macros Used By the Sub-Modules

## Library Functions / Macros

The library and functions / Macros that are called by the various sub modules are identified below,

LPF_KUpdate_f32_m

LPF_OpUpdate_f32_m

HPF_KUpdate_f32_m

HPF_OpUpdate_f32_m

FPM_FloatToFixed_m

FPM_FixedToFloat_m

IntplVarXY_u16_u16Xu16Y_Cnt

BilinearXYM_s16_s16Xs16YM_Cnt

TableSize_m

Limit_m

Sign_f32_m

Rte_Call_NxtrDiagMgr_SetNTCStatus

FPM_Fix_m

Abs_s32_m

## Data Hiding Functions

## Global Functions/Macros Defined by this Module

## Local Functions/Macros Used by this MDD only

Local Function #1

## Function Name

## DriverVelCalc

## Arguments Passed

HwTorque_HwNm_T_f32

float32

CRFMotorVel_MtrRadpS_T_f32

float32

-1350

VehicleSpeed_Kph_T_f32

float32

## Return Value

ScaledDriverVel_MtrRadpS_T_ s14p1

float32

-10000

## Description

EMBED Visio.Drawing.11

## Calculate ADD Coefficient

## Function Name

## ADDCoefCalc

## Arguments Passed

BaseAssistCmd_MtrNm_T_f32

float32

WIRCmdAmpBlnd_MtrNm_T_f32

float32

VehicleSpeed_Kph_T_f32

float32

CRFMotorVel_MtrRadpS_T_f32

Float32

-1350

VehicleLonAccel_KphpS_T_f32

Float32

## Return Value

ADDCoefCalc_MtrNmSpRad_T_ u0p16

uint16

## Description

EMBED Visio.Drawing.11

## Calculate Filter Coefficients

## Function Name

## FilterCoefCalc

## Arguments Passed

ADDCoefCalc_MtrNmSpRad_T_ u0p16

uint16

WIRCmdAmpBlnd_MtrNm_T_f32

float32

VehicleSpeed_Kph_T_f32

float32

filtCoef_Uls_T_Str

filterCoef_T*

## N/A (address)

## Outputs Returned (by reference)

filtCoef_Uls_T_Str->b0_Uls_ s0p15

sint16

-0.975097656

filtCoef_Uls_T_Str->b1_Uls_ u0p16

uint16

0.400024414

filtCoef_Uls_T_Str->b2_Uls_ s0p15

sint16

-0.322692871

0.575073242

filtCoef_Uls_T_Str->a0_Uls_ u2p14

uint16

0.539428711

3.949829102

filtCoef_Uls_T_Str->a1_Uls_s4p11

sint16

-4.797363281

filtCoef_Uls_T_Str->a2_Uls_u5p11

uint16

4.050292969

10.66308594

## Return Value

## Description

EMBED Visio.Drawing.11

## Generate Command

## Function Name

## GenFddIcCmd

## Arguments Passed

ScaledDriverVel_MtrRadpS_T_ s14p1

sint16

-10000

*FilterCoefStr

b0_Uls_ s0p15

sint16

-0.975097656

b1_Uls_ u0p16

uint16

0.400024414

b2_Uls_ s0p15

sint16

-0.322692871

0.575073242

a0_Uls_ u2p14

uint16

0.539428711

3.949829102

a1_Uls_s4p11

sint16

-4.797363281

a2_Uls_u5p11

uint16

4.050292969

10.66308594

## Return Value

Compenstation_MtrNm_T_ s11p20

Sint32

## Unit Testing Considerations

This function is designed to work with argument values from the calling function as used with the other functions in the module, and outputs may be out of the expected range if tested with arbitrary combinations of input values. Unit testing of this function should use only passed argument value combinations coming from the calling function.

## Description

EMBED Visio.Drawing.11

## Software Module Implementation

## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but controlled by the RTE. After RTE initialization, the data in this table will contain these values.

## Value

Rte_InitValue_AsstFirewallActive_Uls_f32

Rte_InitValue_CombinedDamping_MtrNm_f32

Rte_InitValue_DampingCmd_MtrNm_f32

Rte_InitValue_HwTorque_HwNm_f32

Rte_InitValue_InertiaComp_MtrNm_f32

Rte_InitValue_MtrVelCRF_MtrRadpS_f32

Rte_InitValue_VehicleSpeed_Kph_f32

Rte_InitValue_ BaseAssistCmd_MtrNm_f32

Rte_InitValue _WIRCmdAmpBlnd_MtrNm_f32

Rte_InitValue _ VehicleLonAccel_KphpS_f32

Rte_InitValue _ FreqDepDmpSrlComSvcDft_Cnt_lgc

## FALSE

## Initialization Functions

Init:

## DampingFirewall

_Init1

## Design Rationale

## Module Outputs

## Module Internal

## Initialize Filters

EMBED Visio.Drawing.11

## Periodic Functions

## DampingFirewall

_Per1

## Design Rationale

## Program Flow Start

Rte_Call_ActivePull_Per1_CP0_CheckpointReached()

## Store Module Inputs to Local copies

DefeatDampingSvc_Cnt_T_lgc = Rte_IRead_DampingFirewall_Per1_Defeat_Damping_Svc_Cnt_lgc()

MECCounter_Cnt_T_enum = Rte_IRead_DampingFirewall_Per1_MEC_Counter_Cnt_enum()

AsstFirewallActive_Uls_T_f32 = Rte_IRead_DampingFirewall_Per1_AsstFirewallActive_Uls_f32()

DampingCmd_MtrNm_T_f32 = Rte_IRead_DampingFirewall_Per1_DampingCmd_MtrNm_f32()

HwTorque_HwNm_T_f32 = Rte_IRead_DampingFirewall_Per1_HwTorque_HwNm_f32()

InertiaComp_MtrNm_T_f32 = Rte_IRead_DampingFirewall_Per1_InertiaComp_MtrNm_f32()

MtrVelCRF_MtrRadpS_T_f32 = Rte_IRead_DampingFirewall_Per1_MtrVelCRF_MtrRadpS_f32()

VehicleSpeed_Kph_T_f32 = Rte_IRead_DampingFirewall_Per1_VehicleSpeed_Kph_f32()

BaseAsstCmd_MtrNm_T_f32 = Rte_IRead_DampingFirewall_Per1_BaseAssistCmd_MtrNm_f32()

WIRCmdAmpBlnd_MtrNm_T_f32 = Rte_IRead_DampingFirewall_Per1_WIRCmdAmpBlnd_MtrNm_f32()

FDDDefSrvFlg_Cnt_T_lgc = Rte_IRead_DampingFirewall_Per1_FreqDepDmpSrlComSvcDft_Cnt_lgc()

VehicleLonAccel_KphpS_T_f32 = Rte_IRead_DampingFirewall_Per1_VehicleLonAccel_KphpS_f32()

VehicleSpeed_Kph_T_u9p7 = FPM_FloatToFixed_m(VehicleSpeed_Kph_T_f32, u9p7_T)

MtrVelCRF_MtrRadpS_T_s11p4 = FPM_FloatToFixed_m(MtrVelCRF_MtrRadpS_T_f32, s11p4_T)

AbsMtrVelCRF_MtrRadpS_T_u11p5 = FPM_FloatToFixed_m(Abs_f32_m(MtrVelCRF_MtrRadpS_T_f32), u11p5_T)

DampFWPstepNstep_Cnt_T_str.PStep = k_DampFWPstep_Cnt_u16

DampFWPstepNstep_Cnt_T_str.NStep = k_DampFWNstep_Cnt_u16

DampFWPstepNstep_Cnt_T_str.Threshold = t_DampFWPNstepThresh_Cnt_u16[1]

DampFWInrtCmpPstepNstep_Cnt_T_str.PStep = k_DampFWInCmpPStep_Cnt_u16

DampFWInrtCmpPstepNstep_Cnt_T_str.NStep = k_DampFWInCmpNStep_Cnt_u16

DampFWInrtCmpPstepNstep_Cnt_T_str.Threshold = t_DampFWDampInrtCmpPNThesh_Cnt_u16[1]

## Damping Limiter

## Interpolate and Filter Boundaries

EMBED Visio.Drawing.11

## PNCounter

EMBED Visio.Drawing.11

## Additional Damping

EMBED Visio.Drawing.11

## Store Local copy of outputs into Module Outputs

DampFWUprBound_MtrNm_D_f32 = UprBoundRaw_MtrNm_T_f32

DampFWUprBoundFilt_MtrNm_D_f32 = UprBoundFilt_MtrNm_T_f32

DampFWLwrBound_MtrNm_D_f32 = LwrBoundRaw_MtrNm_T_f32

DampFWLwrBoundFilt_MtrNm_D_f32 = LwrBoundFilt_MtrNm_T_f32

DampFWAddedDamp_MtrNm_D_f32 = AddedDamp_MtrNm_T_f32

DampFWAddedDampAFW_MtrNm_D_f32 = AFWAddDamping_MtrNm_T_f32

DampFWAddedDampDFW_MtrNm_D_f32 = DFWAddDamping_MtrNm_T_f32

Rte_IWrite_DampingFirewall_Per1_CombinedDamping_MtrNm_f32(CombinedDamping_MtrNm_T_f32)

## Program Flow End

Rte_Call_ActivePull_Per1_CP1_CheckpointReached()

## Fault Recovery Functions

## Shutdown Functions

## Interrupt Functions

## Serial Communication Functions

## Execution Requirements

## Execution Sequence of the Module

DampingFirewall_Per1 is called at a rate of 2 ms.

## Execution Rates for sub-modules called by the Scheduler

## This table serves as reference for the Scheduler design

## Function Name

## Calling Frequency

## System State(s) in which the function is called

DampingFirewall_Init1

## On Event

## On Init

DampingFirewall_Per1

## Execution Requirements for Serial Communication Functions

## Function Name

## Sub-Module called by (Serial Comm Function Name)

## Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in this module.

## Name of Sub Module

## Software Segment

DampingFirewall_Init1

RTE_START_SEC_AP_DAMPINGFIREWALL_APPL_CODE

DampingFirewall_Per1

RTE_START_SEC_AP_DAMPINGFIREWALL_APPL_CODE

## Local Functions

This table identifies the software segments for local functions identified in this module.

## Name of Sub Module

## Software Segment

## DriverVelCalc

AP_DAMPINGFIREWALL_CODE

## ADDCoefCalc

AP_DAMPINGFIREWALL_CODE

## FilterCoefCalc
