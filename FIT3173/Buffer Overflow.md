The contents of memory location are modified due to programming errors which enables attackers to execute arbitrary code
- using uninitialised memory: treated as garbage values
- using non-owned memory: dangling pointer
- using memory beyong the memory that was allocated: buffer overflow
- faulty heap memory management: memory leaks and freeing non-heap

#### What are buffer overflow attacks?
- a bug that affects low-level code, typically in C and C++, with significant security implications

Defined as any access of a buffer outside of its allocated bounds
- could be an over-read or an over-write
- could be during iterations "running of the end" or by direct access
- out-of-bounds access could be to addresses that flow the buffer

#### Exploits
- depend on how software programs run "under the hood"
	- compilation into binary machine code
	- how functions are called
	- memory layout/stack frame structure
Example
- a program allocates a buffer of length N for user input
- Then it copies user input data without checking input length
	- If length(input) > N, the excess input will overwrite memory addressses after the buffer
	- can be used to overwrite critical program variables
	- overwrite function return address to point to either desired existing program code or code injected by hacker

# Memory
#### How is a program stored in the memory?
- stored in segments
- has
	- text (code) segment: program constants
	- data segment: initalised global and static variables
	- BSS (block started by symbol) segment: uninitialised global and static variables
	- Heap segment: dynamic program data
	- Stack segment: function local variables, arguments, context (calling function return address/stack frame)
#### Memory allocation
- heap grows upwards, stack grows downwards
- stack pointer keeps track fo end of stack
- local variables pushed into stack memory in same order as code, compiler may choose different order based on optimisations
- ![[Pasted image 20250311100913.png]]


## Pointers
- there is a stack pointer that points to end of stack %esp
	- always points the the end of the stack
- there is another pointer (Frame base pointer) %ebp which is set to end of stack pointer location at function entry 
	- uses this as reference, as all following local variables will be relative to this location
	- frame base pointer (location) of caller is pushed on stack before executing function so it can be restored on return
- instruction pointer %eip which keeps track of which instruction it is up to 
	- always point to the current instruction
	- also gets pushed into stack before function call

## Overall process summary
- when calling function
	- args are pushed on stack (reverse order)
	- return address is pushed on stack
	- jumps to function address
- when executing function
	- pushes the location (memory address ) of old frame base pointer to stack  (SFP) saved frame pointer
	- sets frame base pointer to the cell storing the old frame base pointer
	- pushed local variables on stack
- returning function
	- resets previous stack frame (set to old frame base pointer)
	- jumps back to return address
## Example
![[Pasted image 20250320101347.png]]

![[Pasted image 20250320101331.png]]
## 64-bit system difference
- Large address space
- Different register names: RSP, RBP and RIP instead of ESP (extended stack pointed), EBP, and EIP
- Up to 6 arguments are passed via registers, only rest is pushed on stack

## Consequences when assigning to address bigger than buffer
#### Nothing 
- for performance reasons, the OS might allocate multiple bytes
- overflowing buf by a few bytes might not result in an error
#### Segmentation Fault
- if index is large, it will eventually reach a memory zone not allocated to the program
- the OS detects it and stops the program
- the overflow might also corrupt existing data
#### Custom code execution 
- the overflowing bytes have to redirect the execution flow to the customised code

#### Functions
- each function will have its own stack frame

#### Exploiting functions
- need to calculate how many bytes before reaching the return address
- then use buffer overflow to rewrite return address


## Goals
- get access to things that they are not authorised to
	- use buffer overflow to rewrite the return address/authorisation
- jump to its own code e.g. access the shellcode with root user access


## How to prevent buffer overflow
- ban unsafe functions (e.g., read, gets)
- use safer functions such as fgets, strncat from <strsafe.h> or other safe libraries
	- takes the length as explicit parameter do not rely on null termination
- always do bounds checking
- use thorough testing and code reviews


#### Insecure coding
- inputs come from users in a myriad ways:
	- text inputs
	- packets
	- environment variables
	- file input

#### System-level mitigations
- address randomization: randomize the start location of the memory, and other types of memory such as heap libraries, etc...
- stack shield: copies the return address to another place to check whether it is modified
- stackguard - modification place a guard between the return address and the buffer to detect the return address
- hardware protection: modern CPU supports NX bit, OS can mark memory region as non-executable

## More memory exploits
- format string
	- format string is argument of format function that controls how some data is printed to terminal or in buffer
	- exploit occurs when format is not defined
	- C's printf family supports formatted I/O: print data in specific formats
	- %d %x %s define type conversion of data
		- 
	
```C
int int1 = 12;
char str1[6];
strcpy(str1,"hello");
printf("%d %x %s",int1,int1,str1);
```
- damages to improper string formatting
	- compiler will warn if number of format parameter is not same as the number of variables
	- format string is optional
			- if not found, variable is printed in default format, which opens to format string injection attacks

## Integer overflow
- integer variables can overflow if one writes avalue larger (or smaller ) than the maximum value of that the integer can be


## Array indexing errors
- "Negative indexing" errors


## Read overflow
- when asking for read, will take in the length as input
	- if you only give 3 letters as input and specify that the length is 500 letters then it will respond with a message of length 500, giving you access to older messages/other information