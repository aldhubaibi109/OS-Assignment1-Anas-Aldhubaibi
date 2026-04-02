# Development Log

## Instructions
Document your development process as you work on the assignment. Add entries showing:
- What you worked on
- Problems you encountered
- How you solved them
- Time spent

**Requirements**: Minimum 5 entries showing progression over time.

---

## Example Entry Format:

### Entry 1 - [April 1, 2026, 2:30 PM]
**What I did**: Forked the repository and set up my student ID

**Details**: 
- Created GitHub account with university email
- Forked the starter repository
- Changed student ID on line 92 to my actual ID (441234567)
- Compiled and ran the program successfully

**Challenges**: Had to install JDK first because javac wasn't recognized

**Solution**: Downloaded JDK 17 from Oracle website and set PATH variable

**Time spent**: 30 minutes

---

## Your Development Log:

### Entry 1 - [March 21]
**What I did**: Setup the environment and implemented Feature 1

**Details**: Forked the repository and renamed it.  
​Updated the studentID variable in SchedulerSimulation.java.  
​Added the priority field to the Process class and updated the constructor

**Challenges**: Understanding how to integrate the random priority generation within the existing process creation loop

**Solution**: Used random.nextInt(5) + 1 to generate priorities between 1 and 5 and updated the addProcessToQueue method to display it

**Time spent**: 1 hour

---

### Entry 2 - [March 24]
**What I did**: Implemented Feature 2 (Context Switch Counter)

**Details**: Added a static variable contextSwitches to the SchedulerSimulation class.  
​Modified the scheduling loop to increment the counter every time a thread starts.  
​Displayed the total count at the end of the simulation.

**Challenges**: Determining the exact location in the while loop to increment the counter accurately

**Solution**: Placed the increment right before currentThread.start() to capture every switch

**Time spent**: 45 minutes

---

### Entry 3 - [March 25]
**What I did**: Implemented Feature 3 (Waiting Time Tracking)

**Details**: Added creationTime and finishTime variables to the Process class.  
​Used System.currentTimeMillis() to capture the exact time a process enters the system and when it completes.  
​Created a getWaitingTime() method to calculate the difference.  
​Designed a formatted summary table at the end of main to display the results.

**Challenges**: Ensuring the waiting time calculation correctly subtracted the burst time from the total turnaround time.

**Solution**: Verified the logic by comparing manual calculations with the program's output table

**Time spent**: 1 hour

---

### Entry 4 - [March 25,7:30 PM]
**What I did**: Code debugging and output formatting enhancement

**Details**: Fixed a compilation error where the getWaitingTime() method was undefined in the Process class.  
​Corrected the method name from priority() to getPriority() to ensure consistency with Java naming conventions.

**Challenges**: Encountering a "symbol not found" error during compilation after adding the final summary table

**Solution**: Carefully re-examined the Process class scope and ensured all new methods and variables (creationTime, finishTime) were correctly defined inside the class braces.

**Time spent**: 1.5 hours

---

### Entry 5 - [April 2 ]
**What I did**: Recorded the demo video and explained the implementation

**Details**: Opened the project in VS Code and ran the simulation to make sure the output is clean
Recorded a demo video showing the code running with my student ID (445052785)
Explained Feature 1 (Process Priority) by showing how each process enters the ready queue with its priority displayed
Explained Feature 2 (Context Switch Counter) by pointing to the total context switches printed at the end
Explained Feature 3 (Waiting Time Tracking) by walking through the summary table showing each process, burst time, and waiting time
Explained the threading concepts Thread.start(), Thread.join(), and Thread.sleep() using my own code as an example

**Challenges**: Making the explanation clear and under 30 seconds for each concept while also showing the relevant part of the code

**Solution**: Practiced the explanation a few times before recording to make sure it was concise and covered all required points

**Time spent**: 30minutes

---

### Entry 6 - [Optional - Date and Time]
**What I did**: 

**Details**: 

**Challenges**: 

**Solution**: 

**Time spent**: 

---

## Summary

**Total time spent on assignment**: [X hours]

**Most challenging part**: 

**Most interesting learning**: 

**What I would do differently next time**: 
