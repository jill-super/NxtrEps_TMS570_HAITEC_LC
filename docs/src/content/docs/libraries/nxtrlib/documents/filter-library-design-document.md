---
title: "Filter Library Design Document"
description: "Converted from Filter_Library_Design_Document.doc"
---

> **Source document:** `NxtrLib/doc/Filter_Library_Design_Document.doc`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: legacy Word document (`.doc`).

> **Note:** the original file is a legacy binary Word document (`.doc`) which cannot be converted with full fidelity in this environment. The text below was recovered automatically and may be out of order in places; tables and figures are not preserved. See the original file for the authoritative content.

## Partial Notch Filter

## Filter Equations

1.1.1

## Node b State Variable Initialization

1.1.2

## Node d State Variable Initialization

1.1.3

## Filter Output Calculation

1.1.4

## Node b State Variable Calculation

1.1.5

## Node d State Variable Calculation

1.1.6

## Filter Output Calculation

## Library Routines Design

1.2.1

## Notch Filter Initialization Function

1.2.2

## Notch Filter State Variable Update Function

1.2.3

## Notch Filter Output Update Function

1.2.4

## Notch Filter Full Update Function

## Notch Filter Structure Acceptable Ranges

## Usage

1st Order Low Pass Filter, 1 Pole- coefficient

Topology 1

1LP1-C

2.1.1

## Filter Equations

2.1.2

## Library Routines Design

2.1.2.1

## Unity Gain, No Dead band Compensation, Fixed K

calibratable Kn, fixed 16 bit Kd, 32 Bit State Variable, Truncate divide, Unsigned 16 bit Input

2.1.2.2

## Unity Gain, No Dead band Compensation, Fixed K

calibratable Kn, fixed 16 bit Kd, 32 Bit State Variable, Truncate divide, Signed 16 bit Input

Topology 2

1LP1-B

2.2.1

## Filter Equations

2.2.2

## Library Routines Design

2.2.2.1

## Variable Gain, Variable D, Variable K

calibratable 16 bit Kn, variable Kd, 32 Bit State Variable, Truncate divide, Unsigned 16 bit Input

2.2.2.2

Variable Gain, Variable D, Variable K - calibratable 16 bit Kn, variable Kd, 32 Bit State Variable, Truncate divide, Signed 16 bit Input

Topology 3

1LP1-CF (Floating Point Implementation)

2.3.1

## Filter Equations

2.3.1.1

## Coefficient K Calculation and State Variable Initialization

2.3.1.2

## Coefficient K Recalculation

2.3.1.3

## Normal Operation

2.3.2

## Library Routines Design

2.3.2.1

Unity Gain, No Dead band Compensation, calibratable K, Single-Precision Float Input

1st Order High Pass Filter, 1 Pole- coefficient

Topology 1

## HP-CF (Floating Point Implementation)

3.1.1

## Filter Equations

3.1.1.1

## Coefficient K Calculation and State Variable Initialization

3.1.1.2

## Coefficient K Recalculation

3.1.1.3

## Normal Operation

3.1.2

## Library Routines Design

3.1.2.1

Unity Gain, No Dead band Compensation, calibratable K, Single-Precision Float Input

## Revision Control Log

## Partial Notch Filter

## Filter Equations

The first three equations, 1.1.1, 1.1.2, and 1.1.3 shall be combined into a single Notch Filter Initialization function. The next two equations 1.1.4 and 1.1.5 shall be combined into a single state variable update function. Finally, equation 1.1.6 shall be standalone as the output update function. For convenience, the last two function, state variable update and output update shall be combined into a single inline function to provide a single call from the modules _per() sub-module.

## Node b State Variable Initialization

SV2 = In * (B2 - A2);

## Node d State Variable Initialization

SV1 = In * (B1 + B2 - A1 - A2);

## Filter Output Calculation

Out = In;

## Node b State Variable Calculation

SV2 = (B2 * In) - (Out * A2);

## Node d State Variable Calculation

SV1 = (SV2 + (In * B1)) - (Out * A1);

## Filter Output Calculation

Out = SV1 + (B0 * In);

## Library Routines Design

## Notch Filter Initialization Function

## Function Name

NF_Init_f32

UTP Tol.

## Arguments Passed

In_Uls_T_f32

## Initial input to the filter

Float 32

SVPtr_Cnt_T_Str

## Pointer to state variable struct

NotchFiltSV_Str

FiltK_Cnt_T_Str

## Pointer to coefficient structure

NotchFiltK_Str

**See 1.3

## Return Value

Pseudo Code:

KPtr_Cnt_Str = FiltK_Cnt_T_Str;

Out = In;

SV1 = In * (B1 + B2 - A1 - A2);

SV2 = In * (B2 - A2);

## Notch Filter State Variable Update Function

## Function Name

NF_SvUpdate_f32

UTP Tol.

## Arguments Passed

In_Uls_T_f32

## Input to notch filter

Float 32

SVPtr_T_Cnt_Str

## Pointer to state variable struct

NotchFiltSV_Str

**See 1.3

FiltK_Cnt_T_Str

## Pointer to filter cal struct

NotchFiltK_Str

**See 1.3

## Return Value

Pseudo Code:

KPtr_Cnt_Str = FiltK_Cnt_T_Str

SV1 = (SV2 + (In * B1)) - (Out * A1);

SV2 = (B2 * In) - (Out * A2);

## Notch Filter Output Update Function

## Function Name

NF_OpUpdate_f32

UTP Tol.

## Arguments Passed

In_Uls_T_f32

## Input to the notch filter

Float 32

SVPtr_T_Cnt_Str

## Pointer to state variable struct

NotchFiltSV_Str

**See 1.3

## Return Value

## Filtered Output, SV Structure Updated

Float 32

Pseudo Code:

Out = SV1 + (B0 * In);

## Notch Filter Full Update Function

## Function Name

NF_FullUpdate_f32

UTP Tol.

## Arguments Passed

In_Uls_T_f32

## Input to notch filter

Float 32

SVPtr_Cnt_T_Str

## Pointer to state variable struct

NotchFiltSV_Str

**See 1.3

FiltK_Cnt_T_Str

## Pointer to filter cal struct

NotchFiltK_Str

**See 1.3

## Return Value

## Filtered output

Float 32

Pseudo Code:

Full Update simply calls OpUpdate followed by SvUpdate as a convenient alternative to calling each of the functions individually.

## Notch Filter Structure Acceptable Ranges

## Structure Name

NotchFiltSV_Str

UTP Tol.

## Members

SV1_Uls_f32

Float 32

SV2_Uls_f32

Float 32

Out_Uls_f32

Float 32

KPtr_Cnt_Str

**See Below

## Structure Name

NotchFiltK_Str

UTP Tol.

## Members

A1_Uls_f32

Float 32

A2_Uls_f32

Float 32

B0_Uls_f32

Float 32

B1_Uls_f32

Float 32

B2_Uls_f32

Float 32

## Usage

For a module that executes a Notch Filter, in its _Init() sub module execute the following function.

NF_Init_f32(<Input>, <SV_Ptr>, <FiltK_Ptr>);

## In the same module

s _Per() sub module execute the following functions in the given sequence,

NF_OpUpdate_f32(<Input>, <SV_Ptr>);

NF_SvUpdate_f32(<Input>, <SV_Ptr>, <FiltK_Ptr>);

Alternatively, a single call to the following function can be made in place of the above pair within the _Per() sub module.

NF_FullUpdate_f32(<Input>, <SV_Ptr>, <FiltK_Ptr>);

1st Order Low Pass Filter, 1 Pole- coefficient

Topology 1

1LP1-C

The Filter topology 1LP1-C is as given,

There may be multiple library functions defined for the same topology, based on the cut-off frequency, and input size requirements.

## A filter tool is available to design the low pass filter for this topology

1st Order Design,1LP1-B.xls

. This tool provides the bit sizes for all nodes shown in the filter. The tool must be used to see which library function is required for the given input, cut-off frequency, sampling rate, and filter coefficient size.

## The above filter topology requires the following constants to be defined

## Symbol

## Description

## Constant Classification

## Numerator of Filter Coefficient

This may be defined as a calibration constant or an embedded local constant based on the usage.

## Denominator of Filter Coefficient

Based on the implementation, this value may be a fixed value, which is embedded within the library function/macro or could be passed as a parameter.

## Node Symbol

## Description

## Input

State Variable (filt_SV)

Output (filt_O)

## Filter Equations

The filter equations are given below. Each equation shall be implemented as a library macro.

## State Variable (Node e) Initialization

The equation to initialize the state variable, (Node e) is as follows:

filt_SV = Input * Kd.

## Output (Node O) Initialization

The equation to initialize the output, (Node O) is as follows:

filt_O = [( ( Input

(filt_SV / Kd) ) * Kn ) + filt_SV] / Kd

## Normal Operation

During normal operation the state variable (Node e) shall be updated prior to the output of the filter (Node O) being updated.

The equation for the state variable (Node e) is as follows:

filt_SV = ( ( Input

(filt_SV / Kd) ) * Kn ) + filt_SV

The equation for the output (Node O) is as follows:

filt_O = filt_SV / Kd

The equations to update filt_Sv and filt_O or the library routines that calculate these values should be executed in the exact order shown above.

## Library Routines Design

## Unity Gain, No Dead band Compensation, Fixed K

calibratable Kn, fixed 16 bit Kd, 32 Bit State Variable, Truncate divide, Unsigned 16 bit Input

There will be four macros defined for this implementation:- state variable initialization, filter output initialization, state variable update and filter output update.

## Node Symbol

## Description

## Data Type

## Input

UINT 16

UINT16

UINT32

State Variable (filt_SV)

UINT 32

UINT16

Output (filt_O)

UINT 16

## State Variable Initialization Macro

## Function Name

LPF_SvInit_u16InFixKTrunc_m

UTP Tol.

## Arguments Passed

## Input

## Input to the low pass filter

UINT16

## Return Value

## Initialized value of node e

UINT32

Pseudo Code:

Lvalue = Input << Kd

where Kd is pre-defined for a fixed16 bit filter coefficient = 16 bits

## Filter Output Initialization Macro

## Function Name

LPF_OpInit_u16InFixKTrunc_m

UTP Tol.

## Arguments Passed

## Input

## Input to the low pass filter

UINT16

Filt_SV

## Initialized value of the state variable

UINT32

## Kn - Numerator of the filter coefficient

UINT16

## Return Value

## Initialized output of the low pass filter

UINT32

Pseudo Code:

Lvalue = (((Input

(Filt_SV >> Kd)) * Kn ), + Filt_SV)>>Kd

where Kd is pre-defined for a fixed16 bit filter coefficient = 16 bits

## Filter State Variable Update Macro

## Function Name

LPF_SvUpdate_u16InFixKTrunc_m

UTP Tol.

## Arguments Passed

## Input

## Input to the low pass filter

UINT16

Filt_SV

## Calculated value of the state variable

UINT32

## Kn - Numerator of the filter coefficient

UINT16

## Return Value

## Output of the low pass filter

UINT32

Pseudo code:

<Lvalue> = ( ( Input

(filt_SV >> Kd) ) * Kn ) + filt_SV

where Kd is pre-defined for a fixed16 bit filter coefficient = 16 bits

## Output Update Macro

## Function Name

LPF_OpUpdate_u16InFixKTrunc_m

UTP Tol.

## Arguments Passed

Filt_SV

## Calculated value of the state variable

UINT32

## Return Value

## Output of the low pass filter

UINT16

Pseudo code:

<Lvalue> = filt_SV >> Kd

where Kd is pre-defined for a 16 bit filter coefficient = 16 bits

## Usage

For a module that executes a LPF, in its _Init() sub module execute the following macros in the given sequence

LPF_SvInit_u16InFixKTrunc_m (<Input>)

LPF_OpInit_u16InFixKTrunc_m (<Input>, <Filt_SV>, <Kn>)

## In the same module

s _Per() sub module execute the following macros in the given sequence,

LPF_SvUpdate_u16InFixKTrunc_m (<Input>, <filt_SV>, <Kn>)

LPF_OpUpdate_u16InFixKTrunc_m ( <filt_SV>)

## Unity Gain, No Dead band Compensation, Fixed K

calibratable Kn, fixed 16 bit Kd, 32 Bit State Variable, Truncate divide, Signed 16 bit Input

There will be three macros defined for this implementation:- state variable initialization, state variable update and filter output update.

## Node Symbol

## Description

## Data Type

## Input

SINT 16

SINT 32

State Variable (filt_SV)

SINT 32

SINT 16

Output (filt_O)

SINT 16

## State Variable Initialization Macro

## Function Name

LPF_SvInit_s16InFixKTrunc_m

UTP Tol.

## Arguments Passed

## Input

## Input to the low pass filter

SINT16

## Return Value

## Initilized value of Node e

SINT32

Pseudo Code:

Lvalue = Input << Kd

where Kd is pre-defined for a 16 bit filter coefficient as 16 bits

## Filter Output Initialization Macro

## Function Name

LPF_OpInit_s16InFixKTrunc_m

UTP Tol.

## Arguments Passed

## Input

## Input to the low pass filter

SINT16

Filt_SV

## Initialized value of the state variable

SINT32

## Numerator of the filter coefficient

SINT16

## Return Value

## Initialized value of filter output

SINT32

Pseudo Code:

Lvalue = (((Input

(Filt_SV >> Kd)) * Kn ), + Filt_SV)>>Kd

where Kd is pre-defined for a fixed16 bit filter coefficient = 16 bits

## Filter State Variable Update Macro

## Function Name

LPF_SvUpdate_s16InFixKTrunc_m

UTP Tol.

## Arguments Passed

## Input

## Input to the low pass filter

SINT16

Filt_SV

## Initialized value of the state variable

SINT32

## Numerator of the filter coefficient

SINT16

## Return Value

Calculated value of filt_SV

SINT32

Pseudo code:

<Lvalue> = ( ( Input

(filt_SV >> Kd) ) * Kn ) + filt_SV

where Kd is pre-defined for a 16 bit filter coefficient = 16 bits

## Output Update Macro

## Function Name

LPF_OpUpdate_s16InFixKTrunc_m

UTP Tol.

## Arguments Passed

Filt_SV

calculated value of filter state variable

SINT32

## Return Value

## Output of the low pass filter

SINT16

Pseudo code:

<Lvalue> = filt_O >> Kd

where Kd is pre-defined for a 16 bit filter coefficient = 16

## Usage

For a module that executes a LPF, in its _Init() sub module execute the following macros in the given sequence

LPF_SvInit_s16InFixKTrunc_m (<Input>)

LPF_OpInit_s16InFixKTrunc_m (<Input>, <Filt_SV>, <Kn>)

## In the same module

s _Per() sub module execute the following macros in the given sequence

LPF_SvUpdate_s16InFixKTrunc_m (<Input>, <filt_SV>, <Kn>)

LPF_OpUpdate_s16InFixKTrunc_m ( <filt_SV>)

Topology 2

1LP1-B

The filter topology 1LP1-B is as given,

## Filter Equations

The filter equations are given below. Each equation shall be implemented as a library macro.

## State Variable (Node e) Initialization

The equation to initialize the state variable, (Node e) is as follows:

filt_SV = Input * G * Kd * D

## Output (Node O) Initialization

The equation to initialize the output, (Node O) is as follows:

filt_O = [( ( (Input * G * D)

(filt_SV / Kd) ) * Kn ) + filt_SV] / (Kd * D)

## Normal Operation

During normal operation the state variable (Node e) shall be updated prior to the output of the filter (Node O) being updated.

The equation for the state variable (Node e) is as follows:

filt_SV = ( ( (Input * G * D)

(filt_SV / Kd) ) * Kn ) + filt_SV

The equation for the output (Node O) is as follows:

filt_O = filt_SV / (Kd * D)

The equations to update filt_Sv and filt_O or the library routines that calculate these values should be executed in the exact order shown above.

The multiplication for the Filter Input by G shall be implemented external to the library macros. Thus the Input as used by the macros shall represent actual filter input * G, for non unity gain filter implementation.

Note: Constraint on this filter is that Node b cannot exceed 16 bits.

## Library Routines Design

## Variable Gain, Variable D, Variable K

calibratable 16 bit Kn, variable Kd, 32 Bit State Variable, Truncate divide, Unsigned 16 bit Input

## Node Symbol

## Description

## Data Type

## Input

UINT 16

UINT 32

State Variable (filt_SV)

UINT 32

UINT 16

Output (filt_O)

UINT 16

## State Variable Initialization Macro

## Function Name

LPF_SvInit_u16InVarKTrunc_m

UTP Tol.

## Arguments Passed

## Input

## Input to the low pass filter

UINT16

## Denominator bits of filter coefficient

UINT16

## Deadband factor

UINT16

## Return Value

## Initialized value of Node e

UINT32

Pseudo Code:

Lvalue = (Input << Kd) << D

Note:- The multiplication by D shall not be performed for D = 0.

## Filter Output Initialization Macro

## Function Name

LPF_OpInit_u16InVarKTrunc_m

UTP Tol.

## Arguments Passed

## Input

## Input to the low pass filter

UINT16

Filt_SV

## Initialized value of state variable

UINT32

## Numerator of coefficient

UINT16

## Denominator bits of filter coefficient

UINT16

## Deadband factor

UINT16

## Return Value

## Low pass filter output

UINT32

Pseudo Code:

Lvalue = [((((Input<<D)

(Filt_SV >> Kd)) * Kn ) + Filt_SV)>>Kd]>>D

Note:- The multiplication and division by D shall not be performed for D = 0.

## Filter State Variable Update Macro

## Function Name

LPF_SvUpdate_u16InVarKTrunc_m

UTP Tol.

## Arguments Passed

## Input

## Input to the low pass filter

UINT16

Filt_SV

## Calculated value of filter state variable

UINT32

## Numerator of coefficient

UINT16

## Denominator bits of filter coefficient

UINT16

## Deadband factor

UINT16

## Return Value

## Low pass filter output

UINT32

Pseudo code:

<Lvalue> = ( ( (Input << D)

(filt_SV >> Kd) ) * Kn ) + filt_SV

Note:- The multiplication by D shall not be performed for D = 0.

## Output Update Macro

## Function Name

LPF_OpUpdate_u16InVarKTrunc_m

UTP Tol.

## Arguments Passed

Filt_SV

## Calculated value of filter state variable

UINT32

## Denominator bits of filter coefficient

UINT16

## Deadband factor

UINT16

## Return Value

## Low pass filter output

UINT32

Pseudo code:

<Lvalue> = (filt_SV >> Kd ) >>D

Note:- The division by D shall not be performed for D = 0.

## Usage

For a module that executes a LPF, in its _Init() sub module execute the following macros in the given sequence

LPF_SvInit_u16InVarKTrunc_m (<Input>, <Kd>, <D>)

LPF_OpInit_u16InVarKTrunc_m (<Input>, <Filt_SV>, <Kn>, <Kd>, <D>)

## In the same module

s _Per() sub module execute the following macros in the given sequence,

LPF_SvUpdate_u16InVarKTrunc_m (<Input>, <filt_SV>, <Kn>, <Kd>, <D>)

LPF_OpUpdate_u16InVarKTrunc_m ( <filt_SV>, <Kd>, <D>)

Variable Gain, Variable D, Variable K - calibratable 16 bit Kn, variable Kd, 32 Bit State Variable, Truncate divide, Signed 16 bit Input

## Node Symbol

## Description

## Data Type

## Input

SINT 16

SINT 32

State Variable (filt_SV)

SINT 32

SINT 16

Output (filt_O)

SINT 16

## State Variable Initialization Macro

## Function Name

LPF_SvInit_s16InVarKTrunc_m

UTP Tol.

## Arguments Passed

## Input

## Input to the low pass filter

SINT16

## Denominator bits of filter coefficient

SINT16

## Deadband factor

SINT16

## Return Value

## Initialized value of Node e

SINT32

Pseudo Code:

Lvalue = (Input << Kd) << D

Note:- The multiplication by D shall not be performed for D = 0.

## Filter Output Initialization Macro

## Function Name

LPF_OpInit_s16InVarKTrunc_m

UTP Tol.

## Arguments Passed

## Input

## Input to the low pass filter

SINT16

Filt_SV

## Initialized value of filter state variable

SINT32
