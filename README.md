![Phasor](readme-image.jpg)

# PHASOR AVR Demo — Custom PCB

This repository contains a custom double-layer PCB design for running the [PHASOR demo](https://www.linusakesson.net/hardware/phasor/index.php) by Linus Åkesson on an ATmega88-20PU microcontroller.

---

## 📁 Contents

- `JSON/`: EasyEDA schematic and board layout  
- `firmware/`: Precompiled HEX file and Flipper Zero-compatible firmware folder  
- `README.md`: Project documentation

---

## ⚙️ Features

- Pure AVR synth demo running on ATmega88  
- Composite PAL video output  
- Generative visuals synced to audio    
- 5V operation (via 78L05 regulator)  
- ISP programming header for flashing

---

## 📦 Bill of Materials (BOM)

| Qty | Component               | Specification           |
|-----|-------------------------|--------------------------|
| x1  | Resistor                | 220 Ω                    |
| x4  | Resistor                | 442 Ω                    |
| x11 | Resistor                | 1 kΩ                     |
| x19 | Resistor                | 2 kΩ                     |
| x3  | Diode                   | 1N4148-35                |
| x2  | Ceramic Capacitor       | 22 pF                    |
| x2  | Electrolytic Capacitor  | 10 µF                    |
| x1  | Header (SPI)            | 2x3                      |
| x1  | Header (Power)          | 1x2                      |
| x1  | LED                     | 3 mm                     |
| x2  | Transistor              | BC547                    |
| x1  | Voltage Regulator       | 78L05                    |
| x1  | IC Socket               | DIP28                    |
| x1  | Microcontroller         | ATmega88-20PU            |
| x1  | Oscillator              | 17.73447 MHz             |
| x2  | RCA Connector           | RCJ-042                  |

> 💡 **Notes:**
> - The **2x3 header** is used for **ISP/SPI programming** of the ATmega88.
> - The **1x2 header** is for **external power supply** (e.g. battery or adapter).

---

## 🔩 Recommended Soldering Order

Follow this order to make the assembly easier and reduce error risk:

1. **🟫 Resistors (220 Ω, 442 Ω, 1 kΩ, 2 kΩ)**  
   Start with the flattest components.

2. **⬛ Diodes (1N4148-35)**  
   Mind the **polarity** (black stripe = cathode).

3. **📎 Ceramic Capacitors (22 pF)**  
   Non-polarized, orientation doesn’t matter.

4. **📦 DIP Socket for ATmega88**  
   Ensure proper orientation with the notch.

5. **⏱️ Oscillator (17.73447 MHz)**  
   Place after flat components are soldered.

6. **⚙️ Transistors (BC547)**  
   Align with the silkscreen (half-moon shape).

7. **💡 LED (3 mm)**  
   ⚠️ Polarity: longer leg = **anode**.

8. **📏 Headers**  
   - **2x3 (SPI)** for programming — solder straight.  
   - **1x2 (Power)** for external power supply.

9. **🔌 Voltage Regulator (78L05)**  
   Check orientation per the silkscreen.

10. **🧯 Electrolytic Capacitors (10 µF)**  
    ⚠️ Respect polarity: longer leg = positive.

11. **🎵 RCA Connectors (RCJ-042)**  
    Large components — solder last to avoid obstruction.

12. **🧠 Microcontroller (ATmega88-20PU)**  
    Insert into the socket, notch facing the same direction as the socket notch.

---

## 🛠️ Flashing the Firmware

The `firmware/` folder includes:

- `flash.hex` — Precompiled firmware for ATmega88-20PU  
- `AVR Flasher/` — Folder structure compatible with **Flipper Zero**

### 🔧 Flashing with Flipper Zero

1. Copy the contents of the `AVR Flasher/` folder to your Flipper Zero's SD card under `/apps_data/avr_isp/`
2. Connect the Flipper to the PHASOR PCB via the **ISP (2x3) header**
3. Launch the **AVR Flasher** app on your Flipper
4. Select `phasor_pcb.avr` and flash it to the ATmega88

---

## ⚠️ Beware: RCA Connector Signal/Ground Inversion

If the RCA connectors are wired incorrectly — with **signal and ground inverted** — the video output will appear **distorted, wavy, or unstable**, even on CRT displays.

### ✅ Correct RCA wiring:
- **Center pin** = Composite **video signal**
- **Outer ring (shield)** = **Ground**

> 🔧 If your display shows unstable video, check the RCA jack wiring. Inverting signal and ground is a common mistake..

### 💡 Quick Fix:
If you've already soldered the RCA cable and suspect inversion, a quick test is to **cut and reverse the signal and ground wires** on the cable or at the connector.

---

## 🧠 Credits

- **Original demo**: Linus Åkesson  
- **Custom PCB layout**: by me, for my local hackerspace  