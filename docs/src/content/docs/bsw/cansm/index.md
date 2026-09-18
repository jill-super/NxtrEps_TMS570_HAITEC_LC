---
title: "Controller Area Network State Manager (CanSM)"
description: "Vector MICROSAR CanSM: role, repository files and configuration."
---

<div class="origin-badges">
  <span class="origin-badge origin-vector">Vector-provided (MICROSAR)</span>
</div>
## Role

State manager for the CAN network (bus sleep/wake handling together with the Communication Manager).

:::note[Origin: Vector-provided (MICROSAR)]
This module is part of the Vector MICROSAR Basic Software delivery. Sources are proprietary to Vector Informatik GmbH and are integrated — not developed — in this repository. Configuration is generated with the DaVinci/GENy tooling for this Electronic Control Unit.
:::

## Repository files

| File |
| --- |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/CanSM/CanSM.c` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/CanSM/CanSM.h` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/CanSM/CanSM_BswM.h` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/CanSM/CanSM_Cbk.h` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/CanSM/CanSM_ComM.h` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/CanSM/CanSM_EcuM.h` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/CanSM/CanSM_SchM.h` |

_The module directory holds 11 tracked files._

## Generated configuration (GenData)

The following generated files configure this module for the steering Electronic Control Unit:

- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/CanSM_Cfg.h`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/CanSM_Lcfg.c`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/CanSM_PBcfg.c`

## Reference documents

- [TechnicalReference Asr CanSM](../documents/technicalreference-asr-cansm) — converted from `Haitec_LC_EPS_TMS570/HLDD/BSW/TechnicalReference_Asr_CanSM.pdf`

