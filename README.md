# ⭐ 4-Bit Digital Counter System (Manual & Automatic)
### TTL + CMOS + Logisim Simulation + Arduino/ADALM1000 Clocking  
A complete hardware + software project demonstrating binary counting, BCD decoding, and seven-segment display control.

---

## 🚀 Overview
This project implements **two digital counting systems**:

1. **Manual 4-bit Counter**  
   Built using 74LS-series TTL ICs (adder, comparator, BCD-to-7seg driver)

2. **Automatic 4-bit Up Counter**  
   Built using CD4516 CMOS counter with external clock sources  
   (Arduino Nano OR ADALM1000 using Python)

Both systems display output using **dual seven-segment displays** and are fully simulated in **Logisim Evolution**.

---

# 🧩 Features

### 🔹 Manual Counter Hardware
- 74LS83 → 4-bit binary adder  
- 74LS85 → magnitude comparator  
- 74LS47 → BCD-to-7-segment decoder (common anode)  
- Manual input via ADALM1000 or physical switches  
- Output shown on two 7-segment displays  

### 🔹 Automatic Counter Hardware
- CD4516 → 4-bit up/down counter  
- Clock generated using:  
  - Arduino Nano (`clock_generator.ino`)  
  - ADALM1000 (`adalam_clock.py`)  
- Output decoded through ROM/BCD to seven-segment  

### 🔹 Software Simulation
- Logisim Evolution circuits (`manual_counter.circ`, `auto_counter.circ`)  
- ROM-based BCD → 7-segment decoder  
- 7→7 splitter wiring  
- Optional LTspice behavioural model  

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
  ltspice/         → optional 7-segment model
docs/
  BOM.md           → component list
  wiring.md        → wiring & IC pin mapping
LICENSE
README.md
```

---

# 🔍 Logisim ROM Table (BCD → 7-Segment)
Paste this inside the ROM contents editor:

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
Produces a square wave on pin D8 for the CD4516 clock input.

### ⏱️ ADALM1000  
Run:
```
python adalam_clock.py
```
Toggles a digital pin to generate a hardware clock pulse.

---

# 🔧 Hardware Required
- 74LS83 (4-bit adder)  
- 74LS85 (comparator)  
- 74LS47 (BCD → 7-seg)  
- CD4516 (up/down counter)  
- Two 7-segment displays (common anode)  
- Resistors: 330Ω  
- Arduino Nano / ADALM1000  
- Breadboard + jumper wires  

Full list: `docs/BOM.md`.

---

# 🧪 Simulation Tools
| Tool | Purpose |
|------|---------|
| **Logisim Evolution** | Main circuit design & verification |
| **LTspice** | 7-segment behaviour modelling (optional) |

Both `.circ` files are included in the repo.

---

# 📜 License
This project is released under the **MIT License**.  
You may use, modify, and distribute it freely.

---
