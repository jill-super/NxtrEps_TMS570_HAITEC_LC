---
title: "Non-Volatile Memory Manager (NvMMgr)"
description: "Non-Volatile Memory Manager: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This module contains the specific interfacing functions that are needed for TI’s Fee Driver.  This includes an initialization routine and configurable trusted function interfaces that allow compatibility with the NvM/MemIf BSW.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `NvMMgr/src/Cd_FeeIf.c` | implementation |
| `NvMMgr/src/Fapi_UserDefinedFunctions.c` | implementation |
| `NvMMgr/include/Cd_FeeIf.h` | public interface |

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `FeeIf_Init`


**Public interface declarations** (from headers):

- `FeeIf_Init`
- `TWrapC_FeeIf_Init`
- `TRUSTED_TWrapS_FeeIf_Init`
- `TWrapC_Fee_MainFunction`
- `TRUSTED_TWrapS_Fee_MainFunction`
- `TWrapC_Fee_Read`
- `TRUSTED_TWrapS_Fee_Read`
- `TWrapC_Fee_Write`
- `TRUSTED_TWrapS_Fee_Write`
- `TWrapC_Fee_EraseImmediateBlock`
- `TRUSTED_TWrapS_Fee_EraseImmediateBlock`
- `TWrapC_Fee_InvalidateBlock`
- `TRUSTED_TWrapS_Fee_InvalidateBlock`
- `TWrapC_Fee_Cancel`
- `TRUSTED_TWrapS_Fee_Cancel`
- `TWrapC_Fee_GetStatus`
- `TRUSTED_TWrapS_Fee_GetStatus`
- `TWrapC_Fee_GetJobResult`


**Notable header dependencies:** `Cd_FeeIf.h`, `F021.h`

## Documents

- [Fee Interface Module Design Document](documents/fee-interface-mdd) — converted from `NvMMgr/doc/Fee_Interface_MDD.docx`
- [NvMMgr Integration Manual](documents/nvmmgr-integration-manual) — converted from `NvMMgr/doc/NvMMgr_Integration_Manual.docx`

## Repository location

All files live under `NvMMgr/` at the repository root.
