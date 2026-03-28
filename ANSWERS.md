# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:**

[Write your answer here. Consider: What is a process? What is a thread? How do they differ in terms of memory, resources, creation overhead? Why are threads more suitable for this simulation?]

Process: A heavyweight entity with its own address space
Thread: A lightweight entity within a process
Memory 
Process :Independent memory space (code, data, heap, stack) 

Thread: Shares address space with other threads in same process 
Creation 

Process : Expensive to create and manage 

Thread: Cheap to create and manage 

communication

Process: Difficult requires Inter-process communication (IPC) required for communication 
Thread :Easy Direct communication through shared memory 


Shared State: Simulations often require multiple entities to interact with a single environment (e.g., a shared buffer or a counter).
Performance ,Scalability ,Synchronization

---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:**

[Write your answer here. Describe the specific behavior - where does the process go? When does it run again? Give an example from your actual program output showing a process that was re-queued.]

In Round-Robin (RR) Scheduling:
 • Processes are executed in turns, and each one gets a fixed Time Quantum.

If a process does not finish within its time:
 1. It is preempted (interrupted).
 2. Its state is saved (context switch).
 3. It is moved to the end of the ready queue.
 4. The next process gets the CPU.
 5. It waits for its turn again after other processes.
    
Example from my output:
```

  ? P1 executing quantum [4000ms]
  ? Quantum progress: [███████████████] 100%
  ? P1 completed quantum 4000ms │ Overall progress: [███████████░░░░░░░░░] 55%
     Remaining time: 3174ms
  ? P1 yields CPU for context switch
? P2 executing quantum [4000ms]
  ? Quantum progress: [███████████████] 100%
  ? P2 completed quantum 4000ms │ Overall progress: [██████████░░░░░░░░░░] 51%
     Remaining time: 3806ms
  ? P2 yields CPU for context switch

  ? P2 (Priority: 3) added to ready queue │ Burst time: 7806ms
┌─ Ready Queue ─────────────────────────────────────────────────────────────────
│ [P4 ? P5 ? P6 ? P7 ? P8 ? P9 ? P10 ? P11 ? P12 ? P13 ? P14 ? P1 ? P2]


[Paste a relevant snippet from your program output here showing a process being re-queued]
```
 ? P1 executing quantum [3174ms]
  ? Quantum progress: [███████████████] 100%
  ? P1 completed quantum 3174ms │ Overall progress: [████████████████████] 100%
     Remaining time: 0ms
  ? P1 finished execution!

**Explanation of example:**
[Explain what's happening in the output snippet you pasted]
Time 0 ms: Process P1 is running
Time 400 ms: Time quantum expired for P1
Process P1 is preempted and moved to the end of the ready queue
Time 400 ms: Process P2 is running
Time 800 ms: Time quantum expired for P2
Process P2 is preempted and moved to the end of the ready queue
Time 5200 ms: Process P13 is running
Time 5600 ms: Time quantum expired for P13
Process P13 is preempted and moved to the end of the ready queue
Time 5600 ms: Process P14 is running
Time 6000 ms: Time quantum expired for P14
Process P14 is preempted and moved to the end of the ready queue
Time 6000 ms: Process P1 is running again

---

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:**

[Write your answer here. For each state, explain when P1 enters that state during the simulation. Use your understanding of the code to trace through the lifecycle.]

1. **New**: [When is P1 in New state?] :
 P1 is in New state after new Threjld(process) is called in addProcessToQueue), creating the thread object before it starts.


2. **Runnable**: [When does P1 become Runnable?] : P1 becomes Runnable when currentThread start() is called in the main scheduling loop, making it ready for CPU execution.
3. **Running**: [When is P1 Running?] :P1 is Running when the OS scheduler selects it and begins executing the run() method, calculating runtime and processing its quantum.

4. **Waiting**: [When/why would P1 be Waiting?] : Pl enters Timed-Waiting when Thread.sleep(stepTime) is called during execution to simulate work progress; the main thread also waits via currentThread.join() for P1 to complete.

5. **Terminated**: [When is P1 Terminated?] :P1 is Terminated when the run() sethod returns normally after completing its quantum or finishing entirely via runToCompletion().

---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: [ Web Servers (e.g., Apache or Nginx)

**Description**: 
[Describe the real-world scenario or application]
 Handling thousands of incoming HTTP requests from different users simultaneously, where each request is assigned to a worker thread.]


**Why Round-Robin works well here**: 
It ensures fairness and responsiveness. By giving each request a small time slice, the server prevents a single heavy request (like a large file download) from blocking smaller, faster requests. Every user feels their page is loading incrementally.

### Example 2: [Multi-User Operating Systems (Time-Sharing)]

**Description**: 
[Describe the real-world scenario or application]
Environments like a Linux server where multiple users are logged in via terminals, running various scripts and commands at the same time
**Why Round-Robin works well here**: 
[Explain why Round-Robin scheduling is suitable. Consider fairness, responsiveness, predictability, etc.]
It provides predictability and the illusion of parallelism. Even if one user runs a massive code compilation, other users can still type and edit files without lag because the CPU constantly rotates through everyone's active threads

---

## Summary

**Key concepts I understood through these questions:**
1.  The efficiency of shared memory in multi-threaded environments.
2. thread States  New, Runnable, Running, Waiting, Terminated
3.  The specific transitions a thread makes from creation to completion

**Concepts I need to study more:**
1. Advanced synchronization tools like Monitors or Mutexes
2. The impact of different Time Quantum lengths on system overhead. 
