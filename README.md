# Voltage-regulator-LM2596
## Circuit Description: LM2596S-ADJ Buck Converter

<img width="463" height="198" alt="LM2596ADJ-DC TO DC CONVERTOR" src="https://github.com/user-attachments/assets/c48692a3-39d2-4db5-ba6c-821266e4140c" />

---

### Overview
This is a **variable output DC-DC step-down (buck) converter** schematic based on the **LM2596S-ADJ** IC, designed by **Tashfeen Electronics**.

---

### Components Breakdown

| Component | Value | Function |
|---|---|---|
| **U1** | LM2596S-ADJ | Main switching regulator IC |
| **C1** | Capacitor | Input filter capacitor |
| **C2** | 220µF | Output smoothing capacitor |
| **D1** | LN6822 (Schottky) | Freewheeling diode |
| **L1** | Inductor | Energy storage / filtering |
| **RV1** | 10kΩ | Variable resistor (output voltage adjustment) |
| **R1** | 1kΩ | Feedback resistor |

---

### Signal Flow
```
IN+1 (+12V) → LM2596S-ADJ → Inductor L1 → OUT+1
                    ↓                ↓
               ON/OFF pin       Diode D1 (freewheeling)
                    ↓                ↓
                  GND          C2 (220µF filter)
                                     ↓
                              RV1 + R1 (voltage divider feedback)
                                     ↓
                                FB pin (adjusts output)
```

---

### How It Works
1. **Input** receives +12V DC at IN+1/IN-1
2. **LM2596S-ADJ** switches at fixed frequency (150kHz)
3. **L1 inductor** stores and releases energy
4. **D1 Schottky diode** provides a current path when switch is OFF
5. **C2 (220µF)** smooths the output voltage
6. **RV1 (10kΩ potentiometer)** adjusts the feedback voltage to the **FB pin**, which **sets the output voltage**
7. Regulated variable DC voltage appears at **OUT+1 / OUT-1**

---

### Key Features
- **Input:** 12V DC
- **Output:** Adjustable (typically **1.2V to 37V**)
- **Adjustable** via RV1 trimmer potentiometer
- **Efficient** switch-mode design (up to 92% efficiency)
- **ON/OFF control** pin available for enable/disable


---


## Applications

### 1. Power Supply Systems
- Benchtop variable power supplies for electronics labs
- Regulated power supplies for microcontrollers (Arduino, ESP32, STM32)
- Industrial control panel power regulation
- Replacing linear regulators (LM7805, LM317) for better efficiency

### 2. Battery Charging Systems
- Li-ion / LiPo battery chargers (with current limiting)
- Solar panel MPPT charge controllers
- Lead-acid battery maintenance chargers
- Multi-cell battery pack balancing circuits

### 3. Automotive & Vehicle Electronics
- 12V to 5V converters for USB charging in vehicles
- Dashboard electronics power supply
- Electric vehicle (EV) auxiliary power systems
- Motorcycle accessory power regulators

### 4. Renewable Energy Systems
- Solar energy harvesting and regulation
- Wind turbine output regulation
- Off-grid power management
- Energy storage system voltage control

### 5. Embedded Systems & IoT
- Raspberry Pi and single-board computer power supply
- Sensor node power management
- Wireless module (GSM, LoRa, WiFi) power supply
- Wearable electronics power regulation

### 6. LED Lighting
- Constant voltage LED driver
- RGB LED strip power supply
- Automotive LED lighting regulation
- Solar-powered LED street lights

### 7. Consumer Electronics
- Laptop power adapters
- Set-top box power supply
- Gaming console auxiliary power
- Portable device charging

### 8. Industrial Applications
- CNC machine control board power supply
- Motor driver power regulation
- PLC (Programmable Logic Controller) power modules
- Robotics power distribution systems

### 9. Telecommunications
- Base station auxiliary power regulation
- Network switch power supply
- Router and modem power modules
- Signal processing board power supply


---

## Hardware

| Parameter | Specification |
|---|---|
| **Module Length** | *(44.102mm)* |
| **Module Width** | *(21.300mm)* |
| **Mounting Hole Diameter** | *(1.100mm)* |

---

## Electrical Specifications

| Parameter | Value |
|---|---|
| **Input Voltage** | 4.5V – 40V DC |
| **Output Voltage** | 1.2V – 37V DC (Adjustable) |
| **Output Current (Max)** | 3A |
| **Switching Frequency** | 150 kHz |
| **Efficiency** | Up to 92% |
| **Feedback Voltage** | 1.23V (reference) |
| **Input Capacitor** | 100µF / 50V |
| **Output Capacitor** | 220µF / 35V |
| **Adjustment Potentiometer** | 10kΩ |
| **Feedback Resistor** | 1kΩ |
| **Operating Temperature** | 0°C to +125°C |

---

## Key Features
- Adjustable output voltage via onboard trimmer potentiometer
- High efficiency switching design
- Built-in ON/OFF control pin
- Thermal shutdown protection
- Current limiting protection
- Short circuit protection
- Low standby current consumption


### Design Notes

Keep the switching loop (LM2596, diode, and inductor) as short as possible to minimize electromagnetic interference (EMI).

Use wide PCB traces for the input, output, and ground paths to handle higher currents and reduce voltage drop.

Place the input and output capacitors close to the LM2596 pins for improved stability and reduced noise.

Ensure the Schottky diode and inductor are rated for the expected load current.

If the converter is operated at higher output currents, additional thermal management such as larger copper areas or a heatsink may be required.
