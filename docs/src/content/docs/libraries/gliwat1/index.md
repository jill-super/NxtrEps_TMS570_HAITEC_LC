---
title: "Timing Measurement Library (Gliwa T1) (GliwaT1)"
description: "Timing Measurement Library (Gliwa T1): purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-third-party">Third-party</span>
</div>
## Purpose

The Timing Measurement Library (Gliwa T1) software component (GliwaT1) implements part of the electric power steering function on the TMS570 microcontroller.

:::note[Origin: Third-party]
Gliwa T1 timing-measurement library. This is a third-party library used as-is for timing measurement.
:::

## Key files

| File | Role |
| --- | --- |
| `GliwaT1/src/T1_AppInterface.c` | implementation |
| `GliwaT1/src/T1_config.c` | implementation |
| `GliwaT1/src/sys_pmu.asm` | implementation |
| `GliwaT1/include/Metrics.h` | public interface |
| `GliwaT1/include/T1_AppInterface.h` | public interface |
| `GliwaT1/include/T1_MemMap.h` | public interface |
| `GliwaT1/include/T1_baseConfig.h` | public interface |
| `GliwaT1/include/T1_baseInterface.h` | public interface |
| `GliwaT1/include/T1_bid.h` | public interface |
| `GliwaT1/include/T1_config.h` | public interface |
| `GliwaT1/include/T1_contConfig.h` | public interface |
| `GliwaT1/include/T1_contInterface.h` | public interface |
| `GliwaT1/include/T1_delayConfig.h` | public interface |

_Showing a selection; the area contains 3 source files and 20 headers in total._

## Interfaces and dependencies


**Public interface declarations** (from headers):

- `T1_CPULOAD_CALLBACK_CORE0`
- `T1_CPULOAD_CALLBACK_CORE1`
- `T1_CPULOAD_CALLBACK_CORE2`


**Notable header dependencies:** `Std_Types.h`, `T1_AppInterface.h`, `T1_AppInterface_Cfg.h`, `T1_MemMap.h`, `T1_baseConfig.h`, `T1_bid.h`, `T1_contConfig.h`, `T1_delayConfig.h`, `T1_flexConfig.h`, `T1_scopeConfig.h`, `osek.h`, `sys_pmu.h`

## Documents

- [GliwaT1 IntegrationManual](documents/gliwat1-integrationmanual) — converted from `GliwaT1/doc/GliwaT1_IntegrationManual.doc`

## Repository location

All files live under `GliwaT1/` at the repository root.
