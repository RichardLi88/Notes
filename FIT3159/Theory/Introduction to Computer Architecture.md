#Introduction #Hardware 
## Why study this?
- Understand how performance can be affected by coding style
- Robustness can be affected by coding style
- Provides appreciation of trends and limitations of future hardware
- Proliferations of multicore machines requires knowledge of machine hardware to code effectively

## Unit overview
[[Digital Logic, combinatorial and sequential]]
[[Machine arithmetic & data representation]]
[[Micro-programming]]
[[Interrupts]]
[[Caches]]
[[Virtual memory & translation look-aside buffers]]
[[CISC vs RISC machines]]
[[Pipelined and parallel organisation]]
[[Superscalar and VLIW architecture]]
## History
#### Mechanical Computers
- Limitations: Slow, Bulky, Unreliable
### Electronic Computers
- Limited in density, speed and reliability by the switching technology in use
- Thermionic Valves and Relays
- Discrete Germanium Transistors
- Discrete Silicon Transistors and low density integrated circuits
- Computer performance tracks [[#^a20f7d|Moore's Law]]
- 

## What's in a Chip?
- data cache
- cache controller
- instruction sequencer
- instruction cache
- floating point unit
- load store unit
- integer unit


## Impact of exponential Growth on Mass Storage Systems?
- rotating "hard disks" continue to grow in surface storage density following "Kryder's Law", exponentially.
- SSD using "Flash RAM" technology, common to USB thumb drives and SDHC modules, are now becoming available at affordable prices


## Architecture vs Implementation
- the "logical architecture and organisation" of a machine is, in principle, independent of the technology we use to implement it
- can implement the same machine architecture in a range of different types of digital logic
- in practice, the "logical architecture" is usually adapted in a manner which makes it most convenient for the hardware type we intend to use
- Mostly CMOS

#### VLIW Architecture
- VLIW: Very Long Instruction Word
- CPU design that allows for parallel execution of multiple instructions by packing them into a single, long instruction word
	- this lets the compiler to determine which operations can be executed simultaneously, leading to increased performance with a relatively simpler hardware design compared to other parallel processing methods
- Uses [[#^68bfaf|Integrated Circuits]]
	



#### Integrated Circuits

^68bfaf
- much smaller compared to vacuum tubes
- more energy-efficient compared to vacuum tubes

#### Vacuum Tubes
- very large
- use a lot of power
- get hot
	- a significant portion of their operation relies on heating a filament to a high temperature
- don't last very long (less reliable)


#### Moore's Law

^a20f7d

- a prediction made by Intel co-founder Gordon E. Moore in 1965 that the number of transistors on a microchip would double approximately every two years, leading to an exponential increase in processing power and a decrease in cost per transistor
[[Act]]