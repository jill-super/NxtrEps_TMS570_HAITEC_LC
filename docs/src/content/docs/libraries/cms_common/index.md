---
title: "Common Manufacturing Services (CMS_Common)"
description: "Common Manufacturing Services: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
  <span class="origin-badge">Contains Vector SIP adaptation</span>
</div>
## Purpose

Implementation of CMS Common

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `CMS_Common/src/EPS_DiagSrvcs_ISO.c` | implementation |
| `CMS_Common/src/EPS_DiagSrvcs_XCP.Vector.c` | implementation |
| `CMS_Common/src/EPS_DiagSrvcs_XCP.c` | implementation |
| `CMS_Common/include/EPS_DiagSrvcs_CommonData.h` | public interface |
| `CMS_Common/include/EPS_DiagSrvcs_ISO.h` | public interface |
| `CMS_Common/include/EPS_DiagSrvcs_SrvcLUTbl.h` | public interface |
| `CMS_Common/include/EPS_DiagSrvcs_XCP.h` | public interface |

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `EPS_DiagSessionChangeIndicator`
- `EPSDiagSrvcs_Task`
- `EPS_DiagSrvcs_Init`
- `NxtrMEC_Init`
- `DiagSrvcs_MainHandler`
- `DiagSrvcs_PIDIdxSearch`
- `DiagSrvcs_ConfiguredNrcCheck`
- `DiagSrvcs_NRCTranslate`
- `DiagSrvNullFunc`
- `HandsOnDetection`
- `F00FCheckConditions`
- `ProcessF0FF`
- `EPSInternal_RESET_1160`
- `EPSInternal_RID_F000`
- `EPSInternal_RID_F001`
- `EPSInternal_RID_F002`
- `EPSInternal_RID_F003`
- `EPSInternal_RID_F004`


**Public interface declarations** (from headers):

- `UNC`
- `DiagSrvcs_PIDIdxSearch`
- `DiagSrvcs_ConfiguredNrcCheck`
- `DiagSrvcs_NRCTranslate`
- `HandsOnDetection`
- `F00FCheckConditions`
- `ProcessF0FF`
- `ProcessXCPPID`
- `XcpUserDynamicDaqSetup`
- `XcpUserStaticDaqSetup`
- `XcpUserRoutineCmd`
- `XcpUserPIDSrvc`
- `XcpPIDReadResp`
- `XcpErrorHandler`
- `XcpODTEntrySetup`
- `XcpISOErrorConverter`
- `StaticDAQ_ManufSrvc_MtrLearning`
- `StaticDAQ_ManufSrvc_TrqRatio`


**Notable header dependencies:** `EPS_DiagSrvcs_CommonData.h`, `EPS_DiagSrvcs_ISO.h`, `EPS_DiagSrvcs_SrvcLUTbl.h`, `EPS_DiagSrvcs_XCP.h`, `MemMap.h`, `SystemTime.h`, `tiotp_regs.h`

## Documents

_No converted design documents are attached to this page. Original Word, PDF or text documents (if any) remain in the repository._

## Repository location

All files live under `CMS_Common/` at the repository root.
