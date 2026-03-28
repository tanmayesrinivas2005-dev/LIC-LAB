#  Experiment 02  
## Design and Characterization of Common Source (CS) Amplifier Topologies

---

##  1. Problem Statement

**Design Objective:**  
Develop and analyze multiple **Common Source (CS) amplifier configurations** using **TSMC 180 nm CMOS technology** in **LTspice**.

### Design Constraints

- **Maximum Power Dissipation:** \( P \leq 1\,mW \)  
- **Supply Voltage:** \( V_{DD} = 1.8\,V \)  
- **Load Capacitance:** \( C_L = 10\,pF \)  
- **Channel Length:** \( L = 180\,nm \)

###  Goal

To evaluate and compare amplifier performance using:

- DC Operating Point Analysis  
- Transient Response  
- AC Frequency Analysis  

---

##  2. Aim

To design and examine three different CS amplifier configurations:

1. Source Degenerated Amplifier  
2. Active Load (PMOS) Amplifier  
3. Diode-Connected Load Amplifier  

All circuits are designed to:

- Operate within the given power budget  
- Maintain MOSFET operation in the **saturation region**  

---

##  3. Components Required

- **Simulation Tool:** LTspice  
- **Technology Library:** TSMC 180 nm CMOS  
- **Active Devices:** NMOS (\(M_1, M_3\)), PMOS (\(M_2\))  
- **Passive Components:** Resistor (\(R_S\)), Capacitor (\(C_L\))  
- **Sources:** \(V_{DD}\), Bias Voltage (\(V_{bias}\)), Input Signal (\(V_{in}\))  

---

##  4. Theoretical Design and Calculations

###  4.1 Power and Current Constraints

\[
I_D \leq \frac{P}{V_{DD}} = \frac{1\,mW}{1.8\,V} = 555.6\,\mu A
\]

 **Chosen Design Current:**

\[
I_D = 200\,\mu A
\]

 Ensures safe operation within power limits and improves thermal reliability  

---

###  4.2 Biasing and Operating Point

To ensure proper amplification:

\[
V_{DS} \geq V_{ov}
\]

Check:

\[
\frac{V_{DD}}{2} = 0.9V \geq 0.25V
\]

 Condition satisfied  

---

###  Gate Bias Voltage

\[
V_{GS} = V_{ov} + V_{TH} = 0.25 + 0.36 = 0.61V
\]

---

###  NMOS Sizing

Using:

\[
I_D = \frac{1}{2} \mu_n C_{ox} \frac{W}{L} V_{ov}^2
\]

 Calculated width:

\[
W_n \approx 5\,\mu m
\]

---

###  PMOS Sizing

\[
V_{SG} = |V_{THp}| + V_{ov} = 0.39 + 0.25 = 0.64V
\]

\[
V_G = V_{DD} - V_{SG} = 1.16V
\]

 Calculated width:

\[
W_p \approx 11.8\,\mu m
\]

---

###  4.3 Source Degeneration Resistor

To introduce feedback:

\[
I_D R_S = 0.2V
\]

\[
R_S = \frac{0.2}{200\mu A} = 1k\Omega
\]

Updated gate bias:

\[
V_B = V_{GS} + I_D R_S = 0.81V
\]

---

# 5. Circuit Configurations and Results

---

##  Configuration 1: CS Amplifier with Source Degeneration

This configuration incorporates a source resistor to enhance **stability and linearity**, though at the expense of gain.

###  Results

- **Drain Current:** \( 199.1\,\mu A \)  
- **Input:** \( 19.63\,mV_{pp} \)  
- **Output:** \( 223.64\,mV_{pp} \)

\[
A_v \approx 11.22 \, V/V \; (\approx 21\,dB)
\]

- **Bandwidth:** \( 203.52\,MHz \)

<img width="1919" height="800" alt="transient ckt1" src="https://github.com/user-attachments/assets/2c7da381-73df-456f-b6dd-4bc83a162a1e" />

---

##  Configuration 2: CS Amplifier with Active Load (PMOS)

Here, a PMOS transistor replaces the resistor, acting as a **high-resistance load**, significantly improving gain.

### Results

- **Drain Current:** \( 199.3\,\mu A \)  
- **Input:** \( 19.33\,mV_{pp} \)  
- **Output:** \( 279.49\,mV_{pp} \)

\[
A_v \approx 14.68 \, V/V \; (\approx 23.33\,dB)
\]

- **Bandwidth:** \( 422.31\,MHz \)

<img width="1916" height="808" alt="AC Analysis ckt2" src="https://github.com/user-attachments/assets/d9da6825-dd8e-412d-a473-d10261eda497" />

---

## 🔌 Configuration 3: CS Amplifier with Diode-Connected Load

In this configuration, the load MOSFET is diode-connected, resulting in a **low effective resistance**.

###  Results

- **Drain Current:** \( 200.0\,\mu A \)  
- **Input:** \( 19.46\,mV_{pp} \)  
- **Output:** \( 79.49\,mV_{pp} \)

\[
A_v \approx 4.13 \, V/V \; (\approx 12.33\,dB)
\]

- **Bandwidth:** \( 140.92\,MHz \)

<img width="953" height="785" alt="ckt3 DC" src="https://github.com/user-attachments/assets/205df3da-b262-4be9-9b85-800902ed92e4" />

---

#  6. Performance Comparison

| Metric | Source Degeneration | Active Load | Diode-Connected |
|--------|-------------------|------------|----------------|
| Gain (\(A_v\)) | 11.22 | **14.67** | 4.13 |
| Bandwidth | 203.5 MHz | **422.3 MHz** | 140.9 MHz |
| Gain-BW Product | 2.28 GHz | **6.19 GHz** | 582 MHz |
| Power | 0.358 mW | 0.359 mW | 0.358 mW |

---

#  7. Discussion and Interpretation

###  Performance Insights

- The **Active Load configuration** achieves the highest gain due to increased output resistance.
- The **Source Degenerated amplifier** provides better linearity and stability.
- The **Diode-Connected configuration** sacrifices gain but ensures robust and predictable operation.

---

###  Final Observations

- All designs successfully satisfy the power constraint:

\[
P \approx 0.358\,mW < 1\,mW
\]

- Gain and bandwidth trade-offs are clearly observed across configurations.

---

#  8. Conclusion

- The **Active Load CS amplifier** is best suited for high-gain and high-speed applications  
- The **Source Degenerated amplifier** is ideal for linear and stable analog designs  
- The **Diode-Connected load** is useful in circuits requiring predictable and stable biasing  

---

# Inference

This experiment highlights the importance of **load selection in amplifier design**.

- Gain is strongly dependent on output resistance  
- Bandwidth is influenced by parasitic capacitances  
- Trade-offs between gain, stability, and bandwidth must be carefully balanced  

✔ The results validate theoretical expectations for CS amplifier behavior in **TSMC 180 nm CMOS technology**
