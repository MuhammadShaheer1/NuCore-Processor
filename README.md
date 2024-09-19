# NuCore-Processor

A. The NuCore have the following major blocks 

1. A 64 deep Instruction Queue, addressed by a Program Counter. The Program Counter resets on the RESET 
signal. The Program Counter is incremented by one on each subsequent posedge of clock. 
2. Instruction decode module: The instruction from the Instruction Queue Module is decoded according to the 
supported instruction format as given in Table below. 
3. Two register files: REG_FILE_A (for keeping operands A) and REG_FILE_B (for keeping operands B). Both of 
these are 16 deep with a word size of 32 
4. An Arithmetic Logic Unit that performs the arithmetic as defined by the instruction. The output of ALU is 
registered and goes directly as the output of NuCore. ALU also produces a registered ZERO FLAG that goes out 
as an output of “NuCore” module.

B. The testbench “NuCore_TB” perform the following: 

1. Provide the necessary interfacing signal, CLK and RESET and instantiate the NuCore.
2. The testbench should then perform the testing as follows: 
a. Load the following set of instructions to the instruction queue 
i. RESET 
ii. Store values of 1,2,3,4,5,6,7,8,9,10 at locations 1,2,3,4,5,6,7,8,9,10 of REG FILE A 
iii. Store values of 10,9,8,7,6,5,4,3,2,1 at locations 1,2,3,4,5,6,7,8,9,10 of REG FILE B 
iv. Add all the consecutive locations of REG FILE A & REG FILE B 
v. Bitwise‐AND all the consecutive locations of REG FILE A & REG FILE B
