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
| **Full Name** | Raghad Bandar Al-Mutairi |
| **Student ID** | [445052724] |
| **University Email** | 445052724@std.psau.edu.sa |
| **GitHub Username** | raghadbander|
| **Repository Link** |(https://github.com/raghadbander) |
 
---

## 🎥 Video Link

**Video Link**: (https://drive.google.com/file/d/15PmRMD5bGlPCT3F0vfoQNbvrRH9eyocU/view?usp=sharing)]

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

### Entry 1 - [November 13, 2026, 9:30 PM]
**What I did**: Forked the repository, set my student ID, and ran the original starter code

**Details**:
- Forked `makopt/OS-Assignment3-Starter-481` and renamed my fork to `OS-Assignment3-raghad-bnder`
- Updated `studentID` on line 304 in `SchedulerSimulationSync.java` to `445052724`
- Ran the original starter program to observe the initial race conditions and watchdog behavior
- Committed and pushed: `chore: set student ID and import synchronization libraries`

**Challenges**: Multiple CPU threads picked the same process simultaneously from the ready queue before synchronization was added.

**Solution**: Inspected `ReadyQueue.poll()` and saw that `RaceWindow.pause()` exposed a race window between reading the queue head and removing it.

**Time spent**: 40 minutes

---

### Entry 2 - [November 13, 2026, 10:30 PM]
**What I did**: Implemented Statistics Locks with fine-grained granularity (Feature 2)

**Details**:
- Declared a dedicated `ReentrantLock` (`statsLock`) inside `SharedStats`
- Protected `incrementContextSwitch()`, `incrementCompletedProcess()`, `addServiceTime()`, and all reader methods using `try/finally` blocks
- Committed and pushed: `feat: protect shared statistical counters with fine-grained ReentrantLocks`

**Challenges**: Deciding whether to use one lock for `SharedStats` or separate locks per counter without overcomplicating the code.

**Solution**: Used one dedicated `statsLock` for `SharedStats` separated from `ReadyQueue` locking, reducing contention between queue operations and metric updates.

**Time spent**: 45 minutes

---

### Entry 3 - [November 13, 2026, 11:30 PM]
**What I did**: Implemented Ready Queue Lock (Feature 1) and fixed class bracket placement

**Details**:
- Declared `queueLock` (`ReentrantLock`) inside `ReadyQueue` and protected `add()`, `poll()`, `processOf()`, and `snapshot()`
- Fixed a compilation issue where helper methods were accidentally placed outside the `ReadyQueue` closing brace
- Committed and pushed: `feat: add ReentrantLock to protect shared ready queue operations`

**Challenges**: Encountered syntax and symbol resolution errors (`queueLock cannot be resolved`) due to misplaced helper methods outside `ReadyQueue`.

**Solution**: Re-checked the class braces in `ReadyQueue` and placed all helper methods cleanly inside the class body.

**Time spent**: 50 minutes

---

### Entry 4 - [November 14, 2026, 12:30 PM]
**What I did**: Replaced busy waiting with a counting Semaphore and clean shutdown (Feature 3)

**Details**:
- Added a counting `Semaphore` (`readySemaphore`) initialized to `0` in `ReadyQueue`
- Replaced the polling loop in `CpuWorker` with `readySemaphore.acquire()` (`waitForProcess()`) and signaled permits via `release()` in `add()`
- Implemented `signalAllCpus()` when `completedProcessCount >= totalProcesses` for clean thread termination
- Committed and pushed: `feat: replace busy waiting with counting Semaphore and clean shutdown`

**Challenges**: Ensuring waiting CPU threads do not block forever on `acquire()` after the final process completes.

**Solution**: Added a post-acquire completion check and released permits for all CPUs once all 15 processes finished.

**Time spent**: 1 hour 15 minutes

---

### Entry 5 - [November 14, 2026, 2:30 PM]
**What I did**: Verified simulation output across multiple runs and finalized documentation

**Details**:
- Ran the simulation 5 consecutive times in VS Code; every run passed the verification block (`27` context switches, `15` completed processes, `76706` ms service time, `0` busy-wait polls)
- Completed all sections of `MY_WORK.md` based on my actual code and simulation output
- Committed and pushed: `test: verify simulation output and finalize assignment documentation`

**Challenges**: Confirming that `Busy-waiting polls` dropped to `0` consistently across all 5 test runs.

**Solution**: Verified the output table and verification checks after every execution to ensure zero race conditions and zero polling.

**Time spent**: 45 minutes
---

## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.

**Total time spent on assignment**: [X hours]

**Most challenging part**:

**Most interesting learning**:

**What I would do differently next time**:

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

Studying synchronization in this assignment highlighted how vulnerable multithreaded programs are to race conditions caused by unprotected read-modify-write sequences. What surprised me most when running the starter code was seeing multiple CPU threads retrieve the same process from the ready queue or corrupt performance metrics before synchronization was implemented. To ensure mutual exclusion, I learned to protect critical sections with Java’s ReentrantLock and use try/finally blocks to guarantee that locks were safely released. I also discovered that replacing busy-wait polling loops with a counting semaphore lets CPU threads sleep efficiently until a process becomes available. Ultimately, these synchronization primitives eliminated data corruption and reduced busy-wait polls to zero. 

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

The most challenging part of this assignment was ensuring that all CPU threads shut down cleanly after replacing the busy-waiting loop with a counting semaphore. When CPU threads block on acquire(), they can remain stuck waiting for a permit if the final process finishes and no further permits are released. During initial testing, this caused the simulation to hang and trigger the watchdog timeout. To resolve the issue, I implemented a precise termination check that tracks the number of completed processes and releases enough permits to wake any remaining blocked CPU threads. This ensured that all worker threads exited gracefully and the simulation terminated successfully without deadlocks

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

To address the synchronization challenges and deadlock issues I encountered, I followed a systematic, step-by-step debugging process. Whenever a bug or watchdog timeout occurred, I carefully reread the assignment instructions and revisited the relevant synchronization concepts in the course slides. I used targeted System.out.println statements to trace thread execution and monitor queue interactions in real time. I also tested my code after each small change, allowing me to isolate problems quickly rather than debug a large set of changes all at once. Running the simulation repeatedly after each fix helped confirm that the concurrency issues were resolved and that all verification checks continued to pass consistently.

## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

Synchronization is essential in real-world applications where multiple users or threads access and modify shared resources concurrently. For example, in an online ticket or seat booking system, several customers may try to reserve the same seat at once, requiring mutual exclusion locks to prevent double-booking. Similarly, banking systems use critical sections and locks to ensure that transactions and money transfers update account balances accurately without race conditions. A print queue in a networked office environment also resembles the ready queue in this assignment, using semaphores to coordinate access and manage jobs from multiple users. Connecting these real-world systems to what I built highlights the importance of concurrency control in maintaining data integrity in modern software.

### Optional: What would you like to learn more about?

I would like to learn more about advanced synchronization mechanisms used in multiprocessor operating systems, such as read-write locks and non-blocking synchronization algorithms like lock-free data structures. Exploring how operating systems handle priority inversion and deadlock prevention algorithms in complex kernel environments would also be very interesting.

### Optional: How confident do you feel about synchronization concepts now?

Confident. I now understand how to effectively implement mutual exclusion using ReentrantLock with try/finally blocks and how to replace inefficient busy-waiting loops with counting semaphores. I feel comfortable protecting critical sections and managing thread communication, though I would like more practice dealing with complex multi-resource deadlock scenarios.

### Optional: Feedback on the assignment

This assignment was extremely helpful and engaging because it bridged abstract operating system theory from the textbook with practical, multi-threaded Java programming. Seeing the race conditions manifest and then systematically eliminating them with locks and semaphores made the concepts much clearer. The level of difficulty was appropriate and challenged me to think critically about concurrency control.
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

When running the original, unprotected starter code, the simulation hit a watchdog timeout and crashed because multiple CPU threads accessed shared statistical counters and the ready queue concurrently without mutual exclusion. In particular, the observed context-switch count and total service time differed from the expected values because concurrent read-modify-write operations caused lost updates. This bug can occur on real machines even without RaceWindow, since a thread can be preempted at any point between reading a shared variable and writing back its updated value. Such race conditions are notoriously difficult to detect through standard testing because they depend on unpredictable thread interleavings and can surface infrequently and seemingly at random

Verification block of the **original starter**:
```
[═══ VERIFICATION (expected values are computed from YOUR seed) ═══
  Context switches (quanta executed)     expected 27        observed 18        ✘ MISMATCH
  Completed processes                    expected 15        observed 9         ✘ MISMATCH
  Total service time (ms)                expected 76706     observed 44210     ✘ MISMATCH
  Busy-waiting polls (must be 0)         expected 0         observed 1423      ✘ MISMATCH
  ✘ At least one check failed (see the ✘ lines above): a race condition or busy waiting is still present.

⛔ WATCHDOG: the simulation did not finish (45 s). A process was lost, or a CPU is blocked forever, or the 'completed' counter lost an update.]
```

Verification block of **my final version**:
```
[═══ VERIFICATION (expected values are computed from YOUR seed) ═══
  Context switches (quanta executed)     expected 27        observed 27        ✔
  Completed processes                    expected 15        observed 15        ✔
  Total service time (ms)                expected 76706     observed 76706     ✔
  Busy-waiting polls (must be 0)         expected 0         observed 0         ✔
  ✔ All shared values are consistent.)]
```

**Explanation of the timeline:**
[Step 1: CPU-1 reads the shared statistical counter contextSwitchCount and obtains the value 12.

Step 2: RaceWindow.pause() artificially suspends CPU-1 right at that moment.

Step 3: CPU-2 reads the exact same shared counter contextSwitchCount before CPU-1 can update it, also obtaining the value 12.

Step 4: CPU-1 resumes, computes 12 + 1 = 13, and writes 13 back to contextSwitchCount.

Step 5: CPU-2 computes 12 + 1 = 13 and writes 13 back, effectively overwriting CPU-1's update and causing one lost increment.]

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

In my solution, I implemented fine-grained locking with two separate locks: queueLock protects operations on the shared ready queue, while statsLock protects the independent statistical counters. Although a single coarse-grained lock would be simpler, separate locks reduce contention, allowing one CPU to update statistics without blocking other CPUs from polling the ready queue. Mutual exclusion is enforced using ReentrantLock, with lock release handled in try/finally blocks to ensure that locks are always released. This guarantees that only one thread at a time can execute a critical section protected by a given lock. However, Java’s default ReentrantLock is non-fair and permits barging, so threads are not guaranteed to acquire the lock in FIFO order. In theory, this can lead to starvation if newly arriving threads repeatedly bypass a waiting thread.

| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| [e.g., `ReadyQueue.poll()`] | [lock name] | [reason] |
| [...] | [...] | [...] |
ReadyQueue.poll() — Lock used: queueLock — Protects queue head reading and removal so multiple CPUs do not pick the same process simultaneously.

ReadyQueue.add() — Lock used: queueLock — Prevents concurrent structural modifications to the shared FIFO list and process map.

ReadyQueue.processOf() and snapshot() — Lock used: queueLock — Ensures safe read access and string snapshot generation of the shared queue state.

SharedStats counters (contextSwitchCount, completedProcessCount, totalServiceTime) — Lock used: statsLock — Protects shared metric updates against lost updates during concurrent read-modify-write cycles.

## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

[In the original starter version, the CpuWorker relied on busy waiting by continuously polling an empty ready queue in a while loop, which wasted valuable CPU cycles and resulted in an exorbitant number of Busy-waiting polls (1423 polls in my starter run). To eliminate this inefficiency, I introduced a counting semaphore initialized to 0, where the semaphore's value represents the exact number of available processes currently waiting in the ready queue. After the initial numProcesses add() calls, the semaphore's value equals the number of queued processes ready to be executed. Finally, the last CPU calls release(totalCPUs) upon completion to broadcast wake-up permits, ensuring that any remaining threads blocked on acquire() are released so they exit cleanly without triggering a watchdog timeout.]

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*

**Classical problem and roles**:
This simulation models the classical Bounded-Buffer (Producer-Consumer) problem, where the main thread and CPUs act as producers when initializing or re-enqueuing processes back into the ready queue, while the CPU worker threads act as consumers pulling processes for execution.

**Semaphores for a bounded queue (name and initial value)**:
To manage a bounded ready queue of capacity $K$, the three required semaphores would be empty (initialized to $K$ to track available buffer slots), full (initialized to $0$ to track filled slots), and a mutex lock mutex (initialized to $1$ to ensure mutual exclusion over the queue).

**Deadlock scenario and prevention**:
A deadlock scenario occurs if a producer thread acquires the queue mutex before waiting on a space semaphore (empty.acquire()), because if the buffer is full, the producer blocks while holding the lock, preventing any consumer from accessing the queue to free up a slot. To prevent this deadlock, we break the Hold and Wait condition by ensuring that resource acquisition follows a strict ordering—specifically, waiting on the semaphore (empty.acquire()) to secure a buffer slot before acquiring the mutex lock.

## Summary

**Key concepts I understood through these questions:**
1.How race conditions occur during concurrent read-modify-write sequences and how mutex locks (ReentrantLock) restore mutual exclusion in critical sections.
2.The trade-offs of lock granularity and why separating queue locks from statistics locks reduces contention and prevents unnecessary blocking.
3.The inefficiency of busy waiting and how counting semaphores efficiently put threads to sleep until resources become available, achieving zero poll overhead.

**Concepts I need to study more:**
1.Fair versus non-fair lock implementations in Java and their impact on thread starvation and latency bounds.
2.Advanced deadlock detection and prevention algorithms in complex multi-threaded operating system environments.

---

# ✅ Final Checklist (complete before submitting)

> ⚠️ **WARNING:** Go through every line. Blackboard does not accept submissions after the deadline, which is **November 14, 2026**.

**Repository**
- [ ] Repository is **PUBLIC** (Settings → Danger Zone → Visibility)
- [ ] Repository is renamed to `OS-Assignment3-YourFirstName-YourLastName`
- [ ] GitHub account uses the university email (`@std.psau.edu.sa`)

**Code**
- [ ] Student ID is set in `SchedulerSimulationSync.java` (line 304)
- [ ] My code is based **only** on the starter of this repository (nothing copied from previous assignments)
- [ ] Code compiles and runs with no errors, and terminates by itself (no `⛔ WATCHDOG`)
- [ ] Feature 1 (ready queue lock), Feature 2 (statistics locks) and Feature 3 (semaphore, no busy waiting) all work
- [ ] **The four verification lines are ✔ in 5 consecutive runs**
- [ ] Every lock is released in a `finally` block
- [ ] `RaceWindow`, `Config`, the verification block and the watchdog are **unchanged**
- [ ] Each feature has clear comments

**Commits**
- [ ] **At least 4 meaningful commits, ideally 7 or more**
- [ ] **One commit per feature**
- [ ] Commits are spread over **different dates** (not all in the last hour)
- [ ] Everything is **pushed** to GitHub

**This file (`MY_WORK.md`)**
- [ ] Full name and student ID filled in at the top
- [ ] Development log has **5+ entries** on different dates
- [ ] Reflection: 4 questions, 5-7 sentences each
- [ ] Technical answers: 4 questions, 3-5 sentences each, with examples from **your** output (starter output **and** final output pasted in Question 1)
- [ ] No `[...]` placeholders left
- [ ] No section headers deleted

**Video**
- [ ] 2-3 minutes long, named `StudentID_Assignment3_Demo.mp4`
- [ ] Shows your name, ID, repository, 3 features (and your lock granularity choice), IDE execution with the verification block, one synchronization concept, and commit history
- [ ] Link is **public** (tested in an incognito window) and pasted in the **Video Link** section above

**Blackboard**
- [ ] Submit **only** the link to your public GitHub repository

> 🎯 **Good luck!** Start early, commit regularly, and make sure you can explain every line you submit.

