---
title: "Protocol Data Unit Router (PduR)"
description: "Vector MICROSAR PduR: role, repository files and configuration."
---

<div class="origin-badges">
  <span class="origin-badge origin-vector">Vector-provided (MICROSAR)</span>
</div>
## Role

Routes protocol data units between communication modules (CAN Interface, Transport Protocol, Communication).

:::note[Origin: Vector-provided (MICROSAR)]
This module is part of the Vector MICROSAR Basic Software delivery. Sources are proprietary to Vector Informatik GmbH and are integrated — not developed — in this repository. Configuration is generated with the DaVinci/GENy tooling for this Electronic Control Unit.
:::

## Repository files

| File |
| --- |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/PduR/PduR.c` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/PduR/PduR.h` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/PduR/PduR_CanIf.h` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/PduR/PduR_CanNm.h` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/PduR/PduR_CanTp.h` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/PduR/PduR_Dcm.h` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/PduR/PduR_IpduM.h` |

_The module directory holds 11 tracked files._

## Generated configuration (GenData)

The following generated files configure this module for the steering Electronic Control Unit:

- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/PduR_Cfg.c`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/PduR_Cfg.h`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/PduR_Com.h`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/PduR_Lcfg.c`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/PduR_Lcfg.h`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/PduR_PBcfg.c`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/PduR_PBcfg.h`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/PduR_Types.h`

## Reference documents

- [TechnicalReference Asr PduR](../documents/technicalreference-asr-pdur) — converted from `Haitec_LC_EPS_TMS570/HLDD/BSW/TechnicalReference_Asr_PduR.pdf`

