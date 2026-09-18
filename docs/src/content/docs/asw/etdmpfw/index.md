---
title: "End-of-Travel Damping Firewall (EtDmpFw)"
description: "End-of-Travel Damping Firewall: purpose, files, interfaces and documents."
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
| `EtDmpFw/src/Ap_EtDmpFw.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `EtDmpFw_Per1`


**Notable header dependencies:** `Ap_EtDmpFw_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_EtDmpFw.h`, `fixmath.h`, `fpmtype.h`, `interpolation.h`

## Documents

- [EOTDampingFirewall Module Design Document](documents/eotdampingfirewall-mdd) — converted from `EtDmpFw/doc/EOTDampingFirewall_MDD.doc`
- [Unit-Test Report (with Power Steering with Fault Injection)](documents/index-withps-fltinj) — converted from `EtDmpFw/utp/Tessy/report/index_WithPS_FLTINJ.pdf`
- [Unit-Test Report (with Power Steering)](documents/index-withps) — converted from `EtDmpFw/utp/Tessy/report/index_WithPS.pdf`
- [Unit-Test Report (without Power Steering with Fault Injection)](documents/index-withoutps-fltinj) — converted from `EtDmpFw/utp/Tessy/report/index_WithOutPS_FLTINJ.pdf`
- [Unit-Test Report (without Power Steering)](documents/index-withoutps) — converted from `EtDmpFw/utp/Tessy/report/index_WithOutPS.pdf`

## Repository location

All files live under `EtDmpFw/` at the repository root.
