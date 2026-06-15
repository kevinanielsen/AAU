## Q1:
1- a)
2- b)
3- b)

## Q2:
![[Pasted image 20260609092150.png]]

## Q3:
![[Pasted image 20260609092130.png]]
The K-map resulted in two groupings: (011, 010) and (000, 100, 010, 110).
The simplified Boolean function is $\mathbf{F}=z'+x'y$ 

![[Pasted image 20260609092235.png]]
## Q4:
![[Pasted image 20260609092721.png]]

## Q5:
### a)
512 bytes

### b)
Total virtual memory size: 16384 bytes
Total physical memory size: 4096 bytes

## Q6:
### a)
7 bits is enough to represent the OPCODE
6 bits is enough to represent the destination register

### b)
LDR has a 6-bit signed offset, so the range is -32 to +31. The largest address is R2 + 31 = 0x5040 + 0x001F = **0x505F**

## Q7
### a)
`0001 001 010 1 00011`
0x12A3
### b)
`0101 000 000 1 00000`
0x5020
### c)
`1001 011 100 111111`
0x973F
### d)
`0000 111 000010000`
0x0E10

## Q8
### a)

| Symbol | Adress |
| ------ | ------ |
| START  | x3501  |
| LOOP   | x3502  |
| NUMS   | x3505  |
| TEXT   | x350D  |
| COUNT  | x3512  |
| DONE   | x3513  |
### b)
It multiplies the value in address x4001 (label VALUE) with a positive value in address x4000 (label COUNT) and stores the result in address x4002 (label RESULT).

It does so by loading the values from COUNT and VALUE into registers R1 and R2, it then sets the value of R3 to 0, which will act as the accumulator. 
It then adds 0 to the value in R1 to set the condition code which will be used for the `BRnz` command, that ensures if the value in COUNT is negative or zero, it will store the value from R3 (which is 0) in the RESULT address (x4002). 

If the value in R1 was positive, it will enter into a loop that adds the accumulator (R3) with the VALUE (R2) and subtracts 1 from the counter (R1), which it will do until the counter is no longer positive. Then, it will store the accumulator (R3) in the address with label RESULT (x4002) and halt the program.

## Q9
### a)
P1:
- Response time = $16-1=15$
- Turnaround time = $21-1=20$

P2:
- Response time = $9-3=6$
- Turnaround time = $12-3=9$

P3:
- Response time = $0-0=0$
- Turnaround time = $7-0=0$

P4:
- Response time = $9-6=3$
- Turnaround time = $12-6=6$

P5:
- Response time = $12-4=8$
- Turnaround time = $16-4=12$

### b)
When the hardware starts, the pipeline is empty and the first task must pass through every segment sequentially, therefore it takes 6 clock cycles for the first task to complete, as we have 6 segments in our pipeline.

Once that task finishes, the pipeline is in a ready state and from this point one task finishes every clock cycle. Because 1 task is already finished, we are left with 250-1=249 tasks. These take 250-1 clock cycles to finish.

$6+(250-1)=255$ clock cycles

### c)
A non-pipelined system takes 24 ns to process one task. The same task can be processed in a 6-segment pipeline with a clock cycle of 5 ns. Determine the speed-up ratio of the pipeline for 100 tasks. Also determine the asymptotic maximum speed-up for the given non-pipelined execution time and pipeline clock cycle. Explain your steps. (3 points)

100 tasks would take $24 \times 100=2400$ ns to process in the non-pipelined system.

Using the same logic from the question before (b), the first task takes 6 cycles to run because the pipeline is empty. From there, it takes only 1 cycle (or 5ns) per task to process.

Therefore 100 tasks would take $(6+100-1)\times 5\text {ns} =525\text{ ns}$. 

The speed up ratio for 100 tasks would be $2400/525=\mathbf{4.57}$

The maximum speedup happens when the number of tasks increases and approaches infinity. Here, the initial time it takes to fill the pipeline becomes insignificant. 

The asymptotic maximum speed-up ratio is $24/5=\mathbf{4.8}$

## Q10
1- b)
2- b)
3- b)
4- b)
5- c)
6- a)
## Q11
### 3. Online Course Registration System
#### b)
I chose to use the `ReentrantReadWriteLock` because multiple threads need to be able two write or read, and it is important that while one thread is writing, no other threads can read or write. Multiple threads should be able to read at once, but while one or more threads are reading, none should be able to write.

The `ReentrantReadWriteLock` supplies two different locks: a `readLock` and a `writeLock`. The `readLock` blocks any other threads from writing and the `writeLock` blocks any other threads from reading or writing.