# Ideal-Sampling
Aim:
To implement and analyze Ideal sampling using Python.
Tools required:
Google Colab 
Python libraries: 
NumPy
Matplotlib
Program:
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
Output Waveform:
![WhatsApp Image 2025-03-25 at 12 26 01_c36cb71c](https://github.com/user-attachments/assets/1cd0c762-e972-497a-aac5-843b2c1438a3)
![WhatsApp Image 2025-03-25 at 12 26 02_6d89df88](https://github.com/user-attachments/assets/88824f6c-80ee-435e-ace7-f8779d5022aa)
![WhatsApp Image 2025-03-25 at 12 26 03_1aa5891a](https://github.com/user-attachments/assets/82c0031e-e7aa-4a92-86cc-4556fc22e450)
Results:
Thus the code for ideal sampling is verified using python successfully.
