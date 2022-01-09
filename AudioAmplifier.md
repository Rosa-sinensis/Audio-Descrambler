## Audio Amplifier

The goal of this element is to amplify the signal from the low pass filter, since the signal is very small and can barely heard on the speaker.
The schematic of the audio amplifier used is shown below: 

<img width="607" alt="AudioAmplifier" src="https://user-images.githubusercontent.com/82151839/148703506-e11f9644-6f5d-4e52-a384-a88beaad1efc.png">

The audio amplifier above is designed by using LM386 audio amplifier module.
- The potentiometer right before the 1uF capacitor enables the volume at the speaker to be controlled.
- The 1uF capacitor at the input side is used to remove any DC bias on the signal
- The 100uF capacitor before the speaker is designed to remove any DC signal from entering the speaker, 
  which could cause a damage if there is a high enough DC current entering the speaker
- The combination of 10Ω resistor and 0.047uF capacitor forms a Zobel network, 
  which is tuned to cancel out the effects of capacitance and inductance especially at high frequencies.
  
From the schematic of LM386 module, it can be seen that this module is of the form class AB amplifier. [LM386.pdf](https://github.com/Rosa-sinensis/Audio-project/files/7832084/LM386.pdf)


On top of that, a simple class A amplifier using the ZTX450 NPN transistor as the audio amplifier can be a much simpler implementation. 
It provides some amplification but the quality and loudness is of sound is not as good as using the LM386 module.
Shown below is the schematic of audio amplifier using single ZTX450 NPN transistor.

<img width="637" alt="SingleNPNAmplifier" src="https://user-images.githubusercontent.com/82151839/148703674-a2131ca7-4c8c-4e94-8ab8-1aa2120221bd.png">

To ramp up the amplification of ZTX450, I also cascaded two ZTX450 together using a Darlington pair. 
However, there is not much difference between the amplification of single stage transistor and cascaded stage. 
And the only reason I could think of is because the transistor is not biased properly. 
Shown below is the schematic of the Darlington pair circuit I built:

<img width="645" alt="DarlingtonPairAmplifier" src="https://user-images.githubusercontent.com/82151839/148703517-43ab90d8-2f2d-494f-8018-ae75fbf367dc.png">

Further testing of amplifier can be done by building Class AB amplifier by using transistor and building the well-known Class D amplifier
