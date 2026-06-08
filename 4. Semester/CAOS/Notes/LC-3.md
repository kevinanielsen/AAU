**The Hardware Foundation**

- **Registers:** The LC-3 has **eight general-purpose registers (R0 through R7)**, which are used for temporary storage and are each 16 bits wide. The biggest source of errors in LC-3 programming is simply losing track of what each register currently stores, so it is highly recommended to map out each register's role before tracing a loop.
- **Memory:** It uses 16-bit addresses and 16-bit addressability, meaning it can address up to $2^{16}$ memory locations.
- **Special Registers:** It utilizes a Program Counter (PC) to keep track of the next instruction and condition code registers to track the state of recent operations.

**The Instruction Set** Every instruction in LC-3 is exactly **16 bits long** and starts with a **4-bit opcode**. There are only 15 opcodes, divided into three main categories:

- **Operate Instructions (`ADD`, `AND`, `NOT`):** Because the instruction set is so small, there is no direct instruction for subtraction or division. To subtract, you must compute the two's complement of the number (using `NOT` and then `ADD #1`) and then add it. To divide, you use an algorithm of repeated subtraction.
- **Data Movement Instructions (`LD`, `LDI`, `LDR`, `LEA`, `ST`, `STR`, `STI`):** These move data between memory and your registers.
- **Control Instructions (`BR`, `JMP`, `JSR/JSRR`, `RTI`, `TRAP`):** These instructions change the sequence of execution by altering the Program Counter (PC).

**Condition Codes & Branching** The LC-3 maintains three condition codes: **Negative (N), Zero (Z), and Positive (P)**.

- Exactly one of these is set at all times based on the result of the _last instruction that wrote a value to a register_ (which includes `ADD`, `AND`, `NOT`, `LD`, `LDR`, `LDI`, and `LEA`).
- Conditional branches (`BR`) look at these specific bits. If the specified condition is true, the program branches by adding a signed offset to the PC.

**Key Tips for Solving LC-3 Problems**

- **Translating to Machine Code:** Always separate the task into fields (opcode, register fields, and offset/immediate fields) before you start writing any binary bits.
- **Watch the Program Counter (PC):** For PC-relative instructions (like `LD` and `BR`), **never forget that the PC has already been incremented** before the offset is calculated and applied.
- **Building Symbol Tables:** A symbol table maps a label to its memory address. Remember that **a label does not point to the "next line;" it points to the exact address of the line on which the label appears**. Write down the address beside every non-empty line rather than trying to do it mentally.
- **Strings:** Whenever you process strings using `.STRINGZ`, remember that the string is stored as data in memory with a final "0" (null terminator) marking the end.