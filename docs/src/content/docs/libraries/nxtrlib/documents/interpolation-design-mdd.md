---
title: "Interpolation Design Module Design Document"
description: "Converted from Interpolation_Design_MDD.doc"
---

> **Source document:** `NxtrLib/doc/Interpolation_Design_MDD.doc`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: legacy Word document (`.doc`).

> **Note:** the original file is a legacy binary Word document (`.doc`) which cannot be converted with full fidelity in this environment. The text below was recovered automatically and may be out of order in places; tables and figures are not preserved. See the original file for the authoritative content.

Variable X Variable Y 2D Table Lookup function (with interpolation)

## Requirement

Implementation:

1.2.1

## Unsigned X, Unsigned Y

1.2.2

## Signed X, Unsigned Y

1.2.3

## Signed X, Signed Y

1.2.4

## Unsigned X, Signed Y

Fixed X Variable Y 2D Table Lookup function (with interpolation)

## Requirement

Implementation:

2.2.1

## Unsigned X, Unsigned Y

2.2.2

## Signed X, Unsigned Y

2.2.3

## Signed X, Signed Y

2.2.4

## Unsigned X, Signed Y

## Single X Multiple Y (Bilinear Interpolation)

Implementation:

3.1.1

Syntax: BilinearXYM_s16_u16Xs16YM_Cnt (BS, input, *BSTbl, BSize, *XTbl, *YMTbl, Xsize)

3.1.2

Syntax: BilinearXYM_u16_u16Xu16YM_Cnt(BS, input, *BSTbl, BSsize, *XTbl, *YMTbl, Xsize)

3.1.3

Syntax: BilinearXYM_s16_s16Xs16YM_Cnt (BS, input, *BSTbl, BSize, *XTbl, *YMTbl, Xsize)

3.1.4

Syntax: BilinearXYM_u16_s16Xu16YM_Cnt(BS, input, *BSTbl, BSsize, *XTbl, *YMTbl, Xsize)

## Multiple X Multiple Y (Bilinear Interpolation)

## Implementation

4.1.1

Syntax: BilinearXMYM_u16_u16XMu16YM_Cnt( BS, input, *BSTbl, BSsize, *XMTbl, *YMTbl, Xsize)

4.1.2

Syntax: BilinearXMYM_s16_u16XMs16YM_Cnt(BS, input, *BSTbl, BSsize, *XMTbl, *YMTbl, Xsize)

4.1.3

Syntax: BilinearXMYM_u16_s16XMu16YM_Cnt( BS, input, *BSTbl, BSsize, *XMTbl, *YMTbl, Xsize)

UnitTesting Range: Linear and Bilinear Interpolation

## Revision Control Log

Variable X Variable Y 2D Table Lookup function (with interpolation)

## Requirement

The Variable X Variable Y 2D table has the Variable X as the input (independent variable) and the Variable Y as the output (dependent variable). The lookup function with interpolation is used to interpolate the values of Y corresponding to the input value for X. This is implemented using the straight-line equation as given below:

EMBED Equation.3

where,

n = index into the independent and dependent variable tables

n+1 = next consecutive index into the tables.

(yn+1 - yn) = interval in the dependent table within which the interpolated output is calculated.

(xn+1 - xn) = interval in the independent table within which the input lies.

y = interpolated output (dependent variable)

x = input (independent variable)

Note that yn+1 < yn or yn+1 > yn, for negative or positive slopes and xn+1 > xn.

The index n and n+1, are determined using Straight-Forward Search method. Using the indices, the values of xn+1, xn, yn+1 and yn are determined.

The difference (yn+1 - yn) is held in a signed variable to ensure that the interpolation can handle both positive and negative slopes.

The Variable X VariableY interpolation function is defined as a function with the input x value and table name passed as parameters. The function will return the interpolated output y as its output.

Implementation:

Note: Straight Forward Search method is used for calculating the index n.

## Unsigned X, Unsigned Y

Syntax : IntplVarXY_u16_u16Xu16Y_Cnt ( *TableX, *TableY, Size, input)

Arguments:

TableX: - The Variable X 2D table (independent table)

TableY: - The Variable Y 2D table (dependent table)

Size: - Size of the table

input: - The input to the table

output: The output from the table.

Pseudo Code :

UINT16

input, output, Size

UINT16

index = 0

SINT16

diffY, diffX, diffXinput, tmpout2, sOutput

SINT32

diffY, diffX, diffXinput, tmpout1

const UINT16

TableX = [ x1, x2, x3, x4, x5,

const UINT16

TableY = [ y1, y2, y3, y4, y5,

/* Check for Range */

if ( input <= TableX[0] )

return TableY[0]

else if ( input >= TableX[size-1] )

return TableY[size-1]

endif

/* In range. Get Index */

while ( TableX[index + 1] < input )

index = index + 1

endwhile

/* Interpolate and get the output */

diffY = TableY[index+1] - TableY[index]

diffX = TableX[index+1] - TableX[index]

diffXinput = input - TableX[index]

/* Product in 32 bit */

tmpout1 = diffY* diffXinput

/* Check if Divide by zero */

if (diffX == 0)

tmpout2 = 0

/* Here, the lower 16 bits are assigned to tmpout2 */

tmpout2 = tmpout1 / diffX

endif

output = tmpout2 + TableY[index]

return output

## Signed X, Unsigned Y

Syntax : IntplVarXY_u16_s16Xu16Y_Cnt (*TableX, *TableY, Size, input)

Arguments:

TableX: - The Variable X 2D table (independent table)

TableY: - The Variable Y 2D table (dependent table)

Size: - Size of the table

input: - The input to the table

output: The output from the table.

Pseudo Code :

SINT16

input

UINT16

output, Size

UINT16

index = 0

SINT16

diffY, diffX, diffXinput, tmpout2, sOutput

SINT32

diffY, diffX, diffXinput, tmpout1

const SINT16

TableX = [ x1, x2, x3, x4, x5,

const UINT16

TableY = [ y1, y2, y3, y4, y5,

/* Check for Range */

if ( input <= TableX[0] )

return TableY[0]

else if ( input >= TableX[size-1] )

return TableY[size-1]

endif

/* In range. Get Index */

while ( TableX[index + 1] < input )

index = index + 1

endwhile

/* Interpolate and get the output */

diffY = TableY[index+1] - TableY[index]

diffX = TableX[index+1] - TableX[index]

diffXinput = input - TableX[index]

/* Product in 32 bit */

tmpout1 = diffY * diffXinput

/* Check if Divide by zero */

if (diffX == 0)

tmpout2 = 0

/* Here, the lower 16 bits are assigned to tmpout2 */

tmpout2 = tmpout1 / diffX

endif

output = tmpout2 + TableY[index]

return output

## Signed X, Signed Y

Syntax : IntplVarXY_s16_s16Xs16Y_Cnt (*TableX, *TableY, Size, input)

Arguments:

TableX: - The Variable X 2D table (independent table)

TableY: - The Variable Y 2D table (dependent table)

Size: - Size of the table

input: - The input to the table

output: The output from the table.

Pseudo Code :

SINT16

input, output

UINT16

index = 0

SINT16

diffY, diffX, diffXinput, tmpout2

SINT32

diffY, diffX, diffXinput, tmpout1

const SINT16

TableX = [ x1, x2, x3, x4, x5,

const SINT16

TableY = [ y1, y2, y3, y4, y5,

/* Check for Range */

if ( input <= TableX[0] )

return TableY[0]

else if ( input >= TableX[size-1] )

return TableY[size-1]

endif

/* In range. Get Index */

while ( TableX[index + 1] < input )

index = index + 1

endwhile

/* Interpolate and get the output */

diffY = TableY[index+1] - TableY[index]

diffX = TableX[index+1] - TableX[index]

diffXinput = input - TableX[index]

/* Product in 32 bit */

tmpout1 = diffY * diffXinput

/* Check if Divide by zero */

if (diffX == 0)

tmpout2 = 0

/* Here, the lower 16 bits are assigned to tmpout2 */

tmpout2 = tmpout1 / diffX

endif

output = tmpout2 + TableY[index]

return output

## Unsigned X, Signed Y

Syntax : IntplVarXY_s16_u16Xs16Y_Cnt (*TableX, *TableY, Size, input)

Arguments:

TableX: - The Variable X 2D table (independent table)

TableY: - The Variable Y 2D table (dependent table)

Size: - Size of the table

input: - The input to the table

output: The output from the table.

Pseudo Code :

UINT16

input, Size

SINT16

output

UINT16

index = 0

SINT16

diffY, diffX, diffXinput, tmpout2

SINT32

diffY, diffX, diffXinput, tmpout1

const UINT16

TableX = [ x1, x2, x3, x4, x5,

const SINT16

TableY = [ y1, y2, y3, y4, y5,

/* Check for Range */

if ( input <= TableX[0] )

return TableY[0]

else if ( input >= TableX[size-1] )

return TableY[size-1]

endif

/* In range. Get Index */

while ( TableX[index + 1] < input )

index = index + 1

endwhile

/* Interpolate and get the output */

diffY = TableY[index+1] - TableY[index]

diffX = TableX[index+1] - TableX[index]

diffXinput = input - TableX[index]

/* Product in 32 bit */

tmpout1 = diffY * diffXinput

/* Check if Divide by zero */

if (diffX == 0)

tmpout2 = 0

/* Here, the lower 16 bits are assigned to tmpout2 */

tmpout2 = tmpout1 / diffX

endif

output = tmpout2 + TableY[index]

return output

Fixed X Variable Y 2D Table Lookup function (with interpolation)

## Requirement

The Fixed X Variable Y 2D table has the Fixed X as the input (independent variable) and the Variable Y (dependent variable) as the output. The interpolation function is used to interpolate the values of Y corresponding to the input value for X. It is assumed that the independent axis (X) will always start from 0. This is implemented using the straight-line equation as given below:

EMBED Equation.3

where,

n = index into the Table

(yn+1 - yn) = interval in the dependent table within which the interpolated output is calculated.

x = fixed X interval within which the input lies.

y = interpolated output

x = input

Determine the value of n, i.e the index into the table, n = truncate ( x /

x ). Using this index n, determine the values of xn, yn and yn+1. The output y can then be ca

lculated based on the straight line given above.

Implementation:

## Unsigned X, Unsigned Y

Syntax : IntplFxdX_u16_u16Xu16Y_Cnt (DeltaX, *TableY, Size, input)

Arguments:

DeltaX: - The Fixed X interval

TableY: - The Variable Y 2D table (dependent table)

Size: - Size of the table

input: - The input to the table

output: The output from the table.

Pseudo Code :

UINT16

input, output, Size

UINT16

index = 0

SINT16

diffY, diffXinput, tmpout2, sOutput

SINT32

diffY, diffXinput, tmpout1

const UINT16

TableY = [ y1, y2, y3, y4, y5,

if (DeltaX == 0)

/* Cannot do interpolation. Return Y0 */

return TableY[0]

endif

/* Check for Range */

if ( input <= 0 )

return TableY[0]

else if ( input >= DeltaX * (size-1) )

return TableY[size-1]

endif

/* In range. Get Index */

index = truncate (input / DeltaX)

/* Interpolate and get the output */

diffY = TableY[index+1] - TableY[index]

diffXinput = input - DeltaX * index

/* Product in 32 bit */

tmpout1 = diffY * diffXinput

/* Here, the lower 16 bits are assigned to tmpout2 */

tmpout2 = tmpout1 / DeltaX

output = tmpout2 + TableY[index]

return output

## Signed X, Unsigned Y

Syntax : IntplFxdX_u16_s16Xu16Y_Cnt (DeltaX, *TableY, Size, input)

Arguments:

DeltaX: - The Fixed X interval

TableY: - The Variable Y 2D table (dependent table)

Size: - Size of the table

input: - The input to the table

output: The output from the table.

Pseudo Code :

SINT16

input

UINT16

output, Size

UINT16

index = 0

SINT16

diffY, diffXinput, tmpout2, sOutput

SINT32

diffY, diffXinput , tmpout1

const UINT16

TableY = [ y1, y2, y3, y4, y5,

if (DeltaX == 0)

/* Cannot do interpolation. Return Y0 */

return TableY[0]

endif

/* Check for Range */

if ( input <= 0 )

return TableY[0]

else if ( input >= DeltaX * (size-1) )

return TableY[size-1]

endif

/* In range. Get Index */

index = truncate (input / DeltaX)

/* Interpolate and get the output */

diffY = TableY[index+1] - TableY[index]

diffXinput = input - DeltaX * index

/* Product in 32 bit */

tmpout1 = diffY * diffXinput

/* Here, the lower 16 bits are assigned to tmpout2 */

tmpout2 = tmpout1 / DeltaX

output = tmpout2 + TableY[index]

return output

## Signed X, Signed Y

Syntax: IntplFxdX_s16_s16Xs16Y_Cnt (DeltaX, *TableY, Size, input)

Arguments:

DeltaX: - The Fixed X interval

TableY: - The Variable Y 2D table (dependent table)

Size: - Size of the table

input: - The input to the table

output: The output from the table.

Pseudo Code :

SINT16

input, output

UINT16

index = 0

SINT16

diffY, diffXinput, tmpout2

SINT32

diffY, diffXinput , tmpout1

const SINT16

TableY = [ y1, y2, y3, y4, y5,

if (DeltaX == 0)

/* Cannot do interpolation. Return Y0 */

return TableY[0]

endif

/* Check for Range */

if ( input <= 0 )

return TableY[0]

else if ( input >= DeltaX * (size-1) )

return TableY[size-1]

endif

/* In range. Get Index */

index = truncate (input / DeltaX)

/* Interpolate and get the output */

diffY = TableY[index+1] - TableY[index]

diffXinput = input - DeltaX * index

/* Product in 32 bit */

tmpout1 = diffY * diffXinput

/* Here, the lower 16 bits are assigned to tmpout2 */

tmpout2 = tmpout1 / DeltaX

output = tmpout2 + TableY[index]

return output

## Unsigned X, Signed Y

Syntax: IntplFxdX_s16_u16Xs16Y_Cnt (DeltaX, *TableY, Size, input)

Arguments:

DeltaX: - The Fixed X interval

TableY: - The Variable Y 2D table (dependent table)

Size: - Size of the table

input: - The input to the table

output: The output from the table.

Pseudo Code :

UINT16

input, Size

SINT16

output

UINT16

index = 0

SINT16

diffY, diffXinput, tmpout2

SINT32

diffY, diffXinput, tmpout1

const SINT16

TableY = [ y1, y2, y3, y4, y5,

if (DeltaX == 0)

/* Cannot do interpolation. Return Y0 */

return TableY[0]

endif

/* Check for Range */

if ( input <= 0 )

return TableY[0]

else if ( input >= DeltaX * (size-1) )

return TableY[size-1]

endif

/* In range. Get Index */

index = truncate (input / DeltaX)

/* Interpolate and get the output */

diffY = TableY[index+1] - TableY[index]

diffXinput = input - DeltaX * index

/* Product in 32 bit */

tmpout1 = diffY * diffXinput

/* Here, the lower 16 bits are assigned to tmpout2 */

tmpout2 = tmpout1 / DeltaX

output = tmpout2 + TableY[index]

return output

## Single X Multiple Y (Bilinear Interpolation)

Implementation:

Syntax: BilinearXYM_s16_u16Xs16YM_Cnt (BS, input, *BSTbl, BSize, *XTbl, *YMTbl, Xsize)

Arguments:

BS:- Bilinear Selector

Input:-The input to the table

BSTbl:- Bilinear Selector Table 2D

BSize:- Bilinear Selector Table Size

XTbl:- Table X 2D

YMTbl:- Table Y with MxN dimension

Xsize:- Size of XTbl

Output:- The output from the table

Pseudo Code:

UINT16

## BSindex, Xindex

UINT16

ArrayIndex1, ArrayIndex2, ArrayIndex3, ArrayIndex4

SINT32

## BSinputDiff, XInputDiff

FLOAT32

Numerator_f32, Denominator_f32, Output_f32

SINT16

Output_s16

Const UINT16 BSTbl = [z1,z2,z3,z4,

Const UINT16 XTbl = [x1,x2,x3,x4,

Const SINT16 YMTbl[mxn] = [(y1,y2,y3

),(y4,y5,y6

If (BS <= BSTbl[0])

BSindex = 0

BS = BSTbl[0]

Else if (BS >= BSTbl[BSize-1])

BSindex = BSsize -2

BS = BSTbl[BSsize -1]

While ((BSTbl[BSindex] = = BSTbl[BSindex + 1] && (BSindex > 0)))

BSindex = BSindex - 1

BSindex = 0

While ( BSTbl[BSindex +1] < BS)

BSindex = BSindex + 1

## Endif

If (input <= XTbl[0])

Xindex = 0

Input = XTbl[0]

Else if (input >= XTbl[XSize

Xindex = Xsize

Input = XTbl[Xsize -1]

Xindex = 0

While ( XTbl[Xindex +1] < input)

Xindex = Xindex+1

## Endif

ArrayIndex1 = (BSindex * Xsize) + Xindex

ArrayIndex2 = (BSindex * Xsize) + Xindex + 1

ArrayIndex3 = ((BSindex + 1) * Xsize) + Xindex

ArrayIndex4 = ((BSindex + 1) * Xsize) + Xindex + 1

BSInputDiff = BS

BSTbl[BSindex]

XInputDiff = input

XTbl[Xindex]

Numerator_f32 = ( YMTbl[ArrayIndex2]

YMTbl[ArrayIndex1]) * ((BSTbl[BSindex+1]

BSTbl[BSindex]) * XInputDiff) +

(YMTbl[ArrayIndex3]

YMTbl[ArrayIndex1]) *

(BSInputDiff * (XTbl[Xindex+1]

XTbl[Xindex])) +

(XInputDiff * BSInputDiff ) *

((YMTbl[ArrayIndex4])

(YMTbl[ArrayIndex3])

(YMTbl[ArrayIndex2]

YMTbl[ArrayIndex1]))

Denominator_f32 = (BSTbl[BSindex +1]

BSTbl[BSindex]) * (XTbl[Xindex+1]

XTbl[Xindex])

If (Denominator_f32 <= FLT_EPSILON)

Output_f32 = YMTbl[ArrayIndex1]

Output_f32 = YMTbl[ArrayIndex1] + Numerator_f32 / Denominator_f32

## Endif

If (Output_f32 >= 0)

Output_f32 = Output_f32 + 0.5

Output_f32 =Output_f32

## Endif

/*Float to SINT16 typecast*/

Output_s16 = Output_f32

return Output_s16

Syntax: BilinearXYM_u16_u16Xu16YM_Cnt(BS, input, *BSTbl, BSsize, *XTbl, *YMTbl, Xsize)

## Arguments

BS:- Bilinear Selector

input:-The input to the table

BSTbl:- Bilinear Selector Table 2D

BSize:- Bilinear Selector Table Size

XTbl:- Table X 2D

YMTbl:- Table Y with MxN dimension

Xsize:- Size of XTbl

Output:- The output from the table

Pseudo Code:

UINT16

## BSindex, Xindex

UINT16

ArrayIndex1, ArrayIndex2, ArrayIndex3, ArrayIndex4

SINT32

## BSInputDiff, XInputDiff

FLOAT32

Numerator_f32, Denominator_f32

UINT16

Output_u16

Const UINT16 BSTbl = [z1,z2,z3,z4,

Const UINT16 XTbl = [x1,x2,x3,x4,

Const UINT16 YMTbl[mxn] = [(y1,y2,y3

),(y4,y5,y6

If (BS <= BSTbl[0])

BSindex = 0

BS = BSTbl[0]

Else if (BS >= BSTbl[BSsize

BSindex = BSsize -2

BS = BSTbl [ BSsize

While (( BSTbl [BSindex] == BSTbl [ BSindex+1] && (BSindex > 0)))

BSindex = BSindex

BSindex = 0

While (BSTbl[BSindex +1]<BS)

BSindex = BSindex +1

## Endif

If (input <= XTbl[0])

Xindex = 0

Input = XTbl[0]

Else if (input >= XTbl[XSize -1])

Xindex = Xsize -2

input = XTbl[Xsize -1]

Xindex = 0

While ( XTbl[Xindex + 1] < input)

Xindex= Xindex + 1

## Endif

ArrayIndex1 = (BSindex * Xsize) + Xindex

ArrayIndex2 = (BSindex * Xsize) + Xindex + 1

ArrayIndex3 = ((BSindex + 1)* Xsize) + Xindex

ArrayIndex4 = ((BSindex + 1)* Xsize) + Xindex + 1

BSInputDiff = BS

BSTbl[BSindex]

XInputDiff = input

XTbl[Xindex]

Numerator_f32 = ( YMTbl[ArrayIndex2]

YMTbl[ArrayIndex1]) *

((BSTbl [ BSindex + 1]

BSTbl[BSindex]) * XInputDiff) +

(YMTbl [ ArrayIndex3]

YMTbl[ArrayIndex1]) *

(BSInputDiff * (XTbl[Xindex+1]

XTbl[Xindex])) +

(XInputDiff * BSInputDiff) *

((YMTbl[ArrayIndex4])

(YMTbl[ArrayIndex3])

(YMTbl[ArrayIndex2]

YMTbl[ArrayIndex1]))

Denominator_f32 = (BSTbl[BSindex+1]

BSTbl[BSindex]) * (XTbl[Xindex+1]

XTbl[Xindex])

If (Denominator_f32 <= FLT_EPSILON)

Output_u16 = YMTbl[ArrayIndex1] + 0.5

Output_u16 = YMTbl[ArrayIndex1] + (Numerator_f32 / Denominator_f32) + 0.5

## Endif

return Output_u16

Syntax: BilinearXYM_s16_s16Xs16YM_Cnt (BS, input, *BSTbl, BSize, *XTbl, *YMTbl, Xsize)

Arguments:

BS:- Bilinear Selector

Input:-The input to the table

BSTbl:- Bilinear Selector Table 2D

BSize:- Bilinear Selector Table Size

XTbl:- Table X 2D

YMTbl:- Table Y with MxN dimension

Xsize:- Size of XTbl

Output:- The output from the table

Pseudo Code:

UINT16

## BSindex, Xindex

UINT16

ArrayIndex1, ArrayIndex2, ArrayIndex3, ArrayIndex4

SINT32

## BSinputDiff, XInputDiff

FLOAT32

Numerator_f32, Denominator_f32, Output_f32

SINT16
