---
title: "Universal Measurement and Calibration Protocol (Xcp)"
description: "Vector MICROSAR Xcp: role, repository files and configuration."
---

<div class="origin-badges">
  <span class="origin-badge origin-vector">Vector-provided (MICROSAR)</span>
</div>
## Role

Universal Measurement and Calibration Protocol slave, used with CAN-XCP for measurement and calibration.

:::note[Origin: Vector-provided (MICROSAR)]
This module is part of the Vector MICROSAR Basic Software delivery. Sources are proprietary to Vector Informatik GmbH and are integrated — not developed — in this repository. Configuration is generated with the DaVinci/GENy tooling for this Electronic Control Unit.
:::

## Repository files

| File |
| --- |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/Xcp/XcpProf.c` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/Xcp/XcpProf.h` |
| `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/Xcp/XcpProf_Types.h` |

_The module directory holds 7 tracked files._

## Generated configuration (GenData)

The following generated files configure this module for the steering Electronic Control Unit:

- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/XCP.a2l`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/XCP_daq.a2l`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/XCP_events.a2l`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/xcp_cfg.h`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/xcp_par.c`
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/xcp_par.h`

## Reference documents

- [TechnicalReference Asr CanXcp](../documents/technicalreference-asr-canxcp) — converted from `Haitec_LC_EPS_TMS570/HLDD/BSW/TechnicalReference_Asr_CanXcp.pdf`

