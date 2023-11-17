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
        - Carry generator (Gi)
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

 *Pi = Ai &oplus; Bi*  ---------------------- &#9312;
 
 *Gi = Ai &middot; Bi* ----------------------- &#9313;

The output sum (Si) and carry (Ci+) can be expressed as &mdash;

*Si = Pi &oplus; Ci* ---------------------- &#9314;

*Ci+1 = Gi + PiCi* --------------- &#9315;

For four *(4-bit)* binary addition, we can write the carry output as follows by using equetion &#9315;

for **i=0**, 

*Ci + 1 = Gi + PiCi*

*C<sub>0 + 1 </sub> = G<sub>0</sub> + P<sub>0</sub>C<sub>0</sub>*

C<sub>1</sub> = G<sub>0</sub> + P<sub>0</sub>C<sub>0</sub>
| C<sub>1</sub> = G<sub>0</sub> + P<sub>0</sub>C<sub>0</sub> |
| ------- |

for **i=1**, 

*C<sub>2</sub> = G<sub>1</sub> + P<sub>1</sub>C<sub>1</sub>*
 
 *= G<sub>1</sub> + P<sub>1</sub>(G<sub>0</sub> + P<sub>0</sub>C<sub>0</sub>) **[By putting C<sub>1</sub> Value]***
 | C<sub>2</sub> = G<sub>1</sub> + P<sub>1</sub>G<sub>0</sub> + P<sub>0</sub>P<sub>1</sub>C<sub>0</sub> |
 | ----- | 


for **i=2**, 

*C<sub>3</sub> = G<sub>2</sub> + P<sub>2</sub>C<sub>2</sub>*
 
 *= G<sub>2</sub> + P<sub>2</sub>(G<sub>1</sub> + P<sub>1</sub>G<sub>0</sub> + P<sub>1</sub>P<sub>0</sub>C<sub>0</sub>)* 
 | C<sub>3</sub> = G<sub>2</sub> + P<sub>2</sub>G<sub>1</sub> + P<sub>2</sub>P<sub>1</sub>G<sub>0</sub> + P<sub>2</sub>P<sub>1</sub>P<sub>0</sub>C<sub>0</sub> |
 | ----- | 
 


for **i=3**, 

*C<sub>4</sub> = G<sub>3</sub> + P<sub>3</sub>C<sub>3</sub>*
 
 *= G<sub>3</sub> + P<sub>3</sub>(G<sub>2</sub> + P<sub>2</sub>G<sub>1</sub> + P<sub>1</sub>G<sub>0</sub> + P<sub>1</sub>P<sub>0</sub>C<sub>0</sub>)* 
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
If *MSB* is '**0**' indicated that no is **+ve**.
If *MSB* is '**1**' indicates that number is **-ve**.

Conversition to repersent signed binary number &mdash;
- Sign magnitued repersentaion
- 1's complement repersentation
- 2's complement repersentation

### Sign Magnitued Repersentation
For n bit word, the right most(n-1) bits hold magnitude of the integer number
- MSB for Sign bit
    - if **'0'** then number is **+ve**
    - if **'1'** then number is **-ve**

**For Example**
- **+6** in 8-bit representaion *00000110*
- **-6** in 8-bit repersenation *10000110*
- **+8** in 8-bit repersenation *00001000*
- **-7** in 8-bit repersenation *10000111*

#### Disadvantage
- **+0** *00000000*
- **-0** *10000000*

### 1's Complement
1's complement of a binary number is obtained by changing each **0** to *1* & each **1** to *0*

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
- Fixed- point
- Floating- point
     
#### Fixed - Point Repersentaion
- It allow a limited range of values and also require less harware for processing.
- If radix point is fixed, the number system is refferred to as point number system.

**Type-**
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
**(10001111)<sub>2</sub>** = *(143)<sub>10</sub>*

- In the multiplication process we are considering successive bits of the multiplier, least significant bit first.
- If the multiplier bit is 1, the multiplicand is copied down else 0's are copied down.
- The number copied down in successive lines are shifted one position to the left from the previous number.
- Finally number are added & their sum from the product.

#### Flow chart for unsigned binary number
![flow chart for unsigned binary no. diagram]()


### Questions
1. **Multiply *(1101)<sub>2</sub>* & *(1011)<sub>2</sub>***
    - Multiplican (M) = **1101** &rarr; *(13)*
    - Multiplier (Q) = **1011** &rarr; *11*

    ![Multiply Solution fig]()
2. **Multiply 5 digit number *10011* & *11001***
    - Multiplicand (M) = **10011** *(19)*
    - Multiplier (Q) = **11001** *(25)*
    - *{19x25 = 475}* 
    ![Multiply of 5 digit Solution fig]()


### Harware Structure for Add-shift 
**Multiplication**
![Flow chart diagram of multiplication]()

### Booth's Algorithm for Signed Multipication
- The Booth Algorithm is a multiplicatio algorithm that allows us to multiply the two signed binaryintegers in 2's complement representation.
- This algorithm was invented by *Andrew Donald Booth* in **1951** while doing reseaech on crystallography in *London*.
- Booth used desk calculators that were faster at shifting than adding and created the algorithm to increase their speed.
- It is very efficient algorithm and it is used to speed up the performance of the multiplication process.
### Operarional Facts
It strings of 0's in the multiplier requires number additional bit , only shift operation is required at the right- most bit.
It the strings of 1's in the multiplier from bit weight 2<sup>K</sup> to weight 2<sup>m</sup> that can be conidered as 2<sup>k+1</sup> - 2<sup>m</sup>

#### Hardware Structure of Booth Algorithm
![Hardware structure of booth algorithm diagram]()

#### Booth Algorithm Flow chart
![Booth algorithm flow chart]()

### Questions
1. **Multiply *-7* & *-3* using Booth's Algorithm**
    - M &rarr; *(-7)<sub>10</sub>* &rarr; **(1001)<sub>2</sub>**
    - -M &rarr; *(7)<sub>10</sub>* &rarr; **(0111)<sub>2</sub>**
    - Q &rarr; *(-3)<sub>10</sub>* &rarr; **(1101)<sub>2</sub>**
    - -Q &rarr; *(3)<sub>10</sub>* &rarr; **(0011)<sub>2</sub>**

    ![Multiply booth algorithm fig]()

### Advantages
- It is efficient for signed number.
- It is faster than the traditional multiplication.
- It has lower harware requirement.
- It is widly used in harware implementation.
- It can be used for both the positive and negative multiplier in 2's complement form.
### Disadvantages
- This algorithm is more complex to understand and implement than trasitional multiplication method.
- Limited applicability.
- Higher Latency.
- High power consuption.

### Questions
1. **(-7) x (3) = (-21)**
    - M = (-7) *1's* = **0111**, *2's*(+1) = **1001**
    - -M = **(0111)**  
    - Q = 3 *1's* = **0011**

    ![Multiplication solution fig]()

### Array Multiplication
Binary Multiplication is done by doing addition Partial product are calculated by multiplying the multiplicand by each bit of the multiplier and then summing the partial products.

## Questions
1. **Design *2 x 2* binary Array Multiplication.**

![Array multiplication fig]()

## Binary Division
The Division of two *fixed-point* binary number in the *signed-magnitude* repersenation is done by the cycle of successive compare shift, and subtract operations.
1. Initialized Register A, Q with '0' and register M will contain divisor. N is the counter & it is equal to the number of bits in the devidend.
2. Shift left the value of A Q *(combined)*.
3. M will be subtracted from A.
4. Check the most significant bit of A. Suppose the MSB in *A* is **1**, then it set the LSB of *Q* as **0** and the value of *A* will be restore as it was before the substracion operation.
    - If MSB of *A* is **0**, then it will set the LSB of *Q* as **1**.
5. In this step decrease n by 1.
6. Check if the value of N=0, if yes then break the loop or move back to step2.
7. In this step we have our answer with *quotient* in **Q** and the *remainder* in **A**.
### Binary Division Flow chart
![biary divistion flow chart fig.]()

### Floating Point Number Repersentaion
The Foating point number contains this binary point variable in this position and hance these number are called floating point number.
The floating point nuber is typically expressed in the scientific notaion, with a fraction *F*, and exponent *E* of a certain radix *R*, in the form of F x R<sup>E</sup>
> **Note:** Decimal number use radex of *10* **F x 10<sup>E</sup>**, Binary number use radix of *2* **F x 2<sup>E</sup>**.

The range of number that can be represented by a fixed- point number is insuffiecient. This fixed point has limitation.

Floating point number suffer from loss of precision when represented with a Fixed number of bits **(32 bit / 64 bit)**

**For Decimal number**
*975000* can be represented by **9.76 x 10<sup>5</sup>** and *.0000976* can be represented by **9.76 x 10<sup>-5</sup>**.

To repersent binary number. It is necessary to consider Binary point to accomodate very large integer and very large fraction.

A computer must be able to repersent number & operate on them in such a way that the position of Binary point variable and is automatically adjusted as computation proceeds.

In this case- The Binary point is said to float & the number is called floating point number.

The floatinf point number representation has three fields&mdash;
1. **Sign Bit:** It is the first bit of the binary representation. '1' shows negative number and '0' implies positive number.
2. **Mantissa:** It is the fixed point number.
3. **Exponent:** The position of decimal point is called **exponent.**

| GEneral Structure = &plusmn;M x B<sup>&plusmn;E</sup> |
| ------ |

*where*,
- **M** - *Significant/ Mantissa*
- **B** - *Base/ Exponent*
- **E** - Exponent

*e.g.*
1. 1110111.10010 represent in floating point format.
    - *1110111.10010* &rarr; **1.11011110010 x 2<sup>6</sup>**
        - Here, *(1.11011110010)* is **Mantissa**
        - *2<sup>6</sup>* 2 is **Base**, 6 is **Exponent**.

## IEEE Standards of Floating Point Representation or IEEE754 Standards Representation.
The Standards for representing floating point number in 32 bits & 64 bits have been developed in 1985 by the *"Institute of Electrical and Electronics Engineers"*. **(IEEE)**

- **IEEE754** number are divided into two parts base on the total number of bits.

### Single Precision
It is used for *32-bit* representaion.
![32-bit representaion fig]()

1. The Sign of number is given in the first bit followed by a representation for the exponent of the scaling factor(2).
2. Instead of sign exponent *E*, the value actually stored in the wxponent field is **[E' = E + bias]**
3. In the *32-bit* floating point system bias is 127. Hence **E' = E + 127**.
4. This represenation of exponents also called **excess-127** format.
5. The end value of *E'* Namely 0 & 255 are used to indicate the floating point values of exact zero, and infinity in single precision.
6. Thus the Range of *E'* is **0&le;E'&le;255**.
7. The actual Exponent E have the range **-126&le;E&le;127**, the last 23 bit represent the mantissa.

### Double precision Floating Point representation
![Double precision fp rpresentaion fig.]()

**Value Representaion = &plusmn;M x 2<sup>E' - 1023</sup>**

1. Value actually stored in exponent field as E' = E + 1023.
2. The Bias value is 1023 Hence , it is also called **excess-1023**.
3. The end value of *E'* namely 0 & 2047 are used to indicate the floating point exact value of zero & infinity.
4. They have renge of *E'* for normaly vlue is double precision is **0&le;E'&le;2047**.
5. For 64-bit representation the actual exponent E range is **-1022&le;E&le;1023**.

| Parameter | Formate |---->|
| ---- | ----: | ---: |
|^ | **Single** | **Double** |
| Word width | 32 | 64 |
| Exponent width(bits) | 8 | 11 |
| Exponent bias | 127 | 1023 |
| Maximum exponent | 127 | 1023 |
| Minimum exponent | -126 | -1022 |
| Number of Exponent | 254 | 2046 |
| Number of Fraction | 2<sup>23</sup> | 2<sup>54</sup> |

### Normalization
A floating point number said to be normalized if the MSB digit of the mantissa is non-zero.

*e.g.* 
1. The Decimal number 350 is normalized but 00035 is not normalized.

The number is normalized only if its Lest Most Digit is *non zero.*

*e.g.*
1. *8 bit* binary number **00011011** is not normalized because the three leading zero.

If we want to naormalized it by shifteing and discarding the three leading zzero to obtain 11011.
> **Note:** A zero can't be normalized because it doesn't contain non-zero number.

### Questions
1. **Represent the floating point in IEEE standard format for the number 1.00010100 x 2<sup>-10</sup>**

- Given number = *1.00010100 x 2<sup>-10</sup>
- Sign bit(S) = *0* **(1 bit)**
- Mantissa (M) = *00010100...0* **(23 bit)**

Actual Exponent *(E)* = **-10**

Modified Exponent *(E')* = **E + 127** = **-10 + 127**

*E'* = **+ 117**

Equivalent Binary representaion of *E'* = + 117
| E' = 1110101 |
| ---- |

8 bit are allowed to represent the xponent value but it conatin only 7 bit. so padding zero to E'

so, *E'* = **01110101**

![Solution fig]()

2. **Represent the floating pt in IEEE standard formate for the number 1.001010....0 x 2<sup>-87</sup>**

- Sign bit = *0*
- Mantissa (M) = *0001010....0* **(23 bit)**

Actual Exponent *E* = **-87**

Modified Exponent *E'* = **E + 127** = **-87 + 127** 

| E' = **40** |
| ---- |

Equivalent binary representaion of *E'* = **101000**

*E'* = **00101000**

![solution 2 fig.]()

3. **Represent 1460.125<sub>10</sub> in single & double precision format.**

- Convert given decimal number into binary number.
    - intrger part *(1460)<sub>10</sub>* = **(10110110100)<sub>2</sub>**
    - for fraction part *(0.125)* = **(0.001)<sub>2</sub>**
    - so, *(1460.125)<sub>10</sub>* = **(10110110100.001)<sub>2</sub>**
- Normalize the Value
    - **1.0110110100001 x 2<sup>10</sup>**

**Single Precision&mdash;**
- *s* = **0**
- *M* = **0110110100001**
- *E* = **10**
- *E'* = **E + 127** = **10 + 127** = **137**
- *E'* = **(137)<sub>10</sub>**
Binary Represenation of *E'* = **(10001001)<sub>2</sub>**
![solution3 single precision fig]()

**Double Precision&mdash;**
- *s* = **0**
- *M* = **0110110100001**
- *E* = **10**
- *E'* = **E + 1023** = **10 + 1023** = **1033**
- *E'* = **(1033)<sub>10</sub>**
![solution3 double precision fig]()

4. **Represent *(-307.1875)<sub>10</sub>* in Single & double precision format.**

- Convert decimal number into binary 
    - *(307)<sub>10</sub>* = **(100110011)<sub>2</sub>**
- for Fraction *(0.1875)
    - *0.1875 x 2 = 0.3750* = **0** &darr;
    - *0.3750 x 2 = 0.750* = **0** &darr;
    - *0.750 x 2 = 1.5* = **1** &darr;
    - *0.50 x 2 = 1.0* = **1** &darr;
    - *(0.1875)* = **(0.0011)<sub>2</sub>**

- *(307.1875)<sub>10</sub>* = **+(100110011.0011)<sub>2</sub>**
- *(-307.1875)<sub>10</sub>* = **- (100110011.0011)<sub>2</sub>**

**Normalize the value**
- = **-1.001100110011 x 2<sup>8</sup>**

**Single Precision&mdash;**
- *s* = **1** *for negative value*
- *M* = **00110011001**
- Actual Exponent *E* = **8**
- Modified Exponent *E'* = **E + 127** = **8 + 127** = **135**
- *E'* = **(135)<sub>10</sub>**

![solution4 signle pre fig.]()

**Double Precision&mdash;**
- *s* = **1**
- *M* = **00110011001**
- *E* = **8**
- *E'* = **E + 1023** = **8 + 1023** = **1031**
- *E'* = **(1031)<sub>10</sub>**
![solution3 double precision fig]()

5. **(21.75)10** 
- Convert decimal number into binary 
    - *(21)<sub>10</sub>* = **(10101)<sub>2</sub>**
- for Fraction *(0.75)
    - *0.75 x 2 = 1.50* = **1** &darr;
    - *0.50 x 2 = 1.00* = **1** &darr;
    - *0.0 x 2 = 0* = **0** &darr;
    - *(0.75)* = **(0.110)<sub>2</sub>**
- *(21.75)<sub>10</sub> = (10101.11)<sub>2</sub>
*Normalize* = **1.010111 x 2<sup>4</sup>

**Single Precision&mdash;**
- *s* = **0**
- *M* = **010111**
- Actual Exponent *E* = **4**
- Modified Exponent *E'* = **E + 127** = **4 + 127** = **131**
- *E'* = **(131)<sub>10</sub>**
- *E'* = **10000011**

| 0 | 100000011 | 010111....0 |
| --- | ---- | ----- |

| (-1)<sup>5</sup> x (1.fraction) x 2<sup>(Exp-127)</sup> |
| ---- |

- *s* = **0** 
- *M* = **010111**
- *E' - 127* = **E**
- *E* = **137 - 127**= **4**
| E = 4 |
| --- |

| &plusmn; 1.M x 2<sup>E</sup> |
| ------ |

= **1.010111 x 2<sup>4</sup>**

= **(10101.11)<sub>2</sub>**

= **(21.75)<sub>10</sub>**





> *📝* **Author:** *Prof. Anjali*