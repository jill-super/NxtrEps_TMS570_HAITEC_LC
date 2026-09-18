---
title: "Nexteer Software Library (NxtrLib)"
description: "Nexteer Software Library: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

Syntax: BilinearXYM_s16_u16Xs16YM_Cnt (BS, input, *BSTbl, BSize, *XTbl, *YMTbl, Xsize)

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `NxtrLib/src/CheckSums.c` | implementation |
| `NxtrLib/src/SystemTime.c` | implementation |
| `NxtrLib/src/atan2.asm` | implementation |
| `NxtrLib/src/atan2_octants.c` | implementation |
| `NxtrLib/src/filters.c` | implementation |
| `NxtrLib/src/interpolation.c` | implementation |
| `NxtrLib/include/CheckSums.h` | public interface |
| `NxtrLib/include/Filter_Types.h` | public interface |
| `NxtrLib/include/GlobalMacro.h` | public interface |
| `NxtrLib/include/SystemTime.h` | public interface |
| `NxtrLib/include/atan2.h` | public interface |
| `NxtrLib/include/filters.h` | public interface |
| `NxtrLib/include/fixmath.h` | public interface |
| `NxtrLib/include/fpmtype.h` | public interface |
| `NxtrLib/include/interpolation.h` | public interface |

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `BMW_CRC`
- `DtrmnElapsedTime_uS_u16`
- `DtrmnElapsedTime_uS_u32`
- `DtrmnElapsedTime_mS_u16`
- `DtrmnElapsedTime_mS_u32`
- `GetSystemTime_uS_u32`
- `GetSystemTime_mS_u32`
- `SystemTime_Init`
- `SystemTime_Per1`
- `NF_Init_f32`


**Public interface declarations** (from headers):

- `UNC`
- `Blend_f32`
- `NF_SvUpdate_f32`
- `NF_OpUpdate_f32`
- `NF_FullUpdate_f32`
- `BilinearXYM_s16_u16Xs16YM_Cnt`
- `BilinearXYM_u16_u16Xu16YM_Cnt`
- `BilinearXYM_s16_s16Xs16YM_Cnt`
- `BilinearXYM_u16_s16Xu16YM_Cnt`
- `BilinearXMYM_u16_u16XMu16YM_Cnt`
- `BilinearXMYM_s16_u16XMs16YM_Cnt`
- `BilinearXMYM_s16_s16XMs16YM_Cnt`
- `BilinearXMYM_u16_s16XMu16YM_Cnt`
- `IntplVarXY_u16_u16Xu16Y_Cnt`
- `IntplVarXY_u16_s16Xu16Y_Cnt`
- `IntplVarXY_s16_s16Xs16Y_Cnt`
- `IntplVarXY_s16_u16Xs16Y_Cnt`
- `IntplFxdX_u16_u16Xu16Y_Cnt`


**Notable header dependencies:** `CheckSums.h`, `GlobalMacro.h`, `Gpt.h`, `Gpt_Cfg.h`, `MemMap.h`, `Rte_NexteerLibs.h`, `Std_Types.h`, `SystemTime.h`, `SystemTime_Cfg.h`, `filters.h`, `fixmath.h`, `fpmtype.h`

## Documents

- [Filter Library Design Document](documents/filter-library-design-document) — converted from `NxtrLib/doc/Filter_Library_Design_Document.doc`
- [Interpolation Design Module Design Document](documents/interpolation-design-mdd) — converted from `NxtrLib/doc/Interpolation_Design_MDD.doc`
- [NxtrLib Systemtime Integration Manual](documents/nxtrlib-systemtime-integration-manual) — converted from `NxtrLib/doc/NxtrLib_Systemtime Integration_Manual.docx`

## Repository location

All files live under `NxtrLib/` at the repository root.
