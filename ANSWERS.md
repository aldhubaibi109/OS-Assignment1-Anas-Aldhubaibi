# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:**

[A process is an independent program with its own memory and resources, while a thread is a smaller unit of execution within a process that shares the same memory.
Threads are faster and cheaper to create and manage than processes.
They also allow easier communication through shared memory, unlike processes which require special mechanisms.
In this assignment, threads were used because all simulated processes need to share data structures like processQueue and processMap.
Using separate processes would make data sharing complex and less efficient, so threads were a better choice.]

---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:**

[In Round-Robin scheduling, if a process does not finish within its time quantum, it is preempted and moved to the end of the ready queue.
The CPU then selects the next process in the queue to execute.
This cycle continues until all processes complete their execution.
The scheduling method ensures fairness by giving each process equal time slices.
As a result, no single process can monopolize the CPU.]

Example from my output:
 ▶ P4 executing quantum [4000ms]
  ⚡ Quantum progress: [███████████████] 100%
  ⏸ P4 completed quantum 4000ms │ Overall progress: [████████░░░░░░░░░░░░] 43%
     Remaining time: 5128ms
  ↻ P4 yields CPU for context switch

  ➕ P4 (Priority: 3) added to ready queue │ Burst time: 9128ms
┌─ Ready Queue ─────────────────────────────────────────────────────────────────
│ [P4 → P7 → P5 → P8 → P2 → P6 → P3]
└───────────────────────────────────────────────────────────────────────────────

**Explanation of example:**
[P4 had a burst time of 9128ms while the time quantum is 4000ms.
After running for 4000ms, it completed its quantum but still had 5128ms remaining.
Since it did not finish execution, it yielded the CPU for a context switch.
Then, it was re-added to the ready queue using addProcessToQueue() with its priority.
It will execute again in a later round when it reaches the front of the queue.]

---

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:**

[Every thread in Java goes through a well-defined lifecycle. In our simulation, each process is wrapped inside a thread, so we can trace the lifecycle of P1's thread from creation to termination. The Thread.start(), Thread.join(), and Thread.sleep() methods are the key drivers of these state transitions.]

1. **New**: [P1 enters the New state when new Thread(process) is created in addProcessToQueue(), meaning the thread exists but has not started execution yet.]

2. **Runnable**: [P1 becomes Runnable immediately after currentThread.start() is called in the scheduler loop. The thread is now ready and waiting for the JVM scheduler to assign it CPU time.]

3. **Running**: [P1 enters the Running state when the JVM actually allocates CPU to it and begins executing the run() method. Inside run(), P1 simulates its work using Thread.sleep(stepTime) to represent CPU execution time.]

4. **Waiting**: [P1 enters Waiting during sleep() in run() or when the main thread calls join(), pausing until its quantum completes.]

5. **Terminated**: [P1 enters the Terminated state when its run() method finishes. If it still has remaining time, a new thread is created and the cycle restarts from New. If no time remains, P1 is fully completed and its thread is permanently terminated.]

---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: [Web Server Handling Multiple Client Requests]

**Description**: 
A web server like Apache or Nginx handles thousands of simultaneous HTTP requests, processing each without letting any single client block the others.
**Why Round-Robin works well here**: 
Round-Robin gives each client request a fair CPU share, preventing any single request from monopolizing resources.
Threads let the server handle many connections concurrently, sharing memory and connection pools efficiently.
The time quantum acts as a response-time limit, keeping the server responsive under heavy load.

### Example 2: [Multiplayer Online Game Server]

**Description**: 
[An online game server processes inputs from many players simultaneously, updating the game state in real time.
Each player’s session runs as a thread that gets CPU time to handle their actions periodically.]

**Why Round-Robin works well here**: 
[Round-Robin ensures each player’s thread gets regular CPU time, providing a fair and smooth gaming experience.
The fixed time quantum aligns with game tick intervals, maintaining consistent updates.
Using threads lets all player threads share the game state in memory efficiently, avoiding costly inter-process communication.]

---

## Summary

**Key concepts I understood through these questions:**
1. Threads are lightweight and share memory, making them ideal for this scheduler simulation.
2. Round-Robin fairly re-queues unfinished processes, preventing CPU starvation.
3. Thread states (New → Runnable → Running → Waiting → Terminated) correspond directly to the method calls in our code.

**Concepts I need to study more:**
1. Thread synchronization and how to prevent race conditions when multiple threads access shared data
2. Priority scheduling algorithms and how combining priority with Round-Robin affects average waiting time
