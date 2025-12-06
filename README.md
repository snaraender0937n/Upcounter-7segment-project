# ⭐ 4-Bit Digital Counter System (Manual & Automatic)
### TTL + CMOS + Logisim Simulation + Arduino/ADALM1000 Clocking  
A complete hardware + software project demonstrating binary counting, BCD decoding, and seven-segment display control.

---

## 🚀 Overview
This project implements **two complete digital counting systems**:

1. **Manual 4-bit Counter**  
   Built using classic 74LS TTL ICs — binary adder, comparator, and BCD decoder.

2. **Automatic 4-bit Up Counter**  
   Built using the CD4516 CMOS counter driven by a clock from  
   **Arduino Nano** or **ADALM1000 (Python-controlled)**.

Both systems drive **dual seven-segment displays**, and both are fully recreated in **Logisim Evolution** for easy simulation and verification.

---

# 🧩 Features

### 🔹 Manual Counter Hardware
- 74LS83 — 4-bit binary adder  
- 74LS85 — magnitude comparator  
- 74LS47 — BCD-to-7-segment decoder (common anode)  
- Manual increment input from switches or ADALM1000  
- Output displayed on two 7-segment displays  

### 🔹 Automatic Counter Hardware
- CD4516 — 4-bit up/down counter  
- Clock generation methods:  
  - Arduino Nano (`clock_generator.ino`)  
  - ADALM1000 (`adalam_clock.py`)  
- Output decoded to seven-segment via ROM or BCD logic  

### 🔹 Software Simulation (Logisim Evolution)
- Full circuits:
  - `manual_counter.circ`
  - `auto_counter.circ`
- ROM-based BCD → 7-segment decoder  
- Splitter-based segment routing  
- PixelPlus 2 support for waveform/simulation visualization  

---

# 🗂️ Repository Structure
```
hardware/
  schematics/      → diagrams & pin maps
  images/          → hardware photos
firmware/
  arduino/         → Arduino clock (.ino)
  python/          → ADALM1000 clock (.py)
simulations/
  logisim/         → .circ files + ROM data
docs/
  BOM.md           → component list
  wiring.md        → wiring & IC pin mapping
LICENSE
README.md
```

---

# 🔍 Logisim ROM Table (BCD → 7-Segment)
Paste this into your ROM:

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

Use a **7→7 Splitter** to route bits to segments **a–g**.

---

# ⚙️ Clock Generation

### ⏱️ Arduino Nano  
Upload:
```
clock_generator.ino
```
Generates a clean square-wave clock on pin **D8**.

### ⏱️ ADALM1000  
Run:
```
python adalam_clock.py
```
Toggles digital output to create a hardware clock signal.

---

# 🛠️ Hardware Required
- 74LS83 — Binary adder  
- 74LS85 — Comparator  
- 74LS47 — BCD → 7-seg decoder  
- CD4516 — Up/down counter  
- 2× 7-segment displays (common anode)  
- Resistors — 330 Ω  
- Arduino Nano / ADALM1000  
- Breadboard + jumper wires  

More details in `docs/BOM.md`.

---

# 🧪 Simulation Tools
| Tool | Purpose |
|------|---------|
| **Logisim Evolution** | Main digital circuit design & testing |
| **PixelPlus 2** | Waveform and logic visualization |
| **Arduino IDE** | Uploading Arduino clock firmware |
| **Python + pyserial** | ADALM1000 clock control |

---

# 📜 License
This project is released under the **MIT License**.  
You may use, modify, and distribute it freely.

---
