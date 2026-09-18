---
title: "Electronic Control Unit State Manager (EcuM)"
description: "Vector MICROSAR EcuM: role, repository files and configuration."
---

<div class="origin-badges">
  <span class="origin-badge origin-vector">Vector-provided (MICROSAR)</span>
</div>
## Role

Manages Electronic Control Unit states: startup, shutdown, sleep and wake-up.

:::note[Origin: Vector-provided (MICROSAR)]
This module is part of the Vector MICROSAR Basic Software delivery. Sources are proprietary to Vector Informatik GmbH and are integrated — not developed — in this repository. Configuration is generated with the DaVinci/GENy tooling for this Electronic Control Unit.
:::

## Repository files

| File |
| --- |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/EcuM/EcuM.c` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/EcuM/EcuM.h` |

_The module directory holds 2 tracked files._

## Generated configuration (GenData)

The following generated files configure this module for the steering Electronic Control Unit:

- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/EcuM_Cbk.h`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/EcuM_Cfg.h`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/EcuM_Generated_Types.h`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/EcuM_PBcfg.c`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/EcuM_PrivateCfg.h`

## Reference documents

- [TechnicalReference Asr EcuM](../documents/technicalreference-asr-ecum) — converted from `Haitec_LC_EPS_TMS570/HLDD/BSW/TechnicalReference_Asr_EcuM.pdf`

