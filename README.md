# forward-converter-design
Forward Converter Design | LTspice Simulation | Hardware Implementation
# ⚡ Forward Converter Design & Implementation  
**Power Electronics | Magnetics Design | LTspice + Hardware Validation**

This project presents the complete **design, simulation, and hardware implementation** of an isolated forward converter converting **10 V → 15 V (~22.5 W)**.

The work includes **custom magnetics design (transformer + inductor), LTspice simulation with practical parameters, and experimental validation**, demonstrating strong correlation between theory and hardware.

---

## 📌 Specifications

- Input Voltage: 10 V  
- Output Voltage (Design): 15 V  
- Load: 10 Ω  
- Power: 22.5 W  
- Switching Frequency: 10 kHz  
- Topology: Isolated Forward Converter (with reset winding)

---

## 🧠 Key Highlights

- Designed **EE42/21/15 ferrite transformer**
- Reset winding implemented (**same turns as primary**) for proper core demagnetization
- Designed **air-gapped output inductor (3.125 mH)**
- Performed **LTspice simulation including non-idealities**
- Built **hardware prototype on dot board**
- Verified operation using **DSO measurements**
- Achieved **~86% efficiency experimentally**

---

## 🔧 Transformer Design

- Core: EE42/21/15 ferrite  
- Primary: 14 turns (practical: 17 turns)  
- Secondary: 56 turns (practical: 63 turns due to window limitation)  
- Reset winding: **same as primary (17 turns, bifilar)**  

### Key Point:
Due to winding constraints, full secondary turns could not be accommodated, resulting in an effective turns ratio closer to **1:3 instead of 1:4**, which impacted output voltage. :contentReference[oaicite:1]{index=1}  

---

## 🔌 Output Inductor Design

- Designed: 3.125 mH  
- Practical: ~4.67 mH  
- Air-gap: ~0.8 mm  

Higher inductance reduced current ripple and ensured **continuous conduction mode (CCM)**.

---

## 🧪 LTspice Simulation

The complete converter was simulated in LTspice including:

- Transformer (coupled inductors)
- MOSFET and diode losses
- Measured inductance and ESR values

### Results:
- Ideal output ≈ 15 V  
- Practical simulation ≈ 10.4 V  

✔ Simulation updated using measured values closely matches hardware output.

---

## 🛠 Hardware Implementation

- Built on **dot board (perfboard)**
- Controller: TL494 PWM IC  
- MOSFET: IRF540N  
- Diode: MBR20100CT (Schottky)

### Measured Observations:
- Switching frequency ≈ 10 kHz  
- Duty cycle ≈ 38%  
- Proper transformer reset observed  

---

## 📊 Experimental Results

| Parameter | Designed | Practical |
|----------|----------|----------|
| Output Voltage | 15 V | 10.37 V |
| Output Current | 1.5 A | 1.04 A |
| Input Power | — | 12.5 W |
| Output Power | — | ~10.75 W |
| Efficiency | ~90% (ideal) | **~86%** |

✔ Efficiency calculated using measured values :contentReference[oaicite:2]{index=2}  

---

## ⚠️ Engineering Observations

- Transformer window limitation reduced turns ratio  
- Leakage inductance and winding resistance affected output  
- Duty cycle limited to ~38%  
- Practical non-idealities significantly impact performance  

---

## 📚 Key Learnings

- Magnetics design is critical in power converters  
- Simulation must include real parameters to match hardware  
- Reset winding eliminates need for snubber  
- Practical constraints dominate real-world performance  

---
## 📁 Repository Structure
