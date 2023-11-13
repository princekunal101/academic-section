# UNIT - 2
## Aritmatic & Logic Unit
- Look Ahead Carry Adder.
- Multiplication: Signed operand
- Booths Algorithm & Array Multiplier
- Division & Logic operations.
- Floating point arithmatic operation
- Arithmatic & Logic Unit Design
- IEEE Standerd for floating Point number.

## Ripple Carry Adder
- Adding of *two -bit* binary number can be possible by using **half-adder**
- If the input sequence has a *three-bit*, the addition process can be completed by using a **Full Adder**.
- For adding the *n-bit* binary number sequence **Ripple carry Adder** is used.
- This adder includes full adder in the cascaded manner so each carry output bit is rippled to the next stage of a full adder by this reason it is named as **Ripple carry Adder**.

### Block Diagram
![Block diagram of ripple carry adder]()
 
- The carry form the right most position (LSB) has to propagate through all the bits poition.
- If *td* is the time delay for each full adder stage then for *'n-bit'* parallel adder the maximum propagation delay is *'ntd'*.

### Appliction of Ripple Adder
- These carry adder are applicable in the digital processing & microprocessors.
- In addition to *n-bit* input sequence.

## Carry Look Ahead Adders
- It is a type of adder used in digital logic. It improves speed by reducing the amount of time required to detemine carry bits.
- The carry look ahead adder claculates one or more carry bits before the sum, which reduces the wait time to calculate the result of the larger value bits.
- The following method used to improve the speed of adder.
    - For r3educing the carry propagation delay time by using faster gates with reduced delay.
    - The *'look ahead carry'* utilises logic gates to look at the lower-order bits of the augent & addes to see if a higher order carry is to be generated.
    - It uses two function &mdash;
        - carry generator (Gi)
        - Carry Propagate (Pi)
### Full adder Circuit with Pi & Gi
![full adder circit diagram]()

Truth Table
| | Input | | |Output  |
| --- | --- | :---: | :---: | ---- |
| **A** | **B** | **Cin** | **Sum** | **CarryOut** | 
| 0 | 0 | 0 | 0 | 0 *None*|
| 0 | 0 | 1 | 1 | 0 ^ |
| 0 | 1 | 0 | 1 | 0 ^ |
| 0 | 1 | 1  | 0 | 1 *Pi* |
| 1  | 0 | 0 | 1 | 0 | 
| 1 | 0 | 1 | 0 | 1 *Pi* | 
| 1 | 1 | 0 | 0 | 1 *Gi* |
| 1 | 1 | 1 | 1 | 1 ^  |

