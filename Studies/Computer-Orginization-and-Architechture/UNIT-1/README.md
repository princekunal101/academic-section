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

## Processor (CPU) organization
A processor must have three functional unit to be what we call a computer
![Major Componenets of CPU]()
### Types of processor Organization
- Stored Program Organization
- General Register Organization
- Stack Organization

### Stored Program Organization
![stored program organization diagram]()

    main()
    {
       int a=10, b=20, c;

       c= a+b;

       printf("Result %d", c);
    }

In the stored Program concept, both the instruction & the data (that, the instruction operate on) are stored int hte computer memory itself. Before the introduction of this data, instruction and data were considered two totally different entites & were thus stored separately.

It is the simplest organization of the computer.

It is easy to imlement.

It has hardwired control unit.
![Processor diagram]()
| Short Form |Full Form | Size |
| ------ | ----- | ----- |
| **IR** | Instruction Register | *16 bits*.|
| **AR** | Address Register | *12 bits* |
| **DR** | Data Register | *16 bits* |
| **TR** | Temporary Register | *16 bits* |
| **PC** | Program Counter | *12 bits* |
| **AC** | Accumulator | *16 bits* |
| **INPR** | Input Register | *8 bits* |
| **OUTR** | Output Register | |

![Instruction formate fig]()

The First part specifies the operation to be performed & the second species an address.

The Memory Address tells the comntrol where to find an operand in memory.

This operand is read from memory & used as the data to be operated on togather with the data stored in the processor register.

> It is also known as Single - Processor register or Accumulator Organization. 

Processor organization means how the components of processor ae connected and accomplish theor tasks.

A processor does the following thing,.
- Fetch Instruction
- Interpret Instruction
- Fetch Data
- Process Data
- Write Data
#### Fetch Instruction
The processor reads an instruction from memory.
#### Interpret/Decode Instruction
The instruction is decoded to determine what action is required.
#### Fetch Data
The execution of an instruction may require reading data from memory or an Input/Output module.
#### Process Data
It perform some arithmetic or logical operation on the data.
#### Write Data
The result of an execution may require writing data to memory module or Input/Output module.
> **NOTE:** Stores the results of calculation mode by ALU. It holds the intermediate of arithmetic & logical operations. It act as a temporary storage location or device.
#### Drawbacks of SPO
- It works on the sequential process then it takes more steps to execute an instruction.
- It is time consuming.
- It only considered one Register/Accumulator for communication purpose.
### General Register Organization
- Memory access is the most time consuming operation in a computer.(SPO)
- It is more convenient & more efficient to store the intermediate values in processor register.
- The register communicate with each other not only for direct data transfer, but also while performing various micro-opeeration.
- It has a micro-programmed control unit.

![General register organisation fig]()
If a CPU includes some registers therefore a common bus can link these registers. A genral organization of seven CPU register is displayed in the fig. above.

The CPU bus system is managed by the control unit. The CU explicit the data f;ow through the ALU by choosing the function of the ALU and the component of the system.

*for e.g.*
Perform the operation 
> R<sub>1</sub> &larr; R<sub>2</sub> + R<sub>3</sub>
1. **MUX A Selector (SEL A):** TO place the content of R<sub>2</sub> into bus A.
2. **MUX B Selctor (SLE B):** To place the content of R<sub>3</sub> into bus B.
3. **ALU Operation Slector (OPR):** To provide the arithmatic addition A+B.
4. **Decorder destination Selector (SEL D):** To transfer the content of the output bus into R<sub></sub>

#### Control Word
- Sequence of binary information
- Specifies the micro-operation to be performed
- The peration with the content of register is called as micro- operation.

There are 14 binary selection inputs in the unit & their combined value specifies a controlword.

**Encoding of Register Selection Fields.**
| Binary Code | SEL A | SEL B | SEL D |
|------------ |-------| ----- | ----- |
| 000 | Input |Input | Input |
| 001 | R<sub>1</sub> | R<sub>1</sub> | R<sub>1</sub> |
| 010 | R<sub>2</sub> | R<sub>2</sub> | R<sub>2</sub> |
| 011 | R<sub>3</sub> | R<sub>3</sub> | R<sub>3</sub> |
| 100 | R<sub>4</sub> | R<sub>4</sub> | R<sub>4</sub> |
| 101 | R<sub>5</sub> | R<sub>5</sub> | R<sub>5</sub> |
| 110 | R<sub>6</sub> | R<sub>6</sub> | R<sub>6</sub> |
| 111 | R<sub>7</sub> | R<sub>7</sub> | R<sub>7</sub> |

- Specifies the binary code for each of the three fields.
- When SEL A or, SEL B is 000, the corresponding multiplexer selcts the external input data.
- When SEL D = 000, no destination register is selcted but the contents of the output bus are availabe in the external output.

**Encoding of ALU operations**
| OPR Select | Operation | Symbol |
| ---------- | --------- | ------ |
| 00000 | Transfer A | TSFA |
| 00001 | Increment A | INCA |
| 00010 | Add A+B | ADD |
| 00101 | Subtract A-B | SUB |
| 00110 | Decrement A | DECA |
| 01000 | AND A&B | AND |
| 01010 | OR A&B | XOR |
| 01100 | XOR A&B | XOR |
| 01110 | Complement A | COMA |
| 10000 | Shift Right A | SHRA |
| 11000 | Shift Left A | SHLA |

**Example of Micro-operation**
> R<sub>1</sub> &larr; R<sub>2</sub> - R<sub>3</sub>

| Field: | SEL A | SEL B | SEL D | OPR |
| ------ | ----- | ----- | ----- | ---- |
| **Symbol:** | R<sub>2</sub> | R<sub>3</sub> | R<sub>1</sub> | SUB |
| **Control Word:** | 010 | 011 | 001 | 00101 |
| **R<sub>1</sub> &larr; R<sub>2</sub> + R<sub>3</sub>** | R<sub0>2</sub> | R<sub>3</sub> | R<sub>1</sub> | ADD |
| **R<sub>4</sub> &larr; R<sub>4</sub> &or; R<sub>5</sub>** | R<sub>4</sub> | R<sub>5</sub> | R<sub>4</sub> | OR |
| | 100 | 101 | 100 | 01010 |
| **R<sub>6</sub> &larr; R<sub>6</sub> + 1** | R<sub>6</sub> | &mdash; | R<sub>6</sub> | INCA |
| | 110 | 000 | 110 | 00001 |
| **R<sub>7</sub> &larr; R<sub>1</sub>** | R<sub>1</sub> | &mdash; | R<sub>7</sub> | TSFA | 
| | 001 | 000 | 111 | 00000 |
| **OUTPUT &larr; R<sub>2</sub>** | R<sub>2</sub> | &mdash; | None | TSFA |
| | 010 | 000 | 000 | 00000 |
| **OUT &larr; Input** | I/N | &mdash; | None | TSFA |
| | 000 | 000 | 000 | 00000 |
| **R<sub>4</sub> &larr; Shl R<sub>4</sub>** | R<sub>4</sub> | &mdash; |R<sub>4</sub> | SHL |
| | 100 | 000 | 100 | 11000 |
| **R<sub>5</sub> &larr; 0** | R<sub>5</sub> | R<sub>5</sub> | R<sub>5</sub> | XOR |
| **Clear Register** | 101 | 101 | 101 | 01100 |

## Stack Organization
- Stack is a storage device that store information in such a manner that the item stored last is the first item [Missing a word]().
- Stack follows **LIFO** Order
- The register that folds the address for the stack is called a stack pointer (SP). its value always point at the top item in the stack.
- Two operations of a stacj are insertion and deletion of Item.
> **PUSH:** Push- down *'Insertion'*

> **POP:** Pop-up *'Deletion'*

### Type of Stack
### Register Stack
- Stack Depth is limited 
- A finitr number of memeory words or register (stand alone)
### Memory Stack
- Stack Depth is Flexible 
- A portion of large memory

![Memory stack fig]()
| Push Operation | |
| --------- | ----- |
| **SP &larr; SP + 1** | Increment SP |
| **M[SP] &larr; DR** | Write to stack |
| **If(SP=0) then (Full &larr; 1**) | Check if stack is Full |
| **Empty &larr; 0** | Mark not empty |

>It is a zero address Instruction. In it we doesn't specify the operand address.

| Pop Operation | |
| ------ | ----- |
| DR &larr; M[SP] | Read Element |
| SP &larr; SP - 1 | Decrement SP |
| If (SP=0) then (Empty &larr; 1) | Check if SP is Empty |
| Full &larr; 0 | Mark stack not full |

**Infix:** (A **+** B)

**Prefix:** (**+** AB) *[Polish notation]*

**Postfix:** (AB **+**) *[Reverese Polish notation]*
>*e.g.* (2 x 4) + (7 x 6)

>(24x) + (76x)

>24x 76x +

![Operation in system stack diagram]()
>[A * [B + C * (D + E) ] ] / (F * (G + H) )

| | Input | RPN |
| -- | ----- | ---- |
| i. | D + E | DE + |
| ii. | C * (D + E) | CDE +* |
| iii. | B + C * (D + E) | BCDE +*+ |
| iv. | [A * [B + C * (D + E) ] ] | ABCDE + * + * |
| v. | (G + H) | GH + |
| vi. | F * (G + H) | FGH + * |

### Memeory Stack
- A Stack can be implemented in a RAM attached to a CPU.
- The implementation of stack in the CPU is done by assigning a portion of memory to a stck operation and using a processor register as a stack pointer. 

![Memory stack operation diagram]()
#### Push Operation
> SP &larr; SP - 1

> M[SP] &larr; DR

#### Pop Operation
>DR &larr; M[SP]

>SP &larr; SP + 1

#### Advantages of Register stack
- Increase speed of Execution 
- Zero address
- Simple implementation
#### Disadvantages of Register stack
- Costly
- Fixed
#### Advantages of Memory stack
- Efficient Management
- Data Moving is fast
- Cost effective
#### Disadvantages of Memory stack
- **Limited lifespam :** Data on the stck is automatically removed when its scope ends.
### Computer Instructions
- Computer Instructions are a set of machine language instruction
#### Program
A Sequence of instructions.
#### Instruction
An Instruction is a command given to the computer to perform a specific operation.
- An instruction is a group of bits *(binary code)* that instructs the computer to perform a specific operation.
- The purpose of an instruction is to specify both operation to be performed by CPU and the set of operands *(or data)*.

Instruction format refer to the way instructions are encoded & represnted types of instruct format, including zero, one, two & three address instruction.
An instruction format is a binary format which specifies a computer instruction.
A bits of the instructions are divided into group called fields.

#### Types of fields instruction
A computer performs a task based on the instruction provided. Instruction in computers comprises group called fields. These fields contain different information for computer everything is in 0,1 so, each field has different significance based on wich a CPU decides what to perform.

The most common fields in instruction formate are &mdash;
| Mode | Opcode | Addressing (Operand) |
| --- | --- | --- |

**Mode :** A mode field specifies the way the operand or EA (Efective Address) of the operand is determined

**OpCode :** The opcode (Operation Code) field specifies the operation to be performed such as add, sub, multiply, shift, complement etc.

**Address :** An address field specify the location of the operand.
*i.e.* processor register or memory location.

Computers may have instructions of several different lengths containing varying number of address.
The number of address field in the instruction formate of a computer depends on the internal organization of its registers.
CPU organisation is of three types based on the number of address fields.
1. Single Accumulator Organization
2. General Register Organization
3. Stack Organization.

>**In first one :** The operation is done for involving a special register called accumulator

>**In Second :** Multiple Register are used for the computer purpose.

>**In Third :** Due to stack based operation it doesn't contain any address field 
 
#### Types of Instruction Formate
Based on the number of addresser, Instruction are classified as
- Three-address Instruction Formate.
- Two-address Instruction FOrmate.
- One-address Instruction Formate.
- Zero-address Instruction Formate.
#### Threee-Address Instruction formate
- It is done by GRO.
- It uses set of general purpose register. one of the mostky widely accepted models for machine architecture today.
- Specifies all operands explicity.

*e.g.*
| Mode | Opcode | Destination | Source 1 | Source 2 |
| ---- | ------ | ------ | ----- | ---- |

 
| : X = (A + B) * (C + D) : ||
| --- | --- |
**ADD R<sub>1</sub>, A, B** | //R<sub>1</sub> &larr; M[A] + M[B] |
| **ADD R<sub>2</sub>, C, D** | // R<sub>2</sub> &larr; M[C] + M[D] |
| **MUL X, R<sub>1</sub>, R<sub>2<sub>** | // M[X] &larr; R<sub>1</sub> * R<sub>2</sub> |

#### Advantages
- Results in short program.
- It makes the creation of program easy.
- It is more efficient
- It allows more complex operation.
#### Desadvantages
- It require more memory space.
- Instruction become long (many bits)
- It makes the execution of the program slower.
#### Two Address Instruction
- It follows GRO
- Two addresses are used in instruction when each sepecify either a processor register or a memory operand.

| Mode | opcode | Address 1 | Address 2 |
| ---- | ----- | ------ | ------ |

*e.g.*
>X = (A + B) * (C + D)

| | |
|--- | --- |
| MOV R<sub>1</sub>, A | //R<sub>1</sub> &larr; M[A] |
| ADD R<sub>1</sub>, B | //R<sub>1</sub> &larr; R<sub>1</sub> + M[B] |
| MOV R<sub>2</sub>, C | //R<sub>2</sub> &larr; M[C] |
| ADD R<sub>2</sub>, D | //R<sub>2</sub> &larr; R<sub>2</sub> + M[D] |
| MUL R<sub>1</sub>, R<sub>2</sub> | //R<sub>1</sub> &larr; R<sub>1</sub> * R<sub>2</sub> |
| MOV X, R<sub>1</sub> | //M[X] &larr; R<sub>1</sub> |

#### One Address Instruction
- It follow/based on Single Accumulator Organization.
- All Operations are performed on an implied accumulator register.
- With one operand implicity in the accumulator register minimizes the internal complexity of the machine and allow for short instructions.
- The instruction formate uses only one address field *i.e.*,one-address.

| Mode | Opcode | Address /Operand |
| ---- | ----- | ------ |

*e.g.*

|: X = (A + B) * (C + D) : ||
| --- | --- |
| **LOAD A** | // AC &larr; M[A] |
| **ADD B** | // AC &larr; AC + M[B] |
| **Store[T]** | // M[T] &larr; AC |
| **LOAD C** | // AC &larr; M[C] |
| **ADD D** | // AC &larr; AC + M[D] |
| **MUL[T]** | // AC &larr; AC * M[T] |
| **Store X** | // M[X] &larr; AC |

#### Advantages of One-Address
- It require less memory then two & three address instruction.

#### Disadvantages of One-Address
- Program length is incresed.
- It can be slower to execute because it require constant operand fetching & addressing. 

#### Zero Addressing Instruction
- It is udes in stack Organistion.
- These instructions or address, they operate on data stored in registers or memory locations impliecietly defined by the instruction.
- It Simply add the content of two register togather without specify the register name.
- The Operands are put into the stack & the operations are carried out on the top of the stack (ToS). The operand are implicitly specified on ToS.
- It doesn't use an address field for the instruction like ADD, MUL etc.
- PUSH & POP instruction are used t communicate with stack.
*e.g.*
> X = (A + B) * (C + D)


| : (C + D)[AB + CD + *] : ||
| --- | --- |
| **PUSH A** | // TOS &larr; A |
| **PUSH B** | // TOS &larr; B |
| **ADD** | // TOS &larr; A + B |
| **PUSH C** | // TOS &larr; C |
| **PUSH D** | // TOS &larr; D |
| **ADD** | // TOS &larr; C + D |
| **MUL** | // TOS &larr; (A + B) * (C + D) |
| **POP** | // M[X] &larr; TOS |

#### Advantages
- It is simple & can be executed quickly
- It takes less memory space.
#### Disadvantages
- It has limited functionalities & do not allow flexibility in terms of addressing modes or operand types.

## Address Modes
Addressing mode in computer architecutre refers to the techniques & rules used by processors to calculate the effective Address or operand location for data operation.
The term adderessing mode refers to the way in which the operand of an instruct is specified.

|Types of Adresing Modes     ||
| :--------- | :------ |
| Imlied / Implicit Mode |No Address fields is required|
| Immediate Mode |^ |
| Direct Mode | Address specifies memory location |
| Indirect Mode |^   |
| Register Direct Mode | Address specifies Process register |
| Register Indirect Mode |^  |
| Auto-Increment |^ |
| Auto -Decrement |^  |
| Relative Addressing Mode (PC) | Address field + content of CPU Register |
| Indexed Addressing Mode (IR) |^  |
| Base Register address Mode (BR) |^   |

- *These are called displacement addressing*

### Implied Addressing Mode
- Operand are specified implicitly in the definition of the instruction.
- It is also known as implicit addressing mode

*e.g.*
- The instruction *'Complement Accumulator'* (MA) is an implied mode instruction
- In a stack organized computer, zero address instruction are implied mode instruction.
### Immidiate Addressing Mode (Symbol #)
- The Operand is specified in the instruction
- No memory refence to fetch data 
- Fast but limit range

| Opcode | Operand |
| --- | ---- |

*e.g.*
| **ADD 10** | // AC &larr; AC + 10 |
|----- | ---- |
| **MOV R#20** | // R &larr; 20 |

### Register Direct Addressing Mode
- The operand is contained in a register set.
- The address field of the instruction refers to a CPU register that conatins the operand.
- No refrence to memory is required to fetch the operand.
- No memory access, very fast execution, limited address space limited number of registers.

*e.g.*
| ADD Ax, Bx | Add the content of register Bx to Ax |
| ---- | ---- |

![register direct addressing mode fig]()

### Register Indirect Mode 
The address field of the instruction refers to a CPU register that contains the EA (Effective Address) of the operand.
#### Effective Address 
EA is a term that describes the address of an operand that is stored in the memory.
Only one refence to memory is reuired to fetch the operand

![effective address refister fig.]()

*e.g.* 
> MOV[R<sub>1</sub>] , R<sub>2</sub>

- Value of R<sub>3</sub> is moved to the memory loacation specified in R<sub>1</sub>
- EA = R
- Operand is in memory cell pointed to by contents of register R.


### Direct Addressing Mode
It is also known as absolute addressing mode. The address field of the instruction contains the EA of the operand. The operand resides in memory & its address is given directly by the address field of the instruction.

![direct addressing mode fig.]()

*e.g.*
>ADD A

- Add contents of cell A to the accumulqator.
- Single memory refernce to access datga.
- No additonal Calculations for EA.
- Limited Address space.

### Indirect Addressing Mode
In this, mode the address field of the instruction gives the address where the EA is stored in memory.
Control fetches the instruction from memory & uses its address part to access memory again to read the EA.
It maybe nested, multilevel or cascaded.
Multiple memory accesses to find operand, hence it is slower.

![indirect addressing mode fig]()

*e.g.*
>AC &larr; AC + [X]

ADD[X] will indirect the value stored int he accumulator by the value sored atmemory location specified by X.
> EA = Address part of instruction + content of CPU Register.

#### Auto Increment Addressing Mode
These are similar to register Indirect AM (Addressing Mode) except that the register is incremented after its value is located at another location like accumulator.

**EA = R** 

![auto increment AM fig.]()
after loading R<sub>1</sub> is incremented by 1. It becomes 401.

#### Auto Decrement Addressing Mode
It is reverse of Auto increment, as in it the register is decrement before the execution of the instruction.

**EA = (R) - 1**

![auto decrement AM fig.]()

#### Relative Addressing Mode
In this mode, the contents of Program counter is added to the address part of instruction to obtain the EA.

**EA = A + PC**

![relative AM fig]()

- Program Counter (PC) always contains the address of the next instruction to be executed.
- After fetchong the addressing of the instruction the value of program counter immediately increases.

### Index Register Addressing Mode
In it, content of Index Register is added to direct address part of instruct  to obtain the EA.

![index register AM fig.]()

### Base Register Addressing Mode
In this, the content of a Base Register is added to the address part of the instruction to obtain the effective address.
A base register is assumed to hold a base address & the address field of the instruction gives a displacement relative to this base address.
The base Register addressing mode is used in complete to facilitate the relocation of programs in memory.

![Base register AM fig.]()

![Address register block fig.]()


| Addressing Mode | Effective Address (EA) | Content of Effective Address (EA) |
| ------- | -------: | ------: |
| Direct | 100 | 105 |
| Immediate | &mdash; | 100 |
| Indirect | 105 | 500 |
| Relative | 152 | 70 |
| Index | 103 | 65 |
| Register Direct | &mdash; | 98 |
| Register Indirect | 98 | 700 |
| Auto - increment | *100* 101 | *105* 35 |
| Auto - decremnet | 100 *99* | 105 *800* |

## Questions
1. An instruction is stored at location 300 with its address field at local 301. The address field has the value 400. A processor Register R<sub>1</sub> contains the number 200. Evalute the Effective address if the addressing mode of the instruction is.

**Given:**

| | Instruction | Effective Address (EA) | Content of EA |
| ---- | --------- | :------: | :------: |
| **a.**| Direct |      400  ||
| **b.**| Immediate |    301 ||
| **c.**| Relative  |  200 ||
| **d.**| Register Indirect | 600 ||
| **e.**| Index with R<sub>1</sub> as the index Register. | 200 | 302 |

![Address regiser fig.]()

- In direct address mode, the effective address is the address part of the instruction, 400.
- In immediate mode, the second woed of the instruction is taken as the operand rather than an address The EA is 301.
- In Register indirect Mode, the EA is 200, which is the content of R<sub>2</sub>.
- In Relative address mode, hte EA (Effective Address) is the 400 + 302 = 702.
- PC + Address = Register Address 

- In Index Register, the index value of the register is added to the address part.
- EA = XR + Address
- = 200 + 400 = 600

2. ![question no. 2 fig.]()


| Addressing Mode | Effective Address (EA) | Content of EA |
| ----------- | :-------: | :--------: |
| Immediate | 201 | 500 |
| Direct | 500 | 800 |
| Indirect  | 800 | 300 |
| Register Direct | &mdash; | 400 |
| Register Indirect | 400 | 700 |
| Relative | 702 | 325 |
| Index Register | 600 | 900 |
| Base Register | 900 | 150 |
| Auto increment | 400 | 700 |
| Auto decrement | 399 | 450 |



> *📝* **Author:** *Prof. Anjali*