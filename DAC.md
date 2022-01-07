## Digital-to-Analog Converter

The schematic to implement DAC is as follows:

<img width="351" alt="DAC" src="https://user-images.githubusercontent.com/82151839/148621596-e2412ca4-1aa7-4305-82ff-a2394d38d7f7.png">

Digital-to-analog converter is used to convert the digital signal received from MSP432 (P2.0 - P2.7) into an analog signal.
The DAC implemented is called as R2R DAC. Ideally, the resistor used in the circuit should have a ratio of R:2R. However, because there is no resistor
that have a ratio of two when building the circuit, resistors of value 4.7kΩ and 2.2kΩ were used. The R2R ladder DAC is used because of the ease of implementation, 
where only two value of resistors are needed. On top of that, we can also see that the output resistance of the R2R ladder DAC is equal to R.

This video (https://www.youtube.com/watch?v=Pc1aFloxSMw) can be a perfect start to learn about the operation of R2R ladder DAC
