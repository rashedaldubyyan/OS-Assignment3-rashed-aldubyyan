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
| **Full Name** | [rashed aldubyyan]
| **Student ID** | [445050049]
| **University Email** | 445050049@std.psau.edu.sa
| **GitHub Username** | [rashedaldubyyan]
| **Repository Link** | [[Paste your repository link here](https://github.com/rashedaldubyyan/OS-Assignment3-rashed-aldubyyan)] |
 
---

## 🎥 Video Link

**Video Link**: [https://drive.google.com/file/d/1NWU96J2UdZPhf1tVpu6squMrtiikp3N1/view?usp=sharing]

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

### Entry 1 -[November 12, 2026, 3:30 PM]
**What I did**:Set my student ID and ran the original starter.

**Details**:- Changed the student ID to 445050049 in SchedulerSimulationSync.java
- Ran the starter: 14 processes, time quantum 3000ms, 4 CPUs
- All 4 CPUs crashed with a NullPointerException in ReadyQueue.snapshot()
- The verification block showed observed = 0 for all values
- Saved the output for Question 1 of Part C
**Challenges**:I did not understand why all the CPUs crashed before running any process.

**Solution**: I found that snapshot() loops over the list while another CPU removes
elements with poll(). The list changes during the loop, so it crashes.

**Time spent**:40 minutes

---

### Entry 2 - [November 12, 2026, 4:00 PM - 7:00 PM]
**What I did**: Implemented Feature 1 (mutex lock on the ready queue).

**Details**:
- Added `import java.util.concurrent.locks.ReentrantLock;`
- Added `private final ReentrantLock queueLock` in ReadyQueue
- Protected `add()`, `poll()`, `processOf()` and `snapshot()` with `lock()` / `try` / `finally { unlock() }`
- After the fix, no more exceptions and no lost or duplicated process; all 14 processes finished

**Challenges**: Compile errors from duplicated lines in `add()`, and `finally` placed before `try` in `poll()`.

**Solution**: Fixed the order to `lock()`, `try`, `finally`, and removed the duplicated lines.

**Time spent**: 2 hours

---

### Entry 3 - [November 13, 2026, 1:00 PM - 1:15 PM]
**What I did**: Implemented Feature 2 (locks on the shared statistics).

**Details**:
- Added three locks: `ctxLock`, `completedLock`, `serviceLock` (one lock per variable, because the counters are independent)
- Protected `incrementContextSwitch()`, `incrementCompletedProcess()`, `addServiceTime()` and the three getters
- Result: Context switches 29, Completed processes 14, Total service time 67759, all ✔

**Challenges**: `ClassNotFoundException` because the closing braces of `SharedStats` and `ReadyQueue` were missing, so the code did not compile.

**Solution**: Checked the braces and added the missing ones.

**Time spent**: 1 hour


---

### Entry 4 -[November 13, 2026, 1:30 PM - 3:00 PM]
**What I did**: Implemented Feature 3 (counting semaphore instead of busy waiting).

**Details**:
- Added `Semaphore readyCount = new Semaphore(0)` in ReadyQueue (starts at 0 because the queue is empty)
- Added `readyCount.release()` in `add()`
- Added `waitForProcess()` (acquire) and `wakeAll(int n)` (release(n)) in ReadyQueue
- Rewrote `CpuWorker.run()`: wait on the semaphore, poll, run one quantum, re-add if not finished, and call `wakeAll(totalCPUs)` when the last process completes
- Result: all four verification lines ✔ and `Busy-waiting polls = 0`

**Challenges**: The old polling code was still in `run()`, and the closing brace of `CpuWorker` was missing.

**Solution**: Replaced the whole `run()` method and added the missing brace.

**Time spent**: 1.5 hours

---

### Entry 5 - [November 13, 2026, 3:00 PM]
**What I did**: Ran the program several times to verify the solution, then started the documentation.

**Details**:
- Ran the program multiple times: all four lines ✔ and no WATCHDOG
- Filled in the student information in MY_WORK.md
- Started the reflection and technical answers

**Challenges**: Making sure my answers use my own output (the starter crashed before printing numbers).

**Solution**: Used the NullPointerException and the observed = 0 verification block for Question 1.

**Time spent**: 1 hour
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

**Total time spent on assignment**: [6 hours]

**Most challenging part*fixing the compile errors caused by missing closing braces*:

**Most interesting learning*a race condition can destroy the result even in a very small piece of code*:

**What I would do differently next time*commit after every small step, and check the braces before running*:

---

# Part B: Reflection (0.5 mark)

> 🛑 *STOP:** Do **not** start this part until you have read the `README.md`, read the **entire** `SchedulerSimulationSync.java`, run it, and finished the three features.
>
> ⚠️ **WARNING:** Each answer must be **5 to 7 sentences**, in **your own words**. Copied or AI-generated answers without understanding get **0 marks for the whole assignment**. You may be asked to explain them in person.
>
> 💡 **TIP:** Mention concrete things you actually did: a method you wrote, an error you hit, a line of output you saw. Generic answers score low.
>
> 💡 **TIP:** Draft your answer in a few bullet points first, then turn them into sentences.

## Question 1: What did you learn about synchronization?

> 💡 **TIP:** Talk about race conditions (read-modify-write), critical sections, mutual exclusion with `ReentrantLock` and `try/finally`, the role of a counting semaphore, and what surprised you when the starter failed.

**Your Answer:** *(5-7 sentences)*

[I learned that count++ is not a single atomic operation; it actually consists of three separate steps (read, add, and write), which means two concurrent threads can overwrite each other and cause a lost update.

I realized that a critical section requires mutual exclusion to prevent race conditions, so I implemented a ReentrantLock using the lock() / try / finally { unlock() } pattern to guarantee the lock is always released.

I understood how a semaphore tracks available resources and processes, allowing CPUs to block cleanly instead of wasting cycles in busy waiting.

What surprised me the most was that the starter code crashed immediately with a NullPointerException inside snapshot() even before running a single process.]

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

[The most challenging part was dealing with the initial compile errors—specifically duplicated lines in add(), a finally block placed before try, missing braces—along with the ClassNotFoundException.

It was difficult because multiple syntax and structural errors were tangled together in unfamiliar starter code, making it tricky to isolate the root cause of each issue before I could even begin testing the actual concurrency logic.]

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

[I overcame these hurdles by carefully reading the compiler error messages and relying on the IDE's Problems panel to locate every issue.

I focused on fixing one problem at a time and ran the program repeatedly to verify each incremental change.

When I got stuck, I asked an AI assistant for help, making sure to read through and understand every single line of code rather than just copying the fix.]

## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

[Bank transfer: An account balance is shared data that multiple transactions might access at once, so a lock is needed to protect it—just like how ctxLock protects shared state in my code.

Ticket/seat booking: Two users must never be allowed to claim the same seat simultaneously, which mirrors how poll() safely retrieves and removes an item so only one thread gets it.

Print queue: Printers sit idle and wait until print jobs arrive in the queue, which works just like a semaphore initialized with a value of 0 that blocks threads until a resource becomes available.]

### Optional: What would you like to learn more about?

[Any topics related to synchronization or operating systems that you're curious about?]

### Optional: How confident do you feel about synchronization concepts now?

[Beginner / Intermediate / Confident. What do you understand well? What needs more practice?]

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

[In the original starter, all four CPUs crashed with a NullPointerException in ReadyQueue.snapshot(), so no process ran and the verification block showed observed = 0 for the three counters (expected 29, 14 and 67759). After I fixed only the ready queue (Feature 1), the counters still had lost updates: context switches were 25 instead of 29, and total service time was 61759 instead of 67759. A lost update happens because contextSwitchCount++ is three steps: read, RaceWindow.pause(), write. The same bug can happen on a real machine without RaceWindow because count++ is not one atomic instruction, and a thread can be preempted or run on another core between the read and the write. It is hard to detect because it happens rarely and randomly, and the program often looks correct.]

Verification block of the **original starter**:
```
[
Exception in thread "CPU-3" Exception in thread "CPU-4" Exception in thread "CPU-2" Exception in thread "CPU-1" java.lang.NullPointerException: Cannot read field "next" because "this.next" is null
        at java.base/java.util.LinkedList$ListItr.next(Unknown Source)
        at ReadyQueue.snapshot(SchedulerSimulationSync.java:151)
        at CpuWorker.run(SchedulerSimulationSync.java:280)

  Context switches (quanta executed)     expected 29       observed 0        ✘ MISMATCH
  Completed processes                    expected 14       observed 0        ✘ MISMATCH
  Total service time (ms)                expected 67759    observed 0        ✘ MISMATCH
  Busy-waiting polls (must be 0)         expected 0        observed 0        ✔]
```

Verification block of **my final version**:
```
[
  Context switches (quanta executed)     expected 29       observed 29       ✔
  Completed processes                    expected 14       observed 14       ✔
  Total service time (ms)                expected 67759    observed 67759    ✔
  Busy-waiting polls (must be 0)         expected 0        observed 0        ✔
  ✔ All shared values are consistent.
]
```

**Explanation of the timeline:**
[1. CPU-1 reads contextSwitchCount = 12 into tmp.
2. RaceWindow.pause() simulates a preemption, so CPU-1 waits.
3. CPU-2 also reads contextSwitchCount = 12 (it is still 12).
4. CPU-1 writes 13.
5. CPU-2 writes 13 (it overwrites CPU-1's result).
Two increments happened but the counter only increased by one, so one update is lost.]

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

[I protected the ready queue methods (add, poll, processOf, snapshot) with queueLock, and each counter and its getter with its own lock: ctxLock, completedLock and serviceLock. I used one lock per variable because the counters are independent, so updating contextSwitchCount does not need to block totalServiceTime; the trade-off is more code. The queue has a different lock because it protects different data (list and map), so statistics updates do not wait for queue operations. Mutual exclusion is guaranteed because only one thread can hold a ReentrantLock at a time. A default ReentrantLock is not fair, so bounded waiting is not strictly guaranteed, but our critical sections are very short.]

| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| `ReadyQueue.add()`, `poll()`, `processOf()`, `snapshot()` | `queueLock` | `list` and `map` are shared by all CPUs |
| `contextSwitchCount` (`incrementContextSwitch()`, `getContextSwitchCount()`) | `ctxLock` | read-modify-write can lose updates |
| `completedProcessCount` (`incrementCompletedProcess()`, `getCompletedProcessCount()`) | `completedLock` | read-modify-write can lose updates |
| `totalServiceTime` (`addServiceTime()`, `getTotalServiceTime()`) | `serviceLock` | read-modify-write can lose updates |
## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

[In the starter, an idle CPU called poll(), got null, slept 20 ms and tried again, which wastes CPU time (busy waiting). My starter crashed before this loop, so after Feature 1 only I saw Busy-waiting polls = 19 to 20. The value of my semaphore readyCount is the number of processes waiting in the ready queue; it starts at 0 because the queue is empty, and it becomes 14 after the 14 initial add() calls. When the last process completes, the CPU calls release(totalCPUs) to wake the blocked CPUs so they see that everything is finished and stop. Without it, they would stay blocked in acquire() forever and the watchdog would stop the program.

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*
    This is the Producer-Consumer problem (Bounded Buffer). The CPUs are consumers when they take a process with poll(), and they are also producers when they re-add an unfinished process with add(); main is a producer for the initial processes. For a bounded queue of capacity K, I would need three semaphores: empty = K, full = 0 and mutex = 1. A deadlock happens if a producer does wait(mutex) before wait(empty): when the queue is full, it holds the mutex while waiting for a free slot, but a consumer needs the mutex to remove an item, so both wait forever. I would prevent it by breaking the hold-and-wait condition: always call wait(empty) before wait(mutex).
**Classical problem and roles**:
[Name the problem; who is the producer, who is the consumer?]
    Producer-Consumer (Bounded Buffer). Producers: main (initial add) and CPUs (re-add unfinished processes). Consumers: CPUs (poll).
**Semaphores for a bounded queue (name and initial value)**:
[Name the three semaphores and their initial values.]
    empty = K (free slots), full = 0 (items in the queue), mutex = 1 (protects the queue).
**Deadlock scenario and prevention**:
[Describe the scenario and the necessary condition you would break.]

## Summary

**Key concepts I understood through these questions:**
1.A race condition loses updates because count++ is read-modify-write.
2.A ReentrantLock with try/finally gives mutual exclusion.
3. A counting semaphore lets threads block instead of busy waiting.


**Concepts I need to study more:**
1. Deadlock prevention in more complex cases.
2. Fair locks and bounded waiting.

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
