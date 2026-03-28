Experiment 1
PMOS Common Source Amplifier – Analysis using LTspice
Overview

This experiment focuses on the design and analysis of a PMOS Common Source (CS) amplifier using LTspice. The study includes DC operating point verification, transient response, and AC frequency analysis to evaluate amplifier performance such as gain, bandwidth, and phase behavior.

 Objective
Design a PMOS CS amplifier under given power constraints
Ensure operation in the saturation region
Evaluate:
Biasing conditions
Voltage gain
Frequency response
Signal inversion
 Tools & Technology
Parameter	Value
Simulation Tool	LTspice
Technology Node	180 nm CMOS
Supply Voltage	2 V
Load Capacitance	1 pF
Max Power	≤ 1.5 mW
 Theory
 PMOS Common Source Amplifier
Input is applied at the gate
Output is taken from the drain
Source is connected to VDD
Output is inverted (180° phase shift)
 Conditions for Proper Operation

To ensure correct amplification:

Turn ON condition:

𝑉
𝑆
𝐺
≥
𝑉
𝑡
ℎ
V
SG
	​

≥V
th
	​


Saturation condition:

𝑉
𝑆
𝐷
>
𝑉
𝑆
𝐺
−
𝑉
𝑡
ℎ
V
SD
	​

>V
SG
	​

−V
th
	​

Input must be small signal for linear operation
 Key Equations

Drain Current:

𝐼
𝐷
=
1
2
𝑘
𝑝
(
𝑉
𝑆
𝐺
−
∣
𝑉
𝑡
ℎ
∣
)
2
I
D
	​

=
2
1
	​

k
p
	​

(V
SG
	​

−∣V
th
	​

∣)
2

Transconductance:

𝑔
𝑚
=
2
𝐼
𝐷
𝑉
𝑜
𝑣
g
m
	​

=
V
ov
	​

2I
D
	​

	​


Voltage Gain:

𝐴
𝑣
=
−
𝑔
𝑚
𝑅
𝐷
A
v
	​

=−g
m
	​

R
D
	​

 Design Calculations
 Power Constraint
𝐼
𝐷
≤
𝑃
𝑚
𝑎
𝑥
𝑉
𝐷
𝐷
=
1.5
𝑚
𝑊
2
𝑉
=
0.75
𝑚
𝐴
I
D
	​

≤
V
DD
	​

P
max
	​

	​

=
2V
1.5mW
	​

=0.75mA

 Selected:

𝐼
𝐷
=
500
𝜇
𝐴
I
D
	​

=500μA
 Output Voltage (Midpoint Biasing)
𝑉
𝑜
𝑢
𝑡
=
𝑉
𝐷
𝐷
2
=
1
𝑉
V
out
	​

=
2
V
DD
	​

	​

=1V
 Drain Resistor
𝑅
𝐷
=
𝑉
𝑜
𝑢
𝑡
𝐼
𝐷
=
1
0.5
𝑚
𝐴
=
2
𝑘
Ω
R
D
	​

=
I
D
	​

V
out
	​

	​

=
0.5mA
1
	​

=2kΩ
 Process Parameter
𝐶
𝑜
𝑥
=
𝜀
𝑜
𝑥
𝑡
𝑜
𝑥
C
ox
	​

=
t
ox
	​

ε
ox
	​

	​

𝑘
𝑛
=
𝜇
𝑛
𝐶
𝑜
𝑥
=
0.973
×
10
−
4
𝐴
/
𝑉
2
k
n
	​

=μ
n
	​

C
ox
	​

=0.973×10
−4
A/V
2
 Transistor Width Calculation
𝑊
=
2
𝐼
𝐷
𝐿
𝑘
𝑛
(
𝑉
𝑜
𝑣
)
2
W=
k
n
	​

(V
ov
	​

)
2
2I
D
	​

L
	​

Theoretical: 144 µm
Practical (LTspice adjusted): 333.5 µm

 Achieved:

𝐼
𝐷
≈
500
𝜇
𝐴
I
D
	​

≈500μA
 DC Analysis

DC simulation verifies correct biasing.

Results:
Parameter	Value

𝑉
𝐷
𝐷
V
DD
	​

	2 V

𝑉
𝑖
𝑛
V
in
	​

	1.409 V

𝑉
𝑜
𝑢
𝑡
V
out
	​

	1 V

𝐼
𝐷
I
D
	​

	0.5 mA
Power	1 mW

 Transistor operates in saturation region

 Transient Analysis
 Input Signal
Frequency: 1 kHz
𝑉
𝑖
𝑛
(
𝑝
𝑝
)
≈
19.66
𝑚
𝑉
V
in(pp)
	​

≈19.66mV
 Output Signal
𝑉
𝑜
𝑢
𝑡
(
𝑝
𝑝
)
≈
209.37
𝑚
𝑉
V
out(pp)
	​

≈209.37mV
 Voltage Gain
𝐴
𝑣
=
𝑉
𝑜
𝑢
𝑡
(
𝑝
𝑝
)
𝑉
𝑖
𝑛
(
𝑝
𝑝
)
=
209.37
19.66
≈
10.64
A
v
	​

=
V
in(pp)
	​

V
out(pp)
	​

	​

=
19.66
209.37
	​

≈10.64

 Final Gain:

𝐴
𝑣
≈
−
10.64
A
v
	​

≈−10.64

 Negative sign indicates phase inversion

 AC Analysis
 Gain in dB
𝐴
𝑣
(
𝑑
𝐵
)
=
20
log
⁡
(
10.64
)
≈
20.54
𝑑
𝐵
A
v
	​

(dB)=20log(10.64)≈20.54dB
 Bandwidth
Without load capacitor → Very high bandwidth
With 
𝐶
𝐿
=
1
𝑝
𝐹
C
L
	​

=1pF:
𝐵
𝑊
≈
473.54
𝑀
𝐻
𝑧
BW≈473.54MHz
 Gain Bandwidth Product (GBP)
𝐺
𝐵
𝑃
=
𝐴
𝑣
×
𝐵
𝑊
GBP=A
v
	​

×BW
𝐺
𝐵
𝑃
≈
10.64
×
473.54
𝑀
𝐻
𝑧
≈
4.85
𝐺
𝐻
𝑧
GBP≈10.64×473.54MHz≈4.85GHz
 Practical Observation

Simulated GBP differs slightly due to:

Parasitic capacitances (
𝐶
𝑔
𝑠
,
𝐶
𝑔
𝑑
,
𝐶
𝑑
𝑏
C
gs
	​

,C
gd
	​

,C
db
	​

)
Miller effect
Finite output resistance
Short-channel effects
 Key Observations
Proper DC biasing achieved
Transistor remains in saturation region
Output shows clear amplification and inversion
Practical results closely match theoretical values
 Conclusion

The PMOS Common Source amplifier was successfully designed within the specified power limit.

Voltage Gain ≈ 10 V/V (20.54 dB)
Bandwidth ≈ 473.54 MHz (with load capacitor)
Power Consumption ≈ 1 mW

The results confirm correct amplifier operation while accounting for real-world non-ideal effects.

 Inference
The circuit satisfies power and biasing constraints
Gain and bandwidth are suitable for analog applications
Minor deviations arise due to device-level parasitics
Demonstrates practical CMOS amplifier behavior in 180 nm technology
