# AudioDescrambler-project
My 2nd Year Project.

### Goal
Build a digital real time audio descrambler, with a goal to decode a secret message. This project involved using MSP432 and building our own circuitry using the knowledge learnt throughout the study.

### How it Works?
Firstly, a MATLAB program was provided. It works by recording audio signal for 5 seconds and will output the scrambled version of the signal.
By utilising this program, it is possible to analyse how the scrambling is done in the first place. And after analysing has been done, the way the scrambler works is by flipping the frequency spectrum of audio signal at 3.5kHz and adding a 8kHz sine wave. 

Hence, to decode the scrambled message, the signal need to be flip the frequency spectrum of audio signal back at 3.5kHz and deleting the 8kHz sine wave.
The way to accomplish this is by:
1) Build a digital filter to remove 8kHz signal
2) Multiply the signal by 7kHz wave. 
   From trigonometry rule, this will produce a sinusoidal signal with an upper and lower frequency. The original signal is the lower frequency
3) Build an analog low-pass filter to filter the unwanted upper sideband of the signal. This filter will also works as an anti-aliasing filter for DAC

* All the operation (sample the audio input, perform digital filtering and produce an audio output) need to be done synchronously at the same sampling frequency of 50 kHz

### Implementation
The block diagram of elements involved in this project is shown below:







<!-- ###What Have I Learnt?
Analog Electronics
- Building an understanding of analog filter, learning different type of responses of 
- Know how DAC works and how to implement it using R2R DAC
- Building a transistor amplifier using Darlington configuration and get to know LM386 audio amplifier
Digital Circuits 
- Understand how digital filter works, and how it is implemented in code.
- Know different types of filter, IIR and FIR
- The benefit of SOS or biquad method in implementing a high order filter 
Microcontroller Programming (MSP432)
- Learn how to utilise the ADC functionality in MSP432
- Understand the basics of clock in MSP432 and how to use them
- Implementing circuilar buffer 
*Challenge: All this needs to be done synchronously 
-->

### Future Improvements
