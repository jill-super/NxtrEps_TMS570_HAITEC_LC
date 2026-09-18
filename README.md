# Electric Power Steering (EPS) System for HAITEC LC

![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)
![Language: C](https://img.shields.io/badge/Language-C-blue.svg)
![Microcontroller: TMS570](https://img.shields.io/badge/MCU-TMS570-red.svg)
![Architecture: AUTOSAR](https://img.shields.io/badge/Architecture-AUTOSAR-orange.svg)
![Safety: ISO 26262 ASIL D](https://img.shields.io/badge/Safety-ISO_26262_ASIL_D-purple.svg)
![Docs: Astro Starlight](https://img.shields.io/badge/Docs-Astro_Starlight-3577c6.svg)

Complete **Electric Power Steering (EPS)** software for the **HAITEC LC** platform:
an AUTOSAR-based embedded system for the Texas Instruments TMS570 safety microcontroller,
developed to automotive safety standards (ISO 26262 ASIL D).

> **New here?** Start with the browsable documentation site built from [`docs/`](docs/)
> (Astro with the Starlight theme): component pages per AUTOSAR layer, converted design
> documents, and clear Vector-provided vs. in-house labelling. See
> [Documentation](#documentation) below.

## Table of Contents

- [Features](#features)
- [System Architecture](#system-architecture)
- [Repository Structure](#repository-structure)
- [Software Components by AUTOSAR Layer](#software-components-by-autosar-layer)
- [Vector-Provided vs. In-House Code](#vector-provided-vs-in-house-code)
- [Installation and Build](#installation-and-build)
- [Testing and Quality](#testing-and-quality)
- [Documentation](#documentation)
- [HAITEC LC Platform](#haitec-lc-platform)
- [Contributing](#contributing)
- [License](#license)

## Features

- **Precise power-assisted steering control**: base assist curves blended with vehicle speed,
  high-frequency assist, active pull compensation, damping and return control.
- **Motor control**: current-mode field-oriented style control with current command generation,
  proportional-integral current control, torque cancellation and space-vector pulse-width modulation.
- **Functional safety**: independent firewall monitors (assist, damping, return, end-of-travel damping),
  torque reasonableness and compliance checks, temporal monitoring, controlled shutdown paths,
  watchdog supervision and TMS570 hardware self-diagnostics.
- **Vehicle integration**: Controller Area Network communication (Vector MICROSAR stack),
  Unified Diagnostic Services, XCP measurement and calibration, non-volatile memory management.
- **Platform**: Texas Instruments TMS570LS30316U Hercules safety microcontroller (ARM Cortex-R4F).

## System Architecture

```text
+---------------------------------------------------------------+  Application Software
| Base Assist | Damping | Return | Friction Learning | Thermal     |  ~43 components
| Duty Cycle | Vehicle Dynamics | States and Modes | ...           |
+---------------------------------------------------------------+
+---------------------------------------------------------------+  Sensor / Actuator
| Handwheel Torque (SENT) | Motor Velocity | Battery | Temperatures |  9 components
+---------------------------------------------------------------+
+----------------------------------------+----------------------+  Complex Device Drivers
| Analog-Digital Converter | DMA | SPI | PWM/NHet | uDiag | ...  |  10 drivers
+----------------------------------------+----------------------+
+---------------------------------------------------------------+  Runtime Environment
| MICROSAR RTE 2.19.1 (generated)                               |
+---------------------------------------------------------------+
+---------------------------------------------------------------+  Basic Software
| Vector MICROSAR: Com/Can/Dem/Dcm/NvM/EcuM/Os/WdgM/...         |  28 modules
| Texas Instruments: Flash EEPROM Emulation, F021 Flash API     |
+---------------------------------------------------------------+
  Texas Instruments TMS570LS30316U (Hercules, ARM Cortex-R4F)
```

## Repository Structure

```text
<repo root>/
├── <Component>/                 # One folder per software component, e.g. Assist/, Adc/, DiagMgr/
│   ├── src/                     # Implementation (.c)
│   ├── include/                 # Public interfaces (.h) — where present
│   ├── doc/                     # Design documents (Word/PDF) + QAC results
│   ├── autosar/                 # AUTOSAR software-component descriptions (.arxml)
│   ├── generate/                # RTE/config generation templates (.tt) and scripts
│   ├── tools/                   # Integration helpers (Integrate.bat, RteGen.bat, QAC)
│   └── utp/                     # Tessy unit-test projects, contracts and reports
├── Haitec_LC_EPS_TMS570/        # ECU integration project (Vector BSW, GenData, tooling)
│   ├── SwProject/Source/        # BSW/ CDD/ GenData/ GenDataRte/ GenDataOS/ Header/ ...
│   ├── SwProject/*.cmd *.bat    # Linker script and post-build steps
│   ├── HLDD/BSW/                # Vector Technical References (PDF)
│   └── Tools/                   # DaVinci/GENy project, OilTool, QAC, metrics, ...
├── Fee/                         # Texas Instruments Flash EEPROM Emulation driver
├── Fls/                         # Texas Instruments F021 Flash API (headers + library)
├── GliwaT1/                     # Gliwa T1 timing-measurement library (third-party)
├── StdDef/                      # Platform type definitions (Std_Types.h, Compiler.h, ...)
├── NxtrLib/                     # Shared software library (filters, interpolation, ...)
├── CMS_Common/                  # Common manufacturing services (diagnostics, XCP)
├── QAC/                         # Project-wide static-analysis configuration
├── docs/                        # Documentation site sources (Astro + Starlight)
├── LICENSE                      # MIT License
└── README.md                    # This file
```

> **Naming convention:** directory names use short engineering abbreviations (e.g. `AbsHwPos_TcI2cVd`,
> `TmprlMon`, `SgnlCond`). Throughout this README and the documentation site, titles and text use the
> expanded long names (e.g. “Absolute Handwheel Position”, “Temporal Monitor”, “Signal Conditioning”)
> to improve readability; the exact directory name is always shown alongside in code font.

## Software Components by AUTOSAR Layer

<details>
<summary><strong>Application Software — steering functions (expand)</strong></summary>

| Component | Directory | Origin |
| --- | --- | --- |
| Absolute Handwheel Position | `AbsHwPos_TcI2cVd` | Custom (in-house) |
| Active Pull Compensation | `ActivePull` | Custom (in-house) |
| Assist Firewall Monitor | `AssistFirewall` | Custom (in-house) |
| Assist Summation Limiter (Current Mode) | `AstLmt_CM` | Custom (in-house) |
| Average Friction Learning | `AvgFricLrn` | Custom (in-house) |
| Base Assist Control | `Assist` | Custom (in-house) |
| Battery Voltage Diagnostics | `BVDiag` | Custom (in-house) |
| Battery Voltage Sensing | `BatteryVoltage` | Custom (in-house) |
| Calibration Protocol Interface (XCP) | `Xcp` | Custom (in-house) |
| Compliance Error Manager | `ComplErr` | Custom (in-house) |
| Controlled Disable and Shutdown | `CtrldDisShtdn` | Custom (in-house) |
| Damping Control | `Damping` | Custom (in-house) |
| Damping Firewall Monitor | `DampingFirewall` | Custom (in-house) |
| Diagnostic Manager | `DiagMgr` | Custom (in-house) |
| Electric Power Consumption Monitor | `ElePwr` | Custom (in-house) |
| End-of-Travel Actuator Management | `EOTActuatorMng` | Custom (in-house) |
| End-of-Travel Damping Firewall | `EtDmpFw` | Custom (in-house) |
| End-of-Travel Learning | `LrnEOT` | Custom (in-house) |
| Fault Injection | `FltInjection` | Custom (in-house) |
| Frequency Sweep Diagnostics | `Sweep` | Custom (in-house) |
| Frequency-Dependent Damping and Inertia Compensation | `FrqDepDmpnInrtCmp` | Custom (in-house) |
| Global Shutdown Manager | `Gsod` | Custom (in-house) |
| Haitec Torque Command Interface | `HaitecTrqCmd` | Custom (in-house) |
| Hardware Power-Up Sequencing | `HwPwUp` | Custom (in-house) |
| High Load Stall Management | `HiLoadStall` | Custom (in-house) |
| High-Frequency Assist | `HighFreqAssist` | Custom (in-house) |
| Hysteresis Compensation | `HystComp` | Custom (in-house) |
| Limiter Conditioning | `LmtCod` | Custom (in-house) |
| Motor Control (Current Mode) | `MtrCtrl_CM` | Custom (in-house) |
| Motor Temperature Estimation | `MtrTempEst` | Custom (in-house) |
| Power Limit Function (Current Mode) | `PwrLmtFuncCr` | Custom (in-house) |
| Return Control | `Return` | Custom (in-house) |
| Return Firewall Monitor | `ReturnFirewall` | Custom (in-house) |
| Signal Conditioning | `SgnlCond` | Custom (in-house) |
| Signal Polarity Management | `Polarity` | Custom (in-house) |
| Stability Compensation | `StabilityComp` | Custom (in-house) |
| State Output Control | `StOpCtrl` | Custom (in-house) |
| States and Modes Manager | `StaMd` | Custom (in-house) |
| Thermal Duty Cycle Management | `ThrmDutyCycle` | Custom (in-house) |
| Torque Reasonableness Diagnostics | `TqRsDg` | Custom (in-house) |
| Tuning Selection Authority | `TuningSelAuth` | Custom (in-house) |
| Vehicle Dynamics | `VehDyn` | Custom (in-house) |
| Vehicle Speed Limiter | `VehSpdLmt` | Custom (in-house) |

</details>

<details>
<summary><strong>Sensor and Actuator Components — signal interfaces (expand)</strong></summary>

| Component | Directory | Origin |
| --- | --- | --- |
| Bulk Capacitor Pre-Charge Control | `BkCpPc` | Custom (in-house) |
| Common Motor Current Measurement | `CmMtrCurr` | Custom (in-house) |
| Controller Temperature Monitor | `CtrlTemp` | Custom (in-house) |
| Digital Handwheel Torque via SENT | `DigHwTrqSENT` | Custom (in-house) |
| Digital Motor Sensor Bridge | `DigMSB` | Custom (in-house) |
| Digital Motor Velocity Sensing | `MtrVel_Digi` | Custom (in-house) |
| Overvoltage Monitor | `OvrVoltMon` | Custom (in-house) |
| Shutdown Mechanisms | `ShtdnMech` | Custom (in-house) |
| Temporal Monitor | `TmprlMon` | Custom (in-house) |

</details>

<details>
<summary><strong>Complex Device Drivers — hardware-near drivers (expand)</strong></summary>

| Component | Directory | Origin |
| --- | --- | --- |
| Analog-to-Digital Converter Driver | `Adc` | Custom (in-house) |
| Direct Memory Access Driver | `Dma` | Custom (in-house) |
| Enhanced PWM and High-End Timer Driver | `ePWM` | Custom (in-house) |
| Motor Driver and Phase Diagnostics | `SVDiag` | Custom (in-house) |
| Non-Volatile Memory Manager | `NvMMgr` | Custom (in-house) |
| Non-Volatile Memory Proxy | `NvMProxy` | Custom (in-house) |
| Serial Peripheral Interface Driver | `SpiNxt` | Custom (in-house) |
| Space Vector PWM Driver (Current Mode) | `SVDrvr_CM` | Custom (in-house) |
| TMS570 Microcontroller Diagnostics | `TMS570_uDiag` | Custom (in-house) |
| TMS570 Startup Code | `TMS570_Startup` | Custom (in-house) |

</details>

<details>
<summary><strong>Basic Software — Vector MICROSAR stack (expand)</strong></summary>

| Module | Long Name | Origin |
| --- | --- | --- |
| `Can` | Controller Area Network Driver | Vector (MICROSAR) |
| `CanIf` | Controller Area Network Interface | Vector (MICROSAR) |
| `CanSM` | Controller Area Network State Manager | Vector (MICROSAR) |
| `CanTp` | Controller Area Network Transport Protocol | Vector (MICROSAR) |
| `CanXcp` | Controller Area Network Calibration Protocol | Vector (MICROSAR) |
| `Com` | Communication | Vector (MICROSAR) |
| `ComM` | Communication Manager | Vector (MICROSAR) |
| `Crc` | Cyclic Redundancy Check Library | Vector (MICROSAR) |
| `Dcm` | Diagnostic Communication Manager | Vector (MICROSAR) |
| `Dem` | Diagnostic Event Manager | Vector (MICROSAR) |
| `Det` | Development Error Tracer | Vector (MICROSAR) |
| `Dio` | Digital Input Output Driver | Vector (MICROSAR) |
| `EcuM` | Electronic Control Unit State Manager | Vector (MICROSAR) |
| `Gpt` | General Purpose Timer Driver | Vector (MICROSAR) |
| `IoHwAb` | Input Output Hardware Abstraction | Vector (MICROSAR) |
| `Mcu` | Microcontroller Unit Driver | Vector (MICROSAR) |
| `MemIf` | Memory Abstraction Interface | Vector (MICROSAR) |
| `NvM` | Non-Volatile Random Access Memory Manager | Vector (MICROSAR) |
| `Os` | Operating System (OSEK) | Vector (MICROSAR) |
| `PduR` | Protocol Data Unit Router | Vector (MICROSAR) |
| `Port` | Port Driver | Vector (MICROSAR) |
| `VStdLib` | Vector Standard Library | Vector (MICROSAR) |
| `Vmm` | Vector Memory Manager | Vector (MICROSAR) |
| `Wdg` | Watchdog Driver | Vector (MICROSAR) |
| `WdgIf` | Watchdog Interface | Vector (MICROSAR) |
| `WdgM` | Watchdog Manager | Vector (MICROSAR) |
| `Xcp` | Universal Measurement and Calibration Protocol | Vector (MICROSAR) |
| `_Common` | Common Basic Software Files | Vector (MICROSAR) |
| `Fee` | Flash EEPROM Emulation | Texas Instruments |
| `Fls` | Flash Driver (F021 Flash API) | Texas Instruments |

The stack lives under `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/`, configured by generated sources in `.../Source/GenData*`. See the [Basic Software docs](docs/src/content/docs/bsw/index.md).

</details>

<details>
<summary><strong>Libraries, shared code and integration (expand)</strong></summary>

| Component | Directory | Origin |
| --- | --- | --- |
| Common Manufacturing Services | `CMS_Common` | Custom (in-house) |
| Nexteer Software Library | `NxtrLib` | Custom (in-house) |
| Standard Type Definitions | `StdDef` | Vector (MICROSAR) |
| Static Analysis Configuration (QAC) | `QAC` | Custom (in-house) |
| Timing Measurement Library (Gliwa T1) | `GliwaT1` | Third-party (Gliwa) |

| HAITEC LC EPS Integration Project | `Haitec_LC_EPS_TMS570` | Mixed (see below) |

</details>

## Vector-Provided vs. In-House Code

| Origin | Covers | How to recognise it |
| --- | --- | --- |
| **Custom (in-house)** | All application, sensor/actuator and complex-driver components, libraries, startup code | `Copyright … Nexteer Automotive` headers |
| **Vector-provided (MICROSAR)** | Communication, diagnostics, memory, mode-management and OS modules | `Copyright … Vector Informatik GmbH` blocks in `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/` |
| **Vector-generated** | Runtime Environment, OS objects, module configurations | `GENy`/`DaVinci`/`MICROSAR RTE Generator` banners in `.../Source/GenData*` |
| **Texas Instruments-provided** | Flash EEPROM Emulation driver, F021 Flash API | `TEXAS INSTRUMENTS … PROPRIETARY INFORMATION` headers (`Fee/`, `Fls/`) |
| **Third-party** | Timing-measurement library | Prebuilt `GliwaT1` library |

> Application sources contain a `Generator: MICROSAR RTE Generator` banner — that only marks the file as an
> RTE component template; the control code itself is in-house. The in-house `CMS_Common` area additionally
> contains a Vector Software Integration Package adaptation (`EPS_DiagSrvcs_XCP.Vector.c`).

## Installation and Build

### Prerequisites

- Texas Instruments Code Composer Studio toolchain (CGT generation 4.9.x) for the TMS570 (ARM Cortex-R4F).
- Vector DaVinci/GENy tooling for regenerating Basic Software configuration and the Runtime Environment.
- Tessy for unit tests, QAC for static analysis (see [Testing and Quality](#testing-and-quality)).
- Node.js 20+ and npm — only for building this documentation site.

### Build the firmware

1. Clone this repository.
2. Generate the Basic Software configuration and Runtime Environment with DaVinci/GENy from
   `Haitec_LC_EPS_TMS570/Tools/AsrProject/Config/` (see [Build and tooling](docs/src/content/docs/general/build.md)).
3. Build the ECU image with the project make fragments (`SwProject/Source/BSW/*/mak/`),
   link with `SwProject/TMS570LS202x6SFlashLnk.cmd`, and run `SwProject/postbuild.bat`.
4. Flash the resulting image onto the TMS570 microcontroller.

### Build the documentation site

```sh
cd docs
npm install
npm run dev      # live preview
npm run build    # static site in docs/dist/, ready for GitHub Pages
```

The Astro configuration derives the GitHub Pages URL from the git `origin` remote automatically,
so forks are published without configuration changes.

## Testing and Quality

- **Unit tests**: Tessy projects under each component's `utp/` folder (test database, contracts,
  `Tessy/report/index_*.pdf` reports). Report summaries are published on every component documentation page.
- **Static analysis**: QAC/MISRA setup in `QAC/` plus per-component results (`<Component>/doc/QAC_Results/`,
  `<Component>/tools/QAC/`). Process view: [Quality and safety](docs/src/content/docs/general/quality/).
- **Design reviews**: module design documents and integration manuals in each `<Component>/doc/` folder,
  converted to browsable pages in the documentation site.

## Documentation

- **Browsable site sources**: [`docs/`](docs/) — Astro 7 project with the Starlight theme.
  Content lives in `docs/src/content/docs/`, organised by AUTOSAR layer:
  `asw/`, `sensor-actuator/`, `cdd/`, `bsw/`, `libraries/`, `integration/`, `general/`.
- **Converted documents**: all Word (`.doc`/`.docx`), PDF and documentation text files found in the
  repository were converted to Markdown next to their component (`.../documents/` subfolders) and linked
  from the component pages. Legacy `.doc` files carry a note where fidelity is limited; multi-thousand-page
  generated Tessy reports are published as structured summaries.
- **Start reading**: [System architecture](docs/src/content/docs/general/architecture.md),
  [Vector vs. in-house code](docs/src/content/docs/general/origins.md),
  [Build and tooling](docs/src/content/docs/general/build.md).

## HAITEC LC Platform

The **HAITEC LC** platform is an advanced electronic vehicle architecture by HAITEC. This repository
implements its Electric Power Steering function: torque assistance, damping, return behaviour, thermal
protection and diagnostics, communicating with the vehicle over CAN.

## Contributing

We encourage contributions! If you would like to improve this project — code, configuration, tests or
documentation — please submit a pull request. Keep Vector, Texas Instruments and other third-party
deliverables clearly separated from in-house changes and respect their licences.

## License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for the full text.
Note that third-party deliverables integrated in this repository (Vector MICROSAR, Texas Instruments
drivers, Gliwa T1) remain subject to their own proprietary licences.
