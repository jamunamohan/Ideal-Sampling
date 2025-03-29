Ideal-Sampling

AIM : To perform Construction and Re-contruction of impluse or ideal sampling using python.

TOOLS REQUIRED : Softare: Google Colab Python libraries: NumPy, Matplotlib

PROGRAM :
~~~~
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
~~~~
OUTPUT WAVEFORM :
![WhatsApp Image 2025-03-29 at 15 56 07_347826a5](https://github.com/user-attachments/assets/cb0cd251-218e-440b-b2d9-ce0abe34057d)
![WhatsApp Image 2025-03-29 at 15 56 18_c6e515be](https://github.com/user-attachments/assets/ea548004-7d2a-40db-8b2b-2f6281cbd80f)
![WhatsApp Image 2025-03-29 at 15 56 32_9c611e8e](https://github.com/user-attachments/assets/a3f341a2-b16c-4673-b166-13abfa7017c4)

RESULT : The Construction and Re-construction of impulse or ideal sampling using python are verified.
