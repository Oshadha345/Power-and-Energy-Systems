# ⚡ Three Phase Systems - Master Notebook

---

## 📚 1. Introduction to Three-Phase Systems

- What is a three-phase system?
- Importance in Power Systems
- Advantages over Single-Phase Systems

🧠 **Key Concepts:**
- Phase Difference
- Rotating Magnetic Field
- Balanced vs Unbalanced Systems

---

## ⚙️ 2. Delta-Star (Δ-Y) Connection

### 🔹 2.1 Theory
- Delta Connection: Line and Phase Voltage/Current Relations
- Star Connection: Line and Phase Voltage/Current Relations
- Transformation between Delta ↔ Star

### 🛠️ 2.2 Coding Section - Delta-Star Converter

- **Mini Project**: 
  - Input: Phase voltages/currents
  - Output: Equivalent Delta or Star parameters

```python
# Delta to Star and Star to Delta Conversion Tool
import numpy as np

def delta_to_star(Vab, Vbc, Vca):
    R1 = (Vab*Vca) / (Vab + Vbc + Vca)
    R2 = (Vab*Vbc) / (Vab + Vbc + Vca)
    R3 = (Vbc*Vca) / (Vab + Vbc + Vca)
    return R1, R2, R3

def star_to_delta(R1, R2, R3):
    Rab = (R1 + R2 + (R1*R2/R3))
    Rbc = (R2 + R3 + (R2*R3/R1))
    Rca = (R3 + R1 + (R3*R1/R2))
    return Rab, Rbc, Rca

```

---

# 📓 Three Phase Systems - Part 2

## 📊 Visualization Idea
- Draw simple **Delta** and **Star** diagrams using `matplotlib`.

---

# 📈 3. Analysis of Balanced Three-Phase Systems

## 🔹 3.1 Theory

- **Symmetrical voltages and currents**
- **Power Calculations:**
  - Line Voltage, Phase Voltage
  - Power Factor
  - Active Power, Reactive Power, Apparent Power

---

## 🛠️ 3.2 Coding Section - 3-Phase Power Calculator

```python
# Balanced Three Phase Power Calculation
import numpy as np

def three_phase_power(V_L, I_L, pf):
    P = np.sqrt(3) * V_L * I_L * pf
    Q = np.sqrt(3) * V_L * I_L * np.sin(np.arccos(pf))
    S = np.sqrt(3) * V_L * I_L
    return P, Q, S
```

---

## 📊 Visualization Idea
- Animate **rotating phasors** to show balance using `matplotlib`.

---

# 📉 4. Analysis of Unbalanced Three-Phase Systems

## 🔹 4.1 Theory

- **Types of Unbalance**
  - Voltage Unbalance
  - Current Unbalance
- **Impact on Machines and Systems**

---

## 🛠️ 4.2 Coding Section - Voltage Unbalance Index (VUI)

```python
# Voltage Unbalance Calculation
def voltage_unbalance(V1, V2, V3):
    V_avg = (V1 + V2 + V3) / 3
    max_dev = max(abs(V1 - V_avg), abs(V2 - V_avg), abs(V3 - V_avg))
    vui = (max_dev / V_avg) * 100
    return vui
```

---

# 🧪 5. Simulation Projects

🎯 **Mini-Project 1**: Balanced 3-phase System Simulator  
🎯 **Mini-Project 2**: Effect of Voltage Unbalance on Power Factor

---

# 📌 6. Hidden Math Connections

- **Linear Algebra**:
  - Three-phase voltages can be treated as vectors.
  - Use Matrix Operations for transformations (Symmetrical Components).

- **Complex Numbers**:
  - Phasor representation uses Euler's Formula!

## Visualization Tip:
- Use `matplotlib` or `plotly` to rotate vectors over time.

---

# 🏆 7. Challenges

- Create a **GUI (using Python)** to input V and I and calculate 3-phase powers.
- Simulate sudden unbalance and show its effect on Active Power.
- Animate the rotating magnetic field using **Matplotlib**.

---

# 📚 8. References and Learning Resources

- [Electrical 4U - Three Phase Systems](https://www.electrical4u.com/three-phase-systems/)
- *Power System Analysis* - Hadi Saadat (Book)
- [EEVblog - Youtube Lectures](https://www.youtube.com/user/EEVblog)
- [Wikipedia - Delta-Star Transformations](https://en.wikipedia.org/wiki/Y-%CE%94_transform)



