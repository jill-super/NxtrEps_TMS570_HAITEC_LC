---
title: "Generated configuration (GenData)"
description: "DaVinci/GENy output tailoring the BSW to this ECU."
---

<div class="origin-badges"><span class="origin-badge origin-vector-generated">Vector-generated (DaVinci/GENy)</span></div>

## Role

`Haitec_LC_EPS_TMS570/SwProject/Source/GenData/` (plus `GenDataRte/` and `GenDataOS/`) contains the
configuration generated from the ECU description (`Tools/AsrProject/Config/ECUC/EPS.ecuc.vdsxml`):
CAN database bindings, communication matrices, diagnostic configurations, memory block layouts,
OS objects and per-component settings (`Ap_*_Cfg.h`, `CalConstants.c/h`).

## Notable files

- `CalConstants.c/h` — project calibration constants shared by components.
- `*_Cfg.h`, `*_PBcfg.c`, `*_Lcfg.c` — post-build/load-time configurations of the respective modules.
- `WdgM_Graph.pdf` (converted under the [Watchdog Manager](../wdgm/) page) — supervision graph.
- `Fee_Cfg.*`, `NvM_Cfg.*`, `MemIf_Cfg.*` — memory-stack configuration.
- `Can*_Cfg.h`, `Com_Cfg.h`, `Dcm/Dem` configurations — communication and diagnostics.

Regenerate with the DaVinci/GENy tooling after any `.arxml`/`.dcf` change; never hand-edit.
