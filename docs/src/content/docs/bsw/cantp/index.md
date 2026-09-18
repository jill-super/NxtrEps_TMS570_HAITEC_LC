---
title: "Controller Area Network Transport Protocol (CanTp)"
description: "Vector MICROSAR CanTp: role, repository files and configuration."
---

<div class="origin-badges">
  <span class="origin-badge origin-vector">Vector-provided (MICROSAR)</span>
</div>
## Role

Transport protocol for segmented (multi-frame) diagnostic communication over CAN (ISO 15765-2).

:::note[Origin: Vector-provided (MICROSAR)]
This module is part of the Vector MICROSAR Basic Software delivery. Sources are proprietary to Vector Informatik GmbH and are integrated — not developed — in this repository. Configuration is generated with the DaVinci/GENy tooling for this Electronic Control Unit.
:::

## Repository files

| File |
| --- |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/CanTp/CanTp.c` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/CanTp/CanTp.h` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/CanTp/CanTp_Cbk.h` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/CanTp/CanTp_Hooks.h` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/CanTp/CanTp_Priv.h` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/CanTp/CanTp_Types.h` |

_The module directory holds 10 tracked files._

## Generated configuration (GenData)

The following generated files configure this module for the steering Electronic Control Unit:

- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/CanTp_Cfg.c`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/CanTp_Cfg.h`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/CanTp_Lcfg.c`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/CanTp_Lcfg.h`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/CanTp_PBcfg.c`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/CanTp_PBcfg.h`

## Reference documents

- [TechnicalReference Asr CanTp](../documents/technicalreference-asr-cantp) — converted from `Haitec_LC_EPS_TMS570/HLDD/BSW/TechnicalReference_Asr_CanTp.pdf`

