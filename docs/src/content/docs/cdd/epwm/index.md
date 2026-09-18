---
title: "Enhanced PWM and High-End Timer Driver (ePWM)"
description: "Enhanced PWM and High-End Timer Driver: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This module implements functionality with respect to  ES-34B ePWM.  This module implements the subfunctions other than the Motor Control Configuration Override subfunction and register initialization.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `ePWM/src/Ap_ePWM2.c` | implementation |
| `ePWM/src/Cd_Nhet1.c` | implementation |
| `ePWM/src/Nhet.c` | implementation |
| `ePWM/src/Nhet2_ePWM_Prog.c` | implementation |
| `ePWM/src/Nhet2_ePWM_Prog.het` | implementation |
| `ePWM/src/Nhet_SENT_Prog.c` | implementation |
| `ePWM/src/Nhet_SENT_Prog.het` | implementation |
| `ePWM/src/ePWM.c` | implementation |
| `ePWM/include/Nhet.h` | public interface |
| `ePWM/include/Nhet2_ePWM_Prog.h` | public interface |
| `ePWM/include/Nhet_SENT_Prog.h` | public interface |
| `ePWM/include/ePWM.h` | public interface |
| `ePWM/include/std_nhet.h` | public interface |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `ePWM2_Per1`
- `ePWM2_Trns1`
- `ePWM2_Trns2`
- `Nhet1_ProcessSENTData`
- `Nhet1_Per1`
- `Nhet1_Per2`
- `Nhet1_Per3`
- `HTU1_Init`
- `Nhet_Init1`
- `ePWM_Init1`
- `ePWM_Per1`


**Public interface declarations** (from headers):

- `Nhet_Init1`
- `Nhet1_Per3`
- `ePWM_Init1`
- `ePWM_Per1`


**Notable header dependencies:** `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Nhet.h`, `Nhet2_ePWM_Prog.h`, `Nhet_SENT_Prog.h`, `Rte_Ap_ePWM2.h`, `Rte_Cd_Nhet1.h`, `ePWM_Cfg.h`, `ePwm.h`, `htu_regs.h`, `std_nhet.h`

## Documents

- [CD NHET 1 Module Design Document](documents/cd-nhet-1-mdd) — converted from `ePWM/doc/CD_NHET_1_MDD.docx`
- [NHetRegisters](documents/nhetregisters) — converted from `ePWM/doc/NHetRegisters.pdf`
- [Nhet 1 Module Design Document](documents/nhet-1-mdd) — converted from `ePWM/doc/Nhet_1_MDD.docx`
- [RegisterReference EPWM](documents/registerreference-epwm) — converted from `ePWM/doc/RegisterReference_EPWM.pdf`
- [ePWM 1 Module Design Document](documents/epwm-1-mdd) — converted from `ePWM/doc/ePWM_1_MDD.docx`
- [ePWM 2 Module Design Document](documents/epwm-2-mdd) — converted from `ePWM/doc/ePWM_2_MDD.docx`
- [ePWM Integration Manual](documents/epwm-integration-manual) — converted from `ePWM/doc/ePWM_Integration_Manual.docx`

## Repository location

All files live under `ePWM/` at the repository root.
