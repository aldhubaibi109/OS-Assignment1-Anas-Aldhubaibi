# Reflection Questions

## Instructions
Answer the following questions about your learning experience. Each answer should be **at least 5-7 sentences** and show your understanding.

---

## Question 1: What did you learn about multithreading?

**Your Answer:**

[From this assignment, I learned how to create threads in Java using the Runnable interface and the run() method.
I understood that each thread has a lifecycle: New, Runnable, Running, Waiting, and Terminated.
I also learned how methods like start(), join(), and sleep() control these states.
One interesting point was that threads share the same memory, which made data sharing easier.
I noticed that while a thread is sleeping, the main thread can still be waiting using join().
This helped me see how multiple threads can run and coordinate at the same time.

---

## Question 2: What was the most challenging part of this assignment?

**Your Answer:**

[The most challenging part was making the priority feature actually affect scheduling, not just display a value.
At first, processes still ran in FIFO order because I used a LinkedList.
Switching to a PriorityQueue with a custom Comparator caused a NullPointerException.
The issue was that the Comparator was called before the thread was added to processMap.
This made processMap.get() return null, which caused the error.
Fixing it required understanding both PriorityQueue behavior and the order of operations in my code.]

---

## Question 3: How did you overcome the challenges you faced?

**Your Answer:**

[It showed that processMap.get() was returning null inside the Comparator.
I traced addProcessToQueue() step by step to find the issue.
I realized processQueue.add() was called before processMap.put().
I fixed it by swapping the order so the map is updated first.
I also tested each feature separately to avoid multiple issues.
---

## Question 4: How can you apply multithreading concepts in real-world applications?

**Your Answer:**

[Multithreading is used in real apps like web browsers, where different tasks run at the same time.
For example, one thread handles page rendering while another handles user input.
Without it, the app would freeze while waiting for tasks to finish.
Another example is music apps, where audio plays while you browse the UI.
This is similar to the Round-Robin idea of switching between tasks quickly.

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
