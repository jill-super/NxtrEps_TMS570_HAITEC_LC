---
title: "Memory Abstraction Interface (MemIf)"
description: "Vector MICROSAR MemIf: role, repository files and configuration."
---

<div class="origin-badges">
  <span class="origin-badge origin-vector">Vector-provided (MICROSAR)</span>
</div>
## Role

Abstracts the underlying memory hardware (Flash EEPROM Emulation) for the Non-Volatile Memory Manager.

:::note[Origin: Vector-provided (MICROSAR)]
This module is part of the Vector MICROSAR Basic Software delivery. Sources are proprietary to Vector Informatik GmbH and are integrated — not developed — in this repository. Configuration is generated with the DaVinci/GENy tooling for this Electronic Control Unit.
:::

## Repository files

| File |
| --- |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/MemIf/MemIf.c` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/MemIf/MemIf.h` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/MemIf/MemIf_Types.h` |

_The module directory holds 3 tracked files._

## Generated configuration (GenData)

The following generated files configure this module for the steering Electronic Control Unit:

- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/MemIf_Cfg.c`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/MemIf_Cfg.h`

## Reference documents

- [TechnicalReference Asr MemIf](../documents/technicalreference-asr-memif) — converted from `Haitec_LC_EPS_TMS570/HLDD/BSW/TechnicalReference_Asr_MemIf.pdf`

