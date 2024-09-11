# SIC
- 1 *byte* - 8 *bits*
- 1 *word* - 3 *bytes* (24 *bits*)
- Byte addressable
- $2^{15}$ memory space
## REGISTERS IN SIC
- **A**
	- Accumulator
- **X**
	- Index
- **L**
	- Linkage Register
- **PC**
	- Program Counter
- **SW**
	- Status Word
## DATA FORMATS IN SIC
- **Integers**
	- 24 *bit* binary (8 word)
- **Negative Numbers**
	- 2's complement form
- **Characters**
	- 8 *bit* ASCII code
- **No Floating Point**
## INSTRUCTION FORMAT IN SIC
> **24 bit** format
![[Drawing 2024-09-10 20.24.14.excalidraw]]
### ADDRESSING MODES IN SIC (**X**)
- **DIRECT** X=0
	- Target address = address
- **INDIRECT** X=1
	- Target address  = address = (X)
		- X is the contents of the **register X**
## INPUT AND OUTPUT IN SIC
- We use ***TD*** to test weather the device is ready
	- If *CC* < A then **Device is ready**
	- If *CC* = A then **Device is not ready**
- We then use **RD** and **RW**
# SIC XE
> Extra Expensive
- Same as SIC but has $2^{20}$ (1Mb) memory
## REGISTERS IN SIC XE
- All registers in SIC and 4 more
- **B**
	- Base register used for addressing
- **S**
	- General Register
- **T**
	- General Register
- **F**
	-  floating point  accumulator (*48bits*)
## DATA FORMATS IN SIC XE
- **Integers** 
	- 24 bits
- **Negative Numbers**
	- 2's complement
- **Characters**
	- 8 bit ASCII code
- **Floating Point**
	- 48bit floating point
	- ![[Drawing 2024-09-10 20.33.51.excalidraw]]
## INSTRUCTION FORMATS IN SIC XE
### FORMAT 1
- **8 bit**
- FIX, FLOAT
### FORMAT 2
- **16 bit**
- **NEVER REFERENCE MEMORY ONLY REGISTER**
- ADDR , CLEAR, RMO
- ![[Drawing 2024-09-10 20.38.10.excalidraw]]
### FORMAT 3
- **24 bit**
- ![[Drawing 2024-09-10 20.39.37.excalidraw]]
### FORMAT 4
- **32 bit**
- ![[Drawing 2024-09-10 20.39.37.excalidraw 1]]
## ADDRESSING MODES IN SIC XE
### RELATIVE
#### BASE RELATIVE
- N - 1
- I - 1
- **B - 1**
- **P - 0**
- **TA = (B) + DISP**
	- Where **(B)** is contents of register **B**
	- **DISP** is a 12 bit unsigned integer ( 0 - 4095 )
#### PC RELATIVE
- **N - 1**
- **I - 1**
- B - 0
- P - 1
- **TA = (PC) + DSP**
	- Where **(PC)** is content of **PC**
	- **DISP** is a 12 bit signed integer
### DIRECT
- **N - 1**
- **I - 1**
- B - 0
- P - 0 
### INDEXED
> In any case if X is one , the contents of the **X** register is added to the **TA**
### IMMEDIATE ADDRESSING MODE
- I -1 
- N - 0
- **Address is the opearnd itself no memory reference**
	- Denoted by *#*   
### INDIRECT
- I - 0
- N - 1
- **Address of the data is provided as the operand**
	- Denoted by *@* 
### SIMPLE
- N = I
- **Address is directly given as the operand**