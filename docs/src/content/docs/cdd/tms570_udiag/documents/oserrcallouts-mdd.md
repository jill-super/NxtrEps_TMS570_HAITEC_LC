---
title: "OsErrCallouts Module Design Document"
description: "Converted from OsErrCallouts_MDD.docx"
---

> **Source document:** `TMS570_uDiag/doc/OsErrCallouts_MDD.docx`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: Word document (`.docx`, 90 paragraphs, 13 tables, 0 embedded figures).

**Author:** Jeremy Warmbier;Kathleen Creager **Last saved by:** Creager, Kathleen **Revision:** 12

---

# High-Level Description

OsErrCallouts provides the error hook functions ErrorHook() and ProtectionHook() to provide diagnostic information for certain errors that result in calls to these hooks.

# Figures

## Diagram – Function Data Sharing

No Shared Data

# Variable Data Dictionary

For details on module input / output variable, refer to the Data Dictionary for the application.  Input / output variable names are listed here for reference.

(Note: Full variable names required in table.)

(Note: All global variables including End Of Line data used should be shown here)

| Module Inputs | Module Outputs | Module Outputs |
| --- | --- | --- |
| None | None |  |

## Module Internal Variables

This section identifies the name, range and resolutions for module specific data created by this module.  If there are no range restrictions on the variable, the term “FULL” is placed into the table for legal range.

| Variable Name | Resolution | Legal Range<br />(min) | Legal Range<br />(max) | Software Segment |
| --- | --- | --- | --- | --- |
| None |  |  |  |  |

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
| None |  |  |  |

#### Global

This section lists the global constants used by the module.  For details on global constants, refer to the Data Dictionary for the application.

| Constant Name |
| --- |
| UNUSEDINTERRUPT |
| STACKOVERWRITE |
| MPUVIOLATION |
| osdErrSOStackOverflow |
| osdErrYOStackOverflow |
| osdErrUEUnhandledException |

### Module specific Lookup Tables Constants

(This is for lookup tables (arrays) with fixed values, same name as other tables)

| Constant Name | Resolution | Value | Software Segment |
| --- | --- | --- | --- |
| <None> |  |  |  |

# Functions/Macros used by the Sub-Modules

## Library Functions / Macros

The library and functions / Macros that are called by the various sub modules are identified below,

RednRpdShtdn()

## Data Hiding Functions

OSErrorGetosCANError()

## Global Functions/Macros Defined by this Module

### Global Function #1

| Function Name | ErrorHook | Type | Dir. | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- | --- |
| Arguments Passed | ErrorCode | StatusType |  | N/A | N/A |  |
| Return Value | N/A |  |  |  |  |  |

#### Design Rationale

When the error was an unhandled exception, reset with a reset cause indicating unexpected interrupt.  Currently does no handling of other errors.

#### Description

### Global Function #2

| Function Name | ProtectionHook | Type | Dir. | Min | Max | UTP Tol. |
| --- | --- | --- | --- | --- | --- | --- |
| Arguments Passed | ErrorCode | StatusType |  | N/A | N/A |  |
| Return Value | <has return value defined but function does not return> | ProtectionReturnType |  | PRO_SHUTDOWN | PRO_SHUTDOWN |  |

#### Design Rationale

When the protection violation was a stack fault, reset with a reset cause of STACKOVERWRITE.  For any other protection violation, reset with a reset cause of MPUVIOLATION.

#### Description

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

None.

# Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in this module.

| Name of Sub Module | Software Segment |
| --- | --- |
| ErrorHook | APPLCB_CODE |
| ProtectionHook | APPLCB_CODE |

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
| 1 | 1.0 | Initial Revision | 6/26/2013 | KMC |
