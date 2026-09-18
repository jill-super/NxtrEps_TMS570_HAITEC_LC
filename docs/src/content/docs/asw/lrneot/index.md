---
title: "End-of-Travel Learning (LrnEOT)"
description: "End-of-Travel Learning: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

The End-of-Travel Learning software component (LrnEOT) implements part of the electric power steering function on the TMS570 microcontroller.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `LrnEOT/src/Ap_LrnEOT.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `ResetEOT`
- `LrnEOT_Init1`
- `LrnEOT_Per1`
- `LrnEOT_Scom_ResetEOT`


**Notable header dependencies:** `Ap_LrnEOT_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_LrnEOT.h`

## Documents

- [LearnEOT](documents/learneot) — converted from `LrnEOT/doc/LearnEOT.docx`
- [LrnEOT Integration Manual](documents/lrneot-integration-manual) — converted from `LrnEOT/doc/LrnEOT_Integration_Manual.docx`
- [Unit-Test Report (with Power Steering)](documents/index-withps) — converted from `LrnEOT/utp/Tessy/report/index_WithPS.pdf`
- [Unit-Test Report (without Power Steering)](documents/index-withoutps) — converted from `LrnEOT/utp/Tessy/report/index_WithOutPS.pdf`

## Repository location

All files live under `LrnEOT/` at the repository root.
