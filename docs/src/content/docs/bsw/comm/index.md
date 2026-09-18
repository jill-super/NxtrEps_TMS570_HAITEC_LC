---
title: "Communication Manager (ComM)"
description: "Vector MICROSAR ComM: role, repository files and configuration."
---

<div class="origin-badges">
  <span class="origin-badge origin-vector">Vector-provided (MICROSAR)</span>
</div>
## Role

Coordinates network communication states (full/no communication) requested by users such as the Diagnostic Communication Manager.

:::note[Origin: Vector-provided (MICROSAR)]
This module is part of the Vector MICROSAR Basic Software delivery. Sources are proprietary to Vector Informatik GmbH and are integrated — not developed — in this repository. Configuration is generated with the DaVinci/GENy tooling for this Electronic Control Unit.
:::

## Repository files

| File |
| --- |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/ComM/ComM.c` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/ComM/ComM.h` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/ComM/ComM_BusSM.h` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/ComM/ComM_Dcm.h` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/ComM/ComM_EcuM.h` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/ComM/ComM_Nm.h` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/ComM/ComM_Types.h` |

_The module directory holds 11 tracked files._

## Generated configuration (GenData)

The following generated files configure this module for the steering Electronic Control Unit:

- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/ComM_Cfg.h`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/ComM_GenTypes.h`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/ComM_Lcfg.c`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/ComM_Lcfg.h`

## Reference documents

- [TechnicalReference Asr ComM](../documents/technicalreference-asr-comm) — converted from `Haitec_LC_EPS_TMS570/HLDD/BSW/TechnicalReference_Asr_ComM.pdf`

