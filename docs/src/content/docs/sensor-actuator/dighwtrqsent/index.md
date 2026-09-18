---
title: "Digital Handwheel Torque via SENT (DigHwTrqSENT)"
description: "Digital Handwheel Torque via SENT: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This module computes the digital handwheel torque signal from the SENT digital sensor inputs.  It takes the sensor inputs, calculates the hw torque, compensates for trim,  applies filtering and limits, and outputs the handwheel torque in HwNm.  It uses long term correlated compensation to provide a T1 vs T2 correlation fault diagnostic.  It also contains the service calls for a trim to be set or cleared.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `DigHwTrqSENT/src/Sa_DigHwTrqSENT.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `TrimNotPerfDiag`
- `DigHwTrqSENT_Init1`
- `DigHwTrqSENT_Per1`
- `DigHwTrqSENT_Per2`
- `DigHwTrqSENT_Per3`
- `DigHwTrqSENT_SCom_ClrTrqTrim`
- `DigHwTrqSENT_SCom_SetTrqTrim`
- `DigHwTrqSENT_SCom_TrimData`
- `DigHwTrqSENT_SCom_WriteData`


**Notable header dependencies:** `Ap_DiagMgr.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Sa_DigHwTrqSENT.h`, `Sa_DigHwTrqSENT_Cfg.h`, `filters.h`, `fixmath.h`, `interpolation.h`

## Documents

- [DigHwTrqSENT Integration Manual](documents/dighwtrqsent-integration-manual) — converted from `DigHwTrqSENT/doc/DigHwTrqSENT_Integration_Manual.docx`
- [DigHwTrqSENT Module Design Document](documents/dighwtrqsent-mdd) — converted from `DigHwTrqSENT/doc/DigHwTrqSENT_MDD.docx`
- [Unit-Test Report ((skipped cases) with Power Steering with Fault Injection)](documents/index-skipped-withps-fltinj) — converted from `DigHwTrqSENT/utp/Tessy/report/index_Skipped_WithPS_FLTINJ.pdf`
- [Unit-Test Report (with Power Steering with Fault Injection)](documents/index-withps-fltinj) — converted from `DigHwTrqSENT/utp/Tessy/report/index_WithPS_FLTINJ.pdf`
- [Unit-Test Report (with Power Steering)](documents/index-withps) — converted from `DigHwTrqSENT/utp/Tessy/report/index_WithPS.pdf`
- [Unit-Test Report (without Power Steering with Fault Injection)](documents/index-withoutps-fltinj) — converted from `DigHwTrqSENT/utp/Tessy/report/index_WithOutPS_FLTINJ.pdf`
- [Unit-Test Report (without Power Steering)](documents/index-withoutps) — converted from `DigHwTrqSENT/utp/Tessy/report/index_WithOutPS.pdf`

## Repository location

All files live under `DigHwTrqSENT/` at the repository root.
