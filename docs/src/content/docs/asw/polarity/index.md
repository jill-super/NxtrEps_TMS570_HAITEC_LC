---
title: "Signal Polarity Management (Polarity)"
description: "Signal Polarity Management: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This module implements the polarity assignments for the EPS systems to allow for various configurations of input and output signals for proper alignment.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `Polarity/src/Ap_Polarity.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `GetPolarity`
- `Polarity_Init1`
- `Polarity_Per1`
- `Polarity_SCom_ReadPolarity`
- `Polarity_SCom_SetPolarity`


**Notable header dependencies:** `Ap_Polarity_Cfg.h`, `MemMap.h`, `Os.h`, `Rte_Ap_Polarity.h`

## Documents

- [Polarity Module Design Document](documents/polarity-mdd) — converted from `Polarity/doc/Polarity_MDD.docx`

## Repository location

All files live under `Polarity/` at the repository root.
