---
title: "Watchdog Manager (WdgM)"
description: "Vector MICROSAR WdgM: role, repository files and configuration."
---

<div class="origin-badges">
  <span class="origin-badge origin-vector">Vector-provided (MICROSAR)</span>
</div>
## Role

Supervises program flow (alive supervision, deadline supervision, logical supervision) for functional safety.

:::note[Origin: Vector-provided (MICROSAR)]
This module is part of the Vector MICROSAR Basic Software delivery. Sources are proprietary to Vector Informatik GmbH and are integrated — not developed — in this repository. Configuration is generated with the DaVinci/GENy tooling for this Electronic Control Unit.
:::

## Repository files

| File |
| --- |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/WdgM/WdgM.c` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/WdgM/WdgM.h` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/WdgM/WdgM_Cfg.h` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/WdgM/WdgM_Checkpoint.c` |

_The module directory holds 4 tracked files._

## Generated configuration (GenData)

The following generated files configure this module for the steering Electronic Control Unit:

- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/WdgM_Cfg_Features.h`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/WdgM_Graph.pdf`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/WdgM_MemMap.h`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/WdgM_PBcfg.c`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/WdgM_PBcfg.h`

## Documents

- [Watchdog Manager Supervision Graph](documents/wdgm-graph) — converted from `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/WdgM_Graph.pdf`.
