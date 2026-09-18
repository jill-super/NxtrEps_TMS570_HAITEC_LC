---
title: "Build and tooling"
description: "Compiler, configuration workflow, code generation and test tooling."
---

## Toolchain

- **Target:** Texas Instruments TMS570LS30316U (Hercules family, ARM Cortex-R4F).
- **Compiler:** Texas Instruments Code Composer Studio toolchain (CGT), generation 4.9.x as recorded in the
  generated configuration banners.
- **Linker script:** `Haitec_LC_EPS_TMS570/SwProject/TMS570LS202x6SFlashLnk.cmd`.
- **Post-build:** `Haitec_LC_EPS_TMS570/SwProject/postbuild.bat` with `Tools/Postbuild/apmem.vbs`.

## Configuration and code generation workflow

1. The Electronic Control Unit is described in the DaVinci/GENy configuration
   (`Tools/AsrProject/Config/ECUC/EPS.ecuc.vdsxml`, `Tools/AsrProject/Config/DCF/EPS.dcf`).
2. Vector generators produce the Basic Software configuration (`Source/GenData/`), the Runtime Environment
   (`Source/GenDataRte/Rte.c`, `Rte.h`, `Rte.oil`) and the OS objects (`Source/GenDataOS/`).
3. Each application component ships its AUTOSAR description (`<Component>/autosar/`) plus generation templates
   (`<Component>/generate/`, e.g. `Ap_Assist_Cfg.h.tt`) and helper scripts (`tools/Integrate.bat`, `tools/RteGen.bat`).
4. Every Basic Software module ships make fragments (`Source/BSW/<Module>/mak/*_cfg.mak`, `*_defs.mak`,
   `*_rules.mak`, `*_check.mak`) consumed by the ECU build.

## Host-side tooling

- `Haitec_LC_EPS_TMS570/Tools/AsrProject` — DaVinci/GENy project, generators (including ARTT) and configuration.
- `Haitec_LC_EPS_TMS570/Tools/OilTool` — OIL processing for the OSEK operating system.
- `Haitec_LC_EPS_TMS570/Tools/{CCT,GliwaT1,GnuWin32,Metrics,Patch,Polyspace,QAC}` — timing, metrics,
  polyspace analysis and static-analysis tooling.
- Per-component `utp/` folders hold Tessy unit-test projects; the generated `index_*.pdf` reports are
  summarised on each component page under *Documents*.
- Per-component `tools/QAC/` folders and the top-level `QAC/` folder hold the QAC/MISRA static-analysis setup.

## Calibration, measurement and diagnostics

- **XCP over CAN** (`Xcp/` application component plus the Vector `Xcp`/`CanXcp` stack) for measurement and calibration.
- **Unified Diagnostic Services** through the Vector `Dcm`/`Dem` stack and the in-house `DiagMgr` and
  `CMS_Common` manufacturing services.

## Documentation site

The documentation site sources live entirely in the [`docs/`](../integration/project/) folder at the repository
root (Astro with the Starlight theme). Build it locally with:

```sh
cd docs
npm install
npm run build   # output in docs/dist/
npm run dev     # live preview
```

Deploying the static `docs/dist/` output to GitHub Pages publishes the site; the Astro configuration derives
the Pages URL from the git `origin` remote automatically, so forks need no configuration change.
