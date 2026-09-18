---
title: "EOTDampingFirewall Module Design Document"
description: "Converted from EOTDampingFirewall_MDD.doc"
---

> **Source document:** `EtDmpFw/doc/EOTDampingFirewall_MDD.doc`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: legacy Word document (`.doc`).

> **Note:** the original file is a legacy binary Word document (`.doc`) which cannot be converted with full fidelity in this environment. The text below was recovered automatically and may be out of order in places; tables and figures are not preserved. See the original file for the authoritative content.

bjbjW

## Module

## EOTDampingFirewall

## High-Level Description

This MDD describes the summation of all assist and limit terms used in an Electric Power Steering application.

## Figures

## Diagram

## Component Diagram

## Variable Data Dictionary

For details on module input / output variable, refer to the Data Dictionary for the application. Input / output variable names are listed here for reference.

## Module Inputs

## Module Outputs

AssistEOTDamping_MtrNm_f32

EOTDampingLtd_MtrNm_f32

CRFMtrVel_MtrRadpS_f32

HandwheelAuthority_Uls_f32

HandwheelPosition_HwDeg_f32

Vehicle_Speed_Kph_f32

EOTDisable_Cnt_lgc

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

EOTDmpFWActvLtd_MtrNm_D_f32

## Single Precision Float

ETDMPFW_START_SEC_VAR_CLEARED_32

EOTDmpFWInActvLtd_MtrNm_D_f32

## Single Precision Float

ETDMPFW_START_SEC_VAR_CLEARED_32

UprBndActive_MtrNm_D_f32

## Single Precision Float

ETDMPFW_START_SEC_VAR_CLEARED_32

LwrBndActive_MtrNm_D_f32

## Single Precision Floating Point

ETDMPFW_START_SEC_VAR_CLEARED_32

EOTDmpFWActvRegion_Cnt_D_lgc

## FALSE

ETDMPFW_START_SEC_VAR_CLEARED_BOOLEAN

EOTDmpFWHWAuth_Cnt_D_lgc

## FALSE

ETDMPFW_START_SEC_VAR_CLEARED_BOOLEAN

EOTDmpFWMode_Cnt_M_u08

Uint8

ETDMPFW_START_SEC_VAR_CLEARED_08

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

k_MinRackTrvl_HwDeg_u12p4

t2_EOTPosDepDmpTblX_HwDeg_u12p4

k_EOTDynConf_Uls_u8p8

t_EOTDmpFWActiveBoundX_MtrRadpS_s11p4

t2_EOTDmpFWActiveBoundY_MtrNm_s7p8

k_EOTDmpFWInactiveLim_MtrNm_f32

t_EOTDmpFWVehSpd_Kph_u9p7

## Program(fixed) Constants

## Embedded Constants

All embedded constants whose values are provided in Eng units will be evaluated to the equivalent counts by using the FPM_InitFixedPoint_m() macro within the #define statement.

## Local

## Constant Name

## Resolution

## Units

## Value

D_INACTIVEREGION_ULS_U08

## Unitless

D_ACTIVEREGION_ULS_U08

## Unitless

D_FIREWALLLDISABLED_ULS_U08

## Unitless

## Global

This section lists the global constants used by the module. For details on global constants, refer to the Data Dictionary for the application.

## Constant Name

D_ZERO_ULS_F32

D_ONE_ULS_F32

D_MTRTRQCMDHILMT_MTRNM_F32

D_MTRTRQCMDLOLMT_MTRNM_F32

BC_ETDMPFW_FAULTINJECTIONPOINT

STD_ON

FLTINJ_EOTDAMPING_ETDMPFW

D_NEGONE_CNT_S16

D_FALSE_CNT_LGC

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

BilinearXYM_s16_s16Xs16YM_Cnt()

FPM_FloatToFixed_m()

## Data Hiding Functions

## Global Functions/Macros Defined by this Module

## Local Functions/Macros Used by this MDD only

## Software Module Implementation

## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but controlled by the RTE. After RTE initialization, the data in this table will contain these values.

## Value

Rte_InitValue_AssistEOTDamping_MtrNm_f32

Rte_InitValue_CRFMtrVel_MtrRadpS_f32

Rte_InitValue_EOTDampingLtd_MtrNm_f32

Rte_InitValue_HandwheelAuthority_Uls_f32

Rte_InitValue_HandwheelPosition_HwDeg_f32

## Initialization Functions

## Periodic Functions

Per: EtDmpFw_Per1

## Design Rationale

## Program Flow Start

Rte_Call_EtDmpFw_Per1_CP0_CheckpointReached()

## Store Module Inputs to Local copies

## Local Copy

## Module Input Name

AsstEOTDamping_MtrNm_T_f32

Rte_IRead_EtDmpFw_Per1_AssistEOTDamping_MtrNm_f32

HandwheelPosition_HwDeg_T_f32

Rte_IRead_EtDmpFw_Per1_HandwheelPosition_HwDeg_f32

HandwheelAuthority_Uls_T_f32

Rte_IRead_EtDmpFw_Per1_HandwheelAuthority_Uls_f32

CRFMtrVel_MtrRadpS_T_f32

Rte_IRead_EtDmpFw_Per1_CRFMtrVel_MtrRadpS_f32

VehicleSpeed_Kph_T_f32

Rte_IRead_EtDmpFw_Per1_Vehicle_Speed_Kph_f32

EOTDisable_Cnt_T_lgc

Rte_IRead_EtDmpFw_Per1_EOTDisable_Cnt_lgc

MECCounter_Cnt_T_enum

Rte_IRead_EtDmpFw_Per1_MEC_Counter_Cnt_enum

VehicleSpeed_Kph_T_u9p7

FPM_FloatToFixed_m(VehicleSpeed_Kph_T_f32, u9p7_T)

(Processing of function)

EMBED Visio.Drawing.11

## Store Local copy of outputs into Module Outputs

## Local Copy

## Module Output Name

LimitedEOTDamping_MtrNm_T_f32

Rte_IWrite_EtDmpFw_Per1_EOTDampingLtd_MtrNm_f32

## Program Flow End

Rte_Call_EtDmpFw_Per1_CP1_CheckpointReached()

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

EtDmpFw_Per1

## Execution Requirements for Serial Communication Functions

## Function Name

## Sub-Module called by (Serial Comm Function Name)

## Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in this module.

## Name of Sub Module

## Software Segment

EtDmpFw_Per1

RTE_START_SEC_AP_ETDMPFW_APPL_CODE

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

6-Sep-12

## Added watchdog checkpoints

16-Sept-12

## Corrected for static variable software section

19 Sep 12

## Selva

Updated as per FDDVer002, FaultInjectionPoint added to AsstEOTDamping_MtrNm_T_f32 signal

29 Jan 13

## Selva

Updated to SF-27 v003

16-May-13

Removed calibration k_EOTDmpFWInputLim_MtrNm_f32 per anomaly 6850

21-Aug-14

## Updated as per Unit Test Findings

27-Aug-14

KPIT_SM

## SOFTWARE MODULE DESIGN SPECIFICATION

Title:

## EOTDamping Firewall

Gen II+ EPS

Revision:

Product:

Rev. Date:

27-Aug-1421-Aug-14

Group:

Originator:

## Kevin Smith

Page:

## NUMPAGES

## Nexteer

## CONFIDENTIAL

S/W module design template, Rev 2.2b+

gdD-R

(gytmV

gdtDk

`\XTM

(gytmV

gdtDk

(gytmV

gdtDk

(gytmV

gdtDk

(gytmV

yhd`TPTP`IP

ytv:M

wsoh[

~zvzvzrngz

gdaq8

~zrnc[rWrnL

gd'Bb

_S_nDn

gdv:M

gd H=

|xtxlhlxlx[

gd H=

yt H=

Picture 1

E<h@}

IDATx^

VPK!)

PF`Na2

N(7bG

>fj7#

ZC{vD)

9f2%k

`/wora

D3CDoP*

x4lFp

:L4.A`u

'P"LR

I1cj]

}.xYt

^e^Ut

vWy\5

)=Qj!L=pO

MV)T{

}W7]W

BRh'_j

S1::NB ,O

FY9cF

okMltEb

^?)fL

I4aB`$

lMWwc

k.aIu

OO@-LB

-fLja

8$LvW^3{Jl

j}IHR

T:K]g

&$Ps_

}w'+*

(gytmV

ytv:M

## Root Entry

## Data

## WordDocument

## ObjectPool

_1470650462

## EPRINT

## CompObj

## Microsoft Visio Drawing

Visio 11.0 Shapes

Visio.Drawing.11

Owen Tosh (nzx5j

EMF+0@

EMF+*@

## ARIAL

## Start

## Arial

## Start

EMF++@

EMF+*@

## EOTDamping

"R>@w

"R> P

## EOTDamping

EMF++@

## MtrNm

EMF++@

## AsstEOTDamping

"R>@%W@

## AsstEOTDamping

EMF++@

## MtrNm

EMF++@

EMF+*@

## EOTDmpFWX

=@s,?

## EOTDmpFWX

EMF++@

## HwDeg

EMF++@

## MinRackTrvl

EMF++@

## HwDeg

=0R/@

## HwDeg

EMF++@

## EOTPosDepDmpTblX

fv>@>

fv> '

## EOTPosDepDmpTblX

EMF++@

## HwDeg

EMF++@

EMF+*@

## UprBndActive

EMF++@

## MtrNm

EMF++@

## BilinearXYM

=0W!@

## BilinearXYM

EMF++@

## VehicleSpeed

EMF++@

## CRFMtrVel

EMF++@

## MtrRadpS

EMF++@

## EOTDmpFWVehSpd

}> .y@

## EOTDmpFWVehSpd

EMF++@

## TableSize

EMF++@

## EOTDmpFWVehSpd

EMF++@

## EOTDmpFWActiveBoundX

>@pt@

## EOTDmpFWActiveBoundX

EMF++@

## MtrRadpS

EMF++@

## EOTDmpFWActiveBoundY

EMF++@

## MtrNm

EMF++@

## TableSize

?0e7@@

## TableSize

EMF++@

## EOTDmpFWActiveBoundX

EMF++@

## MtrRadpS

EMF++@

EMF+*@

## LwrBndActive

EMF++@

## MtrNm

EMF++@

## BilinearXYM

=0W!@

## BilinearXYM

EMF++@

## VehicleSpeed

EMF++@

## NEGONE

EMF++@

## CRFMtrVel

EMF++@

## MtrRadpS

EMF++@

## EOTDmpFWVehSpd

EMF++@

## TableSize

EMF++@

## EOTDmpFWVehSpd

EMF++@

## EOTDmpFWActiveBoundX

>@pt@

## EOTDmpFWActiveBoundX

EMF++@

## MtrRadpS

EMF++@

## EOTDmpFWActiveBoundY

EMF++@

## MtrNm

EMF++@

## TableSize

?0e7@@

## TableSize

EMF++@

## EOTDmpFWActiveBoundX

EMF++@

## MtrRadpS

EMF++@

EMF+*@

B<D6@

## Contd

EMF++@

EMF+*@

EMF++@

## HandwheelPosition

EMF++@

## HwDeg

EMF++@

## EOTDmpFWX

EMF++@

## HwDeg

EMF++@

EMF+*@

## LwrBndActive

EMF++@

## MtrNm

EMF++@

## UprBndActive

EMF++@

## MtrNm

>@%R@

>@}V@

## MtrNm

EMF++@

EMF+*@

## EOTDmpFWActvRegion

EMF++@

fv>@^L?

EMF++@

## TRUE

fv>`]

## TRUE

EMF++@

EMF+*@

## EOTDmpFWActvRegion

EMF++@

## FALSE

fv>@N_?

## FALSE

EMF++@

EMF+*@

EMF++@

## HandwheelAuthority

EMF++@

## FixedToFloat

Z>@'L?

## FixedToFloat

EMF++@

## EOTDynConf

EMF++@

EMF+*@

## EOTDmpFWHWAuth

EMF++@

## TRUE

fv>@nf?

## TRUE

EMF++@

EMF+*@

## EOTDmpFWHWAuth

EMF++@

## FALSE

EMF++@

EMF+*@

EMF++@

EMF+*@

EMF++@

CB[-D

## Ca -D

C/c*D

EMF+*@

EMF++@

B/c*D

EMF+*@

EMF++@

EMF+*@

## ARIAL

## Arial

EMF++@

## ETDMPFW

EMF++@

## FAULTINJECTIONPOINT

EMF++@

EMF+*@

## ARIAL

## Arial

uSv_uSv

EMF++@

EMF+*@

.pB6@

EMF++@

.pB6@

EMF++@

.pB6@

## Call

EMF++@

.pB6@

EMF++@

.pB6@

## FaultInjection

EMF++@

.pB6@

EMF++@

.pB6@

## SCom

EMF++@

.pB6@

EMF++@

.pB6@

EMF++@

.pB6@

## Injection

EMF++@

.pB6@

EMF++@

.pB6@

EMF++@

.pB6@

## AsstEOTDamping

EMF++@

.pB6@

EMF++@

.pB6@

## MtrN

EMF++@

.pB6@

EMF++@

.pB6@

EMF++@

.pB6@

EMF++@

.pB6@

EMF++@

.pB6@

EMF++@

.pB6@

EMF++@

.pB6@

EMF++@

.pB6@

## FLTINJ

EMF++@

.pB6@

EMF++@

.pB6@

## EOTDAMPING

EMF++@

.pB6@

EMF++@

.pB6@

## ETDMPFW

EMF++@

.pB6@

EMF++@

EMF+*@

EMF++@

EMF+*@

CRFMtrVel@

## CRFMtrVel

EMF++@

## MtrRadpS

EMF++@

## FloatToFixed

f^>@N^?

## FloatToFixed

EMF++@

## CRFMtrVel

f^>@~

## CRFMtrVel

EMF++@

## MtrRadpS

f^>p4

f^>0.

## MtrRadpS

EMF++@

EMF+*@

KrC6@

## EOTDmpFWX
