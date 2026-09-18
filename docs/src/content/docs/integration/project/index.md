---
title: "HAITEC LC EPS Integration Project (Haitec_LC_EPS_TMS570)"
description: "ECU integration project: software project layout, generated artifacts and tooling."
---

<div class="origin-badges"><span class="origin-badge origin-vector">Vector-provided (MICROSAR)</span>
<span class="origin-badge origin-vector-generated">Vector-generated (DaVinci/GENy)</span>
<span class="origin-badge origin-custom">Custom — in-house</span></div>

## Purpose

`Haitec_LC_EPS_TMS570/` is the Electronic Control Unit integration project: it binds all application
components, the Vector MICROSAR Basic Software and the generated configuration into one buildable,
flashable image for the TMS570.

:::note[Mixed origin]
The directory structure and project-specific files (application callbacks, hardware abstraction users,
linker script, post-build) are in-house, while `Source/BSW/` is the Vector MICROSAR delivery and
`Source/GenData*` is Vector-generated output. Badges above reflect this mix.
:::

## Software project layout (`SwProject/`)

- `Source/BSW/` — Vector MICROSAR modules (`Can`, `CanIf`, `CanSM`, `CanTp`, `CanXcp`, `Com`, `ComM`, `Crc`,
  `Dcm`, `Dem`, `Det`, `Dio`, `EcuM`, `Gpt`, `IoHwAb`, `Mcu`, `MemIf`, `NvM`, `Os`, `PduR`, `Port`, `VStdLib`,
  `Vmm`, `Wdg`, `WdgIf`, `WdgM`, `Xcp`, `_Common`), each with sources and `mak/` build fragments.
- `Source/CDD/` — project-level complex-driver glue (`CDD_Data.c/h`, `CDD_Func.h`, `MtrCtrl`, `BasicSysSrvc`).
- `Source/GenData/` — generated module configurations (`*_Cfg.h/c`, `*_PBcfg.c`, calibration constants).
- `Source/GenDataRte/` — generated Runtime Environment (`Rte.c/h`, `Rte_Cbk.h`, `Rte.oil`, per-component data).
- `Source/GenDataOS/` — generated OSEK objects (`tcb.c/h`, `osobjs*.inc`, `intvect.asm`, `trustfct.*`).
- `Source/` root — application callbacks (`ApplCallbacks.c`), `IoHwAb.c`, `NtWrap.c`, schedule tables.
- `Header/` — project-wide configuration headers (`*_Cfg.h`, `MemMap.h`, `NtWrap.h`).
- `CMS_Haitec/`, `ChkPt/`, `DemIf/`, `DiagSvc/`, `DfltConfigData/`, `IoHwAbstractionUsr/`, `SrlComInput/`,
  `SrlComOutput/`, `VehPwrMd/` — integration aspects (manufacturing services, checkpoints, diagnostic
  interfaces, default data, serial-communication I/O, vehicle power modes).
- `TMS570LS202x6SFlashLnk.cmd` — linker script; `postbuild.bat` — post-build steps; `T1_Fast.inc`.

## High-level design documents (`HLDD/BSW/`)

Vector Technical References for the integrated stack, converted under
[Basic Software reference documents](../../bsw/documents/):

Com, CanIf, CanSM, CanTp, CanXcp, ComM, Crc, Dcm, Dem, Det, EcuM, IoHwAb, IpduM, MemIf, NvM, PduR,
the TMS470 DCAN driver, VStdLib and Vmm.

## Tooling (`Tools/`)

`AsrProject` (DaVinci/GENy configuration and generators incl. ARTT), `OilTool`, `CCT`, `GliwaT1`,
`GnuWin32`, `Metrics`, `Patch`, `Polyspace`, `Postbuild`, `QAC` — see [Build and tooling](../../general/build/).

## Documents

- [ARTT Generator Release Notes](../../integration/arctool/documents/releasenotes-artt-generator) — converted from
  `Haitec_LC_EPS_TMS570/Tools/AsrProject/Generators/Artt/artt/ReleaseNotes_Artt_Generator.pdf`.
