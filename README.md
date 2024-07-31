# Layout-of-Bias-Generation-and-Single-Stage-Operational-Amplifier-Circuit
# Internship Report

## Work Sponsored by
EPICAL LAYOUTS PRIVATE LIMITED

## Project 2: Designing of Bias Generation and Single-Stage Operational Amplifier Circuit

### By
AKSHAY B (111721104008)  
RMK ENGINEERING COLLEGE  
April 2024

---

## Table of Contents

1. [Objective](#1-objective)
2. [Bias Generator](#2-bias-generator)
   - [Specification of the Design](#i-specification-of-the-design)
   - [Schematic](#ii-schematic)
   - [DC Analysis](#iii-dc-analysis)
   - [Conclusion](#iv-conclusion)
3. [Single Stage Differential Amplifier](#3-single-stage-differential-amplifier)
   - [Specification of the Design](#i-specification-of-the-design-1)
   - [Schematic](#ii-schematic-1)
   - [DC Analysis](#iii-dc-analysis-1)
   - [AC Analysis](#iv-ac-analysis)
   - [Layout](#v-layout)
   - [Conclusion](#vi-conclusion)

---

## 1. Objective

This report provides an in-depth analysis of the design principles and operational functionalities of both the Bias-generator and Single-stage operational amplifier circuit, adhering to predetermined parameters. Through comprehensive examination, the study aims to assess the performance and efficacy of these circuits by elucidating their design methodologies, circuit realization techniques, and operational behaviors. By offering a detailed exploration of their design concepts and practical implementations, this work seeks to provide a holistic understanding of the functioning of these circuits.

---

## 2. Bias Generator

A bias generation circuit is a fundamental component in electronic circuits, particularly analog circuits such as amplifiers and oscillators. Its primary function is to establish a stable operating point for active devices like transistors or operational amplifiers. The operating point, also known as bias point or quiescent point, ensures that the active device operates in its linear region, where it can accurately amplify or process signals without distortion.

It ensures optimal performance by setting the operating parameters within desired ranges. By maintaining stable bias conditions, it minimizes distortion and improves linearity in signal processing. This circuit plays a vital role in maintaining circuit stability despite variations in temperature, power supply, and component characteristics. Overall, the bias generation circuit is essential for ensuring reliable and consistent operation of electronic systems.

### i. Specification of the Design

Design a cascode Bias Generator circuit using NMOS to produce 3 different branch currents of 1.5mA, 4mA, and 6mA respectively. The bias current is 30uA.

### ii. Schematic

![Schematic Diagram of Bias-generator without specifications](<img width="578" alt="image" src="https://github.com/user-attachments/assets/c58e29e1-b9fc-46cd-b787-b08ee3652fec">)

Strength Determination:
- Reference NMOS strength: 1X (width: 120n)
- First column transistor width: 6.5um
- Second column transistor width: 18um
- Third column transistor width: 27um

### iii. DC Analysis

DC analysis, or Direct Current analysis, is a method used in electronics to study the behavior of electronic circuits under steady-state conditions when all voltages and currents are constant with respect to time. In DC analysis, capacitors are treated as open circuits, and inductors are treated as short circuits, effectively removing their transient effects.

- DC analysis gives us the node current values for the given bias voltage.
- By varying the strength of the transistors, we can observe the change in drain node current of each device by running dc analysis.
- We increase the strength and run DC analysis again and again until we meet our specifications.

![ADL setup for Bias-generator dc analysis](path/to/image)

DC Analysis Output Waveform:
- Input current: 30uA
- Output currents: IA: 1.5mA, IB: 4mA, IC: 6mA

![Output current graph](path/to/image)

### iv. Conclusion

In conclusion, the bias generator circuit is designed for the given specifications. Through careful design and implementation, the bias generator ensures optimal performance by minimizing distortion, improving linearity, and enhancing circuit stability. Its significance lies in enabling reliable and efficient signal processing across a wide range of applications. Moving forward, continued research and development efforts will further refine bias generator designs, contributing to advancements in electronic technology and facilitating the creation of more sophisticated and high-performance electronic systems.

---

## 3. Single Stage Differential Amplifier

A single-stage operational amplifier, often referred to simply as an op-amp, is a fundamental building block in electronics used for amplification, signal conditioning, filtering, and many other applications. It typically consists of a high-gain differential amplifier stage followed by additional circuitry for stabilization and signal processing. A single-stage operational amplifier (op-amp) can indeed be constructed using a current mirror configuration.

By using a current mirror configuration, a single-stage operational amplifier can achieve high gain, precise current matching, and improved linearity. It's a common approach in integrated circuit design, particularly for low-power and high-frequency applications where compactness and efficiency are crucial.

### i. Specification of the Design

Design a differential amplifier with VDD = 1.8V, IN_P = 1.4V, IN_N = 0.7V, Load Capacitance = 12pF, Slew rate = 5 V/u sec for a GBP of 5 MHz (Base L = 1u, Base W = 10u).

### ii. Schematic

![Schematic diagram of single stage differential amplifier](path/to/image)

Steps to design the circuit:
1. Calculate the bias current using the formula: Io = C * SR
2. Assume values for W, L, Vth.
3. Ensure all transistors are in the saturation region.
4. Run DC analysis to find beta_eff and threshold voltages for nMOS and pMOS.

### iii. DC Analysis

DC analysis is used to check whether all the transistors are in the saturation region. If a device is not in the saturation region, the width of the transistor is increased and DC analysis is done again.

![Model Library setup (pMOS and nMOS set to work in fast mode)](path/to/image)

### iv. AC Analysis

AC analysis is done to check whether the design meets the expected gain bandwidth product. If the GBP is less than expected, the width of the NM0 and NM1 transistors is increased, and the AC analysis is run again.

![AC analysis output waveform](path/to/image)

Final transistor widths and lengths:
- M1, M2: 1.6um
- M3, M4: 13um
- M5, M6: 30um

### v. Layout

Matching Process:
- Matching process is crucial in analog circuits where precise matching between components is necessary.
- Types: Interdigitization and Common Centroid
- Here, the common centroid matching method is used.

Pattern of matching:
- A B
- B A
- D C
- C D
- E F
- F E

![Layout of single stage differential amplifier](path/to/image)

### vi. Conclusion

In conclusion, the design of the single-stage amplifier circuit is designed for given specifications. This circuit represents a critical aspect of electronic circuitry. Through meticulous design methodologies and thorough analysis of operational characteristics, the circuits exhibit improved linearity, reduced distortion, and enhanced stability.

Simulation Findings of Single Stage Operational Amplifier:
- M1, M2: 1.6um
- M3, M4: 13um
- M5, M6: 20um
- Gain bandwidth ratio achieved: 5.02MHz

Layout Description:
- Area of the layout: 14771.702 (153.92 X 95.97)
- Number of dummy & void cells used: 12 & 0
- Number of metal layers used: 3
