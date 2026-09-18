---
title: "Battery Voltage Diagnostics"
description: "Converted from Battery_Voltage_Diagnostics.doc"
---

> **Source document:** `BVDiag/doc/Battery_Voltage_Diagnostics.doc`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: legacy Word document (`.doc`).

> **Note:** the original file is a legacy binary Word document (`.doc`) which cannot be converted with full fidelity in this environment. The text below was recovered automatically and may be out of order in places; tables and figures are not preserved. See the original file for the authoritative content.

bjbj$

## Module -- Battery Voltage

## High-Level Description

This module is responsible for applying voltage and time based hysteresis to the battery voltage to determine over voltage(B5) and low voltage faults(B0). Requirements for all these faults are detailed in SER. Also customer specific B1diagnostic is implemented.

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

CCLMSAActive_Cnt_lgc

NTCB1Enbl_Cnt_lgc

NTCB0Enbl_Cnt_lgc

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

BVDiag_LowSetInitBD_ms_M_u32p0

1ms/Cnt

BVDiag_LowClrInitBD_ms_M_u32p0

1ms/Cnt

BVDiag_OvSetInitBD_ms_M_u32p0

1ms/Cnt

BVDiag_OvClrInitBD_ms_M_u32p0

1ms/Cnt

BVDiag_UvSetInitBD_ms_M_u32p0

1ms/Cnt

BVDiag_UvClrInitBD_ms_M_u32p0

1ms/Cnt

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

k_OvDetect_Volts_u10p6

k_OvNotDetect_Volts_u10p6

k_OvDetect_ms_u16p0

k_OvNotDetect_ms_u16p0

k_LowNotDetect_Volts_u10p6

k_LowDetect_Volts_u10p6

k_LowDetect_ms_u16p0

k_LowNotDetect_ms_u16p0

k_MSALowNotDetect_Volts_u10p6

k_MSALowDetect_Volts_u10p6

k_MSALowDetect_ms_u16p0

k_MSALowNotDetect_ms_u16p0

k_BattDiagUvMax_Volt_u10p6

k_BattDiagUvMin_Volt_u10p6

k_UvNotDetect_ms_u16p0

k_UvDetect_ms_u16p0

k_BattUvRecMax_Volt_u10p6

## Program(fixed) Constants

## Embedded Constants

All embedded constants whose values are provided in Eng units will be evaluated to the equivalent counts by using the FPM_InitFixedPoint_m() macro within the #define statement.

## Local

## Constant Name

## Resolution

## Value

D_ABOVEMAX_CNT_U16

D_BELOWMIN_CNT_U16

D_INDEADBAND_CNT_U16

D_DIAGOV_CNT_U16

D_DIAGLOW_CNT_U16

## Global

This section lists the global constants used by the module. For details on global constants, refer to the Data Dictionary for the application.

## Constant Name

NTC_Num_OpVoltage

NTC_Num_OpVoltageOvrMax

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

Rte_Call_BVDiag_Per1_CP0_CheckpointReached()

Rte_Call_BVDiag_Per1_CP1_CheckpointReached()

Rte_IRead_BVDiag_Per1_CCLMSAActive_Cnt_lgc()

Rte_Call_SystemTime_GetSystemTime_mS_u32()

Rte_Call_SystemTime_DtrmnElapsedTime_mS_u16()

Rte_Call_SystemTime_GetSystemTime_mS_u32()

Rte_Call_SystemTime_DtrmnElapsedTime_mS_u16()

## Local Functions/Macros Used by this MDD only

(Note if they are defined in another source file, then reference the appropriate header file)

## The local functions/macros in this module are identified below,

## ApplyHysteresis()

## ControlTimers()

## Software Module Implementation

## Initialization Functions

Module state variables are initialized to 0 at start-up by RAM init.

## Periodic Functions

Per: BVDiag_Per1

## Design Rationale

## All customer SER

s describes same functionality for B0,B5.

B1 NTC is only for Chrysler.

## Program Flow Start

Rte_Call_BVDiag_Per1_CP0_CheckpointReached()

## Store Module Inputs to Local copies

BattVoltage_Volts_T_f32 = Rte_IRead_BVDiag_Per1_Batt_Volt_f32()

MSAActive_T_lgc = Rte_IRead_BVDiag_Per1_CCLMSAActive_Cnt_lgc()

NTCB1Enbl_Cnt_T_lgc = Rte_IRead_BVDiag_Per1_NTCB1Enbl_Cnt_lgc()

NTCB0Enbl_Cnt_T_lgc = Rte_IRead_BVDiag_Per1_NTCB0Enbl_Cnt_lgc()

## Perform Over and Low Voltage Diagnostics

EMBED Visio.Drawing.11

## Store Local copy of outputs into Module Outputs

None.

## Program Flow End

Rte_Call_BVDiag_Per1_CP1_CheckpointReached()

## Fault Recovery Functions

## Shutdown Functions

## Interrupt Functions

## Serial Communication Functions

## Local Function/Macro Definitions

If these are numerous and defined in a separate source file then reference the source file only.

## Control Timers

## Function Name

## ControlTimers

## Arguments Passed

BattVoltage_Volts_T_u10p6

u10p6_T

See DD1

CompareType_T_u16

UINT16

0x0011

0x0022

UpperCal_T_u10p6

u10p6_T

See DD1

LowerCal_T_u10p6

u10p6_T

See DD1

SetTimer_T_ptr

u32p0_T*

ClrTimer_T_ptr

u32p0_T*

SetTimer_ms_T_u16p0

u16p0_T

ClrTimer_ms_T_u16p0

u16p0_T

Option_T_u16

UINT16

0x0001

0x0002

## Return Value

Note 1

See data dictionary for input which corresponds to a calibration or global variable

## Description

This generic local function is used to control set and clear timers for the diagnostic functions as well as control flags used to indicate battery voltage is

for the application. Data is passed to indicate the following:

CompareType_T_u16:

Passed data to indicate the type of comparison to be made internally to the function (Above Max or Below Min). Used in a decision block within the function. Essentially, reverses the logic between an over voltage test (where below min is a normal operating point) and low voltage test (where above max is a normal operating point)

UpperCal_T_u10p6:

Voltage level calibration of the hysteresis (upper threshold).

LowerCal_T_u10p6:

Voltage level calibration of the hysteresis (lower threshold). Note: Lower cal must be <= Upper Cal.

SetTimer_T_ptr:

Pointer to the appropriate module specific 32-bit set timer under test (examples are set timer for over voltage, low voltage, battery Ok, etc.)

ClrTimer_T_ptr:

Pointer to the appropriate module specific 32-bit clear timer under test (examples are set timer for over voltage, low voltage, battery Ok, etc.)

SetTimer_ms_T_u16p0:

Calibration used for the time based hysteresis to set the condition. Note that the calibrations will differ for set timers for over voltage, low voltage, etc.

ClrTimer_ms_T_u16p0:

Calibration used for the time based hysteresis to clear the condition. Note that the calibrations will differ for set timers for over voltage, low voltage, etc.

Option_T_u16:

Identifies which function is being used to identify which set fault, clear fault functions to call, which battery voltage OK state is being checked, etc.

EMBED Visio.Drawing.11

## Apply Hysteresis

## Function Name

## ApplyHysteresis

## Arguments Passed

BattIn_T_u10p6

u10p6_T

See DD1

HighCal_T_u10p6

u10p6_T

See DD1

LowCal_T_u10p6

u10p6_T

See DD1

## Return Value

OutputZone_T_u16

UINT16

0x0011

0x0033

Note 1

See data dictionary for input which corresponds to a calibration or global variable

## Description

This local function is used to determine the next state for a voltage based hysteresis as applied to the battery voltage level. Data is passed to include the battery voltage, upper calibration and a lower calibration. The function returns the state of the battery voltage relative to the cals (either

## Above Max

## Below Min

## In Deadband

). Note that the design requires the upper cal to be larger than the lower cal for proper operation.

EMBED Visio.Drawing.11

## Execution Requirements

## Execution Sequence of the Module

(Describe in words relevant details about the execution sequence of the different sub modules.)

## Execution Rates for sub-modules called by the Scheduler

## This table serves as reference for the Scheduler design

## Function Name

## Task List

## Calling Frequency

## System State(s) in which the function is called

BVDiag_Per1

## Execution Requirements for Serial Communication Functions

## Function Name

## Sub-Module called by (Serial Comm Function Name)

## Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in this module.

## Name of Sub Module

## Software Segment

BVDiag_Per1()

RTE_AP_BVDIAG_APPL_CODE

## Local Functions

This table identifies the software segments for local functions identified in this module.

## Name of Sub Module

## Software Segment

## ControlTimers()

AP_BVDIAG_CODE

## ApplyHysteresis()

AP_BVDIAG_CODE

## Known Issues / Limitations With Design

B1,B4 faults are removed from BMW,K2XX SER.

## Revision Control Log

Item #

Rev #

## Change Description

## Author Initials

Initial AutoSAR release.

19-Oct-12

Updated to SER Rev BMW SER EPS24102912 Rev 011C (CUSTOMER VERSION).docx

18-Mar-2013

Updated to Implement B1 as per Chrysler LWR SER Ver 5G

11-Sep-13

Corrected anomaly allowing configurable enable of B1 fault from SrlComInput

14-Nov-13

## Jared

Configurable enable of B0 fault from SrlComInput

19-Aug-14

M. Story

## SOFTWARE MODULE DESIGN SPECIFICATION

Title:

## Battery Voltage

Gen II+ EPS

Revision:

Product:

Rev. Date:

14-Nov-1319-Aug-14

Group:

Originator:

## Jared Julien

Page:

## NUMPAGES

## Nexteer CONFIDENTIAL

S/W module design template, Rev 3.0a

wpieaZ

gdA8=

teYtY

pld`d`d`d`[

bIDATx^

}pV(YM@

4xQD/l

>$8TK4

;{gh{

{s`r(

^!ltE

BdI72-W

%*<y-;Z

Picture 1

IDATx^

>3====

ImT___MM

:{L!mo

74NZ{XG

\WzdHF

I2#--

p/~"<

Scc#k

-O&$W

UHH<1%YD

@#[CU

%;#\d

kWcc#

#:00@

.yqLB

sfs89

D-?"':

uh?wG

ej0-j

E=H:{1

~'`TN~

^2a``

'sVIK

9YdSD

ZQ`JU

rssiK#:.

t],8V

?~|eeeyy

TTT0-

E1%<;

## LKTpt

*K7U&-

^T~*W{h

-I L`

]SSSTT

}MMMCC

\vd''

QZ#H9

%Z3;e

4A//m

G@8dWL

_,;!S

42NQ?

iO@1$k

F^P!@

---M=

RR29//

544dw

3gd2U

OGooov%

## Root Entry

## Data

## WordDocument

## ObjectPool

_1469973230

## EPRINT

## CompObj

## Microsoft Visio Drawing

Visio 11.0 Shapes

Visio.Drawing.11

kzshz2

EMF+0@

EMF+*@

## ARIAL

## START

P>@F0?

## Arial

## START

EMF++@

*DCY2

EMF+*@

## BattVoltage

EMF++@

## Volts

EMF++@

## FloatToFixed

>@rP?

## FloatToFixed

EMF++@

## BattVoltage

EMF++@

## Volts

EMF++@

>pZ&@

EMF++@

EMF+*@

## ControlTimers

EMF++@

## BattVoltage

EMF++@

## Volts

EMF++@

## BELOWMIN

EMF++@

## OvDetect

EMF++@

## Volts

EMF++@

## OvNotDetect

EMF++@

## Volts

EMF++@

## BVDiag

EMF++@

## OvSetInitBD

EMF++@

## BVDiag

EMF++@

## OvClrInitBD

EMF++@

## OvDetect

EMF++@

## OvNotDetect

EMF++@

## IAGOV

EMF++@

## NTCB

@~c? 3

## NTCB

EMF++@

## Enbl

EMF++@

## BKZYDU

## CKZYDU

|4DUU

## BKZYD

## BKZYDUU

## CKZYDU

EMF+*@

|4D6@

## ControlTimers

EMF++@

|4D6@

EMF++@

|4D6@

## BattVoltage

EMF++@

|4D6@

EMF++@

|4D6@

## Volts

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

## ABOVEMAX

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

## LowNotDetect

EMF++@

|4D6@

EMF++@

|4D6@

## Volts

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

## LowDetect

EMF++@

|4D6@

EMF++@

|4D6@

## Volts

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

## BVDiag

%M?@ ,?

## BVDiag

EMF++@

|4D6@

EMF++@

|4D6@

## LowSetInitBD

%M?@%

## LowSetInitBD

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

%M?@t

EMF++@

|4D6@

EMF++@

|4D6@

## BVDiag

Go?@N/?

## BVDiag

EMF++@

|4D6@

EMF++@

|4D6@

## LowClrInitBD

Go?@5

## LowClrInitBD

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

## LowDetect

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@

|4D6@

EMF++@
