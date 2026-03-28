# Experiment 04  
## Differential Amplifier Analysis

---

## Aim
To design and simulate a MOS differential amplifier with resistive load, determine its DC operating point, and analyze key parameters such as voltage gain, input common-mode range (ICMR), and linearity.

---

## Introduction

A differential amplifier is a fundamental analog circuit used to amplify the difference between two input signals while rejecting common-mode signals. This makes it highly useful in applications such as operational amplifiers, comparators, and noise-sensitive systems.

In MOS differential amplifiers, two identical transistors share a common current source, ensuring symmetric operation. This configuration improves gain accuracy, enhances linearity, and provides strong noise rejection.

This experiment focuses on designing a resistively loaded MOS differential amplifier and evaluating its DC biasing, gain, ICMR, and linearity through simulation.

---

## Theory

### Differential Amplifier with Resistive Load

A MOS differential amplifier consists of:
- Two matched MOSFETs  
- A constant current source (tail current)  
- Load resistors connected at the drains  

It amplifies the difference between input signals while rejecting common-mode components.

---

## Working Principle

### Common-Mode Operation

When both inputs are equal:
