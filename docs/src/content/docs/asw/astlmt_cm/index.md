---
title: "Assist Summation Limiter (Current Mode) (AstLmt_CM)"
description: "Assist Summation Limiter (Current Mode): purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This module combines and limits the various assist command signals from EPS modules.  It puts out several torque commands from different points in the summation and limiting process.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `AstLmt_CM/src/Ap_AstLmt.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `AstLmt_Init`
- `AstLmt_Per1`
- `AstLmt_Scom_GetSteeringAssistDefeat`
- `AstLmt_Scom_ManualTrqCmd`
- `AstLmt_Scom_SetSteeringAssistDefeat`


**Notable header dependencies:** `Ap_AstLmt_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_AstLmt.h`

## Documents

- [Assist Sum Limit CurrentMode Module Design Document](documents/assist-sum-limit-currentmode-mdd) — converted from `AstLmt_CM/doc/Assist_Sum_Limit_CurrentMode_MDD.docx`
- [AstLmt CM IntegrationManual](documents/astlmt-cm-integrationmanual) — converted from `AstLmt_CM/doc/AstLmt_CM_IntegrationManual.docx`
- [Unit-Test Report (with Power Steering)](documents/index-withps) — converted from `AstLmt_CM/utp/Tessy/report/index_WithPS.pdf`
- [Unit-Test Report (without Power Steering)](documents/index-withoutps) — converted from `AstLmt_CM/utp/Tessy/report/index_WithOutPS.pdf`

## Repository location

All files live under `AstLmt_CM/` at the repository root.
