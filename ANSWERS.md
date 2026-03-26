# Assignment Answers - Remas Alrasheed

### 1. How does the priority field affect the scheduling in your implementation?
In this implementation, the priority field is generated randomly (1-5) for each process. While it is displayed in the logs and the final table to provide more context about each process, the core scheduling logic still follows the Round Robin (FIFO) approach as per the assignment requirements.

### 2. What is a "Context Switch" and how did you track it?
A context switch occurs when the CPU stops executing one process and moves to another. I tracked this by:
- Creating a global static counter contextSwitches.
- Incrementing this counter every time a process is pulled from the processQueue using processQueue.poll().
- Displaying the total count at the very end of the simulation.

### 3. How was the Waiting Time calculated?
The waiting time for each process was calculated by:
- Recording the startTime when a process enters the ready queue or yields the CPU.
- Subtracting the startTime from the current system time whenever the process starts its execution quantum.
- Accumulating these differences in the waitingTime variable for each process object.
