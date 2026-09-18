---
title: "Cd uDiagUtility Module Design Document"
description: "Converted from Cd_uDiagUtility_MDD.docx"
---

> **Source document:** `TMS570_uDiag/doc/Cd_uDiagUtility_MDD.docx`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: Word document (`.docx`, 92 paragraphs, 14 tables, 0 embedded figures).

**Author:** Jeremy Warmbier;Kathleen Creager **Last saved by:** Creager, Kathleen **Revision:** 5

---

# High-Level Description

Cd_uDiagUtility provides utility assembly language functions needed by the Cd_uDiag component.

# Figures

## Diagram – Function Data Sharing

No Shared Data

# Variable Data Dictionary

For details on module input / output variable, refer to the Data Dictionary for the application.  Input / output variable names are listed here for reference.

(Note: Full variable names required in table.)

(Note: All global variables including End Of Line data used should be shown here)

| Module Inputs | Module Outputs | Module Outputs |
| --- | --- | --- |
| <None> | <None> | <None> |

## Module Internal Variables

This section identifies the name, range and resolutions for module specific data created by this module.  If there are no range restrictions on the variable, the term “FULL” is placed into the table for legal range.

| Variable Name | Resolution | Legal Range<br />(min) | Legal Range<br />(max) | Software Segment |
| --- | --- | --- | --- | --- |
| <None> |  |  |  |  |

### User defined typedef definition/declaration

This section documents any user types uniquely used for the module.

| Typedef Name | Element Name | User Defined Type | Legal Range<br />(min) | Legal Range<br />(max) |
| --- | --- | --- | --- | --- |
| <None> |  |  |  |  |

# Constant Data Dictionary

## Calibration Constants

This section lists the calibrations used by the module.  For details on calibration constants, refer to the Data Dictionary for the application.

| Constant Name |
| --- |
| <None> |

## Program(fixed) Constants

### Embedded Constants

All embedded constants whose values are provided in Eng units will be evaluated to the equivalent counts by using the FPM_InitFixedPoint_m() macro within the #define statement.

#### Local

| Constant Name | Resolution | Units | Value |
| --- | --- | --- | --- |
| <None> |  |  |  |

#### Global

This section lists the global constants used by the module.  For details on global constants, refer to the Data Dictionary for the application.

| Constant Name |
| --- |
| <None> |

### Module specific Lookup Tables Constants

(This is for lookup tables (arrays) with fixed values, same name as other tables)

| Constant Name | Resolution | Value | Software Segment |
| --- | --- | --- | --- |
| <None> |  |  |  |

# Functions/Macros used by the Sub-Modules

## Library Functions / Macros

The library and functions / Macros that are called by the various sub modules are identified below,

<None>

## Data Hiding Functions

<None>

## Global Functions/Macros Defined by this Module

### Global Function #1

| Function Name | _uDiagGetLinkRegForFiqIsr_() | Type | Dir. | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- | --- |
| Arguments Passed | None |  |  |  |  |  |
| Return Value | Link Register as saved in top stack frame when executing an FIQ ISR | uint32 |  | FULL | FULL |  |

#### Description

The saved link register is at offset 0x5C from the top of the stack.  Load saved link register value to register R0 and return.

ldr	r0, [sp, #0x5C]

bx	lr

## Local Functions/Macros Used by this MDD only

None

# Software Module Implementation

## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but controlled by the RTE. After RTE initialization, the data in this table will contain these values.

| Data | Value |
| --- | --- |
| <None> |  |

## Initialization Functions

None

## Periodic Functions

None

## Fault Recovery Functions

None

## Shutdown Functions

None

## Interrupt Functions

None

## Serial Communication Functions

None

# Execution Requirements

## Execution Sequence of the Module

(Describe in words relevant details about the execution sequence of the different sub modules.)

## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design

| Function Name | Calling Frequency | System State(s) in which the function is called |
| --- | --- | --- |
| <None> |  |  |

## Execution Requirements for Serial Communication Functions

| Function Name | Sub-Module called by (Serial Comm Function Name) |
| --- | --- |
| <None> |  |

# Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in this module.

| Name of Sub Module | Software Segment |
| --- | --- |
| _uDiagGetLinkRegForFiqIsr_ | N/A |

## Local Functions

This table identifies the software segments for local functions identified in this module.

| Name of Local Function | Software Segment |
| --- | --- |
| None |  |

# Known Issues / Limitations With Design

None

# Revision Control Log

| Item # | Rev # | Change Description | Date | Author Initials |
| --- | --- | --- | --- | --- |
| 1 | 1.0 | Initial Revision | 6/6/2013 | KMC |
