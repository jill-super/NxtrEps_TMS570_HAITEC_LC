---
title: "TMS570 Microcontroller Diagnostics (TMS570_uDiag)"
description: "TMS570 Microcontroller Diagnostics: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

Cd_uDiagFPU provides diagnostic data on floating point exceptions.  Based on “Unreleased draft of EA3.x FDD 32.5 uC Diagnostics Execution (0x02A-0x031) v002.docx” as saved on May 7, 2013 and “Unreleased Draft of EA3.x FDD 32.Appendices v002.docx” as saved on May 6, 2013.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `TMS570_uDiag/src/AbortHandler.c` | implementation |
| `TMS570_uDiag/src/Cd_uDiagCCRM.c` | implementation |
| `TMS570_uDiag/src/Cd_uDiagClockMonitor.c` | implementation |
| `TMS570_uDiag/src/Cd_uDiagECC.c` | implementation |
| `TMS570_uDiag/src/Cd_uDiagESM.c` | implementation |
| `TMS570_uDiag/src/Cd_uDiagFPU.c` | implementation |
| `TMS570_uDiag/src/Cd_uDiagIOMM.c` | implementation |
| `TMS570_uDiag/src/Cd_uDiagLossOfExec.c` | implementation |
| `TMS570_uDiag/src/Cd_uDiagParity.c` | implementation |
| `TMS570_uDiag/src/Cd_uDiagPeriphMPU.c` | implementation |
| `TMS570_uDiag/src/Cd_uDiagResetHandler.c` | implementation |
| `TMS570_uDiag/src/Cd_uDiagStaticRegs.c` | implementation |
| `TMS570_uDiag/src/Cd_uDiagUtility.asm` | implementation |
| `TMS570_uDiag/src/Cd_uDiagVIM.c` | implementation |
| `TMS570_uDiag/include/Cd_uDiagUtility.h` | public interface |
| `TMS570_uDiag/include/FlsTst.h` | public interface |
| `TMS570_uDiag/include/RednRpdShtdn.h` | public interface |
| `TMS570_uDiag/include/uDiag.h` | public interface |

_Showing a selection; the area contains 22 source files and 4 headers in total._

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `AbortHandler`
- `uDiagCCRM_Init`
- `CCRMErr`
- `uDiagClockMonitor_Init`
- `ClockMonitorErr`
- `DCCErr`
- `uDiagECC_Per`
- `uDiagECC_Init`
- `FlashECCCorrErr`
- `RAMECCCorrErr`
- `FlashECCUncorrErr`
- `RAMECCUncorrErr`
- `FlashECCLiveLockErr`
- `uDiagECC_RednRpdShtdn`
- `uDiagESM_Init`
- `uDiagFPU_Init1`
- `uDiagFPU_Init2`
- `uDiagIOMM_Init`


**Public interface declarations** (from headers):

- `FlsTst_MainFunction`
- `FlsTst_TestCompleted`
- `FlsTst_Init`
- `FlsTst_DeInit`
- `FlsTst_StartFgnd`
- `FlsTst_GetTestResultBgnd`
- `FlsTst_GetTestResultFgnd`
- `FlsTst_Abort`
- `FlsTst_Suspend`
- `FlsTst_Resume`
- `FlsTst_GetCurrentState`
- `FlsTst_GetTestSignatureBgnd`
- `FlsTst_GetTestSignatureFgnd`
- `FlsTst_GetErrorDetails`
- `FlsTst_TestEcc`
- `UNC`
- `NHETParityErr`
- `NHET2ParityErr`


**Notable header dependencies:** `Ap_DiagMgr.h`, `CalConstants.h`, `Cd_uDiagUtility.h`, `Dma.h`, `FlsTst.h`, `GlobalMacro.h`, `Interrupts.h`, `MemMap.h`, `Nhet.h`, `Os.h`, `RednRpdShtdn.h`, `ResetCause.h`, `Rte_Cd_uDiag.h`, `Std_Types.h`, `WdgM.h`, `adc_regs.h`

## Documents

- [Cd uDiag Integration Manual](documents/cd-udiag-integration-manual) — converted from `TMS570_uDiag/doc/Cd_uDiag_Integration_Manual.docx`
- [Cd uDiagFPU Module Design Document](documents/cd-udiagfpu-mdd) — converted from `TMS570_uDiag/doc/Cd_uDiagFPU_MDD.docx`
- [Cd uDiagUtility Module Design Document](documents/cd-udiagutility-mdd) — converted from `TMS570_uDiag/doc/Cd_uDiagUtility_MDD.docx`
- [FlsTst Integration Manual](documents/flstst-integration-manual) — converted from `TMS570_uDiag/doc/FlsTst_Integration_Manual.docx`
- [FlsTst Module Design Document](documents/flstst-mdd) — converted from `TMS570_uDiag/doc/FlsTst_MDD.docx`
- [OsErrCallouts Module Design Document](documents/oserrcallouts-mdd) — converted from `TMS570_uDiag/doc/OsErrCallouts_MDD.docx`

## Repository location

All files live under `TMS570_uDiag/` at the repository root.
