# Reflection Questions

## Instructions
Answer the following questions about your learning experience. Each answer should be **at least 5-7 sentences** and show your understanding.

---

## Question 1: What did you learn about multithreading?

**Your Answer:**

[Write your answer here. Discuss specific concepts like thread creation, thread states, how threads execute concurrently, what surprised you, etc.]

 I learned how to create and manage multiple threads in Java using the Runnable interface. I understood how threads can execute concurrently, sharing CPU time according to a Round-Robin scheduling algorithm. I explored the lifecycle of threads, including the New, Runnable, Running, and Terminated states, and learned how to use Thread.start(), Thread.join(), and Thread.sleep() to control thread execution. One surprising aspect was seeing how a thread yields the CPU after its time quantum expires, allowing other processes to run fairly. I also learned how to track process information such as remaining time, priority, context switches, and waiting time, which helped me understand how thread scheduling impacts system performance.

---

## Question 2: What was the most challenging part of this assignment?

**Your Answer:**

[Describe the specific challenge. Was it understanding the code? Implementing a feature? Using Git? Explain what made it difficult and how it relates to the course concepts.]

1. Generating and displaying process priorities correctly for each process.
 2. Identifying the exact point to count context switches accurately.
 3. Calculating the waiting time for each process after every execution slice.
 4. Managing GitHub integration and version control from VS Code.
 5. Keeping track of all features while ensuring the scheduler simulation ran correctly.
6.I had a problem updating my Git account in VS Code to use my university accounts.
---

## Question 3: How did you overcome the challenges you faced?

**Your Answer:**

[Describe your problem-solving approach. Did you read documentation? Ask for help? Debug systematically? What resources did you use? What strategies worked?]

I overcame these difficulties by first understanding how each feature worked and what it required, then tackling them step by step. I tested each addition separately to make sure priorities, waiting times, and context switches were calculated correctly. I used print statements and VS Code’s debugger to track thread execution and verify the scheduler’s behavior.
For Git, I faced difficulty changing the account in VS Code, so I researched multiple solutions and finally found the correct method to update it to my university account


---


## Question 4: How can you apply multithreading concepts in real-world applications?

**Your Answer:**

[Give specific examples from real applications you use (web browsers, games, mobile apps, etc.). Explain why threads are useful in those scenarios. Connect to what you learned in this assignment.]

Multithreading is widely used in real-world applications where multiple tasks need to run concurrently. For example, in web browsers, different tabs can run in separate threads to ensure that one slow website does not freeze the entire browser. In video games, multithreading allows rendering graphics, processing user input, and running AI routines simultaneously, improving responsiveness. Similarly, in mobile apps, background threads handle network requests or data processing while keeping the user interface responsive. From this assignment, I learned how to manage threads efficiently, track execution, and avoid blocking the CPU, which is directly applicable to building responsive and efficient applications. Threads help improve performance, maintain fairness, and provide a better user experience in these scenarios.


---

## Additional Reflections (Optional)

### What would you like to learn more about?

[Any topics related to threading, concurrency, or operating systems that you're curious about?]

---

### How confident do you feel about multithreading concepts now?

[Rate yourself and explain: Beginner / Intermediate / Confident]

[Explain your rating - what do you understand well? What needs more practice?]

---

### Feedback on the assignment

[Any comments about the assignment? Was it helpful? Too easy/hard? Suggestions for improvement?]
