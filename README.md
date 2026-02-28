# 5V → 3.3V Voltage Regulator Module (AMS1117)

## Overview

This project implements a compact **5V to 3.3V linear voltage regulator module** using the **AMS1117-3.3 Low Dropout (LDO) regulator**.  
The design converts USB 5V input into a stable 3.3V output for embedded and robotics applications.

The module is intended for powering microcontrollers, sensors, and low-power embedded devices requiring regulated 3.3V supply.

---

## System Architecture

```
USB 5V Input → Input Filter → AMS1117 LDO → Output Filter → 3.3V Output
```

### Functional Blocks

- **Power Input** — USB Micro-B 5V source
- **Input Filtering** — Stabilizes input voltage
- **Voltage Regulation** — AMS1117-3.3 LDO
- **Output Filtering** — Reduces ripple and noise
- **Power Output** — 3.3V screw terminal

---

## Hardware Specifications

| Parameter | Value |
|---|---|
| Input Voltage | 5V (USB VBUS) |
| Output Voltage | 3.3V ±1% |
| Regulator | AMS1117-3.3 |
| Regulator Type | Linear LDO |
| Output Current | Up to 800mA (thermal dependent) |
| Protection | Capacitive filtering |
| Interface | USB Micro-B |

---

## Design Considerations

### Thermal Performance
The AMS1117 is a linear regulator:

```
Power Dissipation = (Vin − Vout) × Load Current
```

Proper PCB copper area or heat dissipation is recommended for high current loads.

### Stability
- Input and output capacitors are required for regulator stability.
- Output ripple minimized using decoupling capacitors.

### Efficiency
As a linear regulator, efficiency decreases with higher load current.

---

## Bill of Materials (BOM)

| Component | Description |
|---|---|
| AMS1117-3.3 | 3.3V LDO Regulator |
| USB Micro-B Connector | Power input |
| Electrolytic Capacitors | Input/output filtering |
| Ceramic Capacitors | Noise suppression |
| Screw Terminal | Output interface |

---

## Repository Structure

```
/hardware
  ├── schematic
  ├── pcb
  └── libraries

/docs
  └── design_notes

README.md
LICENSE
```

---

## Development Environment

- **EDA Tool:** KiCad
- **Design Type:** 2-layer PCB
- **Target Domain:** Embedded Systems / Robotics Hardware

---

## Applications

- Embedded controllers (ESP32, STM32, etc.)
- Robotics power modules
- Sensor power supply
- IoT hardware
- Drone electronics
- Custom PCB projects

---

## Limitations

- Linear regulator → lower efficiency
- Heat generation at high current
- No reverse polarity protection
- No overcurrent protection

---

## Future Work

- Reverse polarity protection circuit
- Current limiting protection
- Power indicator LED
- Switching regulator alternative
- Thermal optimization

---

## License

This project is licensed under the MIT License.

---

## Author

Shital Darvante  
Robotics & Embedded Systems Developer

---

## References

- AMS1117 Datasheet
- KiCad Documentation
