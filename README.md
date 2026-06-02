# VELA-8
VELA-8 or Versatile Experimental Lightweight Architecture - 8 Bit version. Is a Custom CPU Architecture Project. Taking inspiration from modern CPU's but using a Custom made ISA.

--------------------
## Description
The VELA Project is a project that aims to build a Lightweight CPU Architecture for General purpose and educational demonstraions. VELA uses a custom ISA which is designed in tandom with the CPU's Architecture.

--------------------
## GOALS
The goal for Phase one is going to have a fully functional Simulated CPU and ISA. At this moment the CPU Architecture should be fully simulated inside Logisim.
Goals following Phsae one include a custom Assember, being able to load these in to the Logisim Project and run code that's written by the Assembler.

Future Longterm goals include a physical project. Either build as a breadboard version or an FPGA version. Dedicated RAM intigration.

--------------------
# Current Status
This project is in it's infancy and is going through the early stages of planning and research.

--------------------
## Roadmap for Phase I
  1. Plan out the needed hardware and control logic
     1.1 Planning out what hardware is needed, such as Working Registers, Buffers, ROM, RAM (cash), Program Counter, ALU, Bus access and data flow, Flag Handling.
     1.2 Planning out the decode of the instruction to Opcode to Control signals
  2. Planning out the ISA.
     2.1 Planning out Instructions and Opcode.
     2.2 Destination, Source and control matrices
     2.3 Micro code decoding.
  3. Implimentation of Opcode and Microcode
  4. Running the first test programs

     -- This Roadmap is subject to change as the project continues --
