# Amplitude-Modulation-and-Demodulation-using-NumPy-and-Matplotlib
## AIM

To implement and analyze amplitude modulation (AM) using Python's NumPy and Matplotlib libraries. 
## Apparatus Required
## Software: Python with NumPy and Matplotlib libraries

## HARDWARE
Personal Computer

## THEORY

Amplitude Modulation (AM) is a technique used in electronic communication, primarily for transmitting information via a radio carrier wave. In AM, the amplitude of the carrier wave is varied in proportion to that of the message signal. The general form of an AM signal is:<img width="290" height="152" alt="image" src="https://github.com/user-attachments/assets/dbe771a4-4857-47ca-a3e3-c9e0559add09" />

## ALGORITHM

1.	Initialize Parameters: Set the values for carrier frequency, message frequency, and sampling frequency.
2.	Generate Time Axis: Create a time vector for the signal duration.
3.	Generate Message Signal: Define the message signal as a cosine wave.
4.	Generate Carrier Signal: Define the carrier signal as a cosine wave.
5.	Modulate Signal: Apply the AM formula to obtain the modulated signal.
6.	Plot the Signals: Use Matplotlib to plot the message signal, carrier signal, and modulated signal.

## PROGRAM

import numpy as np

import matplotlib.pyplot as plt

from scipy.signal import hilbert


Ac = 21

Am = 10.5

fc = 10330

fm = 1033

fs = 1033000

t = np.arange(0, 2/fm, 1/fs)

m = Am * np.cos(2 * np.pi * fm * t)    

c = Ac * np.cos(2 * np.pi * fc * t) 

s = (Ac + m) * np.cos(2 * np.pi * fc * t) 

env = np.abs(hilbert(s))  

m_demod = env - np.mean(env)  

plt.figure(figsize=(10,8))

plt.subplot(4,1,1)

plt.plot(t, m)

plt.title('Message Signal')

plt.xlabel('Time (s)')

plt.ylabel('Amplitude')

plt.subplot(4,1,2)

plt.plot(t, c)

plt.title('Carrier Signal')

plt.xlabel('Time (s)')

plt.ylabel('Amplitude')

plt.subplot(4,1,3)

plt.plot(t, s)

plt.title('AM Modulated Signal')

plt.xlabel('Time (s)')

plt.ylabel('Amplitude')

plt.subplot(4,1,4)

plt.plot(t, m_demod)

plt.title('Demodulated Signal')

plt.xlabel('Time (s)')

plt.ylabel('Amplitude')

plt.tight_layout()

plt.show()

## TABULATION

![WhatsApp Image 2025-11-19 at 18 04 12_1bd3cfc7](https://github.com/user-attachments/assets/57dd28b7-92da-4828-8944-d66bf9c519cb)

## OUTPUT

![WhatsApp Image 2025-11-19 at 18 05 10_d0433ce3](https://github.com/user-attachments/assets/8cbd0b52-8919-40a8-95bc-a29eb9ef8d65)

## RESULT

The message signal, carrier signal, and amplitude modulated (AM) signal will be displayed in separate plots.

Thus AM is implemented using NumPy and Matplotlib.
