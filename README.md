## F1-Style Steering Wheel ECU (Embedded Automotive System)

## Overview
Led the end-to-end development of an F1-style steering wheel control module based on requirements defined by the Ferrari engineering team.  
The system functions as an embedded ECU, handling driver inputs, CAN communication, and real-time display feedback.

<img width="976" height="600" alt="image" src="https://github.com/user-attachments/assets/cca16b1a-6531-4923-a927-6840cd9a90fe" />


---

## My Role
- Led system-level design and development from requirements to validation
- Owned hardware architecture, schematic design, and PCB development
- Contributed to system integration, bring-up, and validation

---

## System Features
- Multi-input acquisition:
  - Digital inputs (Gear Up/Down + configurable buttons)
  - Analog inputs (clutch control and rotary selector)
- CAN bus communication:
  - Reception of vehicle data (e.g., temperature signals)
  - Control of output indicators (LEDs)
- Real-time user interface:
  - TFT display (SPI) for driver feedback
- Dual power architecture:
  - 12V automotive input
  - USB-based supply for controlled debugging and bring-up

---

## System Architecture
- **MCU:** STM32F103 (ARM Cortex-M3)
- **Communication:** CAN (SN65HVD232 transceiver)
- **Display:** SPI-based TFT LCD (320×240)
- **Interfaces:** UART (debug), USB
- **Power:**
  - Switching regulator (12V → 3.3V)
  - LDO with USB power to test without the dependancy of bench power supply

Defined complete system architecture and block diagram, including:
- Mixed-signal input handling
- Communication interfaces (CAN, SPI, UART)
- Power management strategy with protection

---

## Hardware Design
- Designed full schematic and 4-layer PCB in Altium Designer
- Stack-up: Signal / Ground / Power / Signal
- Controlled impedance routing for CAN and USB signals
- Integrated:
  - STM32F103 MCU
  - Mixed-signal inputs
  - TFT display interface
  - PC communication interface

### Power Design
- Designed 12V automotive power architecture:
  - High-efficiency DC-DC converter (12V → 3.3V) with <5% output ripple
  - LDO-based USB supply for safe bring-up and debugging
- Implemented protection:
  - TVS diode (transient suppression)
  - Reverse polarity protection
  - Input filtering for EMI mitigation

---

## Validation & Bring-Up
- Performed full hardware bring-up and debugging
- Validated system functionality against defined requirements
- Used lab equipment (oscilloscope, power supply) for:
  - Power integrity verification
  - Signal validation
  - Interface debugging (CAN, display)

---

## Key Engineering Decisions
- Modular architecture:
  - Separation of main control board and HMI interface
  - Enabled parallel development and easier iteration
- Power trade-offs:
  - DC-DC for efficiency vs LDO for low-noise operation
- Thermal design:
  - Passive cooling only (no fan)
  - Thermal vias + ground plane heat dissipation

---

## Challenges & Solutions
- **Manufacturing delays:**
  - Continued firmware and system testing using STM32 Nucleo + HMI module


---

## Outcome
- Achieved full compliance with all functional requirements
- Recognized as the **only team project meeting all specifications**
