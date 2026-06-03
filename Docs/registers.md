# Registers
This Document lays out all of the Available registers their names and Usages. as well a "Developer Commentary" on why i chose curtain Registers and why i chose to give them curtain uses 

## General thoughts
I'll be borrowing the naming convention from ARM CPUs to keep things simple  
I'm currently planning to have 4 Working Registers: "r-0" to "r-3"  
there will also be a "scratch register" ["rs"](#rs) which is basically arms r12  
to that are the functional Registers. "pc", "lr", "sp", "cpsr"
to help with a couple of the instructions i will also all 2 buffer registers that can hold data but are not directly used to work with. calling then b1 and b2

---
## Layout
| Register |                  Type                 |                            Note                           |
|----------|:-------------------------------------:|:---------------------------------------------------------:|
| **r0**   |            Working Register           |                      General Purpose                      |
| **r1**   |            Working Register           |                      General Purpose                      |
| **r2**   |      Working Register / Argument      |            General Purpose / Passing Arguments            |
| **r3**   | Working Register / Arguments / Return |   General Purpose / Passing Arguments / Returning Values  |
| **rs**   |            Scratch Register           |                Temporary Values / Iterators               |
| **b1**   |            Buffer Register            |               Holding Values / Not workable               |
| **b2**   |            Buffer Register            |               Holding Values / Not workable               |
| **sp**   |             Stack Pointer             |           Points to the last Stack Entry address          |
| **lr**   |             Link Register             | Hold the next address from the pc before a Jump or branch |
| **pc**   |            Program Counter            |  points to the current address in ram of the instruction  |
| **cpsr** |    Current Program Status Register    |                  N, Z, C, V Flag Register                 |

---

## why these registers?
Well looking back at my first cpu that had a much simpler layout: two working registers, one buffer, and a PC counter. (technically also and IR but that one wasn't exposed to the running program)
Working out instructions was doable but it would have involved moving a lot more data around when ever there was an even more complicated program.
That's why i added four working registers. but to keep things "more compact" i decided to give register r2 and r3 the label of argument register, and r3 specifically the register for the return value.

## "rs" 
this might be a very confusing register. As described in the [General thoughts](#general-thoughts) this is a "Scratch Register" meaning that this can be used to hold very temporary information or used to hold iterators for loops. this register won't be considered to be a "preserved" register and will needed to be explicitly saved to the stack upon entering a new function call if that function call requires an iterator.

## "b1 and b2"
I technically wouldn't need two Buffer registers but i don't see a HUGE problem integrating two and it makes programming simpler down the line. these Registers specifically aren't design to be worked with (meaning they are not made to expose their value to the ALU) they are just there to hold an information for something like a MOV operation that moves a piece of data from one address to another.

## Stack pointer, Link Register and Program Counter
These have the same function as they do in ARM CPU's
the Stack Pointer (sp) points to the last stack entry
the link register (lr) hold the "link" address which generally points back to last next address before a jump or branch operation was initiated
the Program counter (pc) hold the current active address in ram for the Instruction.
