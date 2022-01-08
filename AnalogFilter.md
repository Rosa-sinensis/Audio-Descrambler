## Analog Filter - Lowpass Filter

The schematic of the analog lowpass filter implemented for this project is given below:
<img width="800" alt="LowpassFilter" src="https://user-images.githubusercontent.com/82151839/148622012-575d0030-f56f-4c38-838f-b9f9081dc69f.png">

The reason we are using analog filter in this case instead of a passive filter is because:
- In passive filter, the load does affect the cutoff frequency of the filter
- The output voltage of a passive filter will be always lower than the input voltage, hence it can become difficult to construct a cascade filter just by using passive components.
- Because op amp is used in building an active filter, in which its input impedance is always high and output impedance is always low, there is no need to worry about having a buffer to do impedance matching or impedance bridging.

The analog lowpass filter above is designed using https://tools.analog.com/en/filterwizard/. 
It is a 3rd order Chebyshev filter. 3rd order filter meaning it has a roll-off of -60dB/decade, meaning the signal will attenuate by 1000 times every time the frequency increases by 10.
Chebyshev filter means that the filter.

From the schematic also, we can see that the circuit is implemented with two stages, in which the first stage is implemented as a simple buffered RC circuit,
and the second stage is implemented using Sallen-Key configuration.

After building this circuit and testing it using oscilloscope, the analog filter has a Bode response as shown below:

![Capture](https://user-images.githubusercontent.com/82151839/148623275-586eda6e-da28-48a3-872e-690443a89f54.JPG)

From the above Bode plot, the filter does act as a lowpass filter and has a cutoff frequency around 5kHz hence can be used in this project, 
because the frequency of interest (frequency of the original signal) is only between 0 and 5kHz. 
