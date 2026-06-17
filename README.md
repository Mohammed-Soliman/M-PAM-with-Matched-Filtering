# M-PAM-with-Matched-Filtering
This project implements and analyzes a digital baseband communication system using M-ary Pulse Amplitude Modulation (M-PAM) with matched filtering. The system simulates a correlation receiver operating over an AWGN channel and evaluates its Bit Error Rate (BER) and Symbol Error Rate (SER) performance.

Course: CIE 237 – Probability and Stochastic Processes  
Institution: Zewail City of Science and Technology  
Semester: Spring 2026

---

## 🚀 Project Overview
The project models a baseband M-PAM communication link using both MATLAB Simulink and standalone MATLAB scripts while following strict implementation requirements:
- Designing a matched filter equivalent to an optimal correlation receiver
- Simulating 2-PAM and higher-order M-PAM (4-PAM and 8-PAM)
- Comparing simulated BER/SER against theoretical error probability curves
- Evaluating the effect of different pulse-shaping filters on system performance

---

## 📡 System Model and Methodology
The communication chain consists of:
1. Random integer generation
2. Bit mapping to M-PAM symbols
3. Transmit pulse-shaping filter
4. Transmission over an AWGN channel
5. Receive matched filter
6. Demodulation and error rate calculation (BER and SER)

### Simulink Model
The system was first modeled as a block diagram in Simulink, using an M-PAM modulator, AWGN channel block, matched-filter-based M-PAM demodulator, and error rate calculation blocks for both BER and SER.

### MATLAB Simulation
The Simulink results were verified using standard MATLAB scripts that sweep Eb/N0 from 0 dB to 20 dB. Three pulse shapes were tested at 8 samples per symbol:
- **Rectangular** pulse
- **Square-Root Raised Cosine** pulse (roll-off factor of 0.5)
- **Triangle** pulse

---

## 📊 Results and Discussion
For each pulse shape, BER and SER curves were generated for 2-PAM, 4-PAM, and 8-PAM and compared against theoretical predictions:
- **Rectangular Pulse** — MATLAB and Simulink results match theoretical curves closely; simple to implement but requires larger bandwidth in practice.
- **Raised Cosine Pulse** — Minimizes Inter-Symbol Interference (ISI); simulated results strictly follow theoretical formulas across all M-levels.
- **Triangle Pulse** — Custom filter coefficients in Simulink matched the MATLAB convolution output.

Across all pulse shapes, higher-order modulations (e.g., 8-PAM) require a higher SNR than 2-PAM to achieve the same BER, since symbols are packed more closely together.

---

## ✅ Conclusion
The project confirms the equivalence of correlation receivers and matched filtering in AWGN channels. Simulating 2-PAM, 4-PAM, and 8-PAM revealed the fundamental trade-off in digital communications: higher data rates require significantly more energy to maintain reliable detection. The close agreement between theoretical formulas, MATLAB simulations, and Simulink models validates the system design and error rate calculations.

---

## 👨‍💻 Author
- Mohammed Soliman

---

## 📚 References
- CIE 237 – Course Materials, 2026.

---

## 📌 Key Takeaway
This project demonstrates practical application of core probability and stochastic processes concepts including:
- Matched filtering as the time-domain equivalent of a correlation receiver
- AWGN channel modeling and error rate estimation
- Pulse shaping and its effect on Inter-Symbol Interference (ISI)
- Theoretical vs. simulated BER/SER analysis for M-ary modulation schemes

The system effectively links theoretical probability of error formulas to practical simulation using both MATLAB scripts and Simulink models.
