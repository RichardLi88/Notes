- The digital logic device is the basic building block used in any modern digital computer
- When we wish to implement a logic function in hardware we must consider the hardware limitations
#### Propagation delay ($t_{pd}$)
- the time it takes for a change inthe logcal input to propagate to the output
#### Power Dissipation ($P_{g}$ )
- the amount of waste heat produced by operating a single gate at a given speed. This imposes a limit on the number of gates which we can fit into any given type of package and cooling environment
#### Logic Device Families
- characterised by these attributes:
- - common electrical signalling levels for "1" and "0"
- common power supplies (5V,-5.2V,3.3V,2.5V)
- Similar propagation delay per gate
- Similar setup time per latch
- Identical dissipation per gate
- Usually employ a similar semiconductor fabrication process
- identical "pinouts" for common physical packages
- All devices with identical logical functions are interchangeable!

## Completeness
- the set of gate types we have in a logic device family must be apable of implementing any arbitrary logic function - this is called "completeness"
- Complete sets:
	- AND, OR NOT
	- AND, NOT
	- NAND
	- NOR
- boolean algebera is used to remap a function into the require form 

## Common Logic Device Families
- TTL (transistor Transistor Logic)
	- bipolar transistors, low cost
	- modest dissipation per gate / modest speed
- CMOS (Complementary MOS)
	-  metal oxide field effet transistors
	- low dissipation per gate / modest speed
	- low cost, very high density
- ECL (Emitter coupled logic)
	- fast bipolar transistors
	- high dissipation per gate / very high speed
	- high cost of chips and design work
## Abstraction levels
1. Block level (ALU, register file etc).
2. Functional level (registers, muxes, adders)
3. Logic level (gates, latches, buffers)
4. Switch level (transistors, diodes)