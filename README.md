# F1 Steering Wheel Control Module (Ferrari Challenge Project)

## Overview
Designed and implemented an embedded ECU for an F1-style steering wheel, developed under requirements defined by the Ferrari engineering team.  
The system integrates real-time driver inputs, CAN communication, and display feedback.

Complete hardware design files, schematics, and demonstration are included in this repository.

---

## Demo
👉 Full system demonstration (inputs, CAN, display output):  
[▶ Watch Demo Video](./demo.mp4)

---

## System Architecture
<img width="976" height="600" alt="image" src="https://github.com/user-attachments/assets/2b802034-9352-4ec3-a90b-34f7360a2b17" />


The system is built around a centralized control architecture:
- **MCU:** STM32F103 (ARM Cortex-M3)
- **Communication:** CAN (vehicle interface), UART (debug)
- **Display:** SPI-based TFT LCD
- **Inputs:** Digital switches + analog signals (clutch, rotary)
- **Power:** 12V automotive input + USB fallback

---

## My Contributions
- Led end-to-end system development from requirements to validation
- Defined system architecture and hardware partitioning
- Designed complete schematic and 4-layer PCB (Altium Designer)
- Implemented power architecture (DC-DC + LDO design trade-offs)
- Performed hardware bring-up, debugging, and validation using lab equipment
- Resolved critical hardware issue (boot failure due to reset circuit)

---

## System Features
- Multi-input acquisition:
  - Digital inputs (Gear Up/Down + configurable buttons)
  - Analog inputs (clutch control and rotary selector)
- CAN bus communication:
  - Reception of vehicle data (e.g., temperature signals)
  - Control of LED outputs
- Real-time user interface:
  - TFT display (320×240) with dynamic feedback
- Dual power architecture:
  - 12V automotive supply
  - USB-based supply for controlled debugging

---

## Hardware Design

### PCB Design
- 4-layer stackup: Signal / Ground / Power / Signal
- Controlled impedance routing for CAN and USB
- EMI-aware layout and signal integrity optimization

### Power Architecture
- 12V → 3.3V DC-DC converter (>90% efficiency, <5% ripple)
- LDO regulator for low-noise operation and USB debugging
- Protection features:
  - TVS diode (transient suppression)
  - Reverse polarity protection
  - Input filtering (EMI mitigation)

---

## Firmware
- Developed in C using STM32CubeIDE
- Modular architecture:
  - Input acquisition layer
  - Processing logic
  - Output control (display + LEDs)
- CAN communication handling and debugging
- SPI-based display integration

---

## Validation & Testing
- Hardware bring-up and debugging
- Power integrity verification
- Clock stability validation (external oscillator)
- Functional testing:
  - Inputs (buttons, analog)
  - CAN communication
  - Display output
- System-level validation against requirements

---

## Key Technical Metrics
- Power Conversion Efficiency: >90%
- Output Ripple: <5%
- PCB: 4-layer design
- Supply Inputs: 12V automotive + 5V USB fallback

---

## Challenges & Solutions
- **Thermal constraints (no active cooling):**
  - Used efficient DC-DC + thermal vias and ground planes

- **Manufacturing delays:**
  - Continued development using STM32 Nucleo + HMI module

- **Boot failure issue:**
  - Root cause: incorrect reset switch footprint
  - Fix: hardware rework and validation

- **Cost vs automotive protection:**
  - Replaced surge stopper IC with discrete protection (TVS + diode)

---

## Design Files
- Schematics: `/SCHEMATICS/`
- PCB Layout & Altium Files: root directory
- Gerber Files: `/GERBER/`
- Datasheets: `/DATASHEETS & AN/`

---

## Outcome
- Achieved full compliance with all functional requirements
- Recognized as the **only team project meeting all specifications**
