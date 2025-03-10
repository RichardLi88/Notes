#Hardware
## Why Study Data Representation?
- all data must be represented inside a computer in some form, so data representation is an unavoidable problem
- Designing computer hardware
	- data representation is a critical constraint for designing registers, busses, arithmetic or execution units, and any other components through which the data must pass
- Developing software
	- making software portable across different machines is a common expectation and without understanding representation this is difficult to do

## Memory Addressing
- Every unit in memory has a unique address


## Data representations
- different data types require different amounts of storage
- how much storage is specific to the architecture of the machine
- a machine always has a "native word size" for a basic integer operand

| data type | storage                |
| --------- | ---------------------- |
| char      | usually 1 byte (8bits) |
| int       | 1,2,4 or 8 bytes       |
| short     | half of an int         |
| long      | twice an int           |
| float     |                        |
| double    |                        |

In 32 bit data machine
- first 23 bits, mantissa (fraction)
- next 8 bits exponent
- final bit is sign

In 64 bit double precision floating point
- first 52 bits fraction (mantissa)
- 11 bits exponent
- 1 bit sign
#### Big Endian vs Little endian
- biggest value of left side for big endian
- biggest value on right side for little endian

#### Impact of byte ordering
- binary data files produced by little endian and big endian CPUs are not interchangeable
- therefore software which must manipulate such files must be apable of reordering the bytes in words or longwords


## Floating point data representation
- Integer representations map directly into the bitwise inputs and outputs of functional blocks such as adders and registers. Therefore manipulating integers is very simple, since there is a direct correspondence between the integer value and the bits in the operand.

IEEE Floating Point Data types (32-bit)
- 0-1222 bits mantissa (Fraction)
- 23-30 bits exponent
- 31 sign

IEEE 64-bit double precision floating point
- 0-51 bits mantissa (Fraction)
- 52-62 bits exponent
- 63 sign

Value = Sign bit * (Mantissa * 2 & Exponent)

To write decimals, have the exponent set to 0, then at the end of the mantissa use 1's to represent 2$^{-1}$ , 2$^{-2}$  etc.

#### The Exponent
- the length of the exponent determines the range (size) of a floating point number
- If the exponent > 0, the the number > 1 (-1).
- If the exponent < 0, then the number < 1/2 (-1/2)
- If the exponent == 0, then the number is between 1/2 and 1 ( -1/2 and -1)
- The exponent is usually in two's complement form

## Arithmetic on floating point numbers

## Addition
 - denormalise mantissas (make exponents the same)
 - add 
 - normalise

#### Multiplication
- multiply mantissas
- add expoenents
- normalise

#### Can be implemented
- using software or microcode with conventional arithmetic units
- special purpose hardware

#### Floating Point
- there are an infinite number of real numbers between any two real numbers 
- when we represent real numbers in floating point form, we have a finite number of floating point values between any two numbers we can exactly represent as floating point numbers
- real numbers which cannot be exactly represented can only be approximated with some small error, given by the size of the mantissa

## Combinatorial Logic Optimisation / Logic Circuits

#### Why Simplification and Optimisation of Logic
- Hardware "cost" is typically proportional to circuit complexity - twice as many logic expresssions means twice as many gates:
	- twice as much real estate ona chip
	- twice as much electrical power consumption
	- twice as much heat dissipation
	- twice as much cooling capacity

#### Boolean Function Optimisation
- minimizing the gate input cost of a Boolean equation reduces circuit cost
- we choose gate input cost
- boolean algebra and graphical techniquess are tools to minimize cost criteria values
- Introduce a graphical technique using Karnaugh maps


## Combinatorial Logic
## functions and functional blocks
- don't have to worry about the internals
- Today -> usually very-large-scale-integrated circuit or programmable logic device (PLD)


## Rudimentary logic functions
- wide line is used to represent a bus which is a vector signal
- sets of bits can be split into individual bits 
- the sets of bits need not be continuous 
	- e.g. for F\[3:0] can choose F\[3],F\[1:0] as an output
- enabling permits an input signal t choose which bits to pass through to an output
- disabling blocks an input signal from passing through to an output, replacing it with a fixed value

#### Decoding using decoders
- conversion of an n-bitr input code to an m-bit output code with $n <= m <= 2^{n}$
- circuits that perform decoding are called decoders
- can be used to select



- encoding using encoders
#### selecting using multiplexers
- logic circuits that are used to select are called multiplixers
![[Pasted image 20250311072649.png]]

#### Hazards in Digital Logic
- real logic circuits, whether made up from logic chips or embedded inside complex chips, cannot switch instantly 
	- all are characterised by a real progration delay
- The result of real propagation delays is that some logic circuits will exhibit unwanted output behaviours, which are termed "hazards"
- Hazards sometimes produce no impact on the behaviour of the circuit, but in some circuits can result in problems and incorrect logic behaviour
- Robust design of logic requires that hazards be identified and the logic circuit changed to remove the hazard, or remove the conditions (inputs, timing) that cause the hazard to arise