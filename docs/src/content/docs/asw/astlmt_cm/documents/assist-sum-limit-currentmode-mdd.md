---
title: "Assist Sum Limit CurrentMode Module Design Document"
description: "Converted from Assist_Sum_Limit_CurrentMode_MDD.docx"
---

> **Source document:** `AstLmt_CM/doc/Assist_Sum_Limit_CurrentMode_MDD.docx`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: Word document (`.docx`, 198 paragraphs, 16 tables, 0 embedded figures).

**Author:** Owen Tosh (nzx5jd) **Last saved by:** Balani, Spandana **Revision:** 4

---

# Module –

# High-Level Description

This module combines and limits the various assist command signals from EPS modules.  It puts out several torque commands from different points in the summation and limiting process.

# Figures

## Component Diagram

# Variable Data Dictionary

For details on module input / output variable, refer to the Data Dictionary for the application.  Input / output variable names are listed here for reference.

| Module Inputs | Module Outputs | Module Outputs |
| --- | --- | --- |
| AssistCmd_MtrNm_f32 | AssistCmd_MtrNm_f32 | LimitPercentFiltered_Uls_f32 |
| AssistEOTDamping_MtrNm_f32 | AssistEOTDamping_MtrNm_f32 |  |
| AssistEOTGain_Uls_f32 | AssistEOTGain_Uls_f32 |  |
| AssistEOTLimit_MtrNm_f32 | AssistEOTLimit_MtrNm_f32 | PreLimitForStall_MtrNm_f32 |
|  |  | PreLimitTorque_MtrNm_f32 |
| AssistStallLimit_MtrNm_f32 | AssistStallLimit_MtrNm_f32 | SumLimTrqCmd_MtrNm_T_f32 |
| AssistVehSpdLimit_MtrNm_f32 | AssistVehSpdLimit_MtrNm_f32 | TrqLimitMin_MtrNm_f32 |
| CombinedDamping_MtrNm_f32 | CombinedDamping_MtrNm_f32 |  |
| DefeatLimitService_Cnt_lgc | DefeatLimitService_Cnt_lgc |  |
| LimitedReturn_MtrNm_f32 | LimitedReturn_MtrNm_f32 |  |
| LrnPnCtrCCDisable_Cnt_lgc | LrnPnCtrCCDisable_Cnt_lgc |  |
| LrnPnCtrEnable_Cnt_lgc | LrnPnCtrEnable_Cnt_lgc |  |
| LrnPnCtrTCmd_MtrNm_f32 | LrnPnCtrTCmd_MtrNm_f32 |  |
| OpTrqOvr_MtrNm_f32 | OpTrqOvr_MtrNm_f32 |  |
| OutputRampMult_Uls_f32 | OutputRampMult_Uls_f32 |  |
| PosServCCDisable_Cnt_lgc | PosServCCDisable_Cnt_lgc |  |
| PowerLimitPerc_Uls_f32 | PowerLimitPerc_Uls_f32 |  |
| PrkAssistCmd_MtrNm_f32 | PrkAssistCmd_MtrNm_f32 |  |
| PullCompCmd_MtrNm_f32 | PullCompCmd_MtrNm_f32 |  |
| ThermalLimitPerc_Uls_f32 | ThermalLimitPerc_Uls_f32 |  |
| ThermalLimit_MtrNm_f32 | ThermalLimit_MtrNm_f32 |  |
| VehSpd_Kph_f32 | VehSpd_Kph_f32 |  |
| WheelImbalanceCmd_MtrNm_f32 | WheelImbalanceCmd_MtrNm_f32 |  |

## Module Internal Variables

This section identifies the name, range and resolutions for module specific data created by this module.  If there are no range restrictions on the variable, the term “FULL” is placed into the table for legal range.

| Variable Name | Resolution | Legal Range<br />(min) | Legal Range<br />(max) | Software Segment |
| --- | --- | --- | --- | --- |
| AstLmt_ManualTrqCmd_MtrNm_M_f32 | Single Precision Float | -16 | 15.9995 | ASTLMT_START_SEC_VAR_CLEARED_32 |
| AstLmt_ManualTrqCmdEn_Cnt_M_lgc | n/a | FALSE | TRUE | ASTLMT_START_SEC_VAR_CLEARED_BOOLEAN |
| AstLmt_SteeringAsstDefeat_Cnt_M_lgc | n/a | FALSE | TRUE | ASTLMT_START_SEC_VAR_CLEARED_BOOLEAN |

### User defined typedef definition/declaration

This section documents any user types uniquely used for the module.

| Typedef Name | Element Name | User Defined Type | Legal Range<br />(min) | Legal Range<br />(max) |
| --- | --- | --- | --- | --- |
| None |  |  |  |  |

# Constant Data Dictionary

## Calibration Constants

This section lists the calibrations used by the module.  For details on calibration constants, refer to the Data Dictionary for the application.

| Constant Name |
| --- |
| k_SumLimPlCmpLimit_MtrNm_f32 |

## Program(fixed) Constants

### Embedded Constants

All embedded constants whose values are provided in Eng units will be evaluated to the equivalent counts by using the FPM_InitFixedPoint_m() macro within the #define statement.

#### Local

| Constant Name | Resolution | Units | Value |
| --- | --- | --- | --- |
| None |  |  |  |

#### Global

This section lists the global constants used by the module.  For details on global constants, refer to the Data Dictionary for the application.

| Constant Name |
| --- |
| D_ZERO_ULS_F32 |
| D_ONE_ULS_F32 |
| D_MTRTRQCMDLOLMT_MTRNM_F32 |
| D_MTRTRQCMDHILMT_MTRNM_F32 |
| FLT_EPSILON |

### Module specific Lookup Tables Constants

| Constant Name | Resolution | Value | Software Segment |
| --- | --- | --- | --- |
| None |  |  |  |

# Functions/Macros used by the Sub-Modules

## Library Functions / Macros

The library and functions / Macros that are called by the various sub modules are identified below,

Abs_f32_m

Sign_f32_m

Min_m

Max_m

Limit_m

## Data Hiding Functions

- Rte_Call_SteeringAsstDefeat_WriteBlock

- Rte_Pim_SteerAsstDefeat

- Rte_Call_AstLmt_Per1_CP0_CheckpointReached

- Rte_Call_AstLmt_Per1_CP1_CheckpointReached

## Global Functions/Macros Defined by this Module

None

## Local Functions/Macros Used by this MDD only

None

# Software Module Implementation

## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but controlled by the RTE. After RTE initialization, the data in this table will contain these values.

| Data | Value |
| --- | --- |
| Rte_InitValue_AssistCmd_MtrNm_f32 | 0 |
| Rte_InitValue_AssistEOTDamping_MtrNm_f32 | 0 |
| Rte_InitValue_AssistEOTGain_Uls_f32 | 1 |
| Rte_InitValue_AssistEOTLimit_MtrNm_f32 | 8.8 |
| Rte_InitValue_AssistStallLimit_MtrNm_f32 | 8.8 |
| Rte_InitValue_AssistVehSpdLimit_MtrNm_f32 | 8.8 |
| Rte_InitValue_CombinedDamping_MtrNm_f32 | 0 |
| Rte_InitValue_DefeatLimitService_Cnt_lgc | FALSE |
| Rte_InitValue_LimitPercentFiltered_Uls_f32 | 0 |
| Rte_InitValue_LimitedReturn_MtrNm_f32 | 0 |
| Rte_InitValue_LrnPnCtrCCDisable_Cnt_lgc | FALSE |
| Rte_InitValue_LrnPnCtrEnable_Cnt_lgc | FALSE |
| Rte_InitValue_LrnPnCtrTCmd_MtrNm_f32 | 0 |
| Rte_InitValue_OpTrqOvr_MtrNm_f32 | 0 |
| Rte_InitValue_OutputRampMult_Uls_f32 | 0 |
| Rte_InitValue_PosServCCDisable_Cnt_lgc | FALSE |
| Rte_InitValue_PowerLimitPerc_Uls_f32 | 0 |
| Rte_InitValue_SumLimTrqCmd_MtrNm_f32 | 0 |
| Rte_InitValue_PreLimitForStall_MtrNm_f32 | 0 |
| Rte_InitValue_PreLimitTorque_MtrNm_f32 | 0 |
| Rte_InitValue_PrkAssistCmd_MtrNm_f32 | 0 |
| Rte_InitValue_PullCompCmd_MtrNm_f32 | 0 |
| Rte_InitValue_ThermalLimit_MtrNm_f32 | 8.8 |
| Rte_InitValue_ThermalLimitPerc_Uls_f32 | 0 |
| Rte_InitValue_VehSpd_Kph_f32 | 0 |
| Rte_InitValue_WheelImbalanceCmd_MtrNm_f32 | 0 |

## Initialization Functions

### Init: AstLmt_Init

#### Design Rationale

#### Program Flow Start

N/A

#### Store Module Inputs to Local Copies

N/A

#### (Processing of function)…..

AstLmt_SteeringAsstDefeat_Cnt_M_lgc  = *Rte_Pim_SteerAsstDefeat()

#### Store Local copy of outputs into Module Outputs

N/A

#### Program Flow End

N/A

## Periodic Functions

### Per: _Per1

#### Design Rationale

While the FDD specifies the LimitPercentFiltered output to be populated every 10 ms, the overhead required for another periodic function would be greater than including the single Max_m() macro in the main 2 ms periodic function.

#### Program Flow Start

Rte_Call_AstLmt_Per1_CP0_CheckpointReached()

#### Store Module Inputs to Local copies

AssistCmd_MtrNm_T_f32 = Rte_IRead_AstLmt_Per1_AssistCmd_MtrNm_f32()

AssistEOTDamping_MtrNm_T_f32 = Rte_IRead_AstLmt_Per1_AssistEOTDamping_MtrNm_f32()

AssistEOTGain_Uls_T_f32 = Rte_IRead_AstLmt_Per1_AssistEOTGain_Uls_f32()

AssistEOTLimit_MtrNm_T_f32 = Rte_IRead_AstLmt_Per1_AssistEOTLimit_MtrNm_f32()

AssistStallLimit_MtrNm_T_f32 = Rte_IRead_AstLmt_Per1_AssistStallLimit_MtrNm_f32()

AssistVehSpdLimit_MtrNm_T_f32 = Rte_IRead_AstLmt_Per1_AssistVehSpdLimit_MtrNm_f32()

CombinedDamping_MtrNm_T_f32 = Rte_IRead_AstLmt_Per1_CombinedDamping_MtrNm_f32()

DefeatLimitService_Cnt_T_lgc = Rte_IRead_AstLmt_Per1_DefeatLimitService_Cnt_lgc()

LimitedReturn_MtrNm_T_f32 = Rte_IRead_AstLmt_Per1_LimitedReturn_MtrNm_f32()

LrnPnCtrCCDisable_Cnt_T_lgc = Rte_IRead_AstLmt_Per1_LrnPnCtrCCDisable_Cnt_lgc()

LrnPnCtrEnable_Cnt_T_lgc = Rte_IRead_AstLmt_Per1_LrnPnCtrEnable_Cnt_lgc()

LrnPnCtrTCmd_MtrNm_T_f32 = Rte_IRead_AstLmt_Per1_LrnPnCtrTCmd_MtrNm_f32()

OpTrqOvr_MtrNm_T_f32 = Rte_IRead_AstLmt_Per1_OpTrqOvr_MtrNm_f32()

OutputRampMult_Uls_T_f32 = Rte_IRead_AstLmt_Per1_OutputRampMult_Uls_f32()

PosServCCDisable_Cnt_T_lgc = Rte_IRead_AstLmt_Per1_PosServCCDisable_Cnt_lgc()

PowerLimitPerc_Uls_T_f32 = Rte_IRead_AstLmt_Per1_PowerLimitPerc_Uls_f32()

PrkAssistCmd_MtrNm_T_f32 = Rte_IRead_AstLmt_Per1_PrkAssistCmd_MtrNm_f32()

PullCompCmd_MtrNm_T_f32 = Rte_IRead_AstLmt_Per1_PullCompCmd_MtrNm_f32()

ThermalLimitPerc_Uls_T_f32 = Rte_IRead_AstLmt_Per1_ThermalLimitPerc_Uls_f32()

ThermalLimit_MtrNm_T_f32 = Rte_IRead_AstLmt_Per1_ThermalLimit_MtrNm_f32()

VehSpd_Kph_T_f32 = Rte_IRead_AstLmt_Per1_VehSpd_Kph_f32()

WheelImbalanceCmd_MtrNm_T_f32 = Rte_IRead_AstLmt_Per1_WheelImbalanceCmd_MtrNm_f32()

#### Preconditioning and Command summation

#### Apply Gain and Limit

#### Assist Reduction Level

#### Store Local copy of outputs into Module Outputs

Rte_IWrite_AstLmt_Per1_TrqLimitMin_MtrNm_f32(TrqLimitMin_MtrNm_T_f32)

Rte_IWrite_AstLmt_Per1_LimitPercentFiltered_Uls_f32(LimitPercentFiltered_Uls_T_f32)

Rte_IWrite_AstLmt_Per1_SumLimTrqCmd_MtrNm_f32(SumLimTrqCmd_MtrNm_T_f32)

Rte_IWrite_AstLmt_Per1_PreLimitForStall_MtrNm_f32(PreLimitForStall_MtrNm_T_f32)

Rte_IWrite_AstLmt_Per1_PreLimitTorque_MtrNm_f32(PreLimitTorque_MtrNm_T_f32)

#### Program Flow End

## Rte_Call_AstLmt_Per1_CP1_CheckpointReached()Fault Recovery Functions

None

## Shutdown Functions

None

## Interrupt Functions

None

## Serial Communication Functions

### SCom: AstLmt_SCom_ManualTrqCmd

|  |  | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | EnableManualCtrl | boolean | FALSE | TRUE |  |
|  | MtrTrqCmd_MtrNm_f32 | float32 | -16 | 15.9995 |  |
| Return Value | RetCode | Std_ReturnType | 0 | 34 | 0 |

#### Design Rationale

None

#### Program Flow Start

N/A

#### Store Module Inputs to Local copies

Rte_Read_VehSpd_Kph_f32(&VehSpd_Kph_T_f32)

#### Process Manual Torque Command

#### Store Local copy of outputs into Module Outputs

None

#### Program Flow End

N/A

### SCom: AstLmt_Scom_GetSteeringAssistDefeat

|  |  | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | SteeringAsstDefeat_Cnt_lgc | *boolean | FALSE | TRUE |  |
| Return Value | none |  |  |  |  |

#### Design Rationale

None

#### Program Flow Start

N/A

#### Store Module Inputs to Local copies

N/A

#### Get Steering Assist Defeat Status

*SteeringAsstDefeat_Cnt_lgc = *Rte_Pim_SteerAsstDefeat()

#### Store Local copy of outputs into Module Outputs

None

#### Program Flow End

N/A

### SCom: AstLmt_Scom_SetSteeringAssistDefeat

|  |  | Type | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- |
| Arguments Passed | SteeringAsstDefeat_Cnt_lgc | boolean | FALSE | TRUE |  |
| Return Value | none |  |  |  |  |

#### Design Rationale

None

#### Program Flow Start

N/A

#### Store Module Inputs to Local copies

N/A

#### Get Steering Assist Defeat Status

*Rte_Pim_SteerAsstDefeat() = SteeringAsstDefeat_Cnt_lgc

Rte_Call_SteeringAsstDefeat_WriteBlock(NULL_PTR)

#### Store Local copy of outputs into Module Outputs

None

#### Program Flow End

N/A

# Execution Requirements

## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design

| Function Name | Calling Frequency | System State(s) in which the function is called |
| --- | --- | --- |
| AstLmt_Init | Executed Once after RTE is started | ColdInit |
| AstLmt_Per1 | 2 ms | ALL |

## Execution Requirements for Serial Communication Functions

| Function Name | Sub-Module called by (Serial Comm Function Name) |
| --- | --- |
| AstLmt_Scom_ManualTrqCmd | Server invocation for OperationPrototype <ManualTrqCmd> |
| AstLmt_Scom_GetSteeringAssistDefeat | Server invocation for OperationPrototype <GetSteeringAssistDefeat> |
| AstLmt_Scom_SetSteeringAssistDefeat | Server invocation for OperationPrototype <SetSteeringAssistDefeat> |

# Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in this module.

| Name of Sub Module | Software Segment |
| --- | --- |
| AstLmt_Init | RTE_START_SEC_AP_ASTLMT_APPL_CODE |
| AstLmt_Per1 | RTE_START_SEC_AP_ASTLMT_APPL_CODE |
| AstLmt_Scom_ManualTrqCmd | RTE_START_SEC_AP_ASTLMT_APPL_CODE |
| AstLmt_Scom_GetSteeringAssistDefeat | RTE_START_SEC_AP_ASTLMT_APPL_CODE |
| AstLmt_Scom_SetSteeringAssistDefeat | RTE_START_SEC_AP_ASTLMT_APPL_CODE |

## Local Functions

This table identifies the software segments for local functions identified in this module.

| Name of Sub Module | Software Segment |
| --- | --- |
| None |  |

# Known Issues / Limitations With Design

INLINE functions defined in GlobalMacro.h are not unit tested.

# Revision Control Log

| Item # | Rev # | Change Description | Date | Author Initials |
| --- | --- | --- | --- | --- |
| 1 | 1.0 | Initial Version (SF-04B v001) | 07-Aug-12 | OT |
| 2 | 2.0 | Fixed UTP Issues (global constants) | 08-Aug-12 | OT |
| 3 | 3.0 | Added ManualTrqCmd service | 16-Aug-12 | OT |
| 4 | 4.0 | Replaced HwtrqPolarity with assistassembley polarity | 11-SEP-12 | SAH |
| 5 | 5.0 | - Removed Inputs: MRFMtrVel, AssistAssembly_Polarity, Assist_PowerLimit<br />- Removed Output: PostLimit_ForAssistSumCC<br />- Renamed Output: PreLimit_for_Power to SumLimTrqCmd_MtrNm<br />- Removed calibration: k_OvrSpdMtrTrq2QLmt_MtrNm | 01-Dec-12 | Selva |
| 6 | 6.0 | Updated output limit on sumlimtrqcmd from 0 to -8.8 to match FDD data dictionary | 14-Jan-13 | SAH |
| 7 | 7.0 | Updates to add steering assist defeat | 03-Jun-13 | VK |
| 8 | 8.0 | Update to v4 of FDD. Added new outputs and matched the naming conventions | 23-Nov-13 | Selva |
| 9 | 9.0 | Corrected range of ‘AstLmt_ManualTrqCmd_MtrNm_M_f32’ | 10-Dec-13 | SR |
| 10 | 10.0 | Updated to SF-04B v5, modified PreLimitForStall, AssistCmd, and AbsLimitedTorque | 12-June-06 | VT |
| 11 | 11.0 | Unit Testing Findings fixed | 11-July-14 | KPIT-SSK |
