
| Command                                                            | What it does                                                   |
| ------------------------------------------------------------------ | -------------------------------------------------------------- |
| sudo sysctl -w kernel.randomize_va_space=0                         | - turns off address randomization<br>- to turn back on set =2  |
| gcc -m32 -fno-stack-protector -z execstack -g -o example example.c | - sets as 32-bit machine      <br/>- removes stack protector   |
| x/80xw buffer                                                      | examines memory at the address of buffer and inspects 80 words |

