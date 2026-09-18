---
title: "Damping Firewall Monitor (DampingFirewall)"
description: "Damping Firewall Monitor: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

For details on module input / output variable, refer to the Data Dictionary for the application. Input / output variable names are listed here for reference.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `DampingFirewall/src/Ap_DampingFirewall.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `DriverVelCalc`
- `ADDCoefCalc`
- `FilterCoefCalc`
- `GenFddIcCmd`
- `DampingFirewall_Init1`
- `DampingFirewall_Per1`


**Notable header dependencies:** `Ap_DampingFirewall_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_DampingFirewall.h`, `filters.h`, `fixmath.h`, `interpolation.h`

## Documents

- [Damping Firewall Module Design Document](documents/damping-firewall-mdd) — converted from `DampingFirewall/doc/Damping_Firewall_MDD.doc`

## Repository location

All files live under `DampingFirewall/` at the repository root.
