---
title: "Diagnostic Manager (DiagMgr)"
description: "Diagnostic Manager: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

Note Size and elements of Table constants varies across projects. Check project configuration files Under UTP/ Contract folder for data.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `DiagMgr/src/Ap_DiagMgr_Core.c` | implementation |
| `DiagMgr/src/Ap_DiagMgr_DemIf.c` | implementation |
| `DiagMgr/src/Ap_DiagMgr_FailAction.c` | implementation |
| `DiagMgr/include/Ap_DiagMgr.h` | public interface |
| `DiagMgr/include/Ap_DiagMgr_Types.h` | public interface |

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `FailedCheckAndProcessing`
- `ProcessRampResponse`
- `ProcessDiagSts`
- `SetBits_u8`
- `ClrBits_u8`
- `ReadBit_u8`
- `ReadBit_u32`
- `SetBits_u16`
- `DiagMgr_Init_Core`
- `DiagMgr_Per_Core`
- `DiagMgr_Trns_Core`
- `NxtrDiagMgr_GetNTCFailed_Core`
- `NxtrDiagMgr_GetNTCActive_Core`
- `NxtrDiagMgr_GetNTCStatus_Core`
- `NxtrDiagMgr_SetNTCStatus_Core`
- `NxtrDiagMgr_ReportNTCStatus_Core`
- `CreateStorageArray`
- `DiagMgr_Init1`


**Public interface declarations** (from headers):

- `UNC`


**Notable header dependencies:** `Ap_DiagMgr.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `NvM.h`, `Os.h`, `Std_Types.h`, `fixmath.h`

## Documents

- [Diagnostics Manager Core Module Design Document](documents/diagnostics-manager-core-mdd) — converted from `DiagMgr/doc/Diagnostics_Manager_Core_MDD.docx`
- [Diagnostics Manager DemIf Module Design Document](documents/diagnostics-manager-demif-mdd) — converted from `DiagMgr/doc/Diagnostics_Manager_DemIf_MDD.docx`
- [Diagnostics Manager FailAction Module Design Document](documents/diagnostics-manager-failaction-mdd) — converted from `DiagMgr/doc/Diagnostics_Manager_FailAction_MDD.docx`
- [Diagnostics Manager GeneratedCfg Module Design Document](documents/diagnostics-manager-generatedcfg-mdd) — converted from `DiagMgr/doc/Diagnostics_Manager_GeneratedCfg_MDD.docx`

## Repository location

All files live under `DiagMgr/` at the repository root.
