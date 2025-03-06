#### Question 1:

Moore’s Law is an observation that the number of transistors on an integrated circuit will roughly double every 2 years, with a minimal increase to the cost in production.This projection is important as it enables long-term planning for research and development. 
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
- 
#### Question 3:

| X   | Y   | Z   | X.Y.Z | X+Y+Z | Y’  | Z’  | X+Y’+Z’ | (X+Y)Z’ |
| --- | --- | --- | ----- | ----- | --- | --- | ------- | ------- |
| 0   | 0   | 0   | 0     | 0     | 1   | 1   | 1       | 0       |
| 0   | 0   | 1   | 0     | 1     | 1   | 0   | 1       | 0       |
| 0   | 1   | 0   | 0     | 1     | 0   | 1   | 1       | 1       |
| 0   | 1   | 1   | 0     | 11    | 0   | 0   | 1       | 0       |
| 1   | 0   | 0   | 0     | 1     | 1   | 1   | 1       | 0       |
| 1   | 0   | 1   | 0     | 1     | 1   | 0   | 1       | 1       |
| 1   | 1   | 0   | 0     | 1     | 0   | 1   | 1       | 1       |
| 1   | 1   | 1   | 1     | 1     | 0   | 0   | 0       | 0       |

#### Question 4:
$$
F(A, B, C) = A\cdot B + A\cdot \overline B + B\cdot C + \overline B\cdot C
$$
Given $A\cdot B + A\cdot \overline B$  , the output of $B$ is irrelevant, hence we can express the equation as
$$
F(A, B, C) = A + B\cdot C + \overline B\cdot C
$$
Similarly for $B\cdot C + \overline B\cdot C$, output of B is irrelevant, yielding
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
#### Question 6
- 