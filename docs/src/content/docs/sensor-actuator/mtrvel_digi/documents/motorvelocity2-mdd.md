---
title: "MotorVelocity2 Module Design Document"
description: "Converted from MotorVelocity2_MDD.doc"
---

> **Source document:** `MtrVel_Digi/doc/MotorVelocity2_MDD.doc`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: legacy Word document (`.doc`).

> **Note:** the original file is a legacy binary Word document (`.doc`) which cannot be converted with full fidelity in this environment. The text below was recovered automatically and may be out of order in places; tables and figures are not preserved. See the original file for the authoritative content.

## Module -- Motor Velocity

## High-Level Description

## Figures

## Diagram

## Function Data Sharing

This diagram shows all data that is shared between functions within the module.

## No Shared Data

## Diagram

## MtrVel

This diagram describes the functional characteristics and data flow of a given function.

## Variable Data Dictionary

For details on module input / output variable, refer to the Data Dictionary for the application. Input / output variable names are listed here for reference.

(Note: Full variable names required in table.)

(Note: All global variables including End Of Line data used should be shown here)

## Module Inputs (Global Variable Name)

## Module Outputs (Global Variable Name)

AsstAssemblyPolarity _Cnt_s08

SysCDiagMtrVelMRF_MtrRadpS_f32

HandwheelVel_HwRadpS_f32

SysCDiagHwVel_HwRadpS_f32

MotorVelMRF_MtrRadpS_f32

CumMechMtrPosMRF_Deg_f32

MechMtrPos1Timestamp _uS_u32MechMtrPos1Timestamp_USec_u32

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

MtrVel2_SysCMtrVelMRF_MtrRadpS_M_f32

## Single Precision Floating Point

-1350

MTRVEL2_START_SEC_VAR_CLEARED_32

MtrVel2_SysCHwVelCRF_HwRadpS_M_f32

## Single Precision Floating Point

MTRVEL2_START_SEC_VAR_CLEARED_32

MtrVel2_SysCMtrVelDiffAcc_Cnt_M_u16

MTRVEL2_START_SEC_VAR_CLEARED_16

MtrVel2_SysCHwVelDiffAcc_Cnt_M_u16

MTRVEL2_START_SEC_VAR_CLEARED_16

MtrVel2_PrevSysCDiagCumMtrPos_Rad_M_f32

## Single Precision Floating Point

-6.283185307164

6.283185307164

MTRVEL2_START_SEC_VAR_CLEARED_32

MtrVel2_SysCMtrVelCorrLimDiff_MtrRadpS_D_f32

## Single Precision Floating Point

MTRVEL2_START_SEC_VAR_CLEARED_32

MtrVel2_SysCHwVelCorrLimDiff_HwRadpS_D_f32

## Single Precision Floating Point

MTRVEL2_START_SEC_VAR_CLEARED_32

* Note: These ranges are based on the range of the normalized sine and cosine global inputs, which in turn are based on the maximum amount of signal variation that can be caused by temperature changes on the MSB signals.

## User defined typedef definition/declaration

This section documents any user types uniquely used for the module.

## Typedef Name

## Element Name

## User Defined Type

## Legal Range

(min)

## Legal Range

(max)

(Name given for the user defined typdef of type struct/union)

(Variable name qualified similar to all other variables)

as other variables

## Constant Data Dictionary

## Calibration Constants

This section lists the calibrations used by the module. For details on calibration constants, refer to the Data Dictionary for the application.

## Constant Name

k_GearRatio_Uls_f32

k_MtrVelCorrLim_Cnt_Str

k_HwVelCorrLim_Cnt_Str

k_MtrVelCorrLim_MtrRadpS_f32

k_HwVelCorrLim_HwRadpS_f32

## Program(fixed) Constants

## Embedded Constants

All embedded constants whose values are provided in Eng units will be evaluated to the equivalent counts by using the FPM_InitFixedPoint_m() macro within the #define statement.

## Local

## Constant Name

## Resolution

## Value

D_MICROSECTOSEC_f32

## Single Precision float

0.000001

D_MAXHANDWHEELVEL_HWRADPS_F32

## Single Precision float

D_MINHANDWHEELVEL_HWRADPS_F32

## Single Precision float

## Global

This section lists the global constants used by the module. For details on global constants, refer to the Data Dictionary for the application.

## Constant Name

D_MSECPERSEC_ULS_F32

D_RADPERREV_ULS_F32

## Module specific Lookup Tables Constants

(This is for lookup tables (arrays) with fixed values, same name as other tables)

## Constant Name

## Resolution

## Value

## Software Segment

## Functions/Macros used by the Sub-Modules

## Library Functions / Macros

The library functions / Macros that are called by the various sub modules are identified below,

Abs_f32_m()

LPF_OpUpdate_f32_m ()

LPF_KUpdate_f32_m

## Data Hiding Functions

## The data hiding functions / macros used in this module are identified below,

## Local Functions/Macros Used by this MDD only

(Note if they are defined in another source file, then reference the appropriate header file)

## The local functions/macros in this module are identified below,

## Software Module Implementation

## Initialization Functions

Init: MtrVel2_Init1

## Design Rationale

## Module Outputs

## Module Internal

## Design

EMBED Visio.Drawing.11

CumMtrPosMRF_Deg_T_f32= Rte_IRead_MtrVel2_Init_CumMechMtrPosMRF_Deg_f32()

SysCDiagCumMtrPos_Rad_T_f32 = (CumMtrPosMRF_Deg_T_f32) * D_PIOVR180_ULS_F32;

MtrVel2_PrevSysCDiagCumMtrPos_Rad_M_f32PrevSysCDiagCumMtrPos_Rad_M_f32 = SysCDiagCumMtrPos_Rad_T_f32;

## Periodic Functions

Per: MtrVel2_Per1

## Design Rationale

## Program Flow Start

Rte_Call_MtrVel2_Per1_CP0_CheckpointReached()

## Store Module Inputs to Local copies

AsstAssemPol_Cnt_T_s8 = Rte_IRead_MtrVel2_Per1_AsstAssemblyPolarity_Cnt_s08();

MechMtrPosTimeStamp_uSec_T_u32 = Rte_IRead_MtrVel2_Per1_MechMtrPos1Timestamp_USec_u32();

CumMtrPosMRF_Deg_T_f32 = Rte_IRead_MtrVel2_Per1_CumMechMtrPosMRF_Deg_f32();

## Calculate SysC Motor Velocity

EMBED Visio.Drawing.11

## Store Local copy of outputs into Module Outputs

Rte_IWrite_MtrVel2_Per1_SysCDiagHandwheelVel_HwRadpS_f32 (SysCHwVelCRF_HwRadpS_M_f32)

Rte_IWrite_MtrVel2_Per1_SysCDiagMtrVelMRF_MtrRadpS_f32(SysCMtrVelRawMRF_MtrRadpS_T_f32)

MtrVel2_SysCMtrVelMRF_MtrRadpS_M_f32 = SysCMtrVelRawMRF_MtrRadpS_T_f32 ;

## Program Flow End

Rte_Call_MtrVel2_Per1_CP1_CheckpointReached()

## Periodic Functions

Per: MtrVel2_Per2

## Design Rationale

## Program Flow Start

## Store Module Inputs to Local copies

Rte_Call_MtrVel2_Per2_CP0_CheckpointReached()

HandwheelVel_HwRadpS_T_f32 = Rte_IRead_MtrVel2_Per2_HandwheelVel_HwRadpS_f32 ()

MRFMotorVel_MtrRadpS_T_f32 = Rte_IRead_MtrVel2_Per2_MotorVelMRF_MtrRadpS_f32 ()

## Calculate Raw Motor Velocity

EMBED Visio.Drawing.11

## Program Flow End

Rte_Call_MtrVel2_Per2_CP1_CheckpointReached()

## Fault Recovery Functions

## Shutdown Functions

## Interrupt Functions

## Serial Communication Functions

## Local Function/Macro Definitions

## Execution Requirements

## Execution Sequence of the Module

(Describe in words relevant details about the execution sequence of the different sub modules.)

## Execution Rates for sub-modules called by the Scheduler

## This table serves as reference for the Scheduler design

## Function Name

## Calling Frequency

## System State(s) in which the function is called

MtrVel2_Init1

## ALL STATES

MtrVel2_Per1

## ALL STATES

MtrVel2_Per2

## ALL STATES

## Execution Requirements for Serial Communication Functions

## Function Name

## Sub-Module called by (Serial Comm Function Name)

## Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in this module.

## Name of Sub Module

## Software Segment

MtrVel2_Per1

RTE_START_SEC_SA_MTRVEL2_APPL_CODE

MtrVel2_Per2

RTE_START_SEC_SA_MTRVEL2_APPL_CODE

## Local Functions

## Known Issues / Limitations With Design

## Revision Control Log

Item #

Rev #

## Change Description

## Author Initials

Initial AutoSAR release.

5- June-13

## Selva

## Update the Input and output ports of Motor Velocity

30-July-13

## Selva

## Updated Port interface name to match the FDD

22-Aug-13

## Selva

A-5749 fixes ie replacing MtrVel with raw cal values

06-Oct-13

## Selva

Update Motor Velocity for A7136, A7138, A7385 (Section 6.2.4 , section 6.8.3 flow chart)

12-Dec-14

## Selva

## Updated as per Unit Test Findings

29-Dec-14

## KPIT-AB

## SOFTWARE MODULE DESIGN SPECIFICATION

Title:

## Motor Velocity

Gen II+ EPS

Revision:

Product:

Rev. Date:

0629-Dec-1412-OctDec- -13

Group:

Originator:

## Selva Sengottaiyan

Page:

## NUMPAGES

## NEXTEER CONFIDENTIAL

S/W module design template, Rev 2.2b

gdlpC

gd6sd

gdlpC

ytdNc

gd6sd

gdlpC

ytdNc

gdl:1

gdlpC

}n_PD8D

gdlpC

zrzrzrgcWcWH

gd`-^

yt`-^

ujf_[_fTPfLHAHLH

c\UQU\M

gd)]&

a]VR]N]N]N]N]

eYeYeY

gdxu&

u`uNuJB>B>B

IDATx^

L}v?QI

2SINIQ

Z`[|t

TOj*8

L%0UI

9i]IU751FI

SRI;d

Wkj*nQ

Z=NBG

d9xQg

jauUy

R[W+(

~l!gG<l

*iV?*

## NLEOg

$0UI9

Jj%H}

%]:<8

ytdNc

yt`-^

## Root Entry

## Data

## WordDocument

## ObjectPool

_1481379549

## CompObj

## ObjInfo

## Microsoft Visio Drawing

Visio 11.0 Shapes

Visio.Drawing.11

## Ankita Bhardwaj

jVisioDocument

## VisioInformation

## SummaryInformation

## DocumentSummaryInformation

## Visio (TM) Drawing

T`Nww:

#//?M

>S@#|B:

udH>Q

=Os<P

/#/aLD%

!$FG\

OM?_?

iY_<-:

N_1/C&6

IDLA$

]Kd2c(

9oKo]ooo

}t@9A

grPt6

?P=0Ut

nn69x2

zr@3Up

nh0o5;@x2

K_-S;U4

w_]W3]

0yn6Cx2

g th

Vmt(1

6,LU"

rQ0gc0t

0MQ0c

0oNS0o

2eS0e

0d$_0

iMy+Zs

#R$U!

(@S`+

VVVVV#E

I}8ZsA

## SWDZA

T}O$I

~?uDT

t:Pnl

0#B{GA3U

e*g"`

0+asL`

1]e,`c

Om0fR&`e

R&0u,`d

(d[;A

b^A^A

H\q\qa

[uLH u

/l(?E

rial

ymbo

alib

## Ming

## S PG

othi

tran

gelo

rind

hrut

ordi

a Ne

algu

n Go

imes

## Guide

## Cost

## Owner

ncti

dDat

Row_1

faul

## ASFL

## O /c

## ASFL

## O /c

J#a/.

## Ankita Bhardwaj

## Microsoft Visio

Page-1

## Process

## Pages

## Masters

_PID_LINKBASE

_VPID_ALTERNATENAMES

## Microsoft Visio Drawing

Visio 11.0 Shapes

Visio.Drawing.11

_1481379548

## CompObj

## ObjInfo

## VisioDocument

## VisioInformation

## SummaryInformation

## DocumentSummaryInformation

## Visio (TM) Drawing

T`Nww:

#//?M

>S@#|B:

udH>Q

=Os<P

_W/i/

?'?9?K?]?o?

o/}*1

o/oAl

## EVRSg

0gx)R

2HoZolk

g th

Vmt(1

6,LU"

rQ0gc0t

0MQ0c

0oNS0o

2eS0e

0d$_0

iMy+Zs

#R$U!

(@S`+

VVVVV#E

I}8ZsA

## SWDZA

T}O$I

mina

,%"usi"iO*b

|!p#f-S

$gM",

g on

opyr

M`0c^0o

%sX0ff2W1rZ0

1uaf0iX0n

0 ^8Us

0e^0v

_O*J y

EHgA^_R

0euXojf

Dq!X(b

m1"uI

g th

t (c

(sT"e(

vf dY

Tm!#

Rf"o*

PU0%!pj"A!

s co

} fV6

Tm!#

U ?D1f@M)@c<0

fdBUArTX@

Aad@iV@n3@] f@A

@ \HUs

Be+@e<0v

d3@J@

SV6U8

c0xo)

W,_74b

## U wM h

tY bu R!cY uiW fU r

tS&j%,

"aJY pw oM ^!sY

!ew ,

-SO xY 6

0OY G9

(E?W?

)!4)!2

g th

opyr

&K?hL

#5#2N

?8:5$

E2Zo.u

B2J1J1v2

iM nW t

S kW Bm"iO ,

lM wO hm r8a X!

dm l!W,

pK,jM i] UeK ,m"sM"i

d%b[ z!

c xW 6

0OW 9

0H#2|

)!)!2

g th

opyr

6z Mr cp

sj fx"i!rTl

!ax ij n

] z A

5@P#y6y6

7Nk?h

?_+"vQ!5

:jH8h

"GS+"m

`d3C%U

i!sx {

c4K/G

1(,~c

g th

Vmt(1

02o00m0

0oS0o

2eS0eJ

RHFB4

iMy+Zs

#R$U!

(nQ]p.9

OY0K*

VVVVV#E

jhEI}8ZsA

## SWDZA

UF/X#

cr'Gb

6#UJ6J6

S#Fq#J

## Z-HXE

GRBW3

w"0A?2

S2Mrdor

## POptSp

eQpnC

## SSpaymp

pfP eSr(

pim0h

pddBg

cEI/[/

bApLy4n

APi=R

!FQtd

## COUOgOyO

_-_?_Q_

9mQtey_

Y91OCO>

@gy@i"Pi

o,o>oPoboto

M]RUh

0P`0ss@%i

_s@_"P3

y`ds@o

`R PSM

K%d N

## YaHxh

YahVd?

U%K%e/

/]OoO

_s?5_

G_Y_k_}_

EWy`ik

EL/+*7

aHk?Q1

8/J/\/n/m_

F?X?j?

O0OBN

tm@UP~

;zFTE

dOvJ!B

(uULE

1'32[

Nkq%3

jo]&6

!%36r

f@"ao

_/RJ!D

!UhG t

## PlRv(G

!J!C+Pm

qh=DB

)b?t?DX

9URM`u

?Vohfk

"2TTR

/(/:/L/^/p/

OYO2ODO

/hOzO

oJ/\/<oNo

-/?/n

?)?;?M?_?q?

E_W_i_{_

e3g(hM

*;L]n

0ja;2

L/^/p/

o1oCoUogoyo

1m 0V)

L?^?N

O0OBOTOfO

?'_9_K_]_o_

<_N_`_Qochf-

C*q mUdP)

t@ _m

=lpfo

&1)hd510<

aocpF

a?BOTF

4TE Ix

*_<_g

bnM]sy

)?;?M?_?q?

@_OqO

## R/d/v/

/*B"Q

P_b_t_

o(o:oLi

A?OQO$cO

FzPD9

`DzPP

0_' L

QBQ(i`

Db3-64FUBU{

## NDaAp

pl?Y_

qUoj9

x3a2PTtBA@

/0/B%_'T(

rqc)l

1OCOUOgOyO

o#o5oJGlVS!
