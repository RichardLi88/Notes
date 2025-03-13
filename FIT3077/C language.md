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

```