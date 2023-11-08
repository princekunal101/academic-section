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

#### Binary to Decimal
> (11101)<sub>2</sub> = ( ? )<sub>10</sub>

> = [(1 x 2<sup>4</sup>) + (1 x 2<sup>3</sup>)+ (1 x 2<sup>2</sup>) + (0 x 2<sup>1</sup>) + (1 x 2<sup>0</sup>)]<sub>10</sub>             

> &because; [2<sup>0</sup> = 1]

> = 16 + 8 + 4 + 0 + 1
> (29)<sub>10</sub>
#### Binary to Ocatal
> (1010101)<sub>2</sub> = ( ? )<sub>10</sub>

> = [(1 x 2<sup>6</sup>) + (0 x 2<sup>5</sup>)+ (1 x 2<sup>4</sup>) + (0 x 2<sup>3</sup>) + (1 x 2<sup>2</sup>) + (0 x 2<sup>1</sup>) + (1 x 2<sup>0</sup> )]<sub>10</sub> 

> = 64 + 0 + 16 + 0 + 4 + 0 + 1

> = 64 + 21 

> = (85)<sub>10</sub>

Now convert 
| 8 | *85* | 5 | &uarr; |
| --| -- | -- | -- |
| 8 | *10* | 2 | &uarr; |
|  | *1*  | 1 | &uarr; |
| | | &rarr; | &uarr; |

> = (125)<sub>8</sub>

![Binary to Ocatal with paring]()
#### Octal to Binary Conversion
> (41)<sub>8</sub> = ( ? )<sub>2</sub>

> = (4 x 8<sup>1</sup>) + (4 x 8<sup>0</sup>)

> = 32 + 1

> = (33)<sub>10</sub>

| 2 | *33* | 1 | &uarr; |
| --| -- | -- | -- |
| 2 | *16* | 0 | &uarr; |
| 2 | *8*  | 0 | &uarr; |
| 2 | *4*  | 0 | &uarr; |
| 2 | *2*  | 0 | &uarr; |
|  | *1*  | 1 | &uarr; |
| | | &rarr; | &uarr; |

> = (100001)<sub>10</sub>

![Ocatal to Binary with paring]()
#### Hexa Decimal
> (1001001)<sub>2</sub> = ( ? )<sub>16</sub>

> = [(1 x 2<sup>6</sup>) + (0 x 2<sup>5</sup>)+ (0 x 2<sup>4</sup>) + (1 x 2<sup>3</sup>) + (0 x 2<sup>2</sup>) + (0 x 2<sup>1</sup>) + (1 x 2<sup>0</sup> )]<sub>10</sub> 

> = 64 + 0 + 0 + 8 + 0 + 0 + 1

> = (73)<sub>10</sub>

Now convert 
| 16 | *73* | 9 | &uarr; |
| --| -- | -- | -- |
|  | *4* | 4 | &uarr; |
| | | &rarr; | &uarr; |

> = (149)<sub>16</sub>

![Binary to Hexa Decimal with paring]()
## Register
A register is a group of *flip-flop*. with each *flip-flop* capable of storing one bit of information.
An n-bit register has a group of n *flip-flop* and is capable of storing any binary information of n-bit.
In addition to *flip-flops*, a register may have combinational gates that perform certain data processing task. so,
A register consist of group of *flip-flops* and gate that effect their transitions.
1. The *flip-flop* holds the binary information.
2. Gates control when and how new information i transfered into the registers.
### 4-bit register
- The Simplest register without gates,contains only *flip-flop(D).*
- The common clock input triggers all *flip-flops*. On the rising edge of each puls. The binary data available at the four input are transferred into 4-bit register.
- The 4-Output can be obtain the binary information stored in the register.
- The clear input goes to a special terminal in each *flip-flop*. When iput goes to 'O' all *flip-flop* are reset.
- The clear input is use to clearing the register to all 0's prior to 1's clocked operation.
- The *'clock'* signal enables the 'D' input but the *'clear'* input is independent to check signals.

![Register Diagram]()
### Rgister Load
The transfer of new information into a register is referred to as loadinf the register. If all the bits of register are loaded simulotaniously with a common clock pulse than the loading is said to be done in parallel.
#### Representation of Register
The most common method to represent a register is by a rectangular box with the name of register inside.
> R1

The individual flip-flop in an n-bit register are numbered in sequence from are numbered in sequence from 0 to (n-1) starting from '0' in the right most position & increasing the numbers towards left.
![Showing individual bit]()

The numbering of bits in a 16 bit register can be marked on the top of the Box.
![Numbering of 16-bit]()

A 16-bit register is partitioned into two parts like 
![Devided into two parts]() 
the name of the 16-bit register is PC the symbol
   
    PC(0-7) or PC(L) refers to Lower order bytes. and

    PC(8-15) or PC(H) refers to Higher order bytes.
#### Micro-Operations
The operation executed on the data in registers are called micro-operations.
The are detailed low-level instruction used in some desgins to implement complex machine instructions
A micro-operation is an elementry operation performed on the information stored in one or on more register.
The result of operation may replace the previous binary information of register information may replace the previoud binary information of a register or may be form stored to anothe register.
The micro-operation in digital computers are of 4 types.
- Register transfer micro-operations transfer binary information from one register to another.
> (R<sub>2</sub> &larr; R<sub>1</sub>)
- Arithmatic micro- operations perform arithmatic operations on numeric data stored in register.
> R<sub>3</sub> &larr; R<sub>1</sub> + R<sub>2</sub>
- Subtract micro-operation 
> R<sub>3</sub> &larr; R<sub>1</sub> + R<sub>2</sub> + 1

In substraction, instead of using minus operator we the 1's complement & add to the register which gets sub, i,e,
> R<sub>1</sub> &#8211; R<sub>2</sub> is equivalent to 

> R<sub>3</sub> &larr; R<sub>1</sub> + R<sub>2</sub> + 1

#### Increment/Decrement micro-operation
These are generally pwrformed by adding & Substracting 1 to and from the register respestively
> R<sub>1</sub> &larr; R<sub>1</sub> + 1

> R<sub>3</sub> &larr; R<sub>1</sub> - 1

#### Logic micro-operation
These are binary micro-operations performed on the bits stores in the register.
> P: R<sub>3</sub> &larr; R<sub>1</sub> X - OR R<sub>2</sub>

> (A &middot; B&#773; ) + (A&#773; &middot; B)

> (A + B) &middot; (A&#773; + B&#773;)

- R<sub>1</sub> &rarr; 010
- R<sub>2</sub> &rarr; 100
- R<sub>3</sub> &larr; 110

#### Shift operations
These are used for serial transfer of data. That means we can shift thw content of the register to the left or right.

**Register Trasnfer Language**

The symbolic notaion used to describe the micro-operation transfer amongest register is called RTL.
The term register trasfer means the availability of hardware logic circuits that can perform a stated micro-operation and transfer the result of the operation to the same or another register.
A register transfer language is a system for expressing in symbolic from the mico-operation squence among the register if a digital module.

**Following are commonly used Registers**
1. **Accumlator :** *It is used to store data taken out from the memory.*
2. **General Purpose Register :** *This is used to store data intermediate results during program execution. It can be accessed via assembly programming.*
3. **Special Purpose Register :** *These regiters are for computer system.*
- **MAR :**  *Memory Address Register are those registers that holds the address for memory unit.*
- **MDR :** *Memory data register that store data received from memory & sent from memory.* 
- **PC :** *Program Counter points to the next instruction to be executed.*
- **IC :** *Instruction register holds the information to be educated.*

### Shift Register
A register capable of shifting its binary information in one or both direction is called shift register.
#### Types of Shift Register 
- **Serial In and serial out:** *The data is shifted in and out serially. In **SISO**, A single bit is shifted at a time.*

![Serial input serial output register diagram]()

- **Serial In Parallel out:**
*The data is passed serially to the Register and output are fetched in a parallel way.*

![Serial input parallel output register diagram]()
- **Parallel in Serial out:**
*The data is a transfer in a parallel way and the output comes serially.*

![Paralel input serial output register diagram]()
- **Parallel In parallel out:**
*Parallel data is a transferred simultaneously into the Register and transferred to their respective output by the same **clock pulse.***
![Parallel input parallel output register diagram]()

![Registers types of diagram]()

The Register in CPU performs two roles.
### User visible Register
A user visible register may be refernced by means of a machine language that the processor executes.
#### General Purpose Register
- Can be used by programmer.
- Contains operands for any opcode.
- Can be used for addressing function *(e.g. registered in direct displacement.)*
#### Data Register
It may be used only to hold the data.
#### Address Register
It may be devoted to a particular addressing mode.
*e.g.*
- Segment Pointer
- Index register
- Stack Pointer

**Segment Pointer** holds the address of the base of segment in segmented addressing.

**Index Register** are used for indexed addressing & may be auto indexd.

**Stack pointer** points to the top of the stack. This allows implicit addressing that is push, pop and other stack instructions used not contain an explicit stack operand.
#### Condition codes
It is also referred to as flags.Condition code are the bits set by the processor hardware as the result of operation.
*e.g.*
- Positive or negative Result.
- Zero Result
- Overflow etc.

### Control & status Register
- Registers employed to control the operation of processor.
- Note visible to the users.
- Four registers are essential to instructions execution.
#### PC, IR, MAR, MDR
- **Program counter** contains the address of the instruction to be fetched.
- **Instruction register** contains the instruction most recently fetched. or currently being executed.
- **MDR** contains the address of a location in the memory.
- **MDR/MBR** *(memory buffer register)* contains a word of the data to be written to memory or the word most recently read.



> *📝* **Author:** *Prof. Anjali*