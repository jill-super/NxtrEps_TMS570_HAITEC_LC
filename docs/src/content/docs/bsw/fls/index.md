---
title: "Flash Driver (F021 Flash API) (Fls)"
description: "Flash Driver (F021 Flash API): Texas Instruments memory-stack driver."
---

<div class="origin-badges">
  <span class="origin-badge origin-ti">Texas Instruments-provided</span>
</div>
## Purpose

Texas Instruments F021 Flash API for the Hercules TMS570 family: low-level erase/program primitives used by the Flash EEPROM Emulation. Delivered as headers plus a prebuilt library (`F021_API_CortexR4_BE_V3D16.lib`).

:::note[Origin: Texas Instruments-provided]
Supplied by Texas Instruments with the Hercules safety-microcontroller support package and used as-is by the memory stack (Memory Abstraction Interface, Flash EEPROM Emulation, Non-Volatile Memory Manager).
:::

## Key files

| File | Role |
| --- | --- |
| `Fls/src/F021_API_CortexR4_BE_V3D16.lib` | implementation |
| `Fls/include/CGT.ARM.h` | public interface |
| `Fls/include/CGT.CCS.h` | public interface |
| `Fls/include/CGT.GHS.h` | public interface |
| `Fls/include/CGT.IAR.h` | public interface |
| `Fls/include/CGT.gcc.h` | public interface |
| `Fls/include/Compatibility.h` | public interface |
| `Fls/include/Constants.h` | public interface |
| `Fls/include/F021.h` | public interface |
| `Fls/include/FapiFunctions.h` | public interface |
| `Fls/include/Helpers.h` | public interface |

_Showing a selection; the area contains 1 source files and 14 headers in total._

## Interfaces and dependencies


**Public interface declarations** (from headers):

- `Fapi_enableMainBankSectors`
- `Fapi_enableEepromBankSectors`
- `Fapi_enableFsmDoneEvent`
- `Fapi_disableFsmDoneEvent`
- `Fapi_initializeFlashBanks`
- `Fapi_setActiveFlashBank`
- `Fapi_enableBanksForOtpWrite`
- `Fapi_disableBanksForOtpWrite`
- `Fapi_enableAutoEccCalculation`
- `Fapi_disableAutoEccCalculation`
- `Fapi_flushPipeline`
- `Fapi_remapEccAddress`
- `Fapi_remapMainAddress`
- `Fapi_isAddressEcc`
- `Fapi_isAddressEEPROM`
- `Fapi_issueAsyncCommandWithAddress`
- `Fapi_issueAsyncCommand`
- `Fapi_getLibraryInfo`

## Documents

- [Build Information](documents/build-information) — converted from `Fls/doc/build_information.txt`
- [F021 Flash API License Agreement](documents/f021-flash-api-license-agreement) — converted from `Fls/doc/F021_Flash_API_License_Agreement.pdf`
- [Readme](documents/readme) — converted from `Fls/doc/readme.txt`
- [Release Notes](documents/release-notes) — converted from `Fls/doc/Release_Notes.pdf`
- [SPNA148](documents/spna148) — converted from `Fls/doc/SPNA148.pdf`
- [SPNU501F](documents/spnu501f) — converted from `Fls/doc/SPNU501F.pdf`
- [SPNZ210](documents/spnz210) — converted from `Fls/doc/SPNZ210.pdf`

