# 📝 MY_WORK: Student Information, Development Log, Reflection & Answers

> This is the **only file** your instructor reads to grade Parts 3 and 4 (documentation and video). Everything you write here must be **in your own words**.

---

## 🛑 STOP: Read This Before You Do Anything Else

> ### 1️⃣ Read the whole `README.md` first
> The `README.md` in this repository contains the full instructions: how this assignment continues Assignment 1, the Chapter 5 recap, class descriptions, feature specifications, question prompts and the video script. **If you skip it, you will lose marks.**
>
> ### 2️⃣ Understand the full code before answering any question
> Open `SchedulerSimulationSync.java` and read it **from top to bottom**. You must be able to explain what `SharedStats`, `ReadyQueue`, `CpuWorker`, `RaceWindow.pause()`, `ReentrantLock` and `Semaphore` do **before** you write a single answer in Parts B and C. **Run the original starter first** (it is intentionally broken) and **save its output**: you need it for Question 1 of Part C.
>
> ### 3️⃣ Use only the code of this repository
> Work **only** on `SchedulerSimulationSync.java` from this repository. Do **not** copy or paste code from your previous assignments.
>
> ### 4️⃣ Commit many times, not once
> A single commit, or all commits made in the last hour, costs you **-0.5 mark**. See the [Commit Rules](#-commit-rules-mandatory) below.

**How to use this file:**
1. Fill in your **Student Information** (below) right now.
2. Follow the steps in the **Work Roadmap** in order.
3. Update the **Development Log** *every time* you work on the assignment, not at the end.
4. Do not delete any section header. Replace the `[...]` placeholders with your own text.

---

## 👤 Student Information

> ⚠️ **WARNING:** Fill this in first. Your name and ID must match the student ID you set in `SchedulerSimulationSync.java` (line 304) and the one you say in your video.

| Field | Your Answer |
|-------|-------------|
| **Full Name** | [Khadija Abdulhai Mohammed] |
| **Student ID** | [446052668] |
| **University Email** | [446052668]@std.psau.edu.sa |
| **GitHub Username** | [Khadija-Mohammed-668] |
| **Repository Link** | [https://github.com/Khadija-Mohammed-668/OS-Assignment3-Khadija-MohammedS] |
 
---

## 🎥 Video Link

**Video Link**: [(https://youtu.be/KCJFHD_l-gc?si=OEpYR_U_Qeij_QjO)]

> ⚠️ **WARNING:** The video must be **publicly accessible** ("Anyone with the link can view") on **Google Drive**, **YouTube (Unlisted or Public)** or any other cloud file-sharing system. A private, restricted or broken link counts as a **missing video (-1 mark)**.
>
> 💡 **TIP:** Open the link in a **private/incognito window** before you submit. If it asks you to log in or request access, it is not public.
>
> 📌 **NOTE:** The link goes in **this file only** (`MY_WORK.md`), **not** in `README.md`. Name your video file `StudentID_Assignment3_Demo.mp4`. It must last **2 to 3 minutes**.

---

## 🗺️ Work Roadmap (follow in this order)

| Step | What to do | Where | Marks |
|:----:|------------|-------|:-----:|
| 0 | Read `README.md`, read the full code, **run the original starter and save its output** (it fails on purpose) | Your IDE | – |
| 1 | Fork, rename, keep the repo **PUBLIC**, set your student ID (line 304), **commit** | GitHub + code | Part 1 (1) |
| 2 | Feature 1: Mutex lock on the ready queue, **commit** | Code | Part 2 (0.25) |
| 3 | Feature 2: Mutex lock(s) on the shared statistics, **commit** | Code | Part 2 (0.25) |
| 4 | Feature 3: Counting semaphore instead of busy waiting, **commit** | Code | Part 2 (0.5) |
| 5 | Development Log (5+ entries, different dates) | This file, Part A | Part 3 (0.5) |
| 6 | Reflection (4 questions) | This file, Part B | Part 3 (0.5) |
| 7 | Technical Answers (4 questions) | This file, Part C | Part 3 (0.5) |
| 8 | Record the video, upload it, paste the link above | Video + this file | Part 4 (1.5) |
| 9 | Final check, then submit the repo link on Blackboard | Blackboard | – |

> 💡 **TIP:** Tick each step off as you go. Do not leave the log, the reflection or the video for the last day.

---

## 🔁 Commit Rules (MANDATORY)

> ### ⚠️ MANY COMMITS ARE REQUIRED. A single bulk commit is penalized (-0.5 mark).

**Minimum: 4 meaningful commits. Aim for 7 or more.**

| # | Commit | Example message |
|:-:|--------|-----------------|
| 1 | Student ID set | `Set my student ID: 441234567` |
| 2 | Feature 1: Ready queue lock | `Feature 1: Protected the ready queue with a ReentrantLock` |
| 3 | Feature 2: Statistics locks | `Feature 2: Added locks to the shared statistics counters` |
| 4 | Feature 3: Semaphore | `Feature 3: Replaced busy waiting with a counting semaphore` |
| 5 | Development log entries | `Docs: Added development log entries 1-3` |
| 6 | Reflection and answers | `Docs: Completed reflection and technical answers` |
| 7 | Video link | `Docs: Added demo video link` |

**Rules:**
- ✅ **One commit per feature.** Do not put all three features in one commit.
- ✅ **Commit after each work session**, and after each part of this file.
- ✅ **Spread your commits over different dates.** Not all in one day.
- ❌ **Do not make all commits in the last hour** before the deadline (November 14, 2026).
- ❌ **No vague messages** like `done`, `update` or `final version`.

> 💡 **TIP:** Your commit history is checked and you **show it in your video** (at least 4 commits visible). Your development log dates should match your commit dates.
>
> 💡 **TIP:** **Use VS Code** (see *Recommended Development Environment* in `README.md` for the full setup). Sign in to GitHub in VS Code, then commit from the Source Control panel (Ctrl+Shift+G) → stage → write a message → Commit → Sync/Push. You can edit and commit this file the same way. **Pushing** matters: commits that are not pushed to GitHub are invisible to the instructor.

---

# Part A: Development Log (0.5 mark)

> ⚠️ **WARNING:** Minimum **5 entries**, spread over **different dates**. Five entries written on the same day, or written all at once at the end, will lose marks and look like a copy. Entry dates should be **between the start of the assignment and the deadline (November 14, 2026)**.
>
> 💡 **TIP:** Write an entry at the **end of each work session**, while you still remember what happened. It takes 5 minutes.
>
> 💡 **TIP:** Be specific. "Worked on the code" is a weak entry. "Added a `ReentrantLock queueLock` to `ReadyQueue` and wrapped the body of `poll()` in `lock()` / `try` / `finally { unlock() }`" is a strong one.
>
> 📌 **NOTE:** Each entry needs: date and time, what you did, details, challenges, solution, and time spent. Real challenges are fine (and expected). Do not invent fake ones.

## Example Entry (do not copy it, write your own)

### Entry 1 - [November 2, 2026, 4:30 PM]
**What I did**: Forked the repository, set my student ID, and ran the original starter

**Details**:
- Forked the starter repository and renamed it
- Changed student ID on line 304 to my actual ID (441234567)
- Ran the original program: 4 CPUs started, three of them picked `P1`, then `IllegalThreadStateException` and the watchdog stopped the program
- Saved the output in a text file for Question 1
- Committed and pushed: `Set my student ID: 441234567`

**Challenges**: I did not understand why the same process was picked by three CPUs

**Solution**: Read `ReadyQueue.poll()` again and found the `RaceWindow.pause()` between reading the head and removing it

**Time spent**: 45 minutes

---

## Your Development Log

### Entry 1 - [November 3, 2026, 5:00 PM ]
**What I did**: Forked starter repository, changed line304 to my student ID and commited it

**Details**:-Logged into my github account
-Forked starter repository
-Uploaded it into my VS code 
-Changed line 304 to my student ID 
-Ran the program
-Commited change

**Challenges**:No challenges, I now know how to fork and commit changes

**Solution**:--

**Time spent**:30 minutes

---

### Entry 2 - [November 13, 2026 10:50 PM]
**What I did**: Added feature 1 and filled my info in MYWORK file

**Details**:- Added my name, ID, uni email, repository link and github account into MYWORK file
-Added feature 1: Protiction to readyQueue
-Ran the code
-Commited change

**Challenges**:Code didn't run emmediatly after feature implementation 

**Solution**: Reran the code a few times until it worked

**Time spent**:3 hours

---

### Entry 3 - [November 14&15, 2026, 11:30 PM]
**What I did**: Added Feature 2

**Details**:-Added locks for shared counters for feature 2 
-Ran the code
-Commited change

**Challenges**:Code didn't run emmediatly due to the compiler not loading 

**Solution**: Reloaded the compiler and reran the code

**Time spent**: 1.5 hours

---

### Entry 4 - [November 15,2026 , 7:30 PM]
**What I did**:Added Feature 3

**Details**:-Started replacing busy waiting blocks with counting semaphores

**Challenges**: I did't know where exactly change scope was 

**Solution**: asked my friends and my AI assistant

**Time spent**:1 hour

---

### Entry 5 - [November 16, 2026, 4:30 PM]
**What I did**: Answered MYWORK file questions

**Details**:- Answered Technical questions
-Answered Reflection questions
-Checked my work 

**Challenges**: Answers require long writing

**Solution**: patience

**Time spent**: 4 hours

---

### Entry 6 - [November 17, 2026, 4:00 PM]
**What I did**: Edited and uploaded video

**Details**:- Captured the code and the execution 
-Edited and voice commented the video
-Uploeade the video  

**Challenges**:No challenges

**Solution**:--

**Time spent**:2 hours

---

## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.

**Total time spent on assignment**: [11 hours]

**Most challenging part**: Dealing with my development environment

**Most interesting learning**: How everything I learned in this course and other courses integrate my knowledge.

**What I would do differently next time**: focus and read thoroughly

---

# Part B: Reflection (0.5 mark)

> 🛑 **STOP:** Do **not** start this part until you have read the `README.md`, read the **entire** `SchedulerSimulationSync.java`, run it, and finished the three features.
>
> ⚠️ **WARNING:** Each answer must be **5 to 7 sentences**, in **your own words**. Copied or AI-generated answers without understanding get **0 marks for the whole assignment**. You may be asked to explain them in person.
>
> 💡 **TIP:** Mention concrete things you actually did: a method you wrote, an error you hit, a line of output you saw. Generic answers score low.
>
> 💡 **TIP:** Draft your answer in a few bullet points first, then turn them into sentences.

## Question 1: What did you learn about synchronization?

> 💡 **TIP:** Talk about race conditions (read-modify-write), critical sections, mutual exclusion with `ReentrantLock` and `try/finally`, the role of a counting semaphore, and what surprised you when the starter failed.

**Your Answer:** *(5-7 sentences)*

[I learned that an operation like count++ is not a single step, it has read modify and write, I also learned how to protect a critical section using a ReentrantLock,and why unlock() must be in a finally block, and the difference between making a thread with busy wating and using semaphores.]

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

[The most challenging part was dealing with the coding environment, my VS code kept throwing build errors, and not running code at all due to not loading the needed extensions. ]

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

[I learned how to use the java command pallete to fix the environment and clean the cache and reload the workspace.]

## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

[I think it can be used in softwares that require persice and secure operations and cannot tolerate mistakes like banks or shopping websites or applications.]

### Optional: What would you like to learn more about?

[I would like to know other synchronization methods that could be implemented in this code]

### Optional: How confident do you feel about synchronization concepts now?

[Intemediate, I could use more explaining for the methods used in the code, the most interesting to me is how I can integate all the knowledge from all the courses I had]

### Optional: Feedback on the assignment

[Any comments? Was it helpful? Too easy or hard? Suggestions?]

---

# Part C: Technical Answers (0.5 mark)

> 🛑 **STOP:** You cannot answer these questions without understanding the code. Re-read `SchedulerSimulationSync.java` and **run it** first. Your answers must reference **your own code and your own output** (your student ID makes your output and your expected values unique).
>
> ⚠️ **WARNING:** Each answer must be **3 to 5 sentences**, with specific examples from your code or output. Use correct terms: race condition, critical section, mutual exclusion, mutex lock, semaphore, busy waiting, deadlock, producer, consumer.
>
> 💡 **TIP:** Keep the output of the **original starter** and the output of your **final version** in text files or screenshots, so you can copy real snippets for Question 1.

## Question 1: Race Condition in Your Own Output

**Question**: Run the **original starter** (before any fix) and paste the **verification block** of that run. Which value was wrong (expected vs observed)? Explain **step by step**, with two named threads/CPUs, how **one lost update** happens on one of the shared variables (read, `RaceWindow.pause()`, write). Why can the same bug happen on a real machine even without `RaceWindow`, and why is it hard to detect?

> ⚠️ **WARNING:** The snippet must come from **your own run** (with your student ID), not from a classmate or from this README.
>
> 💡 **TIP:** Use a small timeline: *CPU-1 reads `contextSwitchCount` = 12 → CPU-2 reads 12 → CPU-1 writes 13 → CPU-2 writes 13 → one increment is lost.* If your starter run crashed before printing numbers, run it several times (or paste the exception and the watchdog message and explain it).

**Your Answer:** *(3-5 sentences)*

[In my starter code, the code failed because multiple CPUs accessed the shared ReadyQueue and SharedStats at the same time without protiction, the problem is that poll() was not atomic, meaning that 2 CPUs can read the same head if queue resuling in an IllegalTreadStateException when trying to start a process twice, and therefore the contexSwitchCount lost track of updates, this can happen in real machines beacause the OS can preempt a thread at any machine instruction between the read and write, it is hard to detect because the time window is only a few nanoseconds long]

Verification block of the **original starter**:
```
[✘ At least one check failed (see the ✘ lines above): a race condition or busy waiting is still present.]
```

Verification block of **my final version**:
```
[═══ VERIFICATION (expected values are computed from YOUR seed) ═══
  Context switches (quanta executed)     expected 22       observed 22       ✔
  Completed processes                    expected 12       observed 12       ✔
  Total service time (ms)                expected 33483    observed 33483    ✔
  Busy-waiting polls (must be 0)         expected 0        observed 0        ✔
  ✔ All shared values are consistent.]
```

**Explanation of the timeline:**
[1:CPU-1 calls incrementContextSwitch() and reads contextSwitchCount as 6
2:CPU-1 hits RaceWindow.pause() and temporarily pause by OS
3:CPU-2 calls incrementContextSwitch()and reads contextSwitchCount as 6 too
4:CPU-2 writes 7 back to the variable
5:CPU-1 wakes up and also writes 7 back to the variable, and therefore one increment is completely lost]

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

[I used a single ReentrantLock named statsLock to protect the tgree shared statistics, including both the update methods and the getters, I chose one lock for all three statistics because the contention in this simulation can be ignored with only 3 CPUs, and using one lock keeps the system in safe state and the code simple. But the tradeoff is a coarser granularity meaning that a thread reading the completed count briefly blocks a thread adding service time, but it isn't that big of a problem. The ready queue uses a different lock(queueLock)because the queue and the statistics are comletly independent, if they share a lock a CPU holding the queue lock while updating statistics would unnecessarily block other CPUs from doing any task. My sulotion provides mutual exclusion because only one thread can hold a lock at a time, it provides progress because locks are always released in a try and finally block, so even if an exception occurs it wouldn't affect the progress, but because a ReentrantLock is not fair, a thread could starve if others kee overtaking it, meaning thereis no strict bounded waiting guarentee, but as the critical sections are too short for starvation they won't occur ]

| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| [e.g., `ReadyQueue.poll()`] | [lock name] | [reason] |
| [ReadyQueue(list and map)] | [queueLock] | [To prevent multiple CPUs from reading or removing the same process or corrupting the LinkedList] |
| [SharedSrars (counters)] | [statsLock] | [To prevent lost updates during read-modify-write operations] |

## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

[In the starter code, when the queue was empty, a CPU would sleep for 20ms and wake up to poll the queue again in a while loop, incrementing the busyWaitPolls counter, this is busu waiting or polling because the thread is repeatedly checking  condition and wasting CPU cycles, in my final version I replaced this weth a counting semaphore named available, the value of the semaphoe represents the nube of processes currently waiting in the ready queue, its initial value is 0 because the queue starts empty, and after the 16 initial add()calls in main, its value becomes 16, the semaphore blocks a CPU usin acquire(),meaning it sleeps without consuming CPU time until a process is available, when the last process finishes the completing CPU calls release(SharedStats.totalCPUs) to wakeup all other CPUs blocked in acquire(), if it didn't do this the CPUs would wait forever for a process that will never arrive causing a deadlock and forcing the watchdog to terminate the program .] 

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*

**Classical problem and roles**:
[Producer-Consumer, Producers: main and CPUs reenqueuing processes, Consumers: CPUs taking processes]

**Semaphores for a bounded queue (name and initial value)**:
[1-empty(counts free slots,initial =K)
2-full(counts available processes , initial =0)
3- mutex(binary lock for the queue, initial =1)]

**Deadlock scenario and prevention**:
[If a producer acquires mutex first and then waits on empty, it will block while holding the lock, the consumer cannot empty the buffer because it is blocked waiting for the mutex , this creats a deadlock, we break the hold and wait condition by acquiring the semaphores(empty or full) before acquiring the mutex]

## Summary

**Key concepts I understood through these questions:**
1.Race conditions: I learned that operations like count++ are not a single step operation.
2.Mutual Exclusion: I understand how to use a reentrantLock to create a critical section and locking it.
3.Semaphores and busywaiting: I learned how a counting semaphore replaces a wastefull loop.

**Concepts I need to study more:**
1. I want to learn more about how fair locks work
2. I want to know what other synchronization tools can look like in code

---

# ✅ Final Checklist (complete before submitting)

> ⚠️ **WARNING:** Go through every line. Blackboard does not accept submissions after the deadline, which is **November 14, 2026**.

**Repository**
- [✔] Repository is **PUBLIC** (Settings → Danger Zone → Visibility)
- [✔] Repository is renamed to `OS-Assignment3-YourFirstName-YourLastName`
- [✔] GitHub account uses the university email (`@std.psau.edu.sa`)

**Code**
- [✔] Student ID is set in `SchedulerSimulationSync.java` (line 304)
- [✔] My code is based **only** on the starter of this repository (nothing copied from previous assignments)
- [✔] Code compiles and runs with no errors, and terminates by itself (no `⛔ WATCHDOG`)
- [✔] Feature 1 (ready queue lock), Feature 2 (statistics locks) and Feature 3 (semaphore, no busy waiting) all work
- [✔] **The four verification lines are ✔ in 5 consecutive runs**
- [✔] Every lock is released in a `finally` block
- [✔] `RaceWindow`, `Config`, the verification block and the watchdog are **unchanged**
- [✔] Each feature has clear comments

**Commits**
- [✔] **At least 4 meaningful commits, ideally 7 or more**
- [✔] **One commit per feature**
- [✔] Commits are spread over **different dates** (not all in the last hour)
- [✔] Everything is **pushed** to GitHub

**This file (`MY_WORK.md`)**
- [✔] Full name and student ID filled in at the top
- [✔] Development log has **5+ entries** on different dates
- [✔] Reflection: 4 questions, 5-7 sentences each
- [✔] Technical answers: 4 questions, 3-5 sentences each, with examples from **your** output (starter output **and** final output pasted in Question 1)
- [✔] No `[...]` placeholders left
- [✔] No section headers deleted

**Video**
- [✔] 2-3 minutes long, named `StudentID_Assignment3_Demo.mp4`
- [✔] Shows your name, ID, repository, 3 features (and your lock granularity choice), IDE execution with the verification block, one synchronization concept, and commit history
- [✔] Link is **public** (tested in an incognito window) and pasted in the **Video Link** section above

**Blackboard**
- [ ] Submit **only** the link to your public GitHub repository

> 🎯 **Good luck!** Start early, commit regularly, and make sure you can explain every line you submit.
