---
title: "Hardware Power-Up Sequencing (HwPwUp)"
description: "Hardware Power-Up Sequencing: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This module controls the startup initialization sequence for several modules that would otherwise conflict with one another.  It uses a series of boolean inputs and outputs to control these modules.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `HwPwUp/src/Ap_HwPwUp.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `HwPwUp_Per1`
- `HwPwUp_Trns1`
- `HwPwUp_Trns2`


**Notable header dependencies:** `Ap_HwPwUp_Cfg.h`, `CalConstants.h`, `MemMap.h`, `Rte_Ap_HwPwUp.h`

## Documents

- [Hardware Power Up Module Design Document](documents/hardware-power-up-mdd) — converted from `HwPwUp/doc/Hardware_Power_Up_MDD.docx`
- [HwPwUp Integration Manual](documents/hwpwup-integration-manual) — converted from `HwPwUp/doc/HwPwUp_Integration_Manual.docx`

## Repository location

All files live under `HwPwUp/` at the repository root.
