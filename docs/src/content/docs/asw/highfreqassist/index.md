---
title: "High-Frequency Assist (HighFreqAssist)"
description: "High-Frequency Assist: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This module compensates for system inertia and road feedback.  It puts handwheel torque through a high-pass filter and multiplies it by a tunable gain parameter to compensate for these factors.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `HighFreqAssist/src/Ap_HighFreqAssist.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `HighFreqAssist_Per1`


**Notable header dependencies:** `Ap_HighFreqAssist_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_HighFreqAssist.h`, `filters.h`, `fixmath.h`, `interpolation.h`

## Documents

- [High Frequency Assist Module Design Document](documents/high-frequency-assist-mdd) — converted from `HighFreqAssist/doc/High_Frequency_Assist_MDD.docx`
- [HighFreqAssist Integration Manual](documents/highfreqassist-integration-manual) — converted from `HighFreqAssist/doc/HighFreqAssist_Integration_Manual.docx`

## Repository location

All files live under `HighFreqAssist/` at the repository root.
