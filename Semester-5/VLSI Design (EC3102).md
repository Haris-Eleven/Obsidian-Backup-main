# IC 
Compilation of numerous electrical components, such as transistors, capacitors, resistors, etc., that can fabricate on a single semiconductor chip.
- Analog IC
- Digital IC
- Mixed IC 
# Advantages of VLSI 
1. Size : Shrunking to micrometer sizes
2. Speed
3. Power consumption 
4. Lower **Parasitic Capacitance**
# CMOS Technology 
Why switch from metal to polysilicate:
- High temperature compatibiliy
- Self aligned gate technology: gate itself could be used a s a mask during the ion implantation of source and drain 
*Gate Length* Reduction 
![[Pasted image 20250815114157.png]]
## MOSFET working principle 
Voltage Controlled Devices
1. Enhancement 
2. Depeletion 
![[Pasted image 20250815132540.png]]

## CMOS 
CMOS stands for **Complementary Metal–Oxide–Semiconductor**.  
It uses **both**:
- **p-channel MOSFETs (PMOS)** → conducts when gate is _low_
- **n-channel MOSFETs (NMOS)** → conducts when gate is _high_
The term _complementary_ means the PMOS and NMOS are arranged so that when one is ON, the other is OFF — minimizing power loss.
### Fabrication of CMOS
-  P - Well and N - well structure  (***20 steps***)
- Twin tub/well technology 
**Latch Up:**
Latch-up is a parasitic phenomenon where an unintended low-impedance path is created between the power supply (Vdd) and ground (GND) due to the formation of a parasitic thyristor (SCR-Silicon Controlled Rectifier) within the semiconductor structure which can lead to the following issues:
-  Excessive current flow
-  Device overheating
-  Permanent damage or failure of the IC
# CMOS Logic Gates
1. CMOS Inverter  ![[Pasted image 20250815160228.png]]
2. CMOS NAND
3. 3 Input NAND 
## **1. Pull-up network (PUN)**

- **Made of:** PMOS transistors.
- **Function:** Connects the output to **Vdd** when it’s supposed to be logic high.
- **Behavior:**
    - PMOS conducts when its gate voltage is **low** relative to its source.
    - In an inverter: when the input is 0 → PMOS turns ON → output gets “pulled up” to Vdd.
---
## **2. Pull-down network (PDN)**
- **Made of:** NMOS transistors.
- **Function:** Connects the output to **GND** when it’s supposed to be logic low.
- **Behavior:**
    - NMOS conducts when its gate voltage is **high** relative to its source.
    - In an inverter: when the input is 1 → NMOS turns ON → output gets “pulled down” to GND.
# CMOS Inverter
- **VIL (Input Low Voltage):** Max Vin recognized as logic 0.
- **VIH (Input High Voltage):** Min Vin recognized as logic 1.
- **VM (Switching Threshold):** Point where Vin = Vout.
- **Noise Margins (NML, NMH):** The “safe zones” for logic 0 and 1.
	- Higher the noise margin better the circuit 
# Pass Transistor Logic 
## NMOS
Drain at higher voltage source at lower voltage
Passes Strong logic 0 weak Logic 1 
- The parasitic capacitor gets charged and discharged 
- A $V_T$ voltage drop across transistors 
$V_o = min(V_D,V_G-V_T)$
![[Pasted image 20250902204157.png]]![[Pasted image 20250902204937.png]]
- On Resistance of MOSFET and Parasitic Capacitance
- Ensure that theres always a charging and discharging path at output node
# Stick Diagram 
[Youtube Video](https://www.youtube.com/watch?v=wEm3WOmrfhU)
A stick diagram is a diagrammatic representation of a chip layout that helps to abstract a model for design of full layout from traditional transistor schematic. Stick diagrams are used to convey the layer information with the help
of a color code.
#WatchVideoToUnderstand
## Nmos 
![[Pasted image 20250902222437.png]]
## Pmos
## Cmos

# VLSI Design Rules
Interface or communication link between the circuit designer and the process engineer during the manufacturing phase.
**What is the need of design rules**
Due to Problems like:
-  Photo resist shrinkage, tearing
- Variations in material deposition, temperature and oxide thickness.
- Impurities
- Variations across a wafer.
## Frontend Design 
## Backend Design 
# Design Approaches
# Scaling of MOS Circuit 
## Indicators of figure of merits
Following figure of merits 
- Minimum feature size
- Number of gates of one chip 
- Power dissipation
- Maximum operational frequency 
- Die size
- Production cost
## Scaling models 
1. Constant electric field $\beta = \alpha$ || **Dennard scaling law**
2. Constant voltage scaling model  $\beta = 1$
## Scaling factors
- $\frac{1}{\alpha}$ and $\frac{1}{\beta}$ are considered to accommodate the models
- $\frac{1}{\beta}$ is chosen as the scaling factor for supply voltage and gate oxide thickness D.
- $\frac{1}{\alpha}$ is used for linear dimensions
![[Pasted image 20250925144427.png]]
### Gate area scaling 
#### Capacitor Scaling 
#### Leakage issue
#### Power trade off 
### Parasitic capacitance
### Gate capacitance
### Carrier density in channel 
### Channel resistance
### Gate delay 
### Maximum operating frequency
### Saturation Current 
### Current density 
### Switching energy per gate ($E_{g}$)
### Power dissipation per gate 
### Power dissipation per unit area
### Power speed product ($P_{T}$)
## Other parameters 
### Substrate doping 

# Static and dynamic cmos 
# ASIC
## Types
## Design Approaches
11 step design approach 
1. Chip specification
2. Design entry & functional verification 
3. RTL Synthesis 
4. Chip partitioning
5. Design for test insertion
6. Floorplanning
7. Placement
8. Clock tree synthesis
9. Routing
10. FInal verification 
11. GDSII
# FPGA
## Design approach