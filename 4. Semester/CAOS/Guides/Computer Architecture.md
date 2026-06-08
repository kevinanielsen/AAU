# Response Time and Turnaround Time
To solve Shortest Job First (SJF) scheduling problems, you need to track the current time, monitor which processes are available in the "ready queue," and always select the process with the smallest CPU burst time to run next.

Unless specified as preemptive (often called Shortest Remaining Time First), standard SJF is **non-preemptive**. This means once a process starts running, it cannot be interrupted until it finishes its entire CPU burst.
## The Core Formulas
Before building the timeline, here are the formulas you will use to calculate the requested metrics:
- **Completion Time (CT):** The exact time the process finishes its execution.
- **Turnaround Time (TAT):** The total time a process spends in the system.
$$TAT = CT - Arrival\ Time$$
- **Response Time (RT):** The time elapsed from when a process arrives to when it first gets the CPU.
$$RT = First\ Start\ Time - Arrival\ Time$$
## Walkthrough Example
Here is a completely different set of processes to demonstrate the methodology.

| **Process** | **Arrival Time** | **CPU Time (Burst)** |
| ----------- | ---------------- | -------------------- |
| P1          | 0 ms             | 7 ms                 |
| P2          | 2 ms             | 4 ms                 |
| P3          | 4 ms             | 1 ms                 |
| P4          | 5 ms             | 4 ms                 |

### Step 1: Build the Execution Timeline
You must step through time, checking which processes have arrived.

1. **Time = 0:** * **Ready Queue:** P1
    - **Action:** Only P1 is available. Even though it's long, the CPU can't sit idle. P1 starts running. Since it's non-preemptive, it runs for its full 7 ms.
2. **Time = 7 (P1 completes):**
    - **Ready Queue:** P2 (arrived at 2), P3 (arrived at 4), P4 (arrived at 5)
    - **Action:** Now you check the burst times of all available processes. P2 needs 4 ms, P3 needs 1 ms, and P4 needs 4 ms.
    - The shortest is P3. P3 runs for 1 ms.
3. **Time = 8 (P3 completes):**
    - **Ready Queue:** P2 (4 ms), P4 (4 ms).
    - **Action:** Both have the same burst time. In SJF, ties are broken using First-Come, First-Served (FCFS) based on Arrival Time. P2 arrived earlier than P4. P2 runs for 4 ms.
4. **Time = 12 (P2 completes):**
    - **Ready Queue:** P4
    - **Action:** P4 is the only process left. P4 runs for 4 ms, ending at Time = 16.
### Step 2: Calculate the Metrics
Now, use the timeline to fill in your final answers based on the formulas.

- **P1:** Started at 0, Completed at 7.
    - $TAT = 7 - 0 = 7\ ms$
    - $RT = 0 - 0 = 0\ ms$
- **P2:** Started at 8, Completed at 12.
    - $TAT = 12 - 2 = 10\ ms$
    - $RT = 8 - 2 = 6\ ms$
- **P3:** Started at 7, Completed at 8.
    - $TAT = 8 - 4 = 4\ ms$
    - $RT = 7 - 4 = 3\ ms$
- **P4:** Started at 12, Completed at 16.
    - $TAT = 16 - 5 = 11\ ms$
    - $RT = 12 - 5 = 7\ ms$
# Total Clock Cycles to Process x Tasks
To solve pipeline performance problems, you need to understand how tasks flow through the hardware segments over time. The easiest way to visualize it is by breaking the process into two phases: filling the pipeline and finishing the remaining tasks.
## The Logic and Formula

Let's define our variables based on the problem:
- $k$ = Number of pipeline segments (stages)
- $n$ = Number of tasks to process
### Step 1: The First Task (Filling the Pipeline)
When the hardware starts, the pipeline is entirely empty. The first task must pass through every single segment sequentially. Therefore, it takes exactly $k$ clock cycles for the very first task to complete.
### Step 2: The Remaining Tasks (Steady State)

Once that first task finishes, the pipeline is full (in a steady state). From this point forward, assuming there are no pipeline stalls or hazards, exactly one task finishes every single clock cycle. Because you have already completed 1 task, you have $n - 1$ tasks left. These remaining tasks will require exactly $n - 1$ clock cycles to finish.
### The Formula

Adding the time for the first task and the time for the remaining tasks gives you the standard equation for ideal pipeline execution:
$$Total\ Cycles = k + (n - 1)$$
## Example
Now, apply the steps to your numbers:
- $k = 8$ segments
- $n = 300$ tasks
$$Total\ Cycles = 8 + (300 - 1)$$
$$Total\ Cycles = 8 + 299$$
$$Total\ Cycles = 307\ clock\ cycles$$
It will take **307 clock cycles** to process 300 tasks in an 8-segment pipeline.
# Speedup
To calculate pipeline speedup, you need to compare the total time it takes to execute a set of tasks _without_ a pipeline against the total time it takes _with_ a pipeline.

There are two distinct questions being asked in this type of problem: the **Speedup Ratio** for a specific number of tasks, and the **Maximum Speedup** the pipeline could theoretically achieve if it ran infinitely.
## The Core Formulas
Let's define the variables:
- $t_n$ = Time to process one task in a **non-pipelined** system.
- $t_p$ = Clock cycle time of the **pipelined** system.
- $k$ = Number of segments (stages) in the pipeline.
- $n$ = Number of tasks.
### 1. Total Time (Non-Pipelined)

Without a pipeline, tasks run sequentially. One must finish completely before the next begins.
$$Time_{non-pipelined} = n \times t_n$$
### 2. Total Time (Pipelined)

Using the logic from the previous problem, the first task takes $k$ cycles, and the remaining $n - 1$ tasks take 1 cycle each. You then multiply the total number of cycles by the time per cycle ($t_p$).
$$Time_{pipelined} = (k + n - 1) \times t_p$$
### 3. Speedup Ratio ($S$)
Speedup is simply how many times faster the pipelined system is compared to the non-pipelined system for $n$ tasks.
$$S = \frac{Time_{non-pipelined}}{Time_{pipelined}}$$
### 4. Maximum Speedup ($S_{max}$)

Maximum speedup occurs as the number of tasks ($n$) approaches infinity. The initial time it takes to fill the pipeline becomes mathematically insignificant.
$$S_{max} = \frac{t_n}{t_p}$$
_(Note: If the non-pipelined time is exactly equal to the pipeline stages multiplied by the clock cycle ($t_n = k \times t_p$), then $S_{max}$ will simply equal $k$.)_
## Walkthrough Example
Let's walk through an example using a classic 5-stage pipeline—similar to what you'd see when evaluating MIPS architectures.
### Example Problem
A non-pipelined system takes 50 ns to process a task. The same task can be processed in a 5-segment pipeline with a clock cycle of 10 ns. Determine the speedup ratio for 100 tasks, and the maximum possible speedup.
### Step 1: Calculate Non-Pipelined Time
- $n = 100$, $t_n = 50\text{ ns}$
- $Time_{non-pipelined} = 100 \times 50\text{ ns} = 5000\text{ ns}$
### Step 2: Calculate Pipelined Time
- $k = 5$, $n = 100$, $t_p = 10\text{ ns}$
- $Time_{pipelined} = (5 + 100 - 1) \times 10\text{ ns}$
- $Time_{pipelined} = 104 \times 10\text{ ns} = 1040\text{ ns}$
### Step 3: Determine Speedup Ratio
- $S = \frac{5000\text{ ns}}{1040\text{ ns}}$
- **$S \approx 4.81$** 
### Step 4: Determine Maximum Speedup
- $S_{max} = \frac{t_n}{t_p}$
- $S_{max} = \frac{50}{10}$
- **$S_{max} = 5$

_(Explanation: For 100 tasks, the pipeline is 4.81 times faster. If we ran millions of tasks, the speedup would gradually creep closer and closer to exactly 5 times faster, but it will never exceed 5.)_