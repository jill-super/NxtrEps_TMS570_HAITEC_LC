---
title: "Compliance Error Manager (ComplErr)"
description: "Compliance Error Manager: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This function calculates the compliance error that can be used to compensate for stiffness in the torque path between the motor position sensor and column axis.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `ComplErr/src/Ap_ComplErr.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `ComplErr_Per1`


**Notable header dependencies:** `Ap_ComplErr_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_ComplErr.h`, `fixmath.h`, `interpolation.h`

## Documents

- [ComplErr Integration Manual](documents/complerr-integration-manual) — converted from `ComplErr/doc/ComplErr_Integration_Manual.docx`
- [Compliance Error Module Design Document](documents/compliance-error-mdd) — converted from `ComplErr/doc/Compliance_Error_MDD.docx`

## Repository location

All files live under `ComplErr/` at the repository root.
