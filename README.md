# Signal-Processing-For-Space-Communications
This project simulates BPSK and Gray-coded QPSK transmission over an AWGN channel and evaluates Bit Error Rate (BER) versus Eb/N0 using Monte Carlo methods. Results are validated against theoretical curves and supported by constellation and eye diagram to analyze SNR impact on digital link reliability in noise-limited communication systems.

# Digital Modulation Performance Analysis over AWGN Channel  
## A Monte Carlo-Based BPSK/QPSK Simulation Study

---

## Abstract

This project presents a structured simulation framework for evaluating the performance of coherent digital modulation schemes over an Additive White Gaussian Noise (AWGN) channel. Binary Phase Shift Keying (BPSK) and Gray-coded Quadrature Phase Shift Keying (QPSK) are implemented in complex baseband form and assessed using Monte Carlo Bit Error Rate (BER) estimation.  

Simulated results are compared against theoretical error probability expressions to validate implementation correctness. Constellation diagrams and eye diagrams are additionally used to visualize signal degradation under noise.  

The framework establishes a rigorous baseline for noise-limited communication system analysis and serves as a foundation for advanced studies in space communications, satellite links, and digital modem design.

---

## 1. Introduction

Reliable digital communication is fundamental to satellite systems, deep-space missions, and high-reliability wireless links. In power-constrained communication systems, performance is primarily governed by the ratio of energy per bit to noise spectral density, denoted as Eb/N0.

BER analysis as a function of Eb/N0 provides:

- A normalized performance metric independent of bandwidth
- A direct measure of link reliability
- A validation benchmark for modem implementations
- A foundation for link budget and coding analysis

This project develops a physics-consistent baseband simulation of BPSK and QPSK transmission over AWGN and evaluates system reliability through statistical Monte Carlo estimation.

---

## 2. Objectives

The objectives of this project are:

- To implement coherent BPSK and Gray-coded QPSK modulation.
- To model an AWGN channel using Eb/N0 as the governing metric.
- To estimate BER via Monte Carlo simulation.
- To compare simulated results with theoretical BER expressions.
- To visualize constellation spreading under noise.
- To generate eye diagrams illustrating waveform degradation.
- To analyze SNR impact on digital link reliability.

---

## 3. Theoretical Background

### 3.1 BPSK Modulation

Binary Phase Shift Keying maps:

0 → -1  
1 → +1  

Properties:
- Real-valued baseband signal
- 1 bit per symbol
- Unit average symbol energy (Es = 1)

---

### 3.2 QPSK Modulation (Gray-Coded)

Bit pairs are mapped to I/Q components:

bI = 0 → I = +1  
bI = 1 → I = -1  
bQ = 0 → Q = +1  
bQ = 1 → Q = -1  

Symbol:

s = (I + jQ) / √2  

Properties:
- Complex baseband representation
- 2 bits per symbol
- Unit average symbol energy
- Gray coding minimizes adjacent-bit errors

---

### 3.3 AWGN Channel Model

Thermal noise is modeled as zero-mean Gaussian noise with power spectral density N0/2 per dimension.

Energy relationships:

Eb = Es / (bits per symbol)  
N0 = Eb / (Eb/N0)  

Noise variance:

- Real channel: σ² = N0 / 2  
- Complex channel: σ² = N0 / 2 per dimension  

---

### 3.4 Theoretical BER

For coherent detection in AWGN:

BER = Q( √(2Eb/N0) )

This expression applies to both BPSK and Gray-coded QPSK.

---

## 4. Methodology

The simulation follows a structured digital communication pipeline:

1. Random binary sequence generation.
2. Modulation (BPSK or QPSK).
3. AWGN noise injection for a range of Eb/N0 values.
4. Hard-decision coherent demodulation.
5. Bitwise comparison and BER computation.
6. Theoretical curve calculation.
7. Visualization of BER, constellation, and eye diagrams.

Monte Carlo simulation uses large bit counts (e.g., 200,000 bits per Eb/N0 point) to ensure statistical convergence.

---

## 5. Signal Visualization

### 5.1 Constellation Diagrams

Received symbols are plotted in the complex plane to illustrate:

- Noise-induced spreading
- Decision boundary overlap
- Quadrant detection behavior

Constellation distortion increases as Eb/N0 decreases.

---

### 5.2 Eye Diagrams

An oversampled rectangular pulse waveform is generated:

- Multiple samples per symbol
- AWGN applied at waveform level
- Symbol transitions overlaid

Eye closure visually represents SNR degradation and reduced detection margin.

---

## 6. Results and Analysis

Simulation results exhibit expected communication system behavior:

- BER decreases exponentially with increasing Eb/N0.
- BPSK and Gray-coded QPSK exhibit identical BER vs Eb/N0 performance.
- Simulated BER closely matches theoretical predictions.
- Minor deviations at very low BER arise from finite sample effects.

At low Eb/N0:
- Constellation clusters overlap significantly.
- Eye diagrams show reduced vertical opening.
- Detection errors increase rapidly.

At high Eb/N0:
- Symbol clusters are well separated.
- Eye diagrams remain open.
- BER approaches zero.

---

## 7. Engineering Interpretation

The results demonstrate key digital communication principles:

- System reliability is directly governed by energy efficiency.
- Eb/N0 provides a normalized metric independent of bandwidth.
- QPSK improves spectral efficiency without sacrificing power efficiency.
- Hard-decision detection introduces performance limitations.
- Visual diagnostics complement quantitative BER evaluation.

The simulation serves as a baseline validation step prior to incorporating synchronization errors, fading channels, or channel coding.

---

## 8. Tools and Technologies

- Python
- NumPy
- Matplotlib

Conceptual foundations include:

- Digital communication theory
- Probability and random processes
- Statistical signal processing
- Monte Carlo methods

---

## 9. Conclusion

This project implements a complete digital modulation and performance evaluation framework for BPSK and QPSK transmission over AWGN.

It provides:

- End-to-end baseband simulation
- Monte Carlo BER estimation
- Theoretical validation
- Constellation visualization
- Eye diagram analysis

The framework establishes a rigorous foundation for further research in satellite communications, deep-space links, and advanced digital modem design.

---

## 10. Future Work

Potential extensions include:

- Carrier frequency offset and Doppler modeling
- Phase noise modeling
- Raised cosine pulse shaping
- Matched filtering implementation
- Soft-decision demodulation
- Convolutional and LDPC channel coding
- Rayleigh and Rician fading channel models
- Link budget integration
- Deep-space communication modeling
- Adaptive modulation studies

---

This project demonstrates the integration of theoretical communication models with numerical simulation to evaluate noise-limited digital link performance under controlled and physically meaningful conditions.
