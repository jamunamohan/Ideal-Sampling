![WhatsApp Image 2025-03-22 at 15 45 53_b0f22642](https://github.com/user-attachments/assets/c5f21353-bc29-4fea-b595-e6d83d259b57)# Ideal-Sampling
Aim:
  To implement and analyze Ideal Sampling using Python.
Tools required:
  Google Colab or any Python environment
  Python Libraries:
  NumPy
  Matplotlib
  SciPy
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
![WhatsApp Image 2025-03-22 at 15 46 39_bda2a676](https://github.com/user-attachments/assets/ee455a8f-4053-4c42-bf45-1b92db28ca7f)
![WhatsApp Image 2025-03-22 at 15 46 20_f70ad58d](https://github.com/user-attachments/assets/48c535a1-0ac1-45af-bc68-91e98fcaf945)
![WhatsApp Image 2025-03-22 at 15 45 52_97351b31](https://github.com/user-attachments/assets/5f34bc9e-0ec9-42a5-910f-e98e056d03a1)
Results:
Thus the code for ideal sampling is verified using python successfully.
