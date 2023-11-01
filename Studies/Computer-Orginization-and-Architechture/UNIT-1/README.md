# UNIT-1
- Introduction
- Functional Unit of Digital System & their interconnections.
- Buses
- Types of Buses
- Bus Architecture
- Bus Arbitration
- Register, Bus & Memory Transfer
- Processor Organization
- General Registers Organization
- Stack Organisation
- Addressing Mode.

## Introductions
![COA figure]()

#### Difference between Computer Architecture and Computer Organisation

| Computer Architecture | Computer Organizations |
| --------------------- | ---------------------- |
| It is concerned with the way hardware components are connected to form a computer System.| It is concerned with the way architecture is implemented in terms of structure & behaviour if a computer systm as seen by the user. |
| It helps us to understand the functionalities of a System. | It provide the details of the how exactly all the functional units in the System are arranged & inter connected. |
| A programmer can view System architecture in terms of Instruction format addressing modes. | It is the actual implementation of the System Architecture to achieve specified System Performance. |
| It is the first step while designing and building a computer. | An Organisation is defined & done based on the System architecture. |
| It deals with the high level design issues & specifications. | It basically deals with the low level System desifn issues. |
| Architecutre involves logic (ISA Instruction sets, addressing modes data type, cache memory organization) | Organisation involves pthysical harware components such as circuit design, adderess, signals and Peripherals. |

![Computer Architecture diagram]()
 #### Instruction Cycle 
1. Fetch 
2. Decode 
3. Execute 
4. Store

| Objective | CA (Computer Architecture) | CO (Computer Organiztion) |
| -------- | -------------------------- | -----------------------|
| Focus | It is connected with the design principal & connected structure of a computer System. It encompassing both hardware & s/w aspwcts to achive the desired level of System Performance. | It is Primarily conerned itself with the physical aspects of a computer s\m & how the hardware components are interconnected & operate togather. |
| Level of Details | It deals with the heigher level of abstraction. It focuses on the organization & behavior of the System in terms of System performance. | It deals with the low-level details computer System, such as design & organisation of individual hardware components circuits & logic gates. |
|Performance Evelutions | It involves evaluating & comparing difference architecural design based on performance matrics like expection time, througput & energy efficiency. | It aims to optimize the performance of the compute s\m by considering factor, like clock speed, latency, bandwidth & hardware-level. |
| Examples | It includes instruction set design pipelining, memory hierarchy, parallel processing, virtual memory & overall System performance. | It includes CPU design m\m System, chase hierarchies, bus protocols & Input/Output SubSystems. |
## Functional units of Digital System-
A computer consists of four main components namely.

![Funcitional Block Diagram]()
#### Input Unit
It consists of input devices that allows you to enter data into your computer. Some of the comman Input devices are Keyboard, mouse etc.
#### Central Processing unit
It  is known as the brain of computer System once the information is entered into the computer by the input device the CPU Processes it. It consists of two parts.
#### Aritmetic & Logic Unit (ALU)
It Performs arithmatic & logical operations, such as additon, substraction, multipicaton, division.
#### Control Unit (CU)
It conrol all the activies and operations of the computer System.
#### Output Unit
It consistd of Output devices that are used to display the results of the output of processing.
## Buses
- A bus is a collection of wires that conect several devices.
- It is used to send control signals & data between the processor & other components.
- A bus is used to communicate between the mazor components of a computer is called **System bus.** 
#### Types of Buses
1. Address Bus
2. Data Bus
3. Control Bus
### Data Bus
- It is bidirectional
- It carry the data form a device controller.
- It consists of 8, 16, 32 or more parallel lines.
- It fetch the insruction from memory.
### Address Bus
- It is unidirextional bus.
- It consists of 16, 20, 24, or more parallel lines.
- The CPU sends out the address of the memory location or input port that is to be written or read by using address bus.
### Control Bus
- It regulate the activities on the bus like Memory Read, Memory Write, Input/Output Read Input/Output Write. 
- The CPU sends signals on the control bus to enables the outputs of address memory device or port device. 
## Bus Architecure
![Bus architecure Diagram]()
## Bus Arbitration
It refers to the process by which the current bus master accesses & then leaves the control of the bus & passes it to another bus requsting processor unit.
The controller that has access to a bus at an instance is known as a **Bus master.** 
- The Bus Arbiter decides who would become the current bus master.
### Applications of Bus Arbitaion
#### Shared Memeory System
In it, multiple devices need to access memory to R/w data. Bus Arbitration allows multiple devices to access memory with out interfaring with each other.
#### Multi-Processor System
In it, multiple processer need to communicate with each other to share data & co-ordinate Processing.
#### Input/Output Devices
In it, data needs to be transferred between devices & memory within a specific time frame to ensure timely processing. It ensure that data transfer occurs with a specific time frame by managing accss to the bus.
### There are two approaches to bus arbitration
1. Centralized bus Arbitration
2. Disributed bus Arbitration.

All devices participating in the selection of the next method of centralised Bus Arbitration.
In it, A Single bus arbiter performs the required arbitration.
There are three bus arbitration method.
#### (i) Daisy Changing Method
- this method is cheaper & simple method.
- All master make use of the same line for bus request.
- The bus grant signal serially propagates through each master unit it encounters the first on that is requesting.
- The user can add more device anywhere along the chain, up to a certain maximum value.
- cannot assume faireness 
- slower.

![Bus Arbiter diagram]()
- shared Communication Link
- Set of wires
- Connects Components.
- Bus Speed is listed in MHz.
- Throughput in BPS or MBPS.
#### (ii) Polling or Rotating Priority Method
Polling or Parallel arbitration consists of priority encoder or decorder. In this, each bus arbiter has a bus request output line & input line.

![Polling/Rotaing Diagram]()

In this, the controller is used to generate the address for the master (Unique Priority), the number of master connected in the System. The controller generated a sequence of master addresser. when the requesting master recognizes its address, it activates the busy line & begins to use the bus.
- It serves fairness.
- Extra poll line, polling delay.
#### (iii) Fixed Priority or Indepemdent Request Method
In this, each master has a separate pair of bus request & bus grant lines & each pair has a priority assigned to it.

![Bus Arbiter Diagram]()
- This method generate fast response.
- Hardware cost is high as a larger number of control line is required.
### DCM
- Simple & Scalabity.
- Add more device anywhere along the chain
### PRPM
- Doesn't favour
- Simple
- It one device fails then entire System will not Stop.
- Can't add more device.
### FP/IRM
- Fast
- High cost
## Register, Bus & Memory Transfer
- Micro-operation
- Register Transfer Level
- Register Transfer Language
## Micro-Operation
The operation on the data in register are called **micro-operation**.
An elementry operation performed during one clock pulses, on the information stored in one or more registers.
> R &larr; F(R,R)
- F: shift, load, clear, increment, add, subtract, complement, and, or, xor, etc.
- Control signals that initiate the sequence of micro-operations.
![mico-operation diagram]()
> P:R<sub>2</sub> &larr; R<sub>2</sub>
"If P=1, then load the contents of reister R<sub>1</sub> into Register R<sub>2</sub>", i.e. if (P=1) then (R<sub>2</sub> &larr; R<sub>1</sub>)
![transfer control-circuit]()
- Registera are assumed to use positive edge-triggered *filp-flop*.
- To completely connect *n* registers *n(n-1)* lines.
- O(n<sup>2</sup>) cost.
## Bus & Bus Transfer
![Registers Diagram]()
- Transfer from Bus to a Destination Register.
![Bus lines]()
- A Register is a collection of *Flip-Flops* used to store binary data & manipulate it using control signals.

It consists of mostly memory storsge, allowing it to store data temporarly or permanaetly.

Types of Register.
- Data
- Address
### Register Transfer
Information transferred from one register to another is designated in symbolic form.
> R<sub>2</sub> &larr; R<sub>1</sub>
### Control Function
It is a boolean \variable that is equal to 1 or 0.
> P:R<sub>2</sub> &larr; R<sub>1</sub>
It shows that transfer operation can be executed only if ```P=1```.
### Micro-operations
The operations executed on data stored in registers are called micro-operation.

Types of Micro-operations &mdash;
- Register transfer micro-operation it transfer binary information from one register to another.
> R<sub>2</sub> &larr; R<sub>1</sub>
- To connect *n* Registers we need n(n-1) line.
- O(n<sup>2</sup>) cost.
### Multiplxer
It is a combinational circuit which have many data Input & single Output depeding on controlor select input.
> Number of Mux = Number of Bits in Register.
> Number of Input in Mux = Number of Register.

## Memory Transfer
### Memory Read
The teansfer of information from memory to the outsie environment is callled a **read operation.**
> Read: DR &larr; M[AR]
### Memory Write
Transfer of new information to be stored into the memory is called a **write operation.**
> Write: M[AR] &larr; DR
#### Repersentaion-
| Decimal | Hexadecimal | Binary |
| ------- | ----------- | ------ |
| 0 | 0 | 0000 |
| 1 | 1 | 0001 |
| 2 | 2 | 0010 |
| 3 | 3 | 0011 |
| 4 | 4 | 0100 |
| 5 | 5 | 0101 |
| 6 | 6 | 0110 |
| 7 | 7 | 0111 |
| 8 | 8 | 1000 |
| 9 | 9 | 1001 |
| 10 | A | 1010 |
| 11 | B | 1011 |
| 12 | C | 1100 |
| 13 | D | 1101 |
| 14 | E | 1110 |
| 15 | F | 1111 |

- Dcimal to Binary conversion &mdash;
> (21)<sub>10</sub> = (?)<sub>2</sub>

> = (10101)<sub>2</sub>

| *2* | 21 | --- |
|- | --- | --- |
| *2*  | 10 | &rarr; 1 |
| *2* | 5  | &rarr; 0 |
| *2* | 2  | &rarr; 1 |
|  | &rarr; 1  | &rarr; 0 |

> (1492)<sub>10</sub> = ( ? )<sub>2</sub>

> = (10111010100)<sub>2</sub>

- A number System relates quantities & Symbols. 
- A number System uses a specific *radix* (base).
- The base/radix of a number system repersentd the number of digits in the particular number system.
- An Unsigned integer number, A can be repersented using *n* digits is base **b**.
> A = *( a<sub>n-1</sub> a<sub>n-2</sub> . . . a<sub>2</sub> a<sub>1</sub> a<sub>0</sub> )<sub>b</sub>*

- (29)<sub>10</sub> &rarr; (11101)<sub>2</sub>
- (125)<sub>10</sub> &rarr; (1111101)<sub>2</sub>
- (45)<sub>10</sub> &rarr; (101101)<sub>2</sub>
- (57)<sub>10</sub> &rarr; (111001)<sub>2</sub>
- (36)<sub>10</sub> &rarr; (1100100)<sub>2</sub>
- (247)<sub>10</sub> &rarr; (11110111)<sub>2</sub>

| 2 | *29* | 1 | &uarr; |
| --| -- | -- | -- |
| 2 | *14* | 0 | &uarr; |
| 2 | *7*  | 1 | &uarr; |
| 2 | *3*  | 1 | &uarr; |
|  | *1*  | 1 | &uarr; |
| | | &rarr; | &uarr; |

| 2 | *125* | 1 | &uarr; |
| --| -- | -- | -- |
| 2 | *62* | 0 | &uarr; |
| 2 | *31*  | 1 | &uarr; |
| 2 | *15*  | 1 | &uarr; |
| 2 | *7*  | 1 | &uarr; |
| 2 | *3*  | 1 | &uarr; |
|  | *1*  | 1 | &uarr; |
| | | &rarr; | &uarr; |

#### Data Repersentaion
Computer data repersentation can store a variety of data including discrete data such as number & letters & continousdata such as sounds & Images
- The stored data is handaied by electronic circuit example Transistors semiconductors, Integrated circuit or wires, which exist in two conditions *(state)* **ON** & **OFF** or *1* or *0*.
#### Data Types
Data is a term used to decribe a set of facts. A single fact is known as Datum.
- It can be of *three* types
1. Numeric Data
2. Alphabetic Data
3. Alphabatic Data 
#### Numbers 
- Numbers can be expressed as either **Integers** *Whole numbers e.g. 124, -26* or **Real Numbers** *Numbers with decimal points, e.g. 1.23*

A whole number is real if it is written with a decimal point, *(e.g. 1.25 in it **1** is integer but **.25** is real number)*
#### Alphabetic data
- This is data made from combination of alphabetic characyers, such as names.
#### Alphanumeric Data
- A string is a squence of charecters . This is data made from combination of alphabetic characters, numerals &/or Special charecters.
- e.g. Address &larr; P.O. 299, Gurugram.
- e.g. Date &larr; Nov 14, 1990. Sept 15, 2023


> *📝* **Author:** *Prof. Anjali*