# lecture 14

## [00:00:09](https://youtu.be/EuvT7XlyT0k?t=9s) Introduction to Processes and Threads

In this video, the speaker introduces the topics of processes and threads. They discuss the differences between them and how they are defined.

* Processes have their own address space while threads share an address space.
* User level threads and kernel level threads are discussed.
* Multi-threaded applications are introduced as well as hybrid data structures.

## [00:02:08](https://youtu.be/EuvT7XlyT0k?t=128s) Inter-process Communication

The speaker discusses inter-process communication, which is communication between processes or threads. They explain that there is a synchronization problem when communicating between processes or threads.

* The operating system provides a way to achieve synchronization.
* Mutual exclusion must be supported by the operating system.
* Race conditions can occur when two or more processes are reading or writing shared data in memory.

## [00:06:05](https://youtu.be/EuvT7XlyT0k?t=365s) Race Conditions

The main problem with inter-process communication is race conditions. The speaker explains that if two or more processes are reading or writing shared data in memory, the final result depends on who runs first.

* A mutual exclusion mechanism must be used to prevent race conditions.
* An example of a race condition is shown in a multi-threaded application where different results occur each time it is run due to lack of sequencing/synchronization.

## [00:08:15](https://youtu.be/EuvT7XlyT0k?t=495s) Example of a Spoiler

In this section, the speaker talks about printed spoilers and asks if anyone remembers them.

* The speaker mentions printed spoilers but does not provide further details.

## [00:08:23](https://youtu.be/EuvT7XlyT0k?t=503s) Fuller Printer

The speaker asks why the printer is called Fuller.

* No answer is provided in this section.

## [00:08:44](https://youtu.be/EuvT7XlyT0k?t=524s) Princess Polish

The speaker jokes that someone should ask if the printer uses princess polish.

* This is a humorous comment with no further relevance to the topic at hand.

## [00:09:05](https://youtu.be/EuvT7XlyT0k?t=545s) Is Anyone Talking?

The speaker asks if anyone is talking, possibly indicating a pause or break in the conversation.

## [00:09:15](https://youtu.be/EuvT7XlyT0k?t=555s) Temporary Paint Job

The speaker introduces a process that temporarily stores print jobs until they are ready to be printed. They refer to it as a "demon" that waits for print jobs and prints them when they are available.

* The demon waits for someone to give it print jobs.
* Whenever there is a print job, it prints it.
* There is a directory where these print jobs are stored.
* The demon waits until there are new files in this directory before printing them out.

## [00:09:28](https://youtu.be/EuvT7XlyT0k?t=568s) Spoiler Directory

The speaker explains how the spoiler directory works by giving an example of two processes, A and B, submitting files to the directory.

* Process A submits a file by writing its name to position 7 in the directory.
* The value of n is incremented to 8 after process A writes its file name.
* Process B also submits a file by writing its name to position 7 in the directory.
* If both processes submit their files at the same time, they may write to the same position in the directory and overwrite each other's files.

## [00:10:32](https://youtu.be/EuvT7XlyT0k?t=632s) Page View and Searchers

The speaker mentions "page view" and "searchers," but it is unclear what they are referring to.

## [00:10:44](https://youtu.be/EuvT7XlyT0k?t=644s) Number 52

The speaker briefly mentions number 52, but it is unclear what they are referring to.

## [00:10:53](https://youtu.be/EuvT7XlyT0k?t=653s) Okay

The speaker says "okay" with no further context or explanation.

## [00:10:56](https://youtu.be/EuvT7XlyT0k?t=656s) Dangerous Button

The speaker warns that a button is dangerous and should not be pushed.

## [00:11:12](https://youtu.be/EuvT7XlyT0k?t=672s) Sense of Humor

The speaker mentions having a sense of humor, possibly indicating another humorous comment or joke.

## [00:11:24](https://youtu.be/EuvT7XlyT0k?t=684s) Is

The speaker says "is" with no further context or explanation.

## [00:11:32](https://youtu.be/EuvT7XlyT0k?t=692s) Testament People

The speaker mentions "testament people," but it is unclear what they are referring to.

## [00:12:01](https://youtu.be/EuvT7XlyT0k?t=721s) No

The speaker says "no" with no further context or explanation.

## [00:12:11](https://youtu.be/EuvT7XlyT0k?t=731s) Let's Be Um

The speaker starts a new thought by saying "let's be um."

## [00:13:07](https://youtu.be/EuvT7XlyT0k?t=787s) Please

The speaker says "please" with no further context or explanation.

## [00:13:10](https://youtu.be/EuvT7XlyT0k?t=790s) Music

Music plays in the background, but there is no relevant content during this time.

## \[00:14:49]\(https://youtu.be/EuvT7XlyT0k?t=889s

## [00:20:28](https://youtu.be/EuvT7XlyT0k?t=1228s) Buffering Solution

In this section, the speaker discusses a solution to buffering issues. They suggest using a flag and incrementing its value in y1, then making it zero at the end. However, they encounter problems with their wired connections and decide to try another computer.

* Speaker suggests using a flag to solve buffering issues
* Encounters problems with wired connections and switches to another computer

## [00:28:25](https://youtu.be/EuvT7XlyT0k?t=1705s) Locking Solution

The speaker proposes a locking solution for concurrent access to shared resources. They suggest using an integer lock that is initially set to zero and running an infinite loop while lock is not equal to zero. At the end of the critical section, lock becomes one, and at the end of the next critical section, lock becomes zero again.

* Speaker proposes locking solution for concurrent access
* Suggests using an integer lock that alternates between 0 and 1

## [00:30:23](https://youtu.be/EuvT7XlyT0k?t=1823s) Problem with Locking Solution

The speaker acknowledges that there is still a problem with their proposed locking solution. If a context switch occurs while two processes are accessing shared resources, they will be writing to the same position in memory.

* Speaker acknowledges problem with proposed locking solution
* Context switch can cause two processes to write to same position in memory

## [00:31:54](https://youtu.be/EuvT7XlyT0k?t=1914s) Running Loops and Critical Regions

In this section, the speaker discusses running loops and critical regions. They explain that if two processes are running a loop at the same time, they will both see luck as zero and switch to another line. The speaker then explains that while doing something critical, one should not get a switch. They suggest telling the operating system that you are entering a critical region.

* Both processes will see luck as zero if they run the loop simultaneously
* While doing something critical, one should not get a switch
* Tell the operating system that you are entering a critical region

### [00:33:21](https://youtu.be/EuvT7XlyT0k?t=2001s) Entering and Leaving Critical Region

The speaker explains how to enter and leave a critical region by using specific lines of code. They also mention that no two processes can be in their critical regions at the same time.

* Use "enter critical region" and "leave critical region" lines of code
* No two processes can be in their critical regions at the same time

### [00:34:10](https://youtu.be/EuvT7XlyT0k?t=2050s) Mutual Exclusion

The speaker defines mutual exclusion as ensuring that only one person is using shared variables or files at any given time. They also discuss global variables and how nobody else can use them while someone is inside a critical section.

* Mutual exclusion ensures only one person uses shared variables or files
* Nobody else can use global variables while someone is inside a critical section

### [00:36:08](https://youtu.be/EuvT7XlyT0k?t=2168s) Rules for Critical Regions

The speaker outlines four rules for critical regions. They explain that no two processes can be simultaneously inside the critical region, and that assumptions cannot be made about the speeds or number of CPUs. Additionally, if one process is blocking another from entering a critical region, it can only do so while it is inside its own critical region.

* No two processes can be simultaneously inside the critical region
* Assumptions cannot be made about the speeds or number of CPUs
* If one process is blocking another from entering a critical region, it can only do so while it is inside its own critical region

## [00:39:32](https://youtu.be/EuvT7XlyT0k?t=2372s) Critical Regions

This section discusses critical regions and the issues that can arise when multiple processes try to access them simultaneously.

* A process should not have to wait forever to enter a critical region.
* If a process is running inside the critical region, another process trying to enter it will be blocked until the first one leaves.
* This is called inter-process communication or synchronization and must be managed carefully.

## [00:40:05](https://youtu.be/EuvT7XlyT0k?t=2405s) Examples of Critical Regions

This section provides examples of critical regions and how they work in multi-process programming.

* Process A is running inside the critical region while Process B tries to enter it but cannot until Process A leaves.
* There are many good libraries for inter-process communication as synchronization.

## [00:41:12](https://youtu.be/EuvT7XlyT0k?t=2472s) Operating System's Role in Inter-Process Communication

This section discusses the role of operating systems in managing inter-process communication.

* The chapter focuses on the operating system's role in inter-process communication.
* Many issues can arise with inter-process communication, which must be managed carefully.

## [00:41:55](https://youtu.be/EuvT7XlyT0k?t=2515s) Busy Waiting

This section defines busy waiting and its use in multi-process programming.

* Busy waiting involves continuously testing a variable until some value appears.
* It is used when waiting for something to happen, but it can lead to infinite loops if not done correctly.
* Spin locks involve spinning a loop until a lock becomes available.

## [00:43:04](https://youtu.be/EuvT7XlyT0k?t=2584s) Achieving Mutual Exclusion

This section discusses proposals for achieving mutual exclusion in multi-process programming.

* Disabling all interrupts can prevent a process from being interrupted while running inside a critical region.
* However, this is not available to regular users and may not work with multiple CPUs.
* Busy waiting with strict alternation involves checking the value of a lock and incrementing it until it becomes zero.

## [00:44:45](https://youtu.be/EuvT7XlyT0k?t=2685s) Disabling Interrupts

This section discusses disabling interrupts as a solution for achieving mutual exclusion.

* Disabling interrupts is used by the kernel to achieve mutual exclusion.
* However, it is not available to regular users and may not work with multiple CPUs.
* Other mechanisms can be used to achieve mutual exclusion in multi-process programming.

## [00:47:41](https://youtu.be/EuvT7XlyT0k?t=2861s) Register Zero

In this section, the speaker talks about how to reduce the zero and make a copy of it. They explain that they will store R1 back to lock and check the value of r0. If it is zero, then they can go to the critical region; otherwise, they will stay in here.

* Reduce the zero and make a copy of it
* Store R1 back to lock
* Check the value of r0
* Go to critical region if r0 is zero

### [00:48:25](https://youtu.be/EuvT7XlyT0k?t=2905s) Atomic Value

The speaker explains that atomic value plus blasting will be executed using multiple instructions. If there is a switch between any of these instructions, synchronization problems and race issues may occur.

* Atomic value plus blasting uses multiple instructions
* Switching between instructions can cause synchronization problems and race issues

### [00:49:19](https://youtu.be/EuvT7XlyT0k?t=2959s) High-Level Features

The speaker discusses how using high-level features like lock++ for C++ may be efficient but not just a single SME instruction. It involves multiple exam instructions which makes it vulnerable.

* High-level features like lock++ are efficient but involve multiple exam instructions
* Multiple exam instructions make it vulnerable

## [01:01:48](https://youtu.be/EuvT7XlyT0k?t=3708s) Mutual Exclusion Required

In this section, the speaker emphasizes that mutual exclusion is required without which we run into race issues. They also mention some technical difficulties with their other computer.

* Mutual exclusion is required to avoid race issues
* Technical difficulties with other computer mentioned

### [01:02:26](https://youtu.be/EuvT7XlyT0k?t=3746s) Technical Difficulties

The speaker mentions that their other computer started working too and they will join from the other one as well.

* Other computer started working too
* Speaker will join from the other computer as well

### [01:04:31](https://youtu.be/EuvT7XlyT0k?t=3871s) Screen Sharing Issues

The speaker has trouble sharing their screen with the audience and tries different methods to fix it.

* Speaker has trouble sharing their screen
* Different methods tried to fix the issue

## [01:09:11](https://youtu.be/EuvT7XlyT0k?t=4151s) Technical Difficulties Continue

In this section, the speaker continues to have technical difficulties with sharing their screen and communicating with the audience.

* Technical difficulties continue with sharing screen and communication

## [1:11:13](https://youtu.be/EuvT7XlyT0k?t=4273s) Understanding Race Conditions

In this section, the speaker discusses race conditions and how they can cause issues in a program. They provide an example of a program where threads are not starting in the expected order.

* Threads may not start in the expected order due to race conditions.
* Inconsistencies can occur when running a program multiple times.
* Synchronization is needed to prevent race conditions.

### [1:13:20](https://youtu.be/EuvT7XlyT0k?t=4400s) Strict Alternation

The speaker explains strict alternation as a software-only solution for synchronization between two processes running infinite loops. The first line of each loop checks for a global shared variable called "turn". If turn is not zero or one, the process waits until it becomes zero or one respectively. Once inside the critical region, the process sets turn to its opposite value before exiting.

* Strict alternation is a software-only solution for synchronization.
* Processes wait until turn becomes zero or one before entering critical regions.
* Turn is set to its opposite value after exiting critical regions.

### [1:17:29](https://youtu.be/EuvT7XlyT0k?t=4649s) Violating Rule 3

The speaker explains that their implementation of strict alternation violates rule 3, which states that no process running outside the critical region may block other processes. This violation occurs because changing turn's value blocks other processes from entering their critical regions.

* Violating rule 3 means that no process outside the critical region can block other processes.
* Changing turn's value blocks other processes from entering their critical regions.

## [1:18:49](https://youtu.be/EuvT7XlyT0k?t=4729s) Critical Region

This section discusses the concept of a critical region and how it affects processes.

* A process cannot enter a critical region if another process is already inside.
* If a process is in the critical region, it cannot change its turn value to one until it exits the critical region.
* If a process is outside the critical region, it can change its turn value to one even if another process is still inside.

### [1:19:25](https://youtu.be/EuvT7XlyT0k?t=4765s) Mutual Exclusion Violation

This section explains how mutual exclusion rules are violated when using strict alternation for accessing the critical region.

* If one process runs slower than others, other processes will have to wait for it even though the critical region is available.
* This problem occurs because of long non-critical regions that take time to complete.

### [1:21:53](https://youtu.be/EuvT7XlyT0k?t=4913s) Coordination Problem

This section discusses how coordination problems arise when using strict alternation for accessing the critical region.

* The mutual exclusion rules are violated because slow processes make fast ones wait even though the critical region is available.
* No process running outside of the critical region may block other processes from entering it.

### [1:22:50](https://youtu.be/EuvT7XlyT0k?t=4970s) Patterson's Solution

This section introduces Patterson's solution for achieving mutual exclusion without violating coordination rules.

* The solution involves creating two waiting rooms with doors that lead to each other and to the main room.
* Processes check if anyone else is in their waiting room before entering or leaving.

## [1:26:19](https://youtu.be/EuvT7XlyT0k?t=5179s) Process Number and Leave Region

In this section, the speaker introduces process number zero and leave region process number zero. The same thing happens with process number one.

* Two processes are introduced
* Leave region is mentioned

## [1:27:08](https://youtu.be/EuvT7XlyT0k?t=5228s) Global Variable Term

The speaker mentions a global variable term and an array of integers interested with two elements in it. Interested is set to false for both processes at the beginning.

* Global variable term is introduced
* Array of integers interested is introduced
* Interested is set to false for both processes

## [1:28:19](https://youtu.be/EuvT7XlyT0k?t=5299s) Running Processes

Process zero and one are running, with other being one minus process. Interested zero being true means that process number zero is in the waiting room and wants to go into the critical region.

* Process zero and one are running
* Other is defined as one minus process
* Interested zero being true means that process number zero wants to go into the critical region

## [1:30:02](https://youtu.be/EuvT7XlyT0k?t=5402s) Turn Process

Turn is a global variable that can be changed by other processes. If somebody else changes it, then turn can be different than the current process.

* Turn is a global variable that can be changed by other processes

## [1:34:40](https://youtu.be/EuvT7XlyT0k?t=5680s) Synchronization Problem

In this section, the speaker discusses a synchronization problem and how to solve it.

* If one process changes the turn, then another process waiting for the turn will wait until the other process sees that it has changed.
* When leaving the region, set interest to false so others become false. Then create a loop and enter if signature is true.
* If all processes are doing the same thing, nobody enters the room and they wait indefinitely.
* The solution is to enter critical region before other processes do.

## [1:38:13](https://youtu.be/EuvT7XlyT0k?t=5893s) Generalizing Virtual Exclusion

The speaker talks about generalizing virtual exclusion with busy waiting.

* To generalize virtual exclusion with busy waiting for multiple processes, extend two-process solution to an array of shared variables.
* Keep track of which processor wants to enter critical region with interested variable and use turn variable to determine whose turn it is.
* Use while loop until no other process is interested in entering critical region.

## [1:40:14](https://youtu.be/EuvT7XlyT0k?t=6014s) Entering Critical Region

The speaker explains how to enter critical region using code examples.

* Set interest to true when entering critical region.
* While J is not equal to I (process number), increment J by 1 (modular two).
* Wait on process J until it's no longer interested, then make turn J turn and continue at critical reason.
* Exit critical reason by setting interest to false.

## [1:42:31](https://youtu.be/EuvT7XlyT0k?t=6151s) Single Sentence Asset

In this section, the speaker talks about the importance of having a single sentence asset to prevent race conditions. They discuss the need for mutual exclusion in enterprise communications.

* A single sentence asset is necessary to prevent race conditions.
* Mutual exclusion is needed in enterprise communications to ensure that multiple processes cannot access a shared resource at the same time.

### [1:44:10](https://youtu.be/EuvT7XlyT0k?t=6250s) Using GPT

The speaker discusses using GPT as a tool for learning and asking questions. They caution that while GPT can be helpful, it may not always provide accurate or relevant answers.

* GPT can be used as a tool for learning and asking questions.
* Sometimes GPT provides inaccurate or out-of-context answers.
* Asking questions at the end of book chapters can help determine if GPT is providing accurate answers.

### [1:45:05](https://youtu.be/EuvT7XlyT0k?t=6305s) Do You Need Help?

The speaker addresses the question of why someone might need their help if resources like books and videos are readily available. They explain that they are there to assist with understanding rather than teaching new material.

* The speaker is available to assist with understanding rather than teaching new material.
* Resources like books and videos are readily available for learning.
