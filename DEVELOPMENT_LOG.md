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

### Entry 4 - [Date and Time]
**What I did**: 

**Details**: 

**Challenges**: 

**Solution**: 

**Time spent**: 

---

### Entry 5 - [Date and Time]
**What I did**: 

**Details**: 

**Challenges**: 

**Solution**: 

**Time spent**: 

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
