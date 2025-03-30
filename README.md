Ideal-Sampling

AIM : To perform Construction and Re-contruction of impluse or ideal sampling using python.

TOOLS REQUIRED : Google Colab Python libraries: NumPy, Matplotlib

PROGRAM :

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
plt.plot(t, reconstructed_signal, 'r--', label='Reconstructed Signal (fs = 100 Hz)')
plt.title('Reconstruction of Sampled Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()

OUTPUT WAVEFORM:

![WhatsApp Image 2025-03-30 at 10 17 46_4f327979](https://github.com/user-attachments/assets/713722fc-61d0-4d2d-9b8e-ecd26d35c714)
![WhatsApp Image 2025-03-30 at 10 17 57_3961a7a7](https://github.com/user-attachments/assets/fdaa5817-ef69-468d-89bf-5a106e62b4d0)
![image](https://github.com/user-attachments/assets/55919387-52a5-44d8-874b-a356fb508d43)

RESULT : The Construction and Re-construction of impulse or ideal sampling using python are verified.
