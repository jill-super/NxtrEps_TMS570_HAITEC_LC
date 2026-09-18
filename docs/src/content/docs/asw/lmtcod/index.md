---
title: "Limiter Conditioning (LmtCod)"
description: "Limiter Conditioning: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This MDD describes the summation of all assist and limit terms used in an Electric Power Steering application.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `LmtCod/src/Ap_LmtCod.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `LmtCod_Per1`


**Notable header dependencies:** `Ap_LmtCod_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `Interpolation.h`, `MemMap.h`, `Rte_Ap_LmtCod.h`, `fixmath.h`, `fpmtype.h`

## Documents

- [Limiter Conditioning Module Design Document](documents/limiter-conditioning-mdd) — converted from `LmtCod/doc/Limiter_Conditioning_MDD.doc`

## Repository location

All files live under `LmtCod/` at the repository root.
