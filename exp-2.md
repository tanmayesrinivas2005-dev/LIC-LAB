# 🔬 Experiment 02  
## Detailed Analysis of Common Source (CS) Amplifier Topologies

---

## 🎯 Project Objective

The objective of this experiment is to **design and analyze three Common Source (CS) amplifier configurations** using **TSMC 180 nm CMOS technology**.

The design constraints are:

- Power budget: \( P \leq 1\,mW \)  
- Target drain current: \( I_D \approx 200\,\mu A \)

Each configuration is evaluated based on:

- DC biasing conditions  
- Voltage gain  
- Signal swing  
- Bandwidth and frequency response  

---

# 🔧 1. Configuration A: CS Amplifier with Source Degeneration (\(R_S\))

## 1.1 Circuit Schematic

<img width="1068" height="828" alt="ckt1" src="https://github.com/user-attachments/assets/6ba315ce-bd95-40a4-b2ac-7c89cee4eed0" />

---

## 1.2 Theoretical Analysis

### Transconductance

\[
g_m = \frac{2I_D}{V_{OV}}
\]

### Voltage Gain

\[
A_v = \frac{-g_m R_D}{1 + g_m R_S}
\]

### Key Insight

- The presence of \(R_S\) introduces **negative feedback**
- This improves **linearity and bias stability**
- Gain is reduced compared to a simple CS amplifier

---

## 1.3 Simulation Results

### 🔹 DC Analysis

- \( V_{GS} \approx 0.7V \)  
- \( V_{DS} \approx 0.9V \)  

✔ Condition satisfied:

\[
V_{DS} > V_{GS} - V_{TH}
\]

👉 Transistor operates in **saturation region**

<img width="942" height="780" alt="DC ckt1" src="https://github.com/user-attachments/assets/ef8de1b5-6390-4282-bd10-40c29466f550" />

---

### 🔹 Transient Analysis

- Input: \( 20\,mV_{pp} \)  
- Output: \( 224.4\,mV_{pp} \)

\[
A_v \approx 11.22 \, V/V
\]

✔ Output shows **clear amplification with phase inversion**

<img width="1919" height="800" alt="transient ckt1" src="https://github.com/user-attachments/assets/f05944ac-3d1d-4c2d-b37e-a2cb30a65f97" />

---

### 🔹 AC Analysis

- 3 dB Bandwidth: **203.52 MHz**  
- Unity Gain Bandwidth (UGB): **2.28 GHz**

<img width="1919" height="793" alt="AC Analysis ckt1" src="https://github.com/user-attachments/assets/8fe216c0-89cd-43ab-9ad5-b14ff2953fe2" />

---

# ⚡ 2. Configuration B: CS Amplifier with Active Load (PMOS)

## 2.1 Circuit Schematic

<img width="1195" height="829" alt="ckt2" src="https://github.com/user-attachments/assets/88739370-cd66-422e-920e-3de073e63e40" />

---

## 2.2 Theoretical Analysis

### Output Resistance

\[
R_{out} = r_{o1} \parallel r_{o2}
\]

### Voltage Gain

\[
A_v = -g_m R_{out}
\]

### Key Insight

- Active load increases **output resistance**
- Results in **higher voltage gain**
- More efficient compared to resistive load

---

## 2.3 Simulation Results

### 🔹 DC Analysis

- Bias voltage adjusted to maintain:

\[
I_D \approx 200\,\mu A
\]

✔ Ensures proper operation in saturation

<img width="965" height="779" alt="DC op pnt ckt2" src="https://github.com/user-attachments/assets/d130ff49-0598-4c8a-ab37-319eb25d077f" />

---

### 🔹 Transient Analysis

- Larger output swing due to high load resistance

\[
A_v \approx 14.67 \, V/V
\]

✔ Higher gain than source degeneration case

<img width="1915" height="806" alt="transient analysis ckt2" src="https://github.com/user-attachments/assets/0ccaca6d-5a65-4ca5-8a01-f4619592153d" />

---

### 🔹 AC Analysis

- 3 dB Bandwidth: **422.31 MHz**

✔ Improved gain-bandwidth performance

<img width="1916" height="808" alt="AC Analysis ckt2" src="https://github.com/user-attachments/assets/b275a383-1744-4225-b64e-2889b1f5427d" />

---

# 🔌 3. Configuration C: CS Amplifier with Diode-Connected Load

## 3.1 Circuit Schematic

<img width="1272" height="824" alt="ckt3 exp2" src="https://github.com/user-attachments/assets/9b2b8987-535d-4f6b-9c33-1e766cd12fa9" />

---

## 3.2 Theoretical Analysis

### Load Resistance

\[
R_L = \frac{1}{g_{m3}}
\]

### Voltage Gain

\[
A_v = -g_m R_L
\]

### Key Insight

- Diode-connected MOS acts as a **low-value resistor**
- Leads to **lower gain**
- Provides **good stability and bias robustness**

---

## 3.3 Simulation Results

### 🔹 DC Analysis

✔ Proper biasing ensures stable operation

<img width="953" height="785" alt="ckt3 DC" src="https://github.com/user-attachments/assets/160fa4be-6aac-461f-85d7-a20b2f89a76d" />

---

### 🔹 Transient Analysis

\[
A_v \approx 4.13 \, V/V
\]

✔ Lower gain due to reduced output resistance

<img width="1916" height="834" alt="transient analysis ckt3" src="https://github.com/user-attachments/assets/a5073c75-d8c5-41a2-8c64-15259836331a" />

---

### 🔹 AC Analysis

- 3 dB Bandwidth: **140.92 MHz**

✔ Lower bandwidth due to loading effects

<img width="1914" height="835" alt="ckt3 AC" src="https://github.com/user-attachments/assets/c6576bb3-8dba-42a1-a0af-099f3954c782" />

---

# 📊 Final Performance Comparison

| Configuration | Gain (\(A_v\)) | 3 dB Bandwidth | UGB |
|--------------|---------------|----------------|------|
| Source Degeneration | 11.22 | 203.52 MHz | 2.28 GHz |
| Active Load | **14.67** | **422.31 MHz** | **6.19 GHz** |
| Diode-Connected | 4.13 | 140.92 MHz | 582.45 MHz |

---

# ✅ Conclusion

Among the three configurations:

- **Active Load (Configuration B)** provides the **highest gain and bandwidth**, making it suitable for high-performance analog circuits  
- **Source Degeneration (Configuration A)** offers a **balanced trade-off** between gain, stability, and linearity  
- **Diode-Connected Load (Configuration C)** provides **robust operation** with reduced gain, useful in biasing and low-gain applications  

---

# 📌 Inference

This experiment demonstrates how **different load configurations significantly affect amplifier performance**.

- Gain is primarily influenced by **output resistance**
- Bandwidth depends on **parasitic capacitances and loading**
- Trade-offs are essential in practical IC design

✔ The results validate theoretical expectations for **CS amplifier topologies in 180 nm CMOS technology**
