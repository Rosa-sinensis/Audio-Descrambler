## Bias Circuit

The schematic of bias circuit used is shown below:

<img width="351" alt="BiasCircuit" src="https://user-images.githubusercontent.com/82151839/148616571-97555016-1177-4caf-a590-30acc8b42e19.png">

The job of bias circuit is to ensure the signal entering MSP432 is only consists of +ve signal due to the constraints of the ADC used. 
If there is any -ve signal entering the MSP432, the internal ADC of MSP432 will translate it as bit 00000000.

- Potential divider (R2 and R3) ensures the output signal to be centred at 1k/(1k+1k)*Vref, which is 0.6V

- Capacitor (C1) before the potential divider acts to filter any DC signal in the input audio signal. 
