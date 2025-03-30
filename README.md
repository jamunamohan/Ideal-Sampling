Ideal-Sampling

Aim:

To perform ideal (impulse) sampling of a continuous-time sinusoidal signal, visualize the sampled signal, and reconstruct it using Python.

Tools/Software Required:

Python Software
-> Numpy Library

-> Matplotlib Library

-> Scipy Library (for signal processing)

Program :

#Impulse Sampling

import numpy as np

import matplotlib.pyplot as plt

from scipy.signal import resample

fs = 100

t = np.arange(0, 1, 1/fs)

f = 5

signal = np.sin(2 * np.pi * f * t)

plt.figure(figsize=(10, 4))

plt.plot(t, signal, label='Continuous Signal')

plt.title('Continuous Signal (fs = 100 Hz)')

plt.xlabel('Time [s]')

plt.ylabel('Amplitude')

plt.grid(True)

plt.legend()

plt.show()

t_sampled = np.arange(0, 1, 1/fs)

signal_sampled = np.sin(2 * np.pi * f * t_sampled)

plt.figure(figsize=(10, 4))

plt.plot(t, signal, label='Continuous Signal', alpha=0.7)

plt.stem(t_sampled, signal_sampled, linefmt='r-', markerfmt='ro', basefmt='r-', label='Sampled Signal (fs = 100 Hz)')

plt.title('Sampling of Continuous Signal (fs = 100 Hz)')

plt.xlabel('Time [s]')

plt.ylabel('Amplitude')

plt.grid(True)

plt.legend()

plt.show()

reconstructed_signal = resample(signal_sampled, len(t))

plt.figure(figsize=(10, 4))

plt.plot(t, signal, label='Continuous Signal', alpha=0.7)

plt.plot(t, reconstructed_signal, 'r--', label='Reconstructed Signal (fs = 100 Hz)')

plt.title('Reconstruction of Sampled Signal (fs = 100 Hz)')

plt.xlabel('Time [s]')

plt.ylabel('Amplitude')

plt.grid(True)

plt.legend()

plt.show()

Output Waveform :

![image](https://github.com/user-attachments/assets/1a0a1e24-a149-420b-8d80-25d289faa895)
![image](https://github.com/user-attachments/assets/09a9c23f-8ae0-42a3-8249-bccdbba8660d)
![image](https://github.com/user-attachments/assets/b41aaf3a-4a3e-40b1-a619-1874428d1f2c)

Results :

The continuous sinusoidal signal was successfully sampled using ideal (impulse) sampling.

The sampling was performed at a rate (100 Hz) higher than twice the signal frequency (5 Hz), satisfying the Nyquist criterion.

The reconstruction of the signal using resampling accurately recovered the original waveform.

The experiment demonstrates the fundamental principle of ideal sampling and signal reconstruction.
