---
title: "Space Vector PWM Driver (Current Mode) (SVDrvr_CM)"
description: "Space Vector PWM Driver (Current Mode): purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

For details on module input / output variable, refer to the Data Dictionary for the application.  Input / output variable names are listed here for reference.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `SVDrvr_CM/src/PwmCdd.c` | implementation |
| `SVDrvr_CM/include/PwmCdd.h` | public interface |

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `PwmPeriodDither_u16`
- `ModIndxPhase_u0p16`
- `PwmCdd_Init`
- `PwmCdd_Per1`
- `CDD_ApplyPWMMtrElecMechPol`
- `CDDPorts_ClearPhsReasSum`


**Public interface declarations** (from headers):

- `UNC`


**Notable header dependencies:** `CDD_Data.h`, `CDD_Func.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `PwmCdd.h`, `PwmCdd_Cfg.h`, `Std_Types.h`, `fixmath.h`

## Documents

- [PWM CDD Module Design Document](documents/pwm-cdd-mdd) — converted from `SVDrvr_CM/doc/PWM_CDD_MDD.docx`
- [PWMCdd Integration Manual](documents/pwmcdd-integration-manual) — converted from `SVDrvr_CM/doc/PWMCdd_Integration_Manual.docx`

## Repository location

All files live under `SVDrvr_CM/` at the repository root.
