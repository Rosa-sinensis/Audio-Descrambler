## Audio Amplifier

The goal of this element is to amplify the signal from the low pass filter, since the signal is very small and can barely heard on the speaker.
The schematic of the audio amplifier used is shown below: 

<img width="603" alt="AudioAmplifier" src="https://user-images.githubusercontent.com/82151839/148651870-7f658653-10c0-4e7e-9a53-5b7176821640.png">

The audio amplifier above is designed by using LM386 audio amplifier module.
- The potentiometer right before the 1uF capacitor enables the volume at the speaker to be controlled.
- The 1uF capacitor at the input side is used to remove any DC bias on the signal
- The 100uF capacitor before the speaker is designed to remove any DC signal from entering the speaker, 
  which could cause a damage if there is a high enough DC current entering the speaker
- The combination of 10Ω resistor and 0.047uF capacitor forms a Zobel network, 
  which is tuned to cancel out the effects of capacitance and inductance especially at high frequencies.
  
From the schematic of LM386 module, it can be seen that this module is of the form class AB amplifier. [LM386.pdf](https://github.com/Rosa-sinensis/Audio-project/files/7832084/LM386.pdf)


On top of that, I have also built a class A amplifier using the ZTX450 NPN transistor. It provides some amplification but not as good as using the LM386 module.
To ramp up the amplification of ZTX450, I also cascaded two ZTX450 together using a Darlington pair. 
However, there is not much difference between the amplification of single stage transistor and cascaded stage. 
And the only reason I could think of is because the transistor is not biased properly. 
Shown below are the schematic of the Darlington pair circuit I built:

<img width="609" alt="DarlingtonPairAmplifier" src="https://user-images.githubusercontent.com/82151839/148625710-c207c0cb-5ae1-42ce-a6a3-51be3d2eaafd.png">

Further testing of amplifier can be done by building Class AB amplifier by using transistor and building the well-known Class D amplifier
