---
title: "Electric Power Steering — Documentation"
description: "Documentation for the AUTOSAR-based Electric Power Steering system on the TMS570."
template: splash
hero:
  tagline: Documentation for the AUTOSAR-based Electric Power Steering system on the TMS570 microcontroller.
  actions:
    - text: Browse the software layers
      link: /general/architecture/
      icon: right-arrow
    - text: Vector vs. in-house code
      link: /general/origins/
      icon: open-book
      variant: secondary
---

import { Card, CardGrid } from '@astrojs/starlight/components';

## Software layers

<CardGrid stagger>
  <Card title="Application Software" icon="puzzle">
    Steering functions such as base assist, damping, return, and learning — [browse the components](./asw/).
  </Card>
  <Card title="Sensor and Actuator Components" icon="setting">
    Sensor- and actuator-near software such as handwheel torque over SENT and motor velocity — [browse](./sensor-actuator/).
  </Card>
  <Card title="Complex Device Drivers" icon="cpu">
    Hardware-near drivers for conversion, timing, communication and microcontroller supervision — [browse](./cdd/).
  </Card>
  <Card title="Basic Software" icon="layers">
    Vector MICROSAR stack, generated configuration and Texas Instruments memory drivers — [browse](./bsw/).
  </Card>
  <Card title="Libraries and Shared Code" icon="open-book">
    Reusable math, filter and service libraries plus platform type definitions — [browse](./libraries/).
  </Card>
  <Card title="Integration Project" icon="wrench">
    Electronic Control Unit configuration, build, and quality gates — [browse](./integration/).
  </Card>
</CardGrid>

## How to read these pages

Every software-component page states its **origin** at the top:

- **Custom — in-house** code was written for this steering program (Nexteer/HAITEC) and is fully documented here.
- **Vector-provided (MICROSAR)** code is proprietary Basic Software delivered by Vector Informatik; only its integration and configuration are described.
- **Vector-generated** code is produced by the DaVinci/GENy tooling for this Electronic Control Unit.
- **Texas Instruments-provided** code ships with the Hercules TMS570 support package (Flash EEPROM Emulation, F021 Flash API).
- **Third-party** code (Gliwa T1 timing library) is used as-is.

Short directory and file names keep their original form in code font, while titles and text use the expanded long names
(for example, “Absolute Handwheel Position” for `AbsHwPos_TcI2cVd`) to improve readability.

> The documentation site sources live in the [`docs/`](./general/build/) folder of the repository; the rest of the
> repository (C code, configuration, tooling) is untouched.
