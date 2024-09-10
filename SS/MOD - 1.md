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