---
title: "Flash EEPROM Emulation (FEE) (Fee)"
description: "Flash EEPROM Emulation (FEE): Texas Instruments memory-stack driver."
---

<div class="origin-badges">
  <span class="origin-badge origin-ti">Texas Instruments-provided</span>
</div>
## Purpose

This file defines the layout of Bank7.

:::note[Origin: Texas Instruments-provided]
Supplied by Texas Instruments with the Hercules safety-microcontroller support package and used as-is by the memory stack (Memory Abstraction Interface, Flash EEPROM Emulation, Non-Volatile Memory Manager).
:::

## Key files

| File | Role |
| --- | --- |
| `Fee/src/Device_TMS570LS07.c` | implementation |
| `Fee/src/Device_TMS570LS12.c` | implementation |
| `Fee/src/fee.c` | implementation |
| `Fee/src/ti_fee_Info.c` | implementation |
| `Fee/src/ti_fee_cancel.c` | implementation |
| `Fee/src/ti_fee_eraseimmediateblock.c` | implementation |
| `Fee/src/ti_fee_format.c` | implementation |
| `Fee/src/ti_fee_ini.c` | implementation |
| `Fee/src/ti_fee_invalidateblock.c` | implementation |
| `Fee/src/ti_fee_main.c` | implementation |
| `Fee/src/ti_fee_read.c` | implementation |
| `Fee/src/ti_fee_readSync.c` | implementation |
| `Fee/src/ti_fee_shutdown.c` | implementation |
| `Fee/src/ti_fee_util.c` | implementation |
| `Fee/include/Device_Header.h` | public interface |
| `Fee/include/Device_TMS570LS07.h` | public interface |
| `Fee/include/Device_TMS570LS12.h` | public interface |
| `Fee/include/Device_types.h` | public interface |
| `Fee/include/Fee_Cbk.h` | public interface |
| `Fee/include/fee.h` | public interface |
| `Fee/include/fee_interface.h` | public interface |
| `Fee/include/fee_memmap.h` | public interface |
| `Fee/include/ti_fee.h` | public interface |
| `Fee/include/ti_fee_cfg.h` | public interface |

_Showing a selection; the area contains 16 source files and 11 headers in total._

## Interfaces and dependencies


**Public interface declarations** (from headers):

- `FEE_NVM_JOB_END_NOTIFICATION`
- `FEE_NVM_JOB_ERROR_NOTIFICATION`
- `Fee_CallbackType`
- `Fee_Cancel`
- `Fee_EraseImmediateBlock`
- `Fee_GetJobResult`
- `Fee_GetStatus`
- `Fee_GetVersionInfo`
- `Fee_Init`
- `Fee_InvalidateBlock`
- `Fee_Read`
- `Fee_SetMode`
- `Fee_Write`
- `Fee_MainFunction`
- `Fee_InternalUpdateGlobalStructure`
- `TI_Fee_Cancel`
- `TI_Fee_EraseImmediateBlock`
- `TI_Fee_GetStatus`


**Notable header dependencies:** `Det.h`, `Device_TMS570LS07.h`, `Device_TMS570LS12.h`, `Device_header.h`, `Fee.h`, `Fee_Cbk.h`, `MemMap.h`, `SchM_Fee.h`, `Std_Types.h`, `ti_fee.h`

## Documents

- [AutoSAR FEE Parameter Configuration](documents/autosar-fee-parameter-configuration) — converted from `Fee/doc/AutoSAR FEE Parameter Configuration.pdf`
- [AutoSAR FEE User Guide](documents/autosar-fee-user-guide) — converted from `Fee/doc/AutoSAR FEE User Guide.pdf`
- [DataSheet TMS570LS0714](documents/datasheet-tms570ls0714) — converted from `Fee/doc/DataSheet_TMS570LS0714.pdf`
- [DataSheet TMS570LS1227](documents/datasheet-tms570ls1227) — converted from `Fee/doc/DataSheet_TMS570LS1227.pdf`

