# ⭐ 4-Bit Digital Counter System (Manual & Automatic)
### TTL + CMOS Hardware • Logisim Simulation • Arduino & ADALM1000 Clocking  
A complete hardware + software project demonstrating binary counting, comparator logic, BCD decoding, and seven-segment display control.

---

## 🚀 Overview
This project implements **two digital counting systems**:

1. **Manual 4-bit Counter**  
   Built using classic 74LS-series TTL ICs (binary adder, comparator, BCD decoder).

2. **Automatic 4-bit Up Counter**  
   Built using the CD4516 CMOS counter driven by external clock signals  
   from **Arduino Nano** or **ADALM1000 (Python)**.

Both systems output to **dual 7-segment displays** and are fully recreated in **Logisim Evolution** for simulation.

---

# 🧩 Features

### 🔹 Manual Counter (Hardware)
- 74LS83 — 4-bit binary adder  
- 74LS85 — magnitude comparator  
- 74LS47 — BCD → 7-segment decoder  
- Manual increment via ADALM1000 inputs or switches  
- Output displayed on two 7-segment displays  

### 🔹 Automatic Counter (Hardware)
- CD4516 — 4-bit up/down counter  
- Clock signal options:
  - Arduino Nano (1 Hz digital clock)
  - ADALM1000 Python-based clock generator  
- Output decoded into tens/units via ROM mapping or IC logic  

### 🔹 Software Simulation
- Complete Logisim Evolution circuits  
- ROM-based BCD → 7-segment decoding  
- Splitter-based routing for display segments  
- PixelPlus 2 support for waveform verification  

---

# 📁 Repository Structure

```
HARDWARE/
    IMAGES/         → Breadboard photos, wiring images
    CLOCKCODE/      → Arduino 1Hz clock + ADALM1000 Python clock
SOFTWARE/
    IMAGES/         → Simulation screenshots
    SCHEMATICS/     → Logisim files + ROM text
LICENSE
README.md
```

---

# 🔍 Logisim ROM Table (BCD → 7-Segment)
Use this in your ROM component:

```
v2.0 raw
7E
30
6D
79
33
5B
5F
70
7F
7B
00
00
00
00
00
00
```

Use a **7→7 splitter** to map bits to segments **a–g**.

---

# ⏱️ Clock Signal Generation

### ✔ Arduino Nano Clock  
File located in:  
```
HARDWARE/CLOCKCODE/clock_generator.ino
```

Produces a 1 Hz square-wave clock on pin **D8** for CD4516.

### ✔ ADALM1000 Python Clock  
File located in:  
```
HARDWARE/CLOCKCODE/adalam_clock.py
```

Uses **libm2k** to toggle DIO0 at 1 Hz.

---

# 🖥️ Simulation Tools
| Tool | Purpose |
|------|---------|
| **Logisim Evolution** | Circuit design & verification |
| **PixelPlus 2** | Waveform and logic visualization |
| **Arduino IDE** | Uploading Arduino clock sketch |
| **Python + libm2k** | ADALM1000 clock control |

---

# 🔧 Hardware Required
- 74LS83 (4-bit adder)  
- 74LS85 (comparator)  
- 74LS47 (BCD decoder)  
- CD4516 (up counter)  
- 2 × 7-segment displays  
- 330 Ω resistors  
- Arduino Nano  
- ADALM1000 kit  
- Breadboard + jumpers  

Additional wiring details and diagrams are found in:  
```
SOFTWARE/SCHEMATICS/
```

---

# 📜 License
This project is released under the **MIT License**.  
See `LICENSE` for details.

---
