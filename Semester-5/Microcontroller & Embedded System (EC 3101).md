`PIC Controller Mazidi/ Mc Claney
# Syllabus
- PIC 18 (Peripheral Interfaces Controller)
- 8051*
- ARM (Advanced RISC Microcontroller)
- **Books: Mazidi, McClanky**
# 8051 (not coming in exam)
-  8051 consists of the following units:
	1. 8 bit CPU
	2. 4 KB on chip program memory 
	3. 128 Byte of on chip data RAM
	4. 4 Ports of 8 bit each 
	5. 2 * 16 bit timer circuitry
	6. Full duplex serial port
	7. On chip clock oscillator
## Memory Organization
1. Program Memory : Read only
2. Data memory : Read/ Write
3. Special Function Registers(SFR): Addressed by direct addressing 
---
# Criteria to chose a microcontroller:
![[Pasted image 20250920200302.png]]

# PIC 18  (page 45)
- Invented by Microchip Technology Corporation
- Mostly 8 bit
- 16 bit instruction
## Features 
RISC, ROM , RAM,  ADC, USART, I/O, EEPROM, Timers
`page 46 Mazidi`
![[Pasted image 20250908012635.png]]
![[Pasted image 20250920200925.png]]
In microc the ROM is used to store programs and for that reason it is called program ROM.
**Flash vs Masked memory**
![[Pasted image 20250920201256.png]]
## Architecture
### WREG 
![[Pasted image 20250920201903.png]]
### PIC file register
The data memory is also called the file register, divided into two parts
1. GPR
2. SFR
![[Pasted image 20250920202702.png]]
- Maximum of 4096 Bytes
- Filer register in PIC18 is divided into 256 -Bytes bank 
- 16 Banks
- Access bank is the default bank when PIC is turned on 
- D = 0 , destination = WREG
- Default is 1  = File
![[Pasted image 20250920203354.png]]
### PIC status register
![[Pasted image 20250920204158.png]]
### PIC  Data format
1. hex
2. Binary
3. Decimal
4. ASCII
### Directives 
Also called pseudo instructions give directions to the assembler
ex: EQU, ORG, END , etc
### Steps to create a program 
![[Pasted image 20250920205407.png]]
![[Pasted image 20250920205827.png]]
### Instruction Size
- Byte addressable load store whole bytes 
### I/O Ports programming
A = 7, B,C,D = 8, E = 3 
- Each port has 3 SFR
- $\text{TRIS}_{x} \text{  PORT}_{x} \text{ LAT}_{x}$
#### $TRIS_{x}$
- 0 = output 
If its not activated the value will sit in the SFR of port B inside the CPU but will not get to the pins
(page 158)  example program
![[Pasted image 20250920211835.png]]

### Arithmetic and logical instructions
#### BCD 
1. Unpacked = 8 bits , upper 4 bits are 0
2. Packed = 4 bits, single byte has two bcd 
3. Correction of BCD addition by adding 06
4. DAW (**Decimal Adjust WREG**) instruction to do this 06 addition to correct BCD errors.
5. Add 0110 to upper nibble or lower nibble wherever adjustment is needed 
![[Pasted image 20250920213515.png]]

![[Pasted image 20250920213630.png]]
### Addressing Modes:
1. Immediate
2. Direct
3. Register Indirect
	1. FSR0, FSR1, FSR2
	2. 12 bit register FSR
	3. LFSR 0, 0x30 = Load FSR0
4. Indexed ROM
	1. To store fixed data in code space (ROM)
	2. Need SFR to point to data to be fetched from code space.
	3. Register indirect ROM addressing mode ( Table Processing ) 
	4. TBLPTR : 21 bit reg , points to the byte to be fetched
		1. Divided into 3 parts, TBLPTRL, TBLPTRH, TBLPTRU
### Bank Switching
- Lower 128 Bytes GPR
- Upper 128 Bytes SFR
- Generally Instruction are like: MOVWF filereg, A , where A = 0 implies access bank by default . But when A = 1, the BSR ( bank select register ) is used to select the bank 
### Macros and Modules
![[Pasted image 20250920225126.png]]
Example: 
![[Pasted image 20250920225138.png]]
1. **Local Directives**
If there are labels in the body of the macro then they should be declared before as LABEL before the body of MACRO starts
![[Pasted image 20250920225611.png]]
- This MACRO has a label called BACK so its declared using the LOCAL keyword before the body of MACRO started 
### Modules 
1. Extern directive : To tell the assembler and linker that certain variables are defined in some other module 
2. Global : If a variable is used in some other file then the file its defined in must be defined with the GLOBAL directive 
### PIC programming in C
![[Pasted image 20250920230035.png]]
![[Pasted image 20250920230051.png]]
why while(1) in the end ? 
in microcontroller there is no OS to return to , so if main function returns the mc will crash or start executing some other program.
#### Time Delay
1. using a simple for loop 
2. PIC18 timer
*Ports are bit and byte addressable* 
![[Pasted image 20250920231422.png]]
![[Pasted image 20250920231202.png]]
![[Pasted image 20250920231512.png]]
![[Pasted image 20250920231712.png]]
### Checksum Byte
extra byte attached to the end of series of bytes of data 
1. Add the bytes drop the carry
2. Take 2's complement of the total sum 
3. To do checksum operation add all the bytes including checksum (result must be zero) 
![[Pasted image 20250920232503.png]]
### Data Serialization
Transferring a byte of data one bit at a time through a pin of mc.
Two ways of doing it :
1. using the serial port
2. Transfer one bit at a time and control sequence of data and spaces between them 
### RAM data space vs ROM data space 
In PIC 18 we have two spaces in which to store data 
1. 4096 Bytes of RAM
2. 2M Bytes of ROM
![[Pasted image 20250920233002.png]]
### Storage Qualifiers:
- To indicate in what region the data and code should be placed
- The near qualifier is used to indicate that a program memory data variable is located in first 64K of the program ROM
- Far Qualifier anywhere in the 2M ROM 
- Far qualifier is the default
---
---
---
# Embedded System
![[Pasted image 20250920175319.png]]
![[Pasted image 20250920175543.png]] 

- For late entry, estimated loss: ✓ Difference in triangle areas of actual and estimated triangles.
**Non Recurring Engineering cost**
- This is the **one-time cost** to design and develop a product before mass production starts.
- It includes expenses like **research, prototyping, design, testing, tooling (molds/machines), and software development**.
- Cost per unit = $\frac{C_{NR}}{N} + C_{unit}$
**Difference between microcontroller and PC**
**ES Design and Development Process**
![[Pasted image 20250920181348.png]]
According to functionality of final product, *following requirements* are to be considered: 
- Number of I/O pins 
- Interfaces 
- Memory requirements (ROM/ RAM) 
- Number of interrupts 
- Real-time considerations 
- Development environment 
- Processing speed 
- Memory architecture 
- Power requirement 
- Environmental requirement 
- Life cycle cost
**PWM**
**Efficiency and throughput in case of pipelining**
$$
S_k = \frac{T_1}{T_k} = \frac{N \cdot k}{N + (k-1)}
$$
$$
E_k = \frac{S_k}{k} = \frac{N}{N + (k-1)}
$$
$$
H_k = \frac{N}{T_k} = \frac{N}{(k-1+N)T}
$$
****
## Communication Interfaces
1. Synchronous vs Asynchronous transmission
2. Start Bit : Signal the receiver that a new data word is starting.
- Usually **1 bit**, always **0 (logic low)**.
1. Stop Bit
- Usually **1 or 2 bits**, always **1 (logic high)**.
1. Parity Bit: Adds **1 extra bit** so the number of 1s in the data + parity is even (even parity) or odd (odd parity).
2. Baud Rate: Number of **symbols transmitted per second**.
3. Transfer Rate: Number of **data bits transmitted per second**.
4. Bit time
$$
t_{\text{bit}} = \frac{1}{\text{baud rate}}
$$
5. word time
$$
t_{\text{word}} = \text{number of bits in frame} \times t_{\text{bit}}
$$
6. word rate
$$
\text{word rate} = \frac{1}{t_{\text{word}}}
$$
7. Effective data bit rate
8. UART : 1 start -> 8 data -> 0 parity -> 1 stop
9. I2C
10. SPI
11. CAN
	1. SOF ( start of frame) 
12. USB
13. RS232
	1. Complete serial communication protocol
	2. Uses DB-25 or DB-9 connectors 
	3. DTE DCE communication
	4. Data terminal equipment, Data Communication equipment

