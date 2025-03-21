#### Question 1:
Moore’s Law is an observation that the number of transistors on an integrated circuit will roughly double every 2 years, with a minimal increase to the cost in production.
Importance:
- This projection is important as it enables long-term planning for research and development. 
- Provides a standard to innovate continuous growth
- enables businesses to make strategic investments 
	- e.g. knows that the number of transistors will grow exponentially on an integrated circuit and will conserve money to always upgrade every few years.
#### Question 2:
Multi-core processing is a term to describe using multiple cores which can execute instructions independently and concurrently. 

Advantages:
- enables parallel processing and enhances multi-threading
- more reliable as it possess redundant processing power
- improved multitasking and hence user experience 
Disadvantages
- can be more complex, requires software configuration to take advantage of multiple cores -> making development and maintenance of software harder
- increased heat generation
- use more power overall
- diminishing returns (two cores does not equal double the processing power)
#### Question 3:

| X   | Y   | Z   | X.Y.Z | X+Y+Z | Y’  | Z’  | X+Y’+Z’ | (X+Y')Z’ |
| --- | --- | --- | ----- | ----- | --- | --- | ------- | -------- |
| 0   | 0   | 0   | 0     | 0     | 1   | 1   | 1       | 1        |
| 0   | 0   | 1   | 0     | 1     | 1   | 0   | 1       | 0        |
| 0   | 1   | 0   | 0     | 1     | 0   | 1   | 1       | 0        |
| 0   | 1   | 1   | 0     | 1     | 0   | 0   | 0       | 0        |
| 1   | 0   | 0   | 0     | 1     | 1   | 1   | 1       | 1        |
| 1   | 0   | 1   | 0     | 1     | 1   | 0   | 1       | 0        |
| 1   | 1   | 0   | 0     | 1     | 0   | 1   | 1       | 1        |
| 1   | 1   | 1   | 1     | 1     | 0   | 0   | 1       | 0        |

#### Question 4:
$$
F(A, B, C) = A\cdot B + A\cdot \overline B + B\cdot C + \overline B\cdot C
$$
Given $A\cdot B + A\cdot \overline B$  , we can factor this expression into $A(B+\overline B$) which simplifies to $A$,  hence we can express the equation as
$$
F(A, B, C) = A + B\cdot C + \overline B\cdot C
$$
Similarly for $B\cdot C + \overline B\cdot C$, we can factor this expression into $C(B+\overline B)$ which simplifies to C,  yielding
$$
F(A, B, C) = A + C
$$
#### Question 5:
Gate delay (also propagation delay) is the time it takes after changing the input for it to reach its stable output.
- race conditions can occur 
- Example ->
	- passing $A$, and $\overline A$ into an AND gate (with input $A$ as $0$ )
	- switching input $A$ from $0$ to $1$
	- causes output to spike to $1$ for a period due to delay in inverter converting $A$ to $\overline A$.
- hence as more logic gates that are added, the more gate delay there is and it needs to be accounted for to ensure when you are reading the output it is stable.
#### Question 6
AMD Ryzen AI series (Strix/Strix Halo)
New Feature: Neural Processing Units (NPUs)
- has 50 NPUs which is unique to the newer gen AI CPUs
- NPUs are designed to accelerate neural network processing
- they process large amounts of data in parallel (trillions of operations per second)
- enables faster and more efficient handling for AI tasks
- optimised for lower power consumption
- can free up CPU and GPU for other tasks boosting overall system performance
- enables for faster matrix multiplication