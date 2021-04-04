# N_Output_Sequencer
NE555P / 74HC595 based N Output Sequencer

This is a simple, low cost output sequencer application circuit based on the NE555P timer and 74HC595 serial->parallel shift register that can be used in a variety of applications requiring a sequential output drive with an automatic reset at the final output. Example applications include LED advertising signage, automotive sequential tail lights, games, props and more!

# Schematic

<p align="center">
  <img src="https://github.com/mkengineering/N_Output_Sequencer/blob/main/n_out_seq_circuit.png" alt="Circuit Diagram"/>
</p>

# Circuit Description

The basic idea of the circuit is a NE555P based astable oscillator driving the clock of an 74HC595 shift register which has it's serial data input (SER) line pulled high, it's SRCLK connected to RCLK, and it's Qh' output connected to the base of a 2N3904 npn bjt which pulls the SRCLR line low to clear the shift register at the end of the sequence. 

As the Qh' output can also be used to chain multiple 74HC595 shift registers together, it is possible to extend the number of sequential outputs by inserting additional 74HC595 shift registers before the final "terminating" register to achieve a N output sequencer. 

Based on this requirement, the following equation can be used to calculate the number of sequential outputs.

<p align="center">
  <img src="https://github.com/mkengineering/N_Output_Sequencer/blob/main/n_out_seq_eqn.PNG" alt="Output Equation"/>
</p>

# Timing

<p align="center">
  <img src="https://github.com/mkengineering/N_Output_Sequencer/blob/main/n_out_seq_timing.png" alt="Circuit Diagram"/>
</p>

# Output Capabilities

The Texas Instruments variant of the 74HC595 is rated at 35mA per output and 70mA total for the device. To drive loads greater than the rated output, simply add an output buffer stage to the desired shift register pins. Variants of the 595 shift register are also available with an integrated output buffer stage such as the Texas Instruments TPIC6C595.

# License

MKE supports the open source hardware community by sharing hardware design files freely on GitHub!

Please support MKE by purchasing products on [Tindie](https://www.tindie.com/stores/mkengineering/)!

Designed by Mike Kushnerik for MKEngineering

Licensed under [Creative Commons Attribution-ShareAlike CC BY-SA 3.0](http://creativecommons.org/licenses/by-sa/3.0/)

All text above must be included in any redistribution!
