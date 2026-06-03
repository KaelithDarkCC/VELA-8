# Instruction-set
This Document contains everything you need to know about the ISA. The list of Instructions with Operants. It also includes a "Developer Comentarry" of why i chose to implement curtain ISA as they are

---
# Instruction Layout
Each instruction is 32 bits long. this mineas the memory mapping aligns to a 4 byte pattern. 

each instruction follows a standard frame and is composed of 32 bit's
| Opcode | Operand 1 | Operand 2 | Operand 3 |
|:------:|:---------:|:---------:|:---------:|
|**00**  |**00**      |**00**     |**00**     |
| 8 bits | 8 bits    | 8 bits    | 8 bits    |

Operand 2 and 3, depending on the opcode are sometimes merged to allow full addressing
Operand 1 will almost always be used to address a register

---
# Data Storing and loading instructions
instructions that Store or Load instrctions from or to Registers can have two disdinct varations

### Load from Address
| Opcode | Register | Load from Address   |
|:------:|:--------:|:-------------------:|
|        |**r0**    |**[address]**        |    
| 8 bis  |  8 bits  | 16 bits             |

### Load immidiate
| Opcode | Register | Load immidiate    | Operand 3 |
|:------:|:--------:|:-----------------:|:---------:|
|        |**r0**    |**=value**         | unused    |
| 8 bis  | 8 bits   | 8 bits            | 8 bits    |


### Branching and jumping
jump
| Opcode | Address  | Operand 3 |
|:------:|:--------:|:---------:|
|        |**[addr]**| unused    |
| 8 bis  | 16 bits  | 8 bits    |

Branching after comp
| Opcode | Address  | Operand 3 |
|:------:|:--------:|:---------:|
|        |**[addr]**| unused    |
| 8 bis  | 16 bits  | 8 bits    |

-- more special frames are work in progress --
