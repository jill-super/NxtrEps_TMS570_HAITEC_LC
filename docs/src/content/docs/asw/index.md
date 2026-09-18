---
title: "Application Software (ASW)"
description: "Vehicle-dynamics and steering-function software components (Ap_*) running above the Runtime Environment."
---

Application software components (`Ap_*`) implement the steering control strategy: assist curves, damping, return, friction and inertia compensation, thermal protection, diagnostics of functions, and system state handling. They run as Runtime Environment runnables and share data through standardised ports.

## Modules in this layer (43)

| Component | Directory | Origin |
| --- | --- | --- |
| [Absolute Handwheel Position](./abshwpos_tci2cvd/) | `AbsHwPos_TcI2cVd` | Custom (in-house) |
| [Active Pull Compensation](./activepull/) | `ActivePull` | Custom (in-house) |
| [Assist Firewall Monitor](./assistfirewall/) | `AssistFirewall` | Custom (in-house) |
| [Assist Summation Limiter (Current Mode)](./astlmt_cm/) | `AstLmt_CM` | Custom (in-house) |
| [Average Friction Learning](./avgfriclrn/) | `AvgFricLrn` | Custom (in-house) |
| [Base Assist Control](./assist/) | `Assist` | Custom (in-house) |
| [Battery Voltage Diagnostics](./bvdiag/) | `BVDiag` | Custom (in-house) |
| [Battery Voltage Sensing](./batteryvoltage/) | `BatteryVoltage` | Custom (in-house) |
| [Calibration Protocol Interface (XCP)](./xcp/) | `Xcp` | Custom (in-house) |
| [Compliance Error Manager](./complerr/) | `ComplErr` | Custom (in-house) |
| [Controlled Disable and Shutdown](./ctrlddisshtdn/) | `CtrldDisShtdn` | Custom (in-house) |
| [Damping Control](./damping/) | `Damping` | Custom (in-house) |
| [Damping Firewall Monitor](./dampingfirewall/) | `DampingFirewall` | Custom (in-house) |
| [Diagnostic Manager](./diagmgr/) | `DiagMgr` | Custom (in-house) |
| [Electric Power Consumption Monitor](./elepwr/) | `ElePwr` | Custom (in-house) |
| [End-of-Travel Actuator Management](./eotactuatormng/) | `EOTActuatorMng` | Custom (in-house) |
| [End-of-Travel Damping Firewall](./etdmpfw/) | `EtDmpFw` | Custom (in-house) |
| [End-of-Travel Learning](./lrneot/) | `LrnEOT` | Custom (in-house) |
| [Fault Injection](./fltinjection/) | `FltInjection` | Custom (in-house) |
| [Frequency Sweep Diagnostics](./sweep/) | `Sweep` | Custom (in-house) |
| [Frequency-Dependent Damping and Inertia Compensation](./frqdepdmpninrtcmp/) | `FrqDepDmpnInrtCmp` | Custom (in-house) |
| [Global Shutdown Manager](./gsod/) | `Gsod` | Custom (in-house) |
| [Haitec Torque Command Interface](./haitectrqcmd/) | `HaitecTrqCmd` | Custom (in-house) |
| [Hardware Power-Up Sequencing](./hwpwup/) | `HwPwUp` | Custom (in-house) |
| [High Load Stall Management](./hiloadstall/) | `HiLoadStall` | Custom (in-house) |
| [High-Frequency Assist](./highfreqassist/) | `HighFreqAssist` | Custom (in-house) |
| [Hysteresis Compensation](./hystcomp/) | `HystComp` | Custom (in-house) |
| [Limiter Conditioning](./lmtcod/) | `LmtCod` | Custom (in-house) |
| [Motor Control (Current Mode)](./mtrctrl_cm/) | `MtrCtrl_CM` | Custom (in-house) |
| [Motor Temperature Estimation](./mtrtempest/) | `MtrTempEst` | Custom (in-house) |
| [Power Limit Function (Current Mode)](./pwrlmtfunccr/) | `PwrLmtFuncCr` | Custom (in-house) |
| [Return Control](./return/) | `Return` | Custom (in-house) |
| [Return Firewall Monitor](./returnfirewall/) | `ReturnFirewall` | Custom (in-house) |
| [Signal Conditioning](./sgnlcond/) | `SgnlCond` | Custom (in-house) |
| [Signal Polarity Management](./polarity/) | `Polarity` | Custom (in-house) |
| [Stability Compensation](./stabilitycomp/) | `StabilityComp` | Custom (in-house) |
| [State Output Control](./stopctrl/) | `StOpCtrl` | Custom (in-house) |
| [States and Modes Manager](./stamd/) | `StaMd` | Custom (in-house) |
| [Thermal Duty Cycle Management](./thrmdutycycle/) | `ThrmDutyCycle` | Custom (in-house) |
| [Torque Reasonableness Diagnostics](./tqrsdg/) | `TqRsDg` | Custom (in-house) |
| [Tuning Selection Authority](./tuningselauth/) | `TuningSelAuth` | Custom (in-house) |
| [Vehicle Dynamics](./vehdyn/) | `VehDyn` | Custom (in-house) |
| [Vehicle Speed Limiter](./vehspdlmt/) | `VehSpdLmt` | Custom (in-house) |
