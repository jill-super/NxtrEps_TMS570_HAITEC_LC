---
title: "Direct Memory Access Driver (Dma)"
description: "Direct Memory Access Driver: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This section Lists the title & version of all the documents that are referred for development of this document

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `Dma/src/Dma.c` | implementation |
| `Dma/include/Dma.h` | public interface |

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `Dma_Init`
- `Dma_SlowADCGroupValidity`
- `Dma_InvalidateSlowADCGroup`
- `Dma_SetupMtrCtrlGroups`
- `Dma_SetupFlsTstBlock`
- `Dma_EnableFlsTstBlock`
- `Dma_DisableFlsTstBlock`


**Public interface declarations** (from headers):

- `UNC`


**Notable header dependencies:** `Dma.h`, `MemMap.h`, `dma_regs.h`

## Documents

- [Dma Integration Manual](documents/dma-integration-manual) — converted from `Dma/doc/Dma Integration Manual.docx`
- [Dma Module Design Document](documents/dma-mdd) — converted from `Dma/doc/Dma_MDD.docx`

## Repository location

All files live under `Dma/` at the repository root.
