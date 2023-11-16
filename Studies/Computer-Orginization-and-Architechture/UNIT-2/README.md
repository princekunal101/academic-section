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
    - For reducing the carry propagation delay time by using faster gates with reduced delay.
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


Carry look ahead depends on two things &mdash;
- Calculating, for each digit position , whether that position is going to propagate a carry if one comes in form the right.
- Combining these calulated values to be able to reduce quikly whether, for each group of digits that group is going to propagate a carry that comes in form the right.

We can write two function &mdash;
- carry generator (Gi)
- Carry propagation (Pi)

 *Pi = Ai &oplus; Bi*  ------------------- &#9312;
 
 *Gi = Ai &middot; Bi* ---------------------- &#9313;

The output sum (Si) and carry (Ci+) can be expressed as &mdash;

*Si = Pi &oplus; Ci* ----------------- &#9314;

*Ci+1 = Gi + PiCi* ----------------- &#9315;

For four *(4-bit)* binary addition, we can write the carry output as follows by using equetion &#9315;

for **i=0**, 

Ci + 1 = Gi + PiCi

C<sub>0 + 1 </sub> = G<sub>0</sub> + P<sub>0</sub>C<sub>0</sub>

C<sub>1</sub> = G<sub>0</sub> + P<sub>0</sub>C<sub>0</sub>
| C<sub>1</sub> = G<sub>0</sub> + P<sub>0</sub>C<sub>0</sub> |
| ------- |

for **i=1**, 

C<sub>2</sub> = G<sub>1</sub> + P<sub>1</sub>C<sub>1</sub>
 
 = G<sub>1</sub> + P<sub>1</sub>(G<sub>0</sub> + P<sub>0</sub>C<sub>0</sub>) *[By putting C<sub>1</sub> Value]*
 | C<sub>2</sub> = G<sub>1</sub> + P<sub>1</sub>G<sub>0</sub> + P<sub>0</sub>P<sub>1</sub>C<sub>0</sub> |
 | ----- | 


for **i=2**, 

C<sub>3</sub> = G<sub>2</sub> + P<sub>2</sub>C<sub>2</sub>
 
 = G<sub>2</sub> + P<sub>2</sub>(G<sub>1</sub> + P<sub>1</sub>G<sub>0</sub> + P<sub>1</sub>P<sub>0</sub>C<sub>0</sub>) 
 | C<sub>3</sub> = G<sub>2</sub> + P<sub>2</sub>G<sub>1</sub> + P<sub>2</sub>P<sub>1</sub>G<sub>0</sub> + P<sub>2</sub>P<sub>1</sub>P<sub>0</sub>C<sub>0</sub> |
 | ----- | 
 


for **i=3**, 

C<sub>4</sub> = G<sub>3</sub> + P<sub>3</sub>C<sub>3</sub>
 
 = G<sub>3</sub> + P<sub>3</sub>(G<sub>2</sub> + P<sub>2</sub>G<sub>1</sub> + P<sub>1</sub>G<sub>0</sub> + P<sub>1</sub>P<sub>0</sub>C<sub>0</sub>) 
 | C<sub>4</sub> = G<sub>3</sub> + P<sub>3</sub>G<sub>2</sub> + P<sub>3</sub>P<sub>2</sub>G<sub>1</sub> + P<sub>3</sub>P<sub>2</sub>P<sub>1</sub>G<sub>0</sub> P<sub>3</sub>P<sub>2</sub>P<sub>1</sub>P<sub>0</sub>C<sub>0</sub> |
 | ----- | 
 
 > **Note:** According to CLA definition C<sub>4</sub> does not have to wait for C<sub>3</sub> and C<sub>2</sub> to propagate, infact C<sub>4</sub> is propagated at the same time as C<sub>2</sub> & C<sub>3</sub> .

 ![4 bit look ahead carry adder diagram]()

 #### Advantages
 - The propagation delay is required.
 - It provides the fastest additon logic.

 #### Disadvantages
 - It is costlier as it involves more number of hardware.
 - CLA ciruit gets compicated as the number of variables increase.

### Signed Integer or Binary Number Repersentation
In computer we have only binary digits '0' & '1' and these number or symbol ued to represent +ve & -ve numbers.
It *n-bit* of signed binary number, *one-bit* is reserved to indicate +ve or -ve values and the remaining bits are magnitued.
If-MSB is '0' indicated that no is +ve.
If-Msb is '1' indicates that number is -ve.

Conversition to repersent signed binary number &mdash;
- Sign magnitued repersentaion
- 1's complement repersentation
- 2's complement repersentation

### SIgn Magnitued Repersentation
For n bit word, the right most(n-1) bits hold magnitude of the integer number
- Msb for Sign nit
    - if '0' then number is +ve
    - if '1' then number is -ve

**For Example**
- +6 in 8-bit representaion *00000110*
- -6 in 8-bit repersenation *10000110*
- +8 in 8-bit repersenation *00001000*
- -7 in 8-bit repersenation *10000111*

#### Disadvantage
- +0 *00000000*
- -0 *10000000*

### 1's Complement
1's complement of a binary number is obtained by changing each *0* to *1* & each *1* to *0*
![signbit fig]()

*e.g.*
- 1's complement 11101011
### Two's complement (2's complement)
If 1 is added to 1'scomplement of a binary no the resulting number is known as 2's compliment

*e.g.*
        
- *+6*      **00000110**
- *1's complement* **11111001**
- *2's complement* **(+1)** = **11111010**

### Fixed point Number
A number have fixed length is called as fixed point number. In selecting a number repersentaion to be used in a computer,

The following factors should be taken into account &mdash;
- The number type to be repersented
- The Range of values likely to be encounntered
- The precision of the number *(which referes the maximum accuracy of repersentation)*
- The cost of harware require to store and process the number.

#### Two formats for repersentaion &mdash;
- fixed- point
- floating- point
     
#### Fixed - Point Repersentaion
- It allow a limited range of values and also require less harware for processing.
- If radix point is fixed, the number system is refferred to as point number system.

**Type**
- Signed integer Repersentaion unsigned integer
- Unsigned integer number repersent positive number.

## Multiplication
Multiplication of two fixed point binary number in signed magnitude repersenatation is done with process of seccessive shift and add operation

*e.g.*
- **1101** *Multiplicand (M)* **&lowast;** **1011** *Multiplier (Q)* 

            1101
          X 1011
        ---------
            1101
           1101x
          0000xx
         1101xxx
        ---------
        10001111
**(10001111)<sub>2</sub>** = *143*

- In the multiplication process we are considering successive bits of the multiplier, least significant bit first.
- If the multiplier bit is 1, the multiplicand is copied down else 0's are copied down.
- The number copied down in successive lines are shifted one position to the left from the previous number.
- Finally number are added & their sum from the product.

#### Flow chart for unsigned binary number
![flow chart for unsigned binary no. diagram]()





> *📝* **Author:** *Prof. Anjali*