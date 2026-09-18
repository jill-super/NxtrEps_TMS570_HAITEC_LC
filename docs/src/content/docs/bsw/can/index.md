---
title: "Controller Area Network Driver (Can)"
description: "Vector MICROSAR Can: role, repository files and configuration."
---

<div class="origin-badges">
  <span class="origin-badge origin-vector">Vector-provided (MICROSAR)</span>
</div>
## Role

Low-level Controller Area Network driver for the TMS570 DCAN peripheral (Target: TMS470/TMS570 DCAN).

:::note[Origin: Vector-provided (MICROSAR)]
This module is part of the Vector MICROSAR Basic Software delivery. Sources are proprietary to Vector Informatik GmbH and are integrated — not developed — in this repository. Configuration is generated with the DaVinci/GENy tooling for this Electronic Control Unit.
:::

## Repository files

| File |
| --- |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/Can/Can.c` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/Can/Can.h` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/Can/Can_Hooks.h` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/Can/Can_Irq.c` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/Can/canproto.h` |

_The module directory holds 9 tracked files._

## Generated configuration (GenData)

The following generated files configure this module for the steering Electronic Control Unit:

- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/CanIf_CanTrcv.h`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/CanIf_Cfg.h`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/CanIf_Lcfg.c`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/CanIf_PBcfg.c`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/CanSM_Cfg.h`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/CanSM_Lcfg.c`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/CanSM_PBcfg.c`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/CanTp_Cfg.c`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/CanTp_Cfg.h`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/CanTp_Lcfg.c`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/CanTp_Lcfg.h`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/CanTp_PBcfg.c`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/CanTp_PBcfg.h`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/CanXCPAsr.a2l`

## Reference documents

- [TechnicalReference Asr CanIf](../documents/technicalreference-asr-canif) — converted from `Haitec_LC_EPS_TMS570/HLDD/BSW/TechnicalReference_Asr_CanIf.pdf`
- [TechnicalReference Asr CanSM](../documents/technicalreference-asr-cansm) — converted from `Haitec_LC_EPS_TMS570/HLDD/BSW/TechnicalReference_Asr_CanSM.pdf`
- [TechnicalReference Asr CanTp](../documents/technicalreference-asr-cantp) — converted from `Haitec_LC_EPS_TMS570/HLDD/BSW/TechnicalReference_Asr_CanTp.pdf`
- [TechnicalReference Asr CanXcp](../documents/technicalreference-asr-canxcp) — converted from `Haitec_LC_EPS_TMS570/HLDD/BSW/TechnicalReference_Asr_CanXcp.pdf`
- [TechnicalReference DrvCanAsr Tms470 Dcan](../documents/technicalreference-drvcanasr-tms470-dcan) — converted from `Haitec_LC_EPS_TMS570/HLDD/BSW/TechnicalReference_DrvCanAsr_Tms470_Dcan.pdf`

