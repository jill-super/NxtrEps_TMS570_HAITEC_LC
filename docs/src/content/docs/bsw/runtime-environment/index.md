---
title: "Runtime Environment (RTE)"
description: "Generated MICROSAR RTE connecting application components."
---

<div class="origin-badges"><span class="origin-badge origin-vector-generated">Vector-generated (DaVinci/GENy)</span></div>

## Role

The Runtime Environment implements the AUTOSAR Virtual Function Bus for this Electronic Control Unit:
it routes runnable entities, inter-runnable variables, client-server calls, mode switches and
measurement/calibration hooks between the application components.

:::note[Origin: Vector-generated]
Generated with MICROSAR RTE Generator 2.19.1 from the DaVinci software-component descriptions
(`<Component>/autosar/`) and the ECU configuration. Do not edit generated files by hand; change the
model and regenerate.
:::

## Key generated files

- `Haitec_LC_EPS_TMS570/SwProject/Source/GenDataRte/Rte.c`, `Rte.h`, `Rte_Cbk.h` — the Runtime Environment itself.
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenDataRte/Rte.oil` — OS definitions for the Runtime Environment.
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenDataRte/Components/` — per-component generation data.
- `Haitec_LC_EPS_TMS570/SwProject/Source/GenData/Ap_*_Cfg.h` — per-component configuration headers.
- `<Component>/utp/contract/` — stub Runtime Environment headers used to compile components in the Tessy
  unit-test environment (not flashed).

## Application usage

Application code includes its component header (e.g. `Rte_Ap_Assist.h`) and uses `Rte_IRead_*`,
`Rte_IWrite_*`, `Rte_Call_*` and `Rte_Mode_*` accessors. Checkpoints (`Rte_Call_*_CheckpointReached`)
feed the Watchdog Manager supervision.
