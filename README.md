# -Frequency-Modulation-and-Demodulation-using-NumPy-and-Matplotlib-

__Aim:__

To implement and analyze frequency modulation (FM) using Python's NumPy and Matplotlib libraries.

__Apparatus Required:__ 

1. Software: Python with NumPy and Matplotlib libraries
   
2. Hardware: Personal Computer

 
__Theory:__

Frequency Modulation (FM) is a method of transmitting information over a carrier wave by varying its 
frequency in accordance with the amplitude of the input signal (message signal). The frequency of the carrier 
wave is varied according to the instantaneous amplitude of the message signal.

__Algorithm:__

1. Initialize Parameters: Set the values for carrier frequency, message frequency, sampling frequency, and 
   frequency deviation.
   
2. Generate Time Axis: Create a time vector for the signal duration.
    
3. Generate Message Signal: Define the message signal as a cosine wave.
    
4. Compute the Integral of the Message Signal: Calculate the integral of the message signal over time.
    
5. Generate FM Signal: Apply the FM modulation formula to obtain the modulated signal.
 
6. Plot the Signals: Use Matplotlib to plot the message signal, carrier signal, and modulated signal.

__Programme:__

      import numpy as np
      import matplotlib.pyplot as plt
      
      # Given values
      Am = 16.9
      Ac = 33.8
      fm = 606
      fc = 6060
      
      # Sampling
      fs = 50000
      t = np.arange(0, 0.01, 1/fs)
      
      # Message signal
      m = Am * np.cos(2 * np.pi * fm * t)
      
      # Frequency sensitivity
      kf = 50
      
      # Integrate message signal
      int_m = np.cumsum(m) / fs
      
      # FM signal
      fm_signal = Ac * np.cos(2 * np.pi * fc * t + kf * int_m)
      
      # -------- PLOTTING --------
      plt.figure(figsize=(10, 8))
      
      plt.subplot(3,1,1)
      plt.plot(t, m)
      plt.title("Message Signal")
      
      plt.subplot(3,1,2)
      plt.plot(t, fm_signal)
      plt.title("FM Signal")
      
      plt.subplot(3,1,3)
      plt.plot(t[:500], fm_signal[:500])  # zoomed view
      plt.title("Zoomed FM Signal")
      
      plt.tight_layout()
      plt.show()
__Output:__
<img width="757" height="757" alt="image" src="https://github.com/user-attachments/assets/120ae72c-8e34-48b8-9715-a6040bb2c7b4" />
![20260406_181331](https://github.com/user-attachments/assets/4de54c21-cae7-49e1-a3e0-4a5c0971d689)

__Result:__
![20260406_181337](https://github.com/user-attachments/assets/6a32b710-bcd0-4ef7-893d-b03f0d3d7b27)
