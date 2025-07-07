# 📄 RCA Connector Project File Selection Guide

This project includes two versions of the PCB layout for RCA connectors:

- **Standard Pinout (Non-Inverted)**: `1-PCB_Phasor.json`
- **Swapped Pinout (Inverted)**: `1-PCB_Phasor-RCA-Swap.json`

## 🔍 Identify Your RCA Connector

Use the mechanical drawing of your RCA jack to determine the correct pinout.

### ✅ If your RCA jack matches the one below:

- Has **Pin 1 connected to GND** (as shown in the bottom-right mechanical diagram of the reference image).
- Typically seen with some specific RCA jack models where the pinout is swapped.

📌 **Use:** `1-PCB_Phasor-RCA-Swap.json`  
👉 This version swaps the signal (Pin 1) and ground (Pin 2) to match this connector footprint.

### ✅ If your RCA jack uses the standard layout:

- Follows the **conventional RCA pinout**:
  - Pin 1 = Signal (center)
  - Pin 2 = Ground (shell)

📌 **Use:** `1-PCB_Phasor.json`  
👉 This is the standard design for typical RCA connectors.

## 🗂️ Gerber File Output Guide

| RCA Jack Type                        | Use This Design File            | Notes                                 |
|-------------------------------------|----------------------------------|---------------------------------------|
| Standard RCA (Pin 1 = Signal)       | `1-PCB_Phasor.json`              | Use for most RCA jacks                |
| Swapped RCA (Pin 1 = Ground)        | `1-PCB_Phasor-RCA-Swap.json`     | Use for RCA jacks with reversed pins |

---

⚠️ **Important:** Always verify your RCA jack's mechanical footprint before producing Gerbers and ordering PCBs.