---
title: "Non-Volatile Random Access Memory Manager (NvM)"
description: "Vector MICROSAR NvM: role, repository files and configuration."
---

<div class="origin-badges">
  <span class="origin-badge origin-vector">Vector-provided (MICROSAR)</span>
</div>
## Role

Manages non-volatile data blocks: storage, retrieval, redundancy and write strategies.

:::note[Origin: Vector-provided (MICROSAR)]
This module is part of the Vector MICROSAR Basic Software delivery. Sources are proprietary to Vector Informatik GmbH and are integrated — not developed — in this repository. Configuration is generated with the DaVinci/GENy tooling for this Electronic Control Unit.
:::

## Repository files

| File |
| --- |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/NvM/NvM.c` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/NvM/NvM.h` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/NvM/NvM_Act.c` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/NvM/NvM_Act.h` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/NvM/NvM_Cbk.h` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/NvM/NvM_Crc.c` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/NvM/NvM_Crc.h` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/NvM/NvM_JobProc.c` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/NvM/NvM_JobProc.h` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/NvM/NvM_Qry.c` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/NvM/NvM_Qry.h` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/NvM/NvM_Queue.c` |

_The module directory holds 14 tracked files._

## Generated configuration (GenData)

The following generated files configure this module for the steering Electronic Control Unit:

- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/NvM_Cfg.c`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/NvM_Cfg.h`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/NvM_PrivateCfg.h`

## Reference documents

- [TechnicalReference Asr NvM](../documents/technicalreference-asr-nvm) — converted from `Haitec_LC_EPS_TMS570/HLDD/BSW/TechnicalReference_Asr_NvM.pdf`

