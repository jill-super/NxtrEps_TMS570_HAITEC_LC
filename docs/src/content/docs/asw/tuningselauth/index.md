---
title: "Tuning Selection Authority (TuningSelAuth)"
description: "Tuning Selection Authority: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This function broadcasts an authority to allow switching between calibration subsets while driving.  It compares handwheel torque and vehicle speed to calibratable thresholds and outputs either a zero or a one.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `TuningSelAuth/src/Ap_TuningSelAuth.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `TuningSelAuth_Init1`
- `TuningSelAuth_Per1`


**Notable header dependencies:** `Ap_TuningSelAuth_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_TuningSelAuth.h`, `XcpProf.h`, `filters.h`

## Documents

- [Tuning Select Authority Module Design Document](documents/tuning-select-authority-mdd) — converted from `TuningSelAuth/doc/Tuning_Select_Authority_MDD.docx`

## Repository location

All files live under `TuningSelAuth/` at the repository root.
