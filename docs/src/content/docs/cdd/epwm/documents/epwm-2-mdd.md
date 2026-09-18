---
title: "ePWM 2 Module Design Document"
description: "Converted from ePWM_2_MDD.docx"
---

> **Source document:** `ePWM/doc/ePWM_2_MDD.docx`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: Word document (`.docx`, 161 paragraphs, 13 tables, 0 embedded figures).

**Author:** Owen Tosh (nzx5jd) **Last saved by:** Windows User **Revision:** 9

---

# Module – EPWM 2

# High-Level Description

This module implements the ”Motor Control Configuration Override” subfunction of ES-34B.    It controls enable and disable of the motor control ePWM outputs.

# Figures

## Component Diagram

# Variable Data Dictionary

For details on module input / output variable, refer to the Data Dictionary for the application.  Input / output variable names are listed here for reference.

| Module Inputs | Module Outputs | Module Outputs |
| --- | --- | --- |
| DiagStsNonRecRmpToZeroFltPres_Cnt_lgc | DiagStsNonRecRmpToZeroFltPres_Cnt_lgc |  |
| RampDwnStatusComplete_Cnt_lgc | RampDwnStatusComplete_Cnt_lgc |  |

## Module Internal Variables

This section identifies the name, range and resolutions for module specific data created by this module.  If there are no range restrictions on the variable, the term “FULL” is placed into the table for legal range.

| Variable Name | Resolution | Legal Range<br />(min) | Legal Range<br />(max) | Software Segment |
| --- | --- | --- | --- | --- |

### User defined typedef definition/declaration

This section documents any user types uniquely used for the module.

(Refer the included ref for more details of register)

| Typedef Name | Element Name | User Defined Type | Legal Range<br />(min) | Legal Range<br />(max) |
| --- | --- | --- | --- | --- |

# Constant Data Dictionary

## Calibration Constants

This section lists the calibrations used by the module.  For details on calibration constants, refer to the Data Dictionary for the application.

| Constant Name |
| --- |
| None |

## Program(fixed) Constants

### Embedded Constants

All fixed point embedded constants whose values are provided in Eng units will be evaluated to the equivalent counts by using the FPM_InitFixedPoint_m() macro within the #define statement.

#### Local

| Constant Name | Units | Value |
| --- | --- | --- |
| D_ZEROTHRESHOLD_MTRNM_F32 | MtrNm | 0.05 |

#### Global

This section lists the global constants used by the module.  For details on global constants, refer to the Data Dictionary for the application.

| Constant Name |
| --- |
| None |

### Module specific Lookup Tables Constants

| Constant Name | Resolution | Value | Software Segment |
| --- | --- | --- | --- |
| None |  |  |  |

# Functions/Macros used by the Sub-Modules

## Library Functions / Macros

The library and functions / Macros that are called by the various sub modules are identified below,

Abs_f32_m

ePWM_EnableOutputs

ePWM_DisableOutputs

## Data Hiding Functions

None

## Global Functions/Macros Defined by this Module

### Local Macro

None

## Local Functions/Macros Used by this MDD only

None

# Software Module Implementation

## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but controlled by the RTE. After RTE initialization, the data in this table will contain these values.

| Data | Value |
| --- | --- |
| None |  |

## Initialization Functions

None

#### Design Rationale

None

#### Module Outputs

None

#### Module Internal

None

## Periodic Functions

### ePWM2_Per1

#### Design Rationale

Implements the "ePWM Control Shutdown" portion of ES-34B "Motor Control Configuration Override" Subfunction; this part of the subfunction runs periodically, while the remainder of the subfunction is implemented by two transition functions.

ES-34B specifies a NOR gate which disables the ePWM outputs when the NOR gate output is 0.  This is simplified in the code by checking the OR condition and disabling outputs when the OR condition is true.

#### Store Module Inputs to Local copies

#### Processing

#### Store Local copy of outputs into Module Outputs

None

## Fault Recovery Functions

None

## Shutdown Functions

None

## Interrupt Functions

None

## Serial Communication Functions

None

## Transition Functions

### Trns: ePWM2_Trns1

#### Design Rationale

Implements the "ePWM gate outputs are enable ON entering to operate state" portion of ES-34B "Motor Control Configuration Override" subfunction; function executes on entering mode OPERATE.

#### Program Flow Start

N/A

#### Store Module Inputs to Local copies

None

#### Processing

#### Store Local copy of outputs into Module Outputs

None

#### Program Flow End

N/A

### Trns: ePWM2_Trns2

#### Design Rationale

Implements the "ePWM gate outputs are disable if function leaves operate state" portion of ES-34B "Motor Control Configuration Override" subfunction.  Function executes on exiting mode OPERATE.

#### Program Flow Start

N/A

#### Store Module Inputs to Local copies

None

#### Processing

#### Store Local copy of outputs into Module Outputs

None

#### Program Flow End

N/A

# Execution Requirements

## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design

| Function Name | Calling Frequency | System State(s) in which the function is called |
| --- | --- | --- |
| ePWM2_Trns1 | On Event | On Entering OPERATE |
| ePWM2_Trns2 | On Event | On Leaving OPERATE |
| ePWM2_Per1 | 2ms | all |

## Execution Requirements for Serial Communication Functions

| Function Name | Sub-Module called by (Serial Comm Function Name) |
| --- | --- |
| None |  |

# Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in this module.

| Name of Sub Module | Software Segment |
| --- | --- |
| ePWM2_Trns1 | RTE_START_SEC_AP_EPWM2_APPL_CODE |
| ePWM2_Trns2 | RTE_START_SEC_AP_EPWM2_APPL_CODE |
| ePWM2_Per1 | RTE_START_SEC_AP_EPWM2_APPL_CODE |

## Local Functions

This table identifies the software segments for local functions identified in this module.

| Name of Sub Module | Software Segment |
| --- | --- |
| None |  |

# Known Issues / Limitations With Design

INLINE functions defined in “GlobalMacro.h” are not unit tested

# Revision Control Log

| Rev # | Change Description | Date | Author Initials |
| --- | --- | --- | --- |
| 1.0 | Initial Version (Shutdown Mechs FDD 34B) | 18-Feb-13 | Selva |
| 2 | Updated modes for Trns functions | 8-Mar-13 | OT |
| 3 | Added ePWM2_Per1 and updated transition function sections per ES-34B v007. | 25-Jan-15 | KMC |
