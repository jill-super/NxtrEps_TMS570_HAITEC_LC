---
title: "Motor Driver and Phase Diagnostics (SVDiag)"
description: "Motor Driver and Phase Diagnostics: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This module compares the commanded duty cycle to each phase with the feedback from the NHET module.  The values are compared, compensated with a previously defined fixed value, filtered, and compared against a valid threshold.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `SVDiag/src/Ap_DigPhsReasDiag.c` | implementation |
| `SVDiag/src/Sa_MtrDrvDiag.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `PhaseGroundTabLookupoffset`
- `Read_CountToRev`
- `DigPhsReasDiag_Init`
- `DigPhsReasDiag_Per1`
- `DigPhsReasDiag_Trans1`
- `MotorDriverInit`
- `ProcGateDriveFlt`
- `ProcBridgeFlt`
- `ReadMtrDrvFltData`
- `ResetGateDrive`
- `GateDrvWaitTime`
- `MtrDrvDiag_Per1`
- `MtrDrvDiag_Per2`
- `MtrDrvDiag_Trns1`


**Notable header dependencies:** `Ap_DigPhsReasDiag_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Os.h`, `Rte_Ap_DigPhsReasDiag.h`, `Rte_Sa_MtrDrvDiag.h`, `Sa_MtrDrvDiag_Cfg.h`, `filters.h`, `fixmath.h`

## Documents

- [DigPhsReasDiag Module Design Document](documents/digphsreasdiag-mdd) — converted from `SVDiag/doc/DigPhsReasDiag_MDD.docx`
- [Motor Driver Diagnostics Module Design Document](documents/motor-driver-diagnostics-mdd) — converted from `SVDiag/doc/Motor_Driver_Diagnostics_MDD.docx`
- [SVDiag Integration Manual](documents/svdiag-integration-manual) — converted from `SVDiag/doc/SVDiag_Integration_Manual.docx`

## Repository location

All files live under `SVDiag/` at the repository root.
