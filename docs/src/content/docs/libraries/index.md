---
title: "Libraries and Shared Code"
description: "Shared libraries, platform type definitions, manufacturing services and third-party timing library."
---

Shared code used by many components: the Nexteer software library (filters, interpolation, checksums, system time), the common manufacturing services for diagnostics and calibration, the platform type definitions, and the Gliwa T1 timing-measurement library.

## Modules in this layer (4)

| Component | Directory | Origin |
| --- | --- | --- |
| [Common Manufacturing Services](./cms_common/) | `CMS_Common` | Custom (in-house) |
| [Nexteer Software Library](./nxtrlib/) | `NxtrLib` | Custom (in-house) |
| [Standard Type Definitions](./stddef/) | `StdDef` | Vector (MICROSAR) |
| [Timing Measurement Library (Gliwa T1)](./gliwat1/) | `GliwaT1` | Third-party (Gliwa) |
