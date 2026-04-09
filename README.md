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

Program:
```
import numpy as np
import matplotlib.pyplot as plt

Am = 7.2
fm = 418
Ac = 14.4
fc = 4180
fs = 41800

t = np.arange(0, 2/fm, 1/fs)

# Message signal
m = Am * np.cos(2 * np.pi * fm * t)

plt.subplot(3, 1, 1)
plt.plot(t, m)
plt.title("Message Signal")
plt.xlabel("Time")
plt.ylabel("Amplitude")

# Carrier signal
c = Ac * np.cos(2 * np.pi * fc * t)

plt.subplot(3, 1, 2)
plt.plot(t, c)
plt.title("Carrier Signal")
plt.xlabel("Time")
plt.ylabel("Amplitude")

# DSB-SC Signal
s1 = (Ac + m) * np.cos(2 * np.pi * fc * t)
s2 = (Ac - m) * np.cos(2 * np.pi * fc * t)
s = s1 - s2   # This simplifies to 2*m*cos(...)

plt.subplot(3, 1, 3)
plt.plot(t, s)
plt.title("DSB-SC Signal")
plt.xlabel("Time")
plt.ylabel("Amplitude")

plt.tight_layout()
plt.show()
```

Tabulation:
![cd124b3f-822d-4522-9005-291dd1217b69](https://github.com/user-attachments/assets/7e5bba04-1e3c-47fe-8119-b99a2289a45b)

Output:
 
 <img width="630" height="469" alt="574440331-94ad06af-824b-4f24-bece-eae4e6811989" src="https://github.com/user-attachments/assets/b9e56790-7d6e-4b68-9229-8b66a2a5b172" />

Result:
To generate a Double Sideband Suppressed Carrier (DSB-SC) signal in Python (Google Colab), transmit it (optionally add noise), and recover the message using coherent (synchronous) demodulation with a low-pass filter has been observed and verified
