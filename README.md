📘 4-Bit Counter & 7-Segment Display Project (Manual + Automatic)

This repository contains the full hardware and software implementation of two digital counter systems:

A manual 4-bit counter using TTL ICs

An automatic up-counter using a CMOS counter

Both systems drive dual seven-segment displays and include Logisim Evolution simulations, Arduino-based clock generation, and Python-controlled ADALM1000 clocking.

🔧 Project Features
Manual Counter (Hardware)

74LS83 – 4-bit binary adder

74LS85 – magnitude comparator

74LS47 – BCD-to-7-segment decoder (common anode)

Two 7-segment displays

Manual input from ADALM1000 kit or switches

Automatic Counter (Hardware)

CD4516 – 4-bit up/down counter

Clock sources:

Arduino Nano (C programmed)

ADALM1000 + Python script

Display through 74LS47 or ROM → splitter → 7-seg

Software Simulation

Full Logisim Evolution circuits:

manual_counter.circ

auto_counter.circ

ROM-based BCD→7-segment decoder

Splitter wiring for segment extraction

LTspice behavioural model for 7-segment verification

📁 Repository Structure
hardware/
    schematics/      → wiring diagrams & IC pin maps
    images/          → photos of real hardware
firmware/
    arduino/         → Arduino clock generator (.ino)
    python/          → ADALM1000 clock script (.py)
simulations/
    logisim/         → .circ files + ROM tables
    ltspice/         → 7-segment model
docs/
    BOM.md           → list of all components used
    wiring.md        → step-by-step hardware wiring
LICENSE
README.md

🧠 Manual Counter – How It Works

The manual system allows user-controlled incrementation through switches:

74LS83 adds the manual input bits

74LS85 compares the count with a preset value

74LS47 converts BCD output into 7-segment signals

Two displays show the decimal result

This demonstrates addition, comparison, and BCD decoding using classical TTL ICs.

⚙️ Automatic Counter – How It Works

The automatic mode uses a CD4516 counter that increments on every clock pulse.

Clock sources supported:

Arduino Nano generating a 1–10 Hz square wave

ADALM1000 toggled via Python for arbitrary frequency clocks

The output is decoded the same way as in the manual version.

🖥️ Simulation in Logisim Evolution

The repository includes complete .circ files.

ROM contents:
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


Use a splitter (7 → 7) to route ROM output bits to segments a–g.

🔌 Arduino Clock Generator

Upload clock_generator.ino to Arduino Nano.

It outputs a square wave on a chosen pin (default D8) to drive the CD4516 clock input.

🐍 ADALM1000 Python Clock

Run:

python adalam_clock.py


This toggles GPIO (via DTR or device-specific control) to create a clock pulse for the counter.

📚 Bill of Materials

Located in docs/BOM.md.

Includes:

74LS83

74LS85

74LS47

CD4516

2 × common-anode 7-segment displays

Resistors (330Ω)

Arduino Nano

ADALM1000 kit

Breadboard & jumper wires
