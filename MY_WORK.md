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
| **Full Name** | [Write your full name here] |
| **Student ID** | [Write your student ID here] |
| **University Email** | [yourid]@std.psau.edu.sa |
| **GitHub Username** | [your-github-username] |
| **Repository Link** | [Paste your repository link here] |
 
---

## 🎥 Video Link

**Video Link**: [https://youtu.be/fJwUGYEeUyk]


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

### Entry 1 - [November 6, 2026, 2:00 AM]
**What I did**: Set up the repositiry, changed my student ID, and ran the starter code.

**Details**: 
-Forked the repository and renamed it.
-Updated line 304 with my student ID (446052698).
-Ran the starter code and saved the output. It failed completely: CPU-1 crashed with a ConcurrentModificationException, CPU-3 crashed because it grabbed P1 at the same time as CPU-2, and the watchdog stopped the program after 23 seconds.
-Made my first commit (Set my student ID).

**Challenges**: I was confused at first why P2 and P3 disappeared with 0ms and why two CPUs managed to pick P1 at the exact same time.

**Solution**: Looked at ReadyQueue and realized that without a lock, multiple CPUs were modifying the LinkedList concurrently during RaceWindow.pause().

**Time spent**: 40 minutes.

---

### Entry 2 - [November 6, 2026, 3:39 AM]
**What I did**:Implemented Feature 1 to lock the ReadyQueue.

**Details**:
-Declared a ReentrantLock named queueLock in the ReadyQueue class.
-Protected all methods (add, poll, processOf, and snapshot) using lock() and try-finally blocks to ensure mutual exclusion.
-Tested the code, and all 16 processes finished successfully without any crashes.
-Committed and pushed (Feature 1: Protected the ready queue with a ReentrantLock).

**Challenges**:Making sure I didn't miss any method that touches the shared queue list or map.

**Solution**:Checked every single method in ReadyQueue and wrapped it securely, making sure unlock() is always inside a finally block so locks don't get stuck.

**Time spent**:1 hour.

---

### Entry 3 - [November 9, 2026, 6:38 PM]
**What I did**:Implemented Feature 2 to protect the shared statistics.

**Details**:
-Added a ReentrantLock named statsLock inside SharedStats.
-Locked all update methods (contextSwitchCount, completedProcessCount, totalServiceTime) and also the getter methods to prevent reading messy data.
-Ran the simulation and saw context switches and total service time pass with green checks.
-Committed and pushed (Feature 2: Added locks to the shared statistics counters).

**Challenges**:At first I only thought about locking the increment functions, but I realized getters also need locks so threads don't read data mid-update.

**Solution**:to every single method in SharedStats with try-finally blocks.

**Time spent**:1 hour.

---

### Entry 4 - [November 15, 2026, 11:53 PM]
**What I did**:mplemented Feature 3 with a counting semaphore and clean shutdown, then verified the final output.

**Details**:
-Declared a counting semaphore (queueSemaphore) initialized to 0 in ReadyQueue.
-Replaced the busy-waiting polling loop in CpuWorker with queueSemaphore.acquire(), and called queueSemaphore.release() whenever a process is added.
-Implemented the dual clean shutdown logic using SharedStats.getCompletedProcessCount() >= SharedStats.totalProcesses along with release(SharedStats.totalCPUs) to safely wake up waiting CPUs and prevent deadlocks.
-Ran the simulation 5 consecutive times and confirmed that all verification checks passed with green checks and busy-waiting polls equaled 0.
-Committed and pushed (Feature 3: Replaced busy waiting with a counting semaphore).

**Challenges**:Figuring out the exact placement for the clean shutdown checks and making sure the CPUs wouldn't hang or get stuck waiting forever on the semaphore after the last process finished.

**Solution**:Added the shutdown checks both right after acquire() and after a process quantum finishes, ensuring the last CPU releases all waiting workers so they can terminate cleanly.

**Time spent**:1 hour and 30 minutes

---

### Entry 5 - [November 16, 2026, 7:34 PM]
**What I did**:Checked and reviewed my previous work, organized the development log entries, and reviewed MY_WORK.md.

**Details**:
-Went through all my previous code implementations and git history to make sure everything was fully verified and correct.
-Looked over MY_WORK.md and structured the final development log entries based on my actual work sessions.
-Checked all requirements and prepared for the next sections.
-Committed and pushed the updated entries.

**Challenges**:Making sure all the log entries and details matched my actual work timeline accurately.

**Solution**:Checked my terminal outputs and commit history step-by-step to align everything correctly.

**Time spent**:45 minutes.

---

### Entry 6 - [Optional - Date and Time]
**What I did**:

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

---

## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.

**Total time spent on assignment**: [5 hours and 25 minutes]

**Most challenging part**:Understanding why the starter code crashed with ConcurrentModificationException and figuring out the correct clean shutdown logic for the semaphore without causing deadlocks.

**Most interesting learning**:Seeing how a simple ReentrantLock and counting semaphore completely eliminate busy-waiting polls (0 polls) and keep the CPU scheduler running smoothly and consistently.

**What I would do differently next time**:Experiment with different synchronization approaches and test how different lock designs behave before deciding on the final implementation.

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

[When I first ran the starter code, I was surprised to see it crash right away with a ConcurrentModificationException because multiple CPUs were trying to change the ready queue at the exact same time. This showed me how dangerous race conditions can be when threads share data without locks. By building Feature 1, I learned how to use a ReentrantLock with try/finally blocks to keep critical sections safe. Then, Feature 2 taught me that shared stats counters also need locks on both update and get methods so threads don't read messy data. Finally, adding the counting semaphore in Feature 3 showed me how to stop wasting CPU cycles on busy-waiting by making threads wait and wake up properly. Overall, this assignment really helped me see why synchronization is so important for keeping multi-threaded programs running correctly.]

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

[The hardest part for me was figuring out the clean shutdown logic when using the counting semaphore in Feature 3. At first, after I replaced the polling loop with queueSemaphore.acquire(), the worker threads got stuck waiting forever even after all 16 processes had finished. This happened because the CPUs didn't know when to stop once the queue was empty. It took a lot of trial and error to figure out how to check SharedStats.getCompletedProcessCount() >= SharedStats.totalProcesses and use release(SharedStats.totalCPUs) to wake up the waiting threads. Getting this shutdown part right without causing deadlocks was definitely tricky. Figuring out how to trace the CPU states and make sure every thread exited cleanly took quite a bit of patience.]

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

[To get past these challenges, I took it step-by-step and tested my code after making small changes. Whenever the program threw an error or failed a check, I looked closely at the terminal output to see which CPU caused it. I also went back to the assignment README and lecture notes whenever I got stuck on how locks or semaphores worked. When the semaphore was locking up, I added some temporary print statements to track what the queue was doing. Running the simulation over and over again after each fix helped me find and solve bugs quickly. This patient way of debugging saved me and made everything click.]

## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

[Synchronization is used everywhere in real-world apps where multiple users share the same data at the same time. A great example is an online ticket booking system where two people try to buy the exact same seat at the exact same second. Without locks to protect that data, the system might sell the same seat twice by accident. Another example is a banking app, where transferring money involves updating account balances, and a lock ensures the numbers stay correct and don't get mixed up. Print servers also use shared queues so that documents sent from multiple computers get printed one after another instead of getting jumbled together. Building this scheduler helped me realize that the same locking ideas we used here are what keep real software working safely.]

### Optional: What would you like to learn more about?

[thread pool implementations in Java.]

### Optional: How confident do you feel about synchronization concepts now?

[Confident. I understand locks and semaphores much better now after coding them myself.]

### Optional: Feedback on the assignment

[The assignment was very practical and helped bridge the gap between theory and actual coding.]

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

[In my original starter run, the simulation failed completely because multiple CPUs accessed the shared ready queue without any locking mechanism. When CPU-1 and CPU-2 tried to poll and modify the list concurrently during RaceWindow.pause(), it triggered a ConcurrentModificationException and caused thread collisions. This happens because read-modify-write operations are not atomic, meaning one CPU's update gets overwritten by another, resulting in a lost update. This bug can happen on real machines even without RaceWindow due to CPU core interleaving, and it is very hard to detect because it only occurs intermittently under heavy multi-threading.]

Verification block of the **original starter**:
```
[java.util.ConcurrentModificationException
	at java.base/java.util.LinkedList$Itr.checkForComodification(LinkedList.java:1013)
	at java.base/java.util.LinkedList$ListItr.next(LinkedList.java:1102)
[WATCHDOG] Simulation timed out after 23 seconds (possible deadlock or infinite loop).]
```

Verification block of **my final version**:
```
[═══ VERIFICATION (expected values are computed from YOUR seed) ═══
  Context switches (quanta executed)     expected 28        observed 28        ✔
  Completed processes                    expected 16        observed 16        ✔
  Total service time (ms)                expected 44970     observed 44970     ✔
  Busy-waiting polls (must be 0)         expected 0         observed 0         ✔
  ✔ All checks passed successfully!]
```

**Explanation of the timeline:**
[ECPU-1 reads contextSwitchCount as 12, then CPU-2 reads 12 at the same time. CPU-1 increments it and writes 13 back, but right after that, CPU-2 writes its incremented value 13 back, completely erasing CPU-1's update and causing a lost update.]

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

[I protected the shared ready queue and statistics using separate ReentrantLock instances to ensure mutual exclusion without unnecessary bottlenecks. For lock granularity, I used one lock (queueLock) for the ready queue and another lock (statsLock) for the shared statistics because updating process queues is completely independent of updating performance counters like service time. Using separate locks improves concurrency and avoids performance slowdowns, whereas combining them into a single lock would force statistics updates to wait unnecessarily behind queue operations. However, because Java's default ReentrantLock is not fair, it does not guarantee strict FIFO ordering, meaning a thread might experience starvation if other threads constantly acquire the lock first.]

| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| [e.g., `ReadyQueue.poll()`] | [lock name] | [reason] |
| [ReadyQueue.add() and poll()] | [queueLock] | [Prevents two CPUs from grabbing the same process or crashing the shared LinkedList with ConcurrentModificationException.] |
| [ReadyQueue.processOf() and snapshot()] | [queueLock] | [Ensures threads don't read or iterate over the queue map/list while another thread is actively modifying it.] |
| [SharedStats (contextSwitchCount, completedProcessCount)] | [statsLock] | [Protects the read-modify-write increment operations so updates don't get overwritten or lost between CPUs.] |
| [SharedStats (totalServiceTime and all getter methods)] | [statsLock] | [Guarantees accurate total service time calculations and prevents threads from reading half-updated numbers.] |
| [ReadyQueue queue size / available items] | [queueSemaphore] | [Coordinates producer and consumer access so CPUs sleep safely when the queue is empty instead of busy-waiting.] |

## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

[In the starter code, CPU worker threads used a busy-waiting polling loop (while (readyQueue.isEmpty())) that repeatedly checked the queue, resulting in 12 busy-waiting polls and wasting valuable CPU cycles. To fix this, I used a counting semaphore (queueSemaphore) initialized to 0 because no processes are ready to be executed until they are added. Right after the initial numProcesses add calls, the semaphore value equals 16, representing the number of available processes ready for pickup. At the end of the simulation, the last active CPU calls release(totalCPUs) to wake up any sleeping worker threads, and without this call, those threads would remain blocked forever in acquire() causing a deadlock.]

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*
This scheduler simulation represents the classical Producer-Consumer Problem from synchronization theory, where the main thread acts as the producer adding processes to the queue, and the CPU workers act as consumers taking processes out to execute. If the ready queue were bounded with a fixed capacity K, the three required semaphores would be empty (initialized to K), full (initialized to 0), and mutex (initialized to 1). A deadlock can occur if a worker thread acquires the mutex lock before waiting on the semaphore, because if the queue is empty, the thread holds the lock and sleeps, preventing any producer from ever adding new items. To prevent this deadlock, we must break the Hold and Wait condition by ensuring threads acquire the semaphore permit before locking the mutex, or by acquiring locks in a consistent, strict global order.

**Classical problem and roles**:
[Producer-Consumer Problem. The main thread (or scheduler starter) plays the producer role by adding processes to the queue, while the CPU worker threads play the consumer role by removing and executing them.]

**Semaphores for a bounded queue (name and initial value)**:
[- empty: Initialized to K (tracking available empty slots).
 - full: Initialized to 0 (tracking filled slots with processes).
 - mutex: Initialized to 1 (providing mutual exclusion for queue access).]

**Deadlock scenario and prevention**:
[A deadlock happens if a thread acquires the mutex lock first and then waits on a semaphore for an empty slot; if the queue is full, it sleeps while holding the lock, blocking consumers from freeing space. We prevent this by breaking the Hold and Wait condition—specifically, by waiting on the semaphore to get a slot before acquiring the mutex lock.]

## Summary

**Key concepts I understood through these questions:**
1.How race conditions and lost updates corrupt shared data in multi-threaded environments.
2.The importance of lock granularity in balancing performance and thread safety.
3.How counting semaphores eliminate busy-waiting by efficiently blocking and waking up threads.

**Concepts I need to study more:**
1.Advanced deadlock detection and prevention algorithms.
2.Fairness policies in thread synchronization locks.

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
