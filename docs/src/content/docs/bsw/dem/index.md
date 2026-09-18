---
title: "Diagnostic Event Manager (Dem)"
description: "Vector MICROSAR Dem: role, repository files and configuration."
---

<div class="origin-badges">
  <span class="origin-badge origin-vector">Vector-provided (MICROSAR)</span>
</div>
## Role

Stores and manages diagnostic events, debouncing, freeze frames and fault memory.

:::note[Origin: Vector-provided (MICROSAR)]
This module is part of the Vector MICROSAR Basic Software delivery. Sources are proprietary to Vector Informatik GmbH and are integrated — not developed — in this repository. Configuration is generated with the DaVinci/GENy tooling for this Electronic Control Unit.
:::

## Repository files

| File |
| --- |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/Dem/Dem.c` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/Dem/Dem.h` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/Dem/Dem_Types.h` |

_The module directory holds 7 tracked files._

## Generated configuration (GenData)

The following generated files configure this module for the steering Electronic Control Unit:

- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/Dem_Cbk.h`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/Dem_Cfg.h`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/Dem_IntErrId.h`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/Dem_IntEvtId.h`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/Dem_Lcfg.c`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/Dem_Lcfg.h`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/Dem_PBcfg.c`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/Dem_PBcfg.h`

## Reference documents

- [TechnicalReference Asr Dem](../documents/technicalreference-asr-dem) — converted from `Haitec_LC_EPS_TMS570/HLDD/BSW/TechnicalReference_Asr_Dem.pdf`

