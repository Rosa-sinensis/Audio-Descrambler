### Bias Circuit

The schematic of bias circuit used is shown below:

<img width="320" alt="Screenshot 2022-01-07 at 21 43 51" src="https://user-images.githubusercontent.com/82151839/148611456-c7c6e227-801f-4663-924c-563392759e55.png">

The job of bias circuit is to ensure the signal entering MSP432 is only consists of +ve signal due to the constraints of the ADC used. 
If there is any -ve signal entering the MSP432, the internal ADC of MSP432 will translate it as bit 00000000.

The potential divider (R2 and R3) ensures the output signal to be centred at 1k/(1k+1k)*Vref, which is 0.6V

The capacitor (C1) before the potential divider acts to filter any DC signal in the input audio signal. 
