---
title: "Serial Peripheral Interface Driver (SpiNxt)"
description: "Serial Peripheral Interface Driver: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

The Autosar API naming has been altered from the Autosar standard to allow co-existence of this module and a Third Party Spi driver implementation in the same project.  SWC’s operating within the Rte can be mapped to either the Spi service ports offered by this BSW or the Third Parties Spi driver service ports by only changing the Rte service port mapping.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `SpiNxt/src/SpiNxt.c` | implementation |
| `SpiNxt/src/SpiNxt_Irq.c` | implementation |
| `SpiNxt/include/SpiNxt.h` | public interface |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `mibspiEnableGroupNotification`
- `mibspiSetData8`
- `mibspiGetData8`
- `SpiNxt_SetupEB`
- `SpiNxt_GetSequenceResult`
- `SpiNxt_AsyncTransmit`
- `SpiNxt_Init`
- `mibspiSetData`
- `mibspiSetCtrlData`
- `mibspiGetData`
- `mibspiTransfer`
- `mibspiNotification`
- `mibspiGroupNotification`


**Public interface declarations** (from headers):

- `UNC`
- `mibspiGroupNotification`
- `mibspiNotification`
- `mibspiSetData`
- `mibspiSetCtrlData`
- `mibspiGetData`
- `mibspiTransfer`
- `SpiNxt_Init`
- `SpiNxt_AsyncTransmit`
- `SpiNxt_GetSequenceResult`
- `SpiNxt_SetupEB`


**Notable header dependencies:** `Dio.h`, `MemMap.h`, `Metrics.h`, `Os.h`, `SchM_SpiNxt.h`, `SpiNxt.h`

## Documents

- [Spi Nexteer Integration Manual](documents/spi-nexteer-integration-manual) — converted from `SpiNxt/doc/Spi_Nexteer_Integration_Manual.docx`
- [Spi Nexteer Module Design Document](documents/spi-nexteer-mdd) — converted from `SpiNxt/doc/Spi_Nexteer_MDD.docx`

## Repository location

All files live under `SpiNxt/` at the repository root.
