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
| It is concerned with the way hardware components are connected to form a computer system.| It is concerned with the way architecture is implemented in terms of structure & behaviour if a computer systm as seen by the user. |
| It helps us to understand the functionalities of a system. | It provide the details of the how exactly all the functional units in the s/m are arranged & inter connected. |
| A programmer can view s/m architecture in terms of Instruction format addressing modes. | It is the actual implementation of the system Architecture to achieve specified s/m Performance. |
| It is the first step while designing and building a computer. | An Organisation is defined & done based on the system architecture. |
| It deals with the high level design issues & specifications. | It basically deals with the low level system desifn issues. |
| Architecutre involves logic (ISA Instruction sets, addressing modes data type, cache memory organization) | Organisation involves pthysical harware components such as circuit design, adderess, signals and Peripherals. |
![Computer Architecture diagram]()
 #### Instruction Cycle 
1. Fetch 
2. Decode 
3. Execute 
4. Store

| Objectiv | CA (Computer Architecture) | CO (Computer Organiztion) |
| -------- | -------------------------- | -----------------------|
| Focus | It is connected with the design principal & connected structure of a computer system. It encompassing both hardware & s/w aspwcts to achive the desired level of s/m Performance. | It is Primarily conerned itself with the physical aspects of a computer s\m & how the hardware components are interconnected & operate togather. |
| Level of Details | It deals with the heigher level of abstraction. It focuses on the organization & behavior of the s/m in terms of s/m performance. | It deals with the low-level details computer s/m, such as design & organisation of individual hardware components circuits & logic gates. |
|Performance Evelutions | It involves evaluating & comparing difference architecural design based on performance matrics like expection time, througput & energy efficiency. | It aims to optimize the performance of the compute s\m by considering factor, like clock speed, latency, bandwidth & hardware-level. |
| Examples | It includes instruction set design pipelining, memory hierarchy, parallel processing, virtual memory & overall s/m performance. | It includes CPU design m\m system, chase hierarchies, bus protocols & Input/Output Subsystems. |
## Functional units of Digital System-
A computer consists of four main components namely.
![Funcitional Block Diagram]()
#### Input Unit
It consists of input devices that allows you to enter data into your computer. Some of the comman Input devices are Keyboard, mouse etc.
#### Central Processing unit
It  is known as the brain of computer s/m once the information is entered into the computer by the input device the CPU Processes it. It consists of two parts.
#### Aritmetic & Logic Unit (ALU)
It Performs arithmatic & logical operations, such as additon, substraction, multipicaton, division.
#### Control Unit (CU)
It conrol all the activies and operations of the computer system.
#### Output Unit
It consistd of Output devices that are used to display the results of the output of processing.
## Buses
- A bus is a collection of wires that conect several devices.
- It is used to send control signals & data between the processor & other components.
- A bus is used to communicate between the mazor components of a computer is called **system bus.** 
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

> *📝* **Author:** *Prof. Anjali*