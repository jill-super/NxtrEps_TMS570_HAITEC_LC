---
title: "TMS570 Startup Code (TMS570_Startup)"
description: "TMS570 Startup Code: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This module outlines the functionality of the system startup functions of the TMS570.  This code is intended to be run starting after the sys startup routine in the boot project.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `TMS570_Startup/src/AppStartup.c` | implementation |
| `TMS570_Startup/src/BootStartup.c` | implementation |
| `TMS570_Startup/src/ResetCause.c` | implementation |
| `TMS570_Startup/src/fiqintvect.asm` | implementation |
| `TMS570_Startup/src/prooftestv02.c` | implementation |
| `TMS570_Startup/src/prooftestv02.het` | implementation |
| `TMS570_Startup/src/sys_core.asm` | implementation |
| `TMS570_Startup/src/sys_memory.asm` | implementation |
| `TMS570_Startup/src/sys_pmu.asm` | implementation |
| `TMS570_Startup/src/sys_startup.c` | implementation |
| `TMS570_Startup/include/ResetCause.h` | public interface |
| `TMS570_Startup/include/prooftestv02.h` | public interface |
| `TMS570_Startup/include/sys_core.h` | public interface |
| `TMS570_Startup/include/sys_memory.h` | public interface |
| `TMS570_Startup/include/sys_pmu.h` | public interface |

## Interfaces and dependencies


**Notable header dependencies:** `Compiler.h`, `MemMap.h`, `Platform_Types.h`, `ResetCause.h`, `adc_regs.h`, `appinit_cfg.h`, `ccm_regs.h`, `dcan_regs.h`, `dma_regs.h`, `efc_regs.h`, `esm_regs.h`, `flash_regs.h`, `gio_regs.h`, `htu_regs.h`, `mibspi_regs.h`, `n2het_regs.h`

## Documents

- [Spna106a](documents/spna106a) — converted from `TMS570_Startup/doc/spna106a.pdf`
- [TMS570 Startup BootStartup Module Design Document](documents/tms570-startup-bootstartup-mdd) — converted from `TMS570_Startup/doc/TMS570_Startup_BootStartup_MDD.docx`
- [TMS570 Startup FiqIntVect Module Design Document](documents/tms570-startup-fiqintvect-mdd) — converted from `TMS570_Startup/doc/TMS570_Startup_FiqIntVect_MDD.docx`
- [TMS570 Startup Integration Manual](documents/tms570-startup-integration-manual) — converted from `TMS570_Startup/doc/TMS570_Startup_Integration_Manual.docx`
- [TMS570 Startup SysCore Module Design Document](documents/tms570-startup-syscore-mdd) — converted from `TMS570_Startup/doc/TMS570_Startup_SysCore_MDD.docx`
- [TMS570 Startup SysStartup Module Design Document](documents/tms570-startup-sysstartup-mdd) — converted from `TMS570_Startup/doc/TMS570_Startup_SysStartup_MDD.docx`

## Repository location

All files live under `TMS570_Startup/` at the repository root.
