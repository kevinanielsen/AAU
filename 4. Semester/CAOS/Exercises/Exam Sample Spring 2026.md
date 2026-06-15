## Q1: 
### 1. a) 
### 2. c)
### 3. b)
## Q2:
![[02 - Areas/AAU/4. Semester/CAOS/Media/Image 1.jpeg|400]]
## Q3:
![[02 - Areas/AAU/4. Semester/CAOS/Media/Image.jpeg|400]]
![[02 - Areas/AAU/4. Semester/CAOS/Media/Image 2.jpeg|400]]
## Q4:
![[02 - Areas/AAU/4. Semester/CAOS/Media/Image 3.jpeg|400]]
## Q5:
$N_{VA}=10$
$V_{pages}=16$
$P_{frames}=8$
### a)
$S_{VM}=2^{10}=1024\text{ bytes}$
$P=2^{10}/2^4=2^6=\underline{\underline{64 \text{ bytes}}}$
### b)
$S_{VM}=1024 \text{ bytes} = 1KB$
$S_{PM}=8 \times 64=512 \text{ bytes}$

Total virtual memory size = 1024 bytes
Total physical memory size = 512 bytes
## Q6:
### a)
8 bits for the OPCODE is enough for 256 different opcodes so 215 is within the limit.
7 bits for a destination register would be enough for 128 different registers so 110 is within the limits.
### b)
LDR has a 6-bit signed offset, so the range is −32 to +31. The largest address is R3 + 31 = 0x4011 + 0x001F = **0x4030**.
## Q7:
### a)

| Symbol | Address |
| ------ | ------- |
| DIVIDE | x4001   |
| HELP1  | x4003   |
| HERE   | x4012   |
### b)
The program calculates the square of a value stored at memory address `x4000` and stores the result at memory address `x4001`.

It does this by first loading the value using `LDI`. If the value is negative, it converts it to its absolute value using two's complement (`NOT` and `ADD #1`). It then uses `R1` as a loop counter and `R2` as an accumulator. It repeatedly adds the absolute value to `R2` exactly `R1` times. Finally, it uses `STI` to store the squared result.
## Q8:
### a)
T=0, Ready Queue = P4
- P4 runs for 3 ms
T=3, Ready Queue = P3, P1
- P1 runs for 6 ms
T=9, Ready queue = P3, P2, P5
- P2 runs for 2ms
T=11, Ready queue = P3, P5
- P5 runs for 4ms
T=15, Ready queue = P3
- P3 runs for 8ms

P1: Started 3 ended 9
$TAT = 9 - 2 = 7$
$RT=3-2=1$
P2: Started 9 ended 11
$TAT=11-5=6$
$RT=9-5=4$
P3: Started 15 ended 23
$TAT=23-1=22$
$RT=15-1=14$
P4: Started 0 ended 3
$TAT=3-0=3$
$RT=0-0=0$
P5: Started 11 ended 15
$TAT=15-4=11$
$RT=11-4=7$
### b)
$k=8$
$n=300$
$Total\ Cycles = 8+(300-1)=307$
### c)
$t_n=20ns$
$t_p=4ns$
$k=8$
$n=200$

Without a pipeline, the tasks run sequentially, one must finish completely before the next begins.
Total time non-pipelined $= 200\times 20ns=4000ns$ 

In a pipelined system, the first task takes 8 cycles and the remaining $n-1$ tasks take 1 cycle each.
Total time pipelined $= (8+200-1)\times 4ns=828ns$

The speed up ratio is now $\dfrac{4000ns}{828ns}=4.83$
The maximum speedup occurs when the number of tasks approaches infinity as the initial time it takes to fill the pipeline becomes mathematically insignificant.
Max speedup $= \dfrac{20ns}{4ns}=5$ 
# Q10
## 3
### b)
**Chosen Lock:** `java.util.concurrent.locks.ReentrantReadWriteLock`

**How it works:** A `ReentrantReadWriteLock` maintains a pair of associated locks: a `ReadLock` and a `WriteLock`.

- The **ReadLock** is a shared lock. It can be acquired simultaneously by multiple threads (students), as long as the write lock is not currently held by any thread.
    
- The **WriteLock** is an exclusive lock. Only one thread (a teacher) can acquire it at a time. Furthermore, if a thread holds the write lock, no other thread can acquire either the read lock or the write lock until it is released.
    

**Why it was chosen:** The problem instructions explicitly mandate a classic "Readers-Writers" paradigm:

1. _"Students can read the exam questions concurrently."_ 2. _"Teachers can write... but only one teacher can do so at a time to prevent inconsistency."_
    

If we had used a standard `ReentrantLock` or a `synchronized` block, it would have treated reading and writing equally, locking out other reading students while one student was merely viewing the questions. The `ReentrantReadWriteLock` perfectly fulfills the requirements by optimizing performance (allowing concurrent reads) while preserving thread safety and data consistency during writes (exclusive locking).