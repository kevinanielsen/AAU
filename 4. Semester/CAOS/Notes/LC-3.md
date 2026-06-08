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

# Common Commands
### Arithmetic & Logic
_(Note: These instructions always update the N, Z, P condition codes)_

- **`ADD DR, SR1, SR2`** / **`ADD DR, SR1, imm5`**
    - **Description:** Adds two registers OR a register and a small hardcoded number (-16 to +15).

- **`AND DR, SR1, SR2`** / **`AND DR, SR1, imm5`**
    - **Description:** Bitwise AND. Essential for isolating bits (masking) or clearing a register entirely (`AND R1, R1, #0`).

- **`NOT DR, SR`**
    - **Description:** Bitwise NOT. Flips all 1s to 0s and 0s to 1s. The first step in creating a negative number.

### Data Movement
_(Note: `LD`, `LDI`, and `LDR` update condition codes. `ST`, `STI`, `STR`, and `LEA` do not)._

- **`LD DR, label`**
    - **Description:** Load. Fetches data from a nearby memory address and places it in a register.

- **`LDR DR, BaseR, offset6`**
    - **Description:** Load Base+Offset. Fetches data using an address calculated from a base register plus a small offset.

- **`LDI DR, label`**
    - **Description:** Load Indirect. Looks at a memory address to find a _second_ memory address, then loads the data from that second location.

- **`LEA DR, label`**
    - **Description:** Load Effective Address. Calculates a memory address and stores the **address itself** into a register (does not fetch the data).

- **`ST SR, label`**
    - **Description:** Store. Saves a register's current value into a nearby memory location.

- **`STR SR, BaseR, offset6`**
    - **Description:** Store Base+Offset. Saves a register's value to an address calculated using a base register plus an offset.

- **`STI SR, label`**
    - **Description:** Store Indirect. Looks up a pointer in memory, and saves the register's value to that destination address.

### Control Flow
- **`BR[nzp] label`**
    - **Description:** Conditional Branch. Jumps to a specific label _only if_ the chosen condition codes (`n`, `z`, or `p`) match the result of the last operation.

- **`JMP BaseR`**
    - **Description:** Unconditional Jump. Forces the Program Counter to jump to the exact address currently held in a specific register.

- **`JSR label`** / **`JSRR BaseR`**
    - **Description:** Jump to Subroutine. Jumps to a block of code (like a function) and automatically saves the return address in **R7**.

- **`RET`**
    - **Description:** Return. Forces the Program Counter to the address stored in **R7**, effectively exiting a subroutine.

- **`TRAP xVector`** (Includes `HALT`, `IN`, `OUT`, `PUTS`)
    - **Description:** System Call. Pauses the user program to allow the Operating System to handle a specific routine, usually related to Input/Output.