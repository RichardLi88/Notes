## Question 1
#### a)
-   A larger data path will allow for more precise calculations and better performance
	-  more bits for mantissa results in more precise numbers (mainly floating point)
	- better performance as wider datapath will require less cycles to process larger arithmetic calculations 
	- real-world application: weather forecasting, or any scientific computing/simulation
		- larger datapath enables higher-precision which is a must to correctly simulate/model the real-world event and higher throughput enabling more data processing
#### b)
- on different systems, 
	- char and short usually same across systems
	- int increases from 2->4 bytes (for 32/64-bit) , and long increases from 4->8 bytes (for 64-bit) as the datapath grows.
- variation in data storage sizes can result in memory misalignment -> results in worse data access speeds/performance
	- modern 64-bit systems will pad structures to ensure proper alignment
#### c)
- challenges:
	- requires adjusting the exponent to match before arithmetic is carried out
	- loss of precision due to rounding when converting exponent
- IEEE754
	- consistent representation (provides a standard)
	- has ways to represent special values (infinity, NaN etc.) 
#### d)
- Little Endian: least significant bit/byte is stored first (lowest memory address)
- Big Endian: most signifiant bit/byte is stored first
	- choice of endianness can lead to misinterpretation of data 
- example: 2005 Apple transitioning from Big Endian to Little Endian (intel transition) for their Mac 
	- issues with software compability due to binary misinterpretation since older mac applications at the time assumed big endian  byte order

## Question 2
- In 2017 Apples A9 chip throttling occurred when Apple introduced an update to dynamically throttle older iphones that have degraded batteries to prevent unexpected shutdowns and manage battery.
- the controversy with the A9 chip was due to apple having two manufacturers - TSMC and Samsung - manufacture A9 chip leading to two variations of chips and the firmware did not fully take into consideration the differences of the hardware
	- Samsung's chip had higher power consumption and a lower battery life -> leading to different throttling behaviours and hence had its performance throttled earlier and exhibited greater throttling
	- caused due to:
		- memory and data management inconsistencies
		- potential big endian and little endian mismatches in the software optmizations for the chip variants
	- lessons:
		- importance of consistent hardware design
		- when optimising software -> must take into consideration the hardware variations
## Question 3
![[Pasted image 20250316230002.png]]
#### b)
Simplified boolean expression,
$$
Z = f(A,B) = A' + B'
$$
#### c)
- static hazard is when input changes and output causes the output to momentarily change before stablising at the back to the correct output
	- occurs due to propagation delays when multiple inputs are required for one output and some of the inputs arrive later than others 
- dynamic hazard is when the output changes multiple times when it should only change from 
  0 ->1 or 1->0 only once.
	- occur when there are race conditions
		- due to the timing of the inputs and propagation delays

## Question 4
![[Pasted image 20250316231229.png]]
*From week 3 Lecture slides*
- shifters work through accepting data of fixed length and shifts the data either left or right by x number of bits
- above shifter is a one-bit shifter
- works as each bit is connected to two AND gates, which require both bits to be one to output 1. Hence the shifter can control shifting left or right by toggling either the left or right lines as 1, which allows the bits of the input D to pass through to output S.
	- E.g. looking at D1, connected to the second and third AND gate from top, if shifting right then the output of D1 will output at S0, if shifting left then the output of D1 will be at S2.
	- Hence in above graph where its left = 1, D\[0:3] = S\[1:4] (note D4 input does not matter as will not be used)

#### b)
![[Pasted image 20250317001745.png]]

*from elprocus \[1]
- the carry look ahead adder works by "looking ahead"  and calculate the carry bits in parallel rather the calculations being sequential
-  relies on two main concepts
	- generate:
		- indicates if it will generate a carry (out) independent of it is going to have a carry in
	- propagate:
		- indicates if a bit is carried out if the previous bit adder will carry in a bit
- by calculating the generate and propagate values for each bit adder, then the carries can be calculated for all bit adders

CLA vs Ripple-carry adder
- CLA is faster as the carries are calculated in parallel for every bit
- Ripple carry adder performs the carry calculations sequentially resulting in more delay

## Question 5
#### a)

For the NAND gate implementation of SR latch (NOR gate Q and $\overline Q$ are flipped),
- When S = 1 and R = 0, then the output Q = 1 and $\overline {Q}$ = 0
- When S = 0 and R = 1, then the output Q = 0 and $\overline Q$ = 1
- Q stays same when S = 0 and R = 0
![[Pasted image 20250316235027.png]]
*from learnabout-electronics \[2]
- from a to b,
	- Set operation is performed which turns Q = 1 and $\overline Q$ = 0
	- 
	- When S = 0 again Q keeps its state
- from b to c
	- When R = 1, then regardless of the previous state $\overline Q$ becomes 1 and Q becomes 0
- When both S and R are 1 then it is an invalid state and can result in unpredictable behaviour
#### b)
![[Pasted image 20250317000022.png]]
*Clocked D-Latch from Week 3 Lecture Slides*
- Similar to SR latch except only requires one input and a clock (or enable).
- Unlike SR latch has no invalid state since only one input
- In above diagram
	- If D = 1 and clock ticks (becomes 1 momentarily), a 1 will pass through the top AND gate causing the top NOR gate to output 0, since the bottom AND gate will output 0 ($\overline D$ = 0 if D is 1), the bottom NOR gate will have 0 and 0 as its input and hence Q = 1. This value will be stored in the latch and the input D will not be able to change this value until clock ticks again
#### c)
- they are the fundamental buiilding blocks for memory storage and state holding, and often used for sequential circuits
	- used to build registers and flip-flops
	- used as buffers
	- Finite State Machines














<div style="page-break-after: always;"></div>

## Citations

1. Agarwal, T. (2020, May 22). _Carry Look-ahead Adder - Circuit Diagram, Applications & Advantages_. ElProCus - Electronic Projects for Engineering Students. https://www.elprocus.com/carry-look-ahead-adder/

2. SR flip-flops_. (n.d.). https://learnabout-electronics.org/Digital/dig52.php

3.  Week 3 Lecture Slides
	