## Basic rules in C
- All C programs should start from the main function at the time of execution
- External functions can be used if its implementation file (header file) is explicitly imported using include directive
- curly brackets to define scope such as function


## Data types
- int
- float
- double
- bool
- char
- int
- struct -> define your own
```C
struct point {
	float x;
	float y;
	float z;
};

struct point p1; //declare point 1
p1.x = 0;
p1.y = 1;
p1.z = 2; //sets the properties for point
```


#### While loop
```C
//generic while loop
while (expression)
{


}
//do while loop
do 
{


} while (expression);


//for loop
for (expr1; expr2; expr3) {
	
}
```

#### Functions
```C
return_type function_name(parameters)
{
	//body
}
```
#### Pointers
```C
int x[4];
int *px = &x[0]; //using *sets px as a pointer, using & gets the direct location                    of where the variable is stored
// note that x will point to the first element x[0] as well

```

#### Malloc
```C
#include <stdio>
#include <stdlib.h>

void main(){
	char *name; //makes it a pointer
	char *command;
	name = (char*)malloc(10);
	command = (char*)malloc(128);
	printf("Enter your name:")
	gets(name);
	printf("Hello %s\n",name);
	system(command);
}

```
- malloc stands for memory allocation
	- malloc(10) is an allocation of 10 bytes of uninitalised memory
	- naturally a void* pointer 
	- using (char*) casts it to a char pointer
###### Differences between * and &
- * makes it a pointer that points to the memory address (e.g. points to the memory address of an array)
- & gets the location (the memory address) of the variable itself


## Memory allocation methods
malloc -> memory allocation
calloc -> memory allocation for arrays: takes in number of elements and element size
```C
#include <stdlib.h>
void *calloc(size_t num, size_t size);
```
realloc -> reallocates memory
```C
#include <stdlib.h>
void *realloc(void *ptr, size_t new_size);
```
