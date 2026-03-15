# DSB--SC-MODULATION-AND-DEMODULATION-USING-PYTHON--T12-C12--EVEN
AIM:

To generate a Double Sideband Suppressed Carrier (DSB-SC) signal in Python (Google Colab), transmit it (optionally add noise), and recover the message using coherent (synchronous) demodulation with a low-pass filter. Observe time and frequency domain waveforms and measure demodulation performance

APPARATUS REQUIRED:

Google Colab (or any Python environment)

Python libraries: numpy, matplotlib, scipy (scipy.signal)

Theory:

DSB-SC signal: s(t) = m(t) · cos(2πf_c t) Coherent demodulation: multiply received s(t) by a synchronized carrier cos(2πf_c t) then low-pass filter (LPF) to remove double-frequency components:

r(t) = s(t)·cos(2πf_c t) = m(t)·cos²(2πf_c t) = 0.5 m(t) + 0.5 m(t)·cos(4πf_c t) LPF extracts 0.5·m(t) → scale by 2 to recover m(t).

Procedure:

Import libraries and set parameters

Define message and carrier signals

Generate DSB-SC signal (modulation)

View spectra (FFT) of message and DSB-SC

(Optional) Add noise

Coherent demodulation (multiply by synchronized carrier)

Low-pass filter to recover message

Tabulation:

Output:

Result:
