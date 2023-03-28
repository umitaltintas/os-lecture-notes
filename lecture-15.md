# lecture 15

## [00:00:02](https://youtu.be/nbvUPbMjuII?t=2s) Introduction to Mutual Exclusion with Busy Waiting Paterson Solution

In this lecture, the instructor introduces Mutual Exclusion with Busy Waiting Paterson Solution as a software-only solution for avoiding race conditions. The main idea is to use a variable called "turn" to check if another process is working on the critical region before entering it.

* Before entering the critical region, call a function after waiting.
* When leaving the critical region, call another function.
* Busy waiting or spin lock happens when one process waits for another to complete its task.

### [00:01:08](https://youtu.be/nbvUPbMjuII?t=68s) Main Idea of Mutual Exclusion with Busy Waiting Paterson Solution

The main idea of Mutual Exclusion with Busy Waiting Paterson Solution is to make the variable turn your process numbers and check if the turn is the same as yours. If somebody else is working on the turn, then wait until they are done.

### [00:02:12](https://youtu.be/nbvUPbMjuII?t=132s) Alternatives to Busy Waiting

There are several alternatives to busy waiting for mutually exclusive processes:

* Disabling interrupts
* Using log variables
* Stick alternation
* Strict alternation

However, strict alternation has a problem where one process takes longer than others in completing non-critical regions, causing other processes to wait indefinitely.

### [00:05:13](https://youtu.be/nbvUPbMjuII?t=313s) Reconciliation and Critical Region Rules

Reconciliation occurs when one process takes longer than others in completing non-critical regions. This causes other processes to wait even though there are no processes in the critical region. Critical region rules state that no process running outside of a critical region may block another process.

### [00:07:23](https://youtu.be/nbvUPbMjuII?t=443s) Importance of Checking Process Equality

It is important to check the process equality when using the turn variable for mutual exclusion. If another process changes the value of turn, then we cannot enter the critical region.

## [0:09:33](https://youtu.be/nbvUPbMjuII?t=573s) Introduction to Critical Regions

In this section, the speaker introduces the concept of critical regions and explains why they are important in concurrent programming.

* Critical regions are sections of code that must be executed atomically to avoid race conditions.
* Race conditions occur when multiple processes access shared resources simultaneously, leading to unpredictable behavior.
* The goal of concurrent programming is to ensure that processes can execute concurrently without interfering with each other.

## [0:09:42](https://youtu.be/nbvUPbMjuII?t=582s) Entering a Critical Region

The speaker discusses how to enter a critical region and what happens if another process is already inside.

* To enter a critical region, a process must first check if it is safe to do so.
* If no other process is currently inside the critical region, then the process can enter without issue.
* However, if another process is already inside, then the waiting process must wait until it is safe to enter.

## [0:11:01](https://youtu.be/nbvUPbMjuII?t=661s) Waiting for Entry into a Critical Region

The speaker explains how a waiting room can be used to manage access to a critical region.

* When a process wants to enter a critical region but finds that another process is already inside, it enters a waiting room instead of blocking indefinitely.
* While in the waiting room, the process periodically checks if it is safe to enter the critical region.
* If another process leaves the critical region and there are no other processes in line ahead of it, then the waiting process can safely enter.

## [0:12:14](https://youtu.be/nbvUPbMjuII?t=734s) Checking Turn Status

The speaker discusses how turn status can be used to manage access to a critical region.

* Turn status is a global variable that indicates which process has the right to enter the critical region.
* When a process wants to enter the critical region, it first checks if it is its turn.
* If it is not its turn, then it enters the waiting room until its turn arrives.
* However, if it is its turn and no other processes are in line ahead of it, then it can safely enter.

## [0:14:03](https://youtu.be/nbvUPbMjuII?t=843s) Preventing Deadlock

The speaker explains how checking for other interested processes can prevent deadlock.

* If two processes are both interested in entering the critical region but neither has priority over the other, they may end up deadlocked in the waiting room.
* To prevent this, each process should check if any other processes are also interested before entering the waiting room.
* If another process is already waiting, then the current process should wait until that process has entered or left the critical region.

## [00:17:27](https://youtu.be/nbvUPbMjuII?t=1047s) Waiting Room Algorithm

In this section, the speaker explains an algorithm for entering a critical region when there are multiple waiting rooms.

* When entering the waiting room, immediately check if the other room is occupied.
* If it is occupied, continue without waiting into the critical region.
* If it is not occupied, wait until it becomes available before entering.

## [00:17:48](https://youtu.be/nbvUPbMjuII?t=1068s) Refining the Algorithm

The speaker refines the algorithm from the previous section and provides more details on how to enter a critical region.

* If there is someone in the other waiting room, wait until they leave before checking again.
* If there is no one in the other waiting room, proceed to check if it's your turn to enter.
* If it's not your turn yet, don't check again and continue waiting in your own waiting room.

## [00:18:25](https://youtu.be/nbvUPbMjuII?t=1105s) Mutual Exclusion with Busy Waiting

The speaker introduces mutual exclusion with busy waiting as another way of solving synchronization problems.

* In this method, each process repeatedly checks a shared variable until it becomes available.
* This creates a spin lock where processes are constantly checking for access to a resource.

## [00:19:02](https://youtu.be/nbvUPbMjuII?t=1142s) Test-and-set Instruction

The speaker introduces the test-and-set instruction as a way of implementing mutual exclusion with busy waiting more efficiently.

* The test-and-set instruction reads a memory word (lock), puts its value into a register (RX), and sets lock to 1 atomically.
* This ensures that only one process can access the critical region at a time.

## [00:19:50](https://youtu.be/nbvUPbMjuII?t=1190s) Using Test-and-set Instruction in Assembly

The speaker explains how to use the test-and-set instruction in assembly language to implement mutual exclusion with busy waiting.

* When entering the critical region, call the enter\_region function.
* The function copies the value of lock into RX and checks if it's 0 (unlocked).
* If it's 0, set lock to 1 and enter the critical region.
* If it's not 0, keep checking until it becomes available before entering.

## [0:25:43](https://youtu.be/nbvUPbMjuII?t=1543s) Mutual Exclusion and TSL Instruction

In this section, the speaker discusses mutual exclusion and the Test-and-Set-Lock (TSL) instruction.

* The TSL instruction is used to implement mutual exclusion in hardware-supported systems.
* The speaker explains how the TSL instruction works by moving a copy of a block to a register, copying one to lock, comparing them, and entering an infinite loop until someone makes lock zero.
* This solution is simpler and more efficient than other solutions that require keeping an interested array or waiting rooms.
* The TSL instruction generalizes to end processes without any modification.
* CPUs must provide the TSL instruction or something similar for hardware-supported mutual exclusion.

### [0:27:48](https://youtu.be/nbvUPbMjuII?t=1668s) Exchange Instruction

The speaker discusses another way to implement mutual exclusion using the exchange instruction.

* The exchange instruction swaps values between a register and a memory location.
* It can be used to observe values of memory locations with registers.
* The speaker demonstrates how it works by copying A1 to their register, exchanging one with the lock if lock is one before, then comparing register with zero. If they are not equal, they will enter an infinite loop until someone makes lock zero.
* Both TSL and exchange instructions are atomic and perform similarly.

### [0:31:11](https://youtu.be/nbvUPbMjuII?t=1871s) Address Solution

The speaker briefly mentions an address solution for implementing mutual exclusion when hardware support is not available.

* This solution requires using addresses instead of instructions but is more expensive than using hardware-supported solutions like TSL or exchange instructions.

### [0:33:03](https://youtu.be/nbvUPbMjuII?t=1983s) TSL vs Exchange

The speaker clarifies the difference between TSL and exchange instructions.

* Both instructions are designed for synchronization, but TSL is primarily used for synchronization while exchange is a more general-purpose instruction.
* Some systems may have both TSL and exchange instructions available.

## [00:35:01](https://youtu.be/nbvUPbMjuII?t=2101s) TSL and Swapping

In this section, the speaker discusses the use of Test-and-Set Lock (TSL) for synchronization and swapping. They also explore whether swapping can be used instead of TSL.

* TSL is designed purely for synchronization.
* Swapping is different from TSL as it swaps the values of two registers and a lock.
* If you want to use Exchange for synchronization, you have to move one value to register and do this which is more expensive than a single instruction.
* Exchange can be used to exchange register values too.

### [00:39:04](https://youtu.be/nbvUPbMjuII?t=2344s) Intel Platform and TSL

The speaker talks about whether Intel platform has TSL or not. They also discuss how Exchange was a solution for inter-platform instructions.

* The speaker is not sure if they have TSL in entire environment then they have to use exchange.
* It's possible that TSL may be patented, which could explain why it's not available on all platforms.
* The Intel platform may not have PSL but Exchange was a solution for inter-platform instructions.

## [00:40:26](https://youtu.be/nbvUPbMjuII?t=2426s) Wasted CPU Time with Spin Locks

In this section, the speaker discusses wasted CPU time with spin locks and suggests an alternative approach using sleep mode.

* Running a continuous loop while waiting for a lock wastes CPU time.
* Instead of running a loop, go to sleep until someone changes the lock variable in memory.
* Alternatively, whoever holds the lock should wake up others who are waiting on it.
* Two correct solutions are suggested - sending a message to chat or using Exchange instead of TSL.

## [00:42:25](https://youtu.be/nbvUPbMjuII?t=2545s) TSL and Busy Waiting Problem

The speaker discusses the busy waiting problem associated with TSL.

* TSL has a simple and efficient mechanism but suffers from a problem called the busy waiting problem.
* The busy waiting problem occurs because TSL is always making busy waiting while checking the register.
* Exchange, on the other hand, just copies the content and does not always check.

## [0:43:15](https://youtu.be/nbvUPbMjuII?t=2595s) Comparison of Exchange Instruction

This section discusses the comparison between DSL and Euro exchange. The speaker mentions that they are exactly the same, but he is not sure if the euro exchange is the same as their exchange instruction.

* The Euro exchange instruction may be different from their exchange instruction.

### [0:43:35](https://youtu.be/nbvUPbMjuII?t=2615s) Exchange Instruction with Registers and Memory

The speaker explains that in the context of destination source operands, it can be two general-purpose registers or a memory location. However, this does not talk about waiting.

* Exchange instruction can use two general-purpose registers or a memory location.
* It does not talk about waiting.

### [0:44:06](https://youtu.be/nbvUPbMjuII?t=2646s) Limitations of Chat GPT

The speaker talks about how chat GPT is good for trivial answers but fails when it comes to specific questions. He also mentions that if there are one or two correct answers somewhere, it doesn't have much ways of finding them.

* Chat GPT is good for trivial answers.
* It fails when it comes to specific questions.
* It cannot find one or two correct answers somewhere.

### [0:45:03](https://youtu.be/nbvUPbMjuII?t=2703s) Specific Questions and References

The speaker advises being careful when asking very specific questions to check GPT because it may run into problems. He also mentions that check GPT cannot provide web page addresses as references because maybe it doesn't know where the data is coming from.

* Be careful when asking very specific questions to check GPT.
* Check GPT cannot provide web page addresses as references.

### [0:45:55](https://youtu.be/nbvUPbMjuII?t=2755s) Good Questions for Check GPT

The speaker explains that check GPT can answer general questions such as what is a process or the difference between kernel level thread and user level thread. However, it may run into problems when answering specific questions.

* Check GPT can answer general questions.
* It may run into problems when answering specific questions.

### [0:46:48](https://youtu.be/nbvUPbMjuII?t=2808s) Busy Waiting with Exchange Instruction

The speaker clarifies that busy waiting is not true for build rating with exchange instruction. He also mentions that if it is used with the lock prefix, then there is another instruction called lock which might be used for that purpose.

* Busy waiting is not true for build rating with exchange instruction.
* If exchange instruction is used with the lock prefix, then there is another instruction called lock which might be used for that purpose.

### [0:49:40](https://youtu.be/nbvUPbMjuII?t=2980s) Spin Lock and CPU Time

The speaker explains that spin locks waste CPU time but they are acceptable for short reads especially on multiprocessors. He also mentions that going to sleep means making a system call which causes context switches and is expensive.

* Spin locks waste CPU time.
* They are acceptable for short reads especially on multiprocessors.
* Going to sleep means making a system call which causes context switches and is expensive.

## [00:50:47](https://youtu.be/nbvUPbMjuII?t=3047s) Introduction to Spin Locks

In this section, the speaker introduces the concept of spin locks and how they work.

* Spin locks are used to protect critical regions in code from being accessed by multiple processes at once.
* When a process enters a critical region, it acquires a lock. If another process tries to enter the same region while the lock is held, it will spin until the lock is released.
* This spinning wastes CPU time and can cause delays in other processes.

### [00:51:31](https://youtu.be/nbvUPbMjuII?t=3091s) Single CPU Case

The speaker discusses what happens when there is only one CPU available.

* When a process enters a critical region, it holds onto the lock until it completes its task.
* If another process tries to enter the same region while the lock is held, it spins and wastes CPU time.
* This spinning can cause delays in other processes and slow down overall system performance.

### [00:53:15](https://youtu.be/nbvUPbMjuII?t=3195s) Multiple CPU Case

The speaker discusses what happens when there are multiple CPUs available.

* When a process enters a critical region on one CPU, another process can run on another CPU without waiting for the lock to be released.
* This reduces wasted CPU time and improves overall system performance.
* However, spin locks should still be avoided as much as possible because they can cause delays and waste resources.

### [00:57:03](https://youtu.be/nbvUPbMjuII?t=3423s) Comparison of Single vs Multiple CPUs

The speaker compares how spin locks affect system performance with one versus multiple CPUs.

* With one CPU, spin locks waste 50% of the CPU's time and can cause delays in other processes.
* With multiple CPUs, spin locks waste less CPU time but should still be avoided as much as possible.
* Overall, spin locks are a suboptimal solution to protecting critical regions and should only be used when necessary.

## [0:59:33](https://youtu.be/nbvUPbMjuII?t=3573s) Priority Scheduling and Spin Locks

This section discusses the problem of priority inversion in spin locks, where a high-priority process is waiting for a low-priority process to release a lock. This can lead to an infinite loop and deadlock.

* Never schedule process B because its priority is lower than A's priority.
* Two processes with different priorities can cause problems with spin locks.
* Process H is running while L will never get its turn if H is runnable.
* Before H starts running, L is in a critical region doing some useful stuff.
* As soon as H starts running, it will run infinitely until L releases the lock.
* This situation is an example of a deadlock caused by priority scheduling and inversion.
* Multiple CPUs may not solve this specific problem if multiple high-priority processes are waiting for the same lock held by a low-priority process.

### [1:02:14](https://youtu.be/nbvUPbMjuII?t=3734s) Problems with Spin Locks

This section continues discussing the problems with spin locks and how they can cause issues in operating systems.

* Operating systems are complex pieces of software that can have problems arising from simple ideas like spin locks.
* Priority inversion can happen with spin locks, causing deadlocks and infinite loops.
* Multiple CPUs may not solve all problems caused by spin locks.

### [1:04:29](https://youtu.be/nbvUPbMjuII?t=3869s) Turing Test

This section briefly mentions the Turing test, which tests whether an agent (human or computer) can be distinguished from another human based on their responses to questions.

* The Turing test determines whether an agent is human or computer-based on their responses to questions.
