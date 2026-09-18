---
title: "Calibration Protocol Interface (XCP) (Xcp)"
description: "Calibration Protocol Interface (XCP): purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

The Calibration Protocol Interface (XCP) software component (Xcp) implements part of the electric power steering function on the TMS570 microcontroller.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `Xcp/src/Ap_ApXcp.c` | implementation |
| `Xcp/include/Ap_ApXcp.h` | public interface |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `XcpSetError`
- `CreateXcpCalSession`
- `GetPersIndexes`
- `GetSetIndexes`
- `EERead`
- `EEWrite`
- `CheckXcpAccess`
- `GetFcnIdx`
- `GetAppIdx`
- `ApXcp_Per1`
- `ApXcp_Init`
- `ApXcpWriteCommon`
- `ApplXcpGetPointer`
- `ApplXcpGetTimestamp`
- `ApplXcpReset`
- `ApplXcpFlashClear`
- `ApplXcpFlashProgram`
- `ApplXcpProgramStart`


**Public interface declarations** (from headers):

- `ApXcp_Init`
- `ApXcpWriteCommon`
- `CopyCalsToRam`


**Notable header dependencies:** `Ap_ApXcp.h`, `EPS_DiagSrvcs_SrvcLUTbl.h`, `EPS_DiagSrvcs_XCP.h`, `Eep_30_At25128.h`, `Mcu.h`, `MemMap.h`, `Rte_Ap_ApXcp.h`, `SystemTime.h`

## Documents

- [ApXcp Integration Manual](documents/apxcp-integration-manual) — converted from `Xcp/doc/ApXcp_Integration_Manual.docx`

## Repository location

All files live under `Xcp/` at the repository root.
