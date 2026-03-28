# Differential Amplifier Analysis

---

## Circuit 2: Differential Amplifier Using Active Load

---

## Aim

To design and simulate a MOS differential amplifier using an active load (current mirror), and to evaluate its DC operating conditions, gain, linearity, and frequency response using LTspice.

---

## Introduction

A differential amplifier amplifies the difference between two input signals while rejecting common-mode signals.

In this circuit, an active load is implemented using a PMOS current mirror instead of resistive loads. This approach increases voltage gain, improves output resistance, and enhances overall amplifier performance.

The circuit consists of an NMOS differential pair and a PMOS current mirror load, making it suitable for high-gain and high-speed applications.

---

## Circuit Description

The circuit consists of:

- **M1, M2** → NMOS differential pair  
- **M3, M4** → PMOS current mirror (active load)  
- **M5** → Tail current source  

![Circuit Diagram](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-28%20172015.png)

---

## Given Parameters

- $V_{DD} = 0.9\ \mathrm{V}$  
- $V_{SS} = -0.9\ \mathrm{V}$  
- Power $P = 2.2\ \mathrm{mW}$  
- Threshold voltage $V_T \approx 0.4\ \mathrm{V}$  
- Overdrive voltage $V_{ov} \approx 0.3\ \mathrm{V}$  
- Channel length $L = 540\ \mathrm{nm}$  

---

## Design Calculations

### Tail Current

$$
I_{SS} = \frac{P}{V_{DD} - V_{SS}} = \frac{2.2\ \mathrm{mW}}{1.8\ \mathrm{V}} \approx 1.22\ \mathrm{mA}
$$

### Branch Current

$$
I_D = \frac{I_{SS}}{2} \approx 0.61\ \mathrm{mA}
$$

### Bias Voltage

$$
V_{GS} = V_T + V_{ov} = 0.4 + 0.3 = 0.7\ \mathrm{V}
$$

$$
V_B = V_S + V_{GS} = -0.9 + 0.7 \approx -0.2\ \mathrm{V}
$$

---

## DC Analysis

![DC Analysis](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-28%20172139.png)

### Results

- $I_{SS} \approx 1.23\ \mathrm{mA}$  
- $I_{D1} = I_{D2} \approx 0.615\ \mathrm{mA}$  
- $V_P \approx -0.724\ \mathrm{V}$  
- $V_{out1} \approx V_{out2} \approx -0.055\ \mathrm{V}$  

---

## Input Common Mode Range (ICMR)

### Minimum Value

$$
V_S = V_{SS} + V_{ov} = -0.9 + 0.3 = -0.6\ \mathrm{V}
$$

$$
V_{ICM(min)} = V_S + V_T = -0.6 + 0.4 = -0.2\ \mathrm{V}
$$

### Maximum Value

$$
V_D \approx V_{DD} - V_{ov} = 0.9 - 0.3 = 0.6\ \mathrm{V}
$$

$$
V_{ICM(max)} = V_D - V_{ov} = 0.6 - 0.3 = 0.3\ \mathrm{V}
$$

### Final Range

$$
-0.2\ \mathrm{V} \leq V_{ICM} \leq 0.3\ \mathrm{V}
$$

---

## Differential Input Range (Linear Operation)

$$
V_{id} < \sqrt{2} \cdot V_{ov}
$$

$$
V_{id(max)} \approx 0.42\ \mathrm{V}
$$

---

## Transient Analysis

Load capacitance:

$$
C_L = 10\ \mathrm{pF}
$$

### Small Signal Input

- $V_{in1} = +10\ \mathrm{mV}$  
- $V_{in2} = -10\ \mathrm{mV}$  

**Observation:**

- Clean sinusoidal output  
- No distortion  
- Outputs are equal and opposite  
- Linear operation  

---

### Large Signal Input

- $V_{in1} = +300\ \mathrm{mV}$  
- $V_{in2} = -300\ \mathrm{mV}$  

**Observation:**

- Output distortion observed  
- Peaks are clipped  
- One transistor dominates  
- Nonlinear behavior  

---

## AC Analysis

![AC Analysis](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-28%20194658.png)

### Midband Gain

$$
A_v \approx 6\ \mathrm{dB} \approx 2\ \mathrm{V/V}
$$

---

### Cutoff Frequencies

- $f_L \approx 0\ \mathrm{Hz}$  
- $f_H \approx 3\text{–}5\ \mathrm{GHz}$  

---

### Bandwidth

$$
BW \approx 4\ \mathrm{GHz}
$$

---

## Unity Gain Bandwidth

![UGB](https://github.com/praphul-biradar/LIC-LAB/blob/main/Screenshot%202026-03-28%20194209.png)

$$
UGB \approx 5.035\ \mathrm{GHz}
$$

---

## Observations

- Gain crosses 0 dB near 5 GHz  
- Phase shift ≈ −90° at unity gain  
- High-frequency roll-off due to parasitic capacitances  
- Stable amplifier behavior  

---

## Conclusion

- Active load improves gain compared to resistive load  
- ICMR: **−0.2 V to 0.3 V**  
- Linear operation for **|V_id| < 0.42 V**  
- Midband gain ≈ **6 dB (≈2 V/V)**  
- Bandwidth in **GHz range**  
- Unity Gain Bandwidth ≈ **5 GHz**

The differential amplifier demonstrates high-speed performance with improved gain due to the current mirror active load configuration.
