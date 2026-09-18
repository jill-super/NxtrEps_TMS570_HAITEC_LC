---
title: "Limiter Conditioning Module Design Document"
description: "Converted from Limiter_Conditioning_MDD.doc"
---

> **Source document:** `LmtCod/doc/Limiter_Conditioning_MDD.doc`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: legacy Word document (`.doc`).

> **Note:** the original file is a legacy binary Word document (`.doc`) which cannot be converted with full fidelity in this environment. The text below was recovered automatically and may be out of order in places; tables and figures are not preserved. See the original file for the authoritative content.

## Module

## Limiter Conditioning

## High-Level Description

This MDD describes the summation of all assist and limit terms used in an Electric Power Steering application.

## Figures

## Diagram

## Component Diagram

## Variable Data Dictionary

For details on module input / output variable, refer to the Data Dictionary for the application. Input / output variable names are listed here for reference.

## Module Inputs

## Module Outputs

AssistEOTGain_Uls_f32

EOTGainLtd_Uls_f32

AssistEOTLimit_MtrNm_f32

EOTLimitLtd_MtrNm_f32

AssistStallLimit_MtrNm_f32

OutputRampMultLtd_Uls_f32

AssistVehSpdLimit_MtrNm_f32

StallLimitLtd_MtrNm_f32

OutputRampMult_Uls_f32

ThermalLimitLtd_MtrNm_f32

ThermalLimit_MtrNm_f32

VehSpdLimitLtd_MtrNm_f32

VehicleSpeed_Kph_f32

CCLTrqRamp_Uls_f32

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

CurrAssistEOTGain_Uls_M_f32

## Single Precision Float

LMTCOD_START_SEC_VAR_CLEARED_32

CurrOutputRampMult_Uls_M_f32

## Single Precision Float

LMTCOD_START_SEC_VAR_CLEARED_32

CurrAssistEOTLimit_MtrNm_M_f32

## Single Precision Float

LMTCOD_START_SEC_VAR_CLEARED_32

CurrAssistStallLimit_MtrNm_M_f32

## Single Precision Floating Point

LMTCOD_START_SEC_VAR_CLEARED_32

CurrAssistVehSpdLimit_MtrNm_M_f32

## Single Precision Floating Point

LMTCOD_START_SEC_VAR_CLEARED_32

CurrThermalLimit_MtrNm_M_f32

## Single Precision Floating Point

LMTCOD_START_SEC_VAR_CLEARED_32

CCLTrqRamp_Uls_M_f32

## Single Precision Floating Point

LMTCOD_START_SEC_VAR_CLEARED_32

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

k_GainDecSlew_UlspS_f32

k_TorqueDecSlew_MtrNmpS_f32

t_GainIncSlewTblX_Kph_u9p7[2]

t_GainIncSlewTblY_UlspS_u9p7[2]

t_TorqueIncSlewTblX_Kph_u9p7[2]

t_TorqueIncSlewTblY_MtrNmpS_u13p3[2]

k_CCLTrqRampIncSlew_UlspS_f32

## Program(fixed) Constants

## Embedded Constants

All embedded constants whose values are provided in Eng units will be evaluated to the equivalent counts by using the FPM_InitFixedPoint_m() macro within the #define statement.

## Local

## Constant Name

## Resolution

## Units

## Value

## Global

This section lists the global constants used by the module. For details on global constants, refer to the Data Dictionary for the application.

## Constant Name

D_2MS_SEC_F32

FLTINJ_ASSTEOTGAIN_LMTCOD

FLTINJ_OUTPUTRAMPMULT_LMTCOD

FLTINJ_ASSTEOTLIMIT_LMTCOD

BC_LMTRCONDN_FAULTINJECTIONPOINT

## Module specific Lookup Tables Constants

(This is for lookup tables (arrays) with fixed values, same name as other tables)

## Constant Name

## Resolution

## Value

## Software Segment

## Functions/Macros used by the Sub-Modules

## Library Functions / Macros

The library and functions / Macros that are called by the various sub modules are identified below,

Limit_m()

Sign_f32_m()

Min_m()

Max_m()

Abs_f32_m()

IntplVarXY_u16_u16Xu16Y_Cnt()

FPM_FloatToFixed_m()

FPM_FixedToFloat_m()

## Data Hiding Functions

## Global Functions/Macros Defined by this Module

## Local Functions/Macros Used by this MDD only

## Software Module Implementation

## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but controlled by the RTE. After RTE initialization, the data in this table will contain these values.

## Value

Rte_InitValue_AssistEOTGain_Uls_f32

Rte_InitValue_AssistEOTLimit_MtrNm_f32

Rte_InitValue_AssistStallLimit_MtrNm_f32

Rte_InitValue_AssistVehSpdLimit_MtrNm_f32

Rte_InitValue_OutputRampMult_Uls_f32

Rte_InitValue_ThermalLimit_MtrNm_f32

Rte_InitValue_EOTGainLtd_Uls_f32

Rte_InitValue_EOTLimitLtd_MtrNm_f32

Rte_InitValue_OutputRampMultLtd_Uls_f32

Rte_InitValue_StallLimitLtd_MtrNm_f32

Rte_InitValue_ThermalLimitLtd_MtrNm_f32

Rte_InitValue_VehSpdLimitLtd_MtrNm_f32

Rte_InitValue_VehicleSpeed_Kph_f32

Rte_InitValue_CCLTrqRamp_Uls _f32

## Initialization Functions

## Periodic Functions

Per: LmtCod_Per1

## Design Rationale

This function provides a layer of protection from erroneous signals feeding into SF-04 Sum & Limit. It is applied primarily to

## Limiting

signals that serve to reduce motor torque command under certain operating conditions. This function can prevent step response or

toggling

behavior that might cause undesirable vehicle feel. It includes capability of fault injection at some inputs to facilate tuning. See FDD SF-38 for more details.

## Program Flow Start

Rte_Call_LmtCod_Per1_CP0_CheckpointReached()

## Store Module Inputs to Local copies

## Local Copy

## Module Input Name

AssistEOTGain_Uls_T_f32

Rte_IRead_LmtCod_Per1_AssistEOTGain_Uls_f32

AssistEOTLimit_MtrNm_T_f32

Rte_IRead_LmtCod_Per1_AssistEOTLimit_MtrNm_f32

AssistStallLimit_MtrNm_T_f32

Rte_IRead_LmtCod_Per1_AssistStallLimit_MtrNm_f32

AssistVehSpdLimit_MtrNm_T_f32

Rte_IRead_LmtCod_Per1_AssistVehSpdLimit_MtrNm_f32

OutputRampMult_Uls_T_f32

Rte_IRead_LmtCod_Per1_OutputRampMult_Uls_f32

ThermalLimit_MtrNm_T_f32

Rte_IRead_LmtCod_Per1_ThermalLimit_MtrNm_f32

VehicleSpeed_Kph_T_f32

Rte_IRead_LmtCod_Per1_VehicleSpeed_Kph_f32

_CCLTrqRamp_Uls _T_f32

Rte_IRead_LmtCod_Per1_CCLTrqRamp_Uls _f32

(Processing of function)

EMBED Visio.Drawing.11

## Store Local copy of outputs into Module Outputs

## Local Copy

## Module Output Name

CurrAssistEOTGain_Uls_M_f32

Rte_IWrite_LmtCod_Per1_EOTGainLtd_Uls_f32

CurrAssistEOTLimit_MtrNm_M_f32

Rte_IWrite_LmtCod_Per1_EOTLimitLtd_MtrNm_f32

FinalCurrOutputRampMult_Uls_T_f32CurrOutputRampMult_Uls_M_f32

Rte_IWrite_LmtCod_Per1_OutputRampMultLtd_Uls_f32

CurrAssistStallLimit_MtrNm_M_f32

Rte_IWrite_LmtCod_Per1_StallLimitLtd_MtrNm_f32

CurrThermalLimit_MtrNm_M_f32

Rte_IWrite_LmtCod_Per1_ThermalLimitLtd_MtrNm_f32

CurrAssistVehSpdLimit_MtrNm_M_f32

Rte_IWrite_LmtCod_Per1_VehSpdLimitLtd_MtrNm_f32

## Program Flow End

Rte_Call_LmtCod_Per1_CP1_CheckpointReached()

## Fault Recovery Functions

## Shutdown Functions

## Interrupt Functions

## Serial Communication Functions

## Execution Requirements

## Execution Sequence of the Module

## Execution Rates for sub-modules called by the Scheduler

## This table serves as reference for the Scheduler design

## Function Name

## Calling Frequency

## System State(s) in which the function is called

LmtCod_Per1

## Execution Requirements for Serial Communication Functions

## Function Name

## Sub-Module called by (Serial Comm Function Name)

## Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in this module.

## Name of Sub Module

## Software Segment

LmtCod_Per1()

RTE_START_SEC_AP_LMTCOD_APPL_CODE

## Local Functions

This table identifies the software segments for local functions identified in this module.

## Name of Sub Module

## Software Segment

## Known Issues / Limitations With Design

INLINE functions defined in globalmacro.h are not unittested.

## Revision Control Log

Item #

Rev #

## Change Description

## Author Initials

## Document creation for component based design process

28-Aug-12

## Check points corrected

23-Sep-12

## Selva

Update to FDD SF38 v002

CR8292

17-May-13

Update to FDD SF38 v003

09-July-13

## Selva

## Changed the init value of

## CCLTrqSlew

## SOFTWARE MODULE DESIGN SPECIFICATION

Title:

## Limiter Conditioning

Gen II+ EPS

Revision:

Product:

Rev. Date:

17-May-13

10-Jul-13

Group:

Originator:

Selva Sengottaiyan(rz3h1n)

Page:

## NUMPAGES

## Nexteer

## CONFIDENTIAL

S/W module design template, Rev 2.2b+

gdD-R

|pl]pQpEpEp]

gdD-R

gdtDk

hd`YUIE9IE

gdtDk

|xgYHD

ytv:M

gdR0H

}yuyuynjnyfb^bfbfyWSWyI

gdaq8

qfb[WH>,

vlhdZMZMF5

mfb^Wb

gdv:M

~zvrv~hbhWhbhbhWh~Q~

IDATx^

xa\'O

5F4b(=

))Vry

A.e&\C2

{b4k[

$7V!P

\r dW,?

B?+"o

rD`Z9V

+m>c:

KY .g

5,^i/*n

"~Ufk

^.O %.@%

6cILC=Q

nL3:sk

yIDATx^

H:ZF4

~Owv:gY

F 0i7

UjJd*

frfo3

## NTBUM

8N>GO

*xGTh

,P^Q#

FXPm9Y

3]5y,

=!V`cG

;V/iQ

";Vhy

@@ `*=

[25Kct

G`\>1

gcQw4

OH{O/v,

ytv:M

## Root Entry

## Data

## WordDocument

## ObjectPool

_1434871354

## EPRINT

## CompObj

## Microsoft Visio Drawing

Visio 11.0 Shapes

Visio.Drawing.11

wz7x3j

EMF+0@

#NC)\

EMF+*@

## ARIAL

## True

## Arial

## True

EMF++@

EMF+*@

EMF++@

=@.p?

EMF++@

## LMTCOD

m>@L(?

## LMTCOD

EMF++@

## FAULTINJECTIONPOINT

EMF++@

EMF+*@

BA'3C!

## False

EMF++@

EMF+*@

## Start

EMF++@

EMF+*@

k`D6@

## CurrThermalLimit

= \&@

=PZ7@

## CurrThermalLimit

EMF++@

k`D6@

EMF++@

k`D6@

## MtrNm

=`!I@

## MtrNm

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

## Limit

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

## ThermalLimit

EMF++@

k`D6@

EMF++@

k`D6@

## MtrNm

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

## CurrThermalLimit

}>pLd@

}>0^o@

## CurrThermalLimit

EMF++@

k`D6@

EMF++@

k`D6@

## MtrNm

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

## TorqueDecSlew

EMF++@

k`D6@

EMF++@

k`D6@

## MtrNmpS

>P:)@

## MtrNmpS

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

>`Xr@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

## CurrThermalLimit

EMF++@

k`D6@

EMF++@

k`D6@

## MtrNm

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

## TorqueIncSlew

? (@@

## TorqueIncSlew

EMF++@

k`D6@

EMF++@

k`D6@

## MtrNmpS

?0?`@@

## MtrNmpS

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

EMF++@

k`D6@

) ))

EMF++@

EMF+*@

## CurrAssistEOTGain

EMF++@

## Limit

EMF++@

## AssistEOTGain

EMF++@

## CurrAssistEOTGain

= J~@

## CurrAssistEOTGain

EMF++@

## GainDecSlew

EMF++@

## UlspS

>P6*@

>pM3@

## UlspS

EMF++@

## CurrAssistEOTGain

EMF++@

## GainIncSlew

EMF++@

## UlspS

EMF++@

) ))

EMF++@

k*^#k*^#

EMF+*@

## CurrOutputRampMult

9>@m>?

9>@TF?

## CurrOutputRampMult

EMF++@

## Limit

EMF++@

## OutputRampMult

EMF++@

## CurrOutputRampMult

EMF++@

## GainDecSlew

EMF++@

## UlspS

>P6*@

>pM3@

## UlspS

EMF++@

## CurrOutputRampMult

EMF++@

## GainIncSlew

> _F@

## GainIncSlew

EMF++@

## UlspS

EMF++@

) ))

EMF++@

+:D{t

EMF+*@

## CurrAssistEOTLimit

=pM;@

=P.E@

## CurrAssistEOTLimit

EMF++@

## MtrNm

EMF++@

## Limit

EMF++@

## AssistEOTLimit

EMF++@

## MtrNm

EMF++@

## CurrAssistEOTLimit

}>0vg@

}>0Vq@
