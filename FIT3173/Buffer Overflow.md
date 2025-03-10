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
- 