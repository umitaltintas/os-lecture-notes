# lecture 11

## [0:00:10](https://youtu.be/S4Mq0kEfmck?t=10s) Three States of a Process

Overview: A process can be in one of three states - running, blocked, or ready to run.

* Running process is using the CPU and executing its instructions.
* Ready process has a CPU but is waiting for its turn to execute.
* Blocked process is waiting for help from the operating system and cannot execute.

### [0:00:45](https://youtu.be/S4Mq0kEfmck?t=45s) Difference Between Running and Ready Process

* Running process is currently using the CPU while ready process is waiting for its turn to use it.
* A single CPU can only execute one running process at a time.

### [0:01:15](https://youtu.be/S4Mq0kEfmck?t=75s) Ridicule Queue

* The ridicule queue contains processes that are ready to run.
* When the CPU becomes available, the operating system picks a process from the ridicule queue to execute.

### [0:01:54](https://youtu.be/S4Mq0kEfmck?t=114s) Scheduling Decision

* The transition from ridicule queue to running state is called scheduling decision number three.
* The scheduler picks a process from the ridicule queue and lets it use the CPU.

### [0:02:28](https://youtu.be/S4Mq0kEfmck?t=148s) Transition from Running State to Ridicule Queue

Overview: Something happened that caused an interrupt.

### [0:03:03](https://youtu.be/S4Mq0kEfmck?t=183s) Interrupt Handling

Overview: An interrupt occurs when something needs attention from the operating system.

### [0:03:59](https://youtu.be/S4Mq0kEfmck?t=239s) Blocked Process

Overview: A blocked process is waiting for help from the operating system and cannot execute until it receives assistance.

### [0:04:57](https://youtu.be/S4Mq0kEfmck?t=297s) Block Queue

Overview:

* The block queue contains processes that are blocked and waiting for data or input/output operations.
* Demons such as printer demons are usually in this queue.

### [0:05:32](https://youtu.be/S4Mq0kEfmck?t=332s) Causes of Transitions

Overview:

Transition numbers correspond with different causes:

1. Process itself
2. Hardware interrupts
3. Scheduler (operating system)
4. Operating system

## [0:08:43](https://youtu.be/S4Mq0kEfmck?t=523s) Operating System Processes

Overview: This section discusses the producer-consumer model and how processes communicate with each other through the operating system. It also explains that there are no direct transitions between blocked and running states.

* The operating system is triggered by interrupts or other processes.
* In the producer-consumer model, one process produces data while another consumes it.
* Processes cannot directly talk to each other, so they must tell the operating system when data is ready.
* There are no direct transitions between blocked and running states because a blocked process needs data to be unblocked, which must be put in the queue for scheduling.

### [0:12:02](https://youtu.be/S4Mq0kEfmck?t=722s) Scheduler as a Process

* The scheduler is a process that decides which process to run next.
* It has top priority when it's ready because it needs to schedule other processes.
* Operating system processes behave similarly to regular processes but have different priorities and behaviors.
* The scheduler is usually written in assembly code and makes simple decisions based on first come first served or priority-based approaches.

### [0:14:57](https://youtu.be/S4Mq0kEfmck?t=897s) The Role of the Scheduler

Overview: This section explains that the scheduler is the lowest layer of the operating system and its main function is to pick a process from the queue and let it run.

* The scheduler is written mostly in assembly code and is not very complicated.
* Its main function is to decide which process should run next from the queue.
* Most of the time, this decision-making process follows a first come first served approach or uses priorities for some operating systems.

## [0:17:17](https://youtu.be/S4Mq0kEfmck?t=1037s) Handling Interrupts and Process Scheduling

Overview: This section discusses the handling of interrupts and how process scheduling is implemented in the kernel.

* Interrupt handling occurs frequently, so it is more efficient to handle them in the kernel.
* The scheduler handles interrupt handling and details of starting/stopping processors.
* Process scheduling is the lowest level of operating system and is crucial for managing processes.

### [0:17:56](https://youtu.be/S4Mq0kEfmck?t=1076s) Implementation of Processes

* Each computer has many processes that need to be managed.
* Data about each process is kept in a table called the process table, which is stored in kernel space.
* The process table contains information about the state of each process (running, ready, blocked), as well as its program counter, stack pointer, registers, open files, accounting and scheduling information.
* Memory management involves keeping track of pointers for text/code, stack, and data segments.
* File descriptors are only available for Unix-type operating systems.

### [0:23:02](https://youtu.be/S4Mq0kEfmck?t=1382s) Memory Management

* Memory is divided into text/code, stack, and data segments.
* Pointers are used to keep track of each segment.
* Other memory management tasks include root directory/working directory management and file descriptor management.

### [0:23:44](https://youtu.be/S4Mq0kEfmck?t=1424s) Process Table

* The process table contains a single entry for each process on a computer.
* It stores a large amount of information about each process such as its state (running/ready/blocked), program counter, stack pointer, registers, open files etc.

## [0:25:12](https://youtu.be/S4Mq0kEfmck?t=1512s) Handling Interrupts

Overview: This section discusses how interrupts are handled in the operating system.

* When an interrupt occurs, the interrupt handling function is called.
* The interrupt could be due to data being ready, which means a process waiting for data is now ready to run.
* The scheduler then decides which process to run next.

### [0:28:42](https://youtu.be/S4Mq0kEfmck?t=1722s) Implementation of Processes

Overview: This section explains how processes are implemented in the operating system.

* When a disk interrupt happens while a user process is running, the hardware stacks important registers automatically.
* Depending on the type of interrupt, the correct interrupt handler is selected from the interrupt table and saves the original program counter and program status word for that process.
* Assembly language procedures written by the operating system save registers and set up a new stack space in kernel space.
* The C interrupt service runs and handles any data created or received from external devices.
* The scheduler then decides which process to run next.

## [0:33:23](https://youtu.be/S4Mq0kEfmck?t=2003s) Understanding the Interrupt Controller

Overview: In this section, we learn about the interrupt controller and its role in operating systems.

* The interrupt controller is a part of the CPU that helps it handle interrupts.
* When an interrupt occurs, the interrupt controller stops the CPU from whatever it's doing and saves all relevant information to the stack.
* The interrupt controller is connected to the bus and is responsible for controlling interrupts.

### [0:34:00](https://youtu.be/S4Mq0kEfmck?t=2040s) Importance of Understanding Hardware

* It's important to understand hardware in order to understand what an operating system does.
* While high-level programming languages are preferred for writing operating system code, sometimes assembly language must be used to modify registers or save data to the process table.

### [0:35:31](https://youtu.be/S4Mq0kEfmck?t=2131s) Modeling Multiprogramming

Overview: This section discusses how multiprogramming works and how it can keep a CPU busy.

* Multiprogramming involves having multiple processes ready to run on a single CPU.
* If one process is running and n - 1 processes are ready, then there will always be enough processes available to keep the CPU busy.
* Processes can be in three states: running, ready, or blocked.
* If many processes are blocked and no other processes are ready, then CPU time will be wasted.
* By adding more processes, we can increase process utilization ratio.

## [0:42:28](https://youtu.be/S4Mq0kEfmck?t=2548s) CPU Efficiency

Overview: The speaker discusses the importance of CPU efficiency in operating systems, particularly for batch processing.

* Higher CPU efficiency is better for batch processing operating systems.
* Interactive operating systems require the CPU to be free most of the time.

### [0:43:02](https://youtu.be/S4Mq0kEfmck?t=2582s) Keeping CPU Free

* Speaker's CPU is almost 90% free despite running multiple tasks.
* Keeping the CPU free ensures that it stays interactive and responsive.

### [0:43:43](https://youtu.be/S4Mq0kEfmck?t=2623s) Multi-programming Calculation

* The calculation for multi-programming is 1 minus P to the N.
* For example, if P value is 80%, then the utilization is 96%.

### [0:45:25](https://youtu.be/S4Mq0kEfmck?t=2725s) IO Intensive Process

* A process that spends most of its time waiting for IO is an IO intensive process.
* Examples include editors like Excel or C program editor.

### [0:47:30](https://youtu.be/S4Mq0kEfmck?t=2850s) Processes That Keep CPU Busy

* A single process can keep the CPU 20% busy while two processes can keep it 40% busy.
* Three processes can keep the computer almost 90% busy.
* An example of a process that keeps the CPU busy all the time is a video player.

## [0:51:32](https://youtu.be/S4Mq0kEfmck?t=3092s) CPU Utilization

Overview: In this section, the speaker discusses how CPU utilization is affected by the amount of memory and processes in a computer.

* A computer with 8GB of memory can fit three processes plus the operating system.
* With 50% utilization, the CPU can be kept busy for 15% of the time.
* Increasing memory to 16GB allows for seven processes and an 80% utilization rate.
* Adding another eight gigabytes of memory only increases performance slightly.

### [0:57:59](https://youtu.be/S4Mq0kEfmck?t=3479s) Graphic Drivers as Intensive Applications

* Video games are intensive applications that use graphics drivers.
* Most of the time, video games are busy doing IO and pushing data to graphics cards.
* Graphics cards have their own CPUs (GPUs) and memory, making them another kind of computer.
* By keeping most data on the graphics card memory, CPUs are not as busy.

## [1:00:58](https://youtu.be/S4Mq0kEfmck?t=3658s) Playing Videos and GPU Usage

Overview: The speaker is trying to play a video while keeping another window on top. They open YouTube and observe the GPU usage while playing a video.

* The GPU usage starts jumping but it's not clear why.
* When the video window is obscured, it stops loading data, but when brought back into view, it loads more data.
* The CPU time doesn't change much during this process as most of the work is handled by the GPU.

## [1:03:31](https://youtu.be/S4Mq0kEfmck?t=3811s) Processes and Threads

Overview: The speaker explains the difference between processes and threads in an operating system.

* Processes are separate entities that have their own memory space.
* Each process has its own code (text), data, and stack sections in memory.
* Threads are parts of a process that share the same memory space as other threads in that process.
* Multiple threads can run seemingly at the same time using multi-programming techniques, even on a single CPU.
* Using threads can make programs more efficient and easier to design and implement.

## [1:09:22](https://youtu.be/S4Mq0kEfmck?t=4162s) Threads vs Processes

Overview: This section discusses the differences between threads and processes, including their address space, creation speed, and protection.

* Thread number one and thread number two are part of process number one (P1), while thread number one, thread number two, and thread number three are part of process number two (P2).
* T1 and T2 share the same address space of P2.
* Threads share the same address space and data of a single process.
* Threads are lighter and faster to create than processes (10 to 100 times faster).
* Making a new process is expensive compared to making a new thread.
* There is no protection between threads, unlike processes that have hardware protection.

### [1:11:15](https://youtu.be/S4Mq0kEfmck?t=4275s) Memory Sharing

* Threads share memory with each other but not with other processes.
* When creating a new thread, there is no need to copy any memory.
* When creating a new process from an existing process, it requires copying the entire memory.

### [1:12:05](https://youtu.be/S4Mq0kEfmck?t=4325s) Protection Between Threads

* There is no protection between threads in terms of accessing each other's memory.
* Protection is necessary between different processes as they have separate address spaces protected by hardware.
* The lack of protection between threads means that they cannot guarantee that they will not interfere with each other.

### [1:14:00](https://youtu.be/S4Mq0kEfmck?t=4440s) Cooperation vs Competition

Overview: This section explains how multi-threaded programs cooperate while multi-process programs compete for resources.

* Multi-threaded programs cooperate since they try to help each other out by sharing data.
* Multi-process programs compete for resources such as CPU time or memory since they have different tasks to run.
* If all threads are CPU-bound, then there may be no performance gain from using multi-threaded applications.

### [1:16:08](https://youtu.be/S4Mq0kEfmck?t=4568s) Word Processors

Overview: This section discusses word processors and their competition in the market.

* Microsoft Word dominates the commercial word processor market.
* Other competitors include open-source applications like LibreOffice.
* Microsoft was a latecomer in this game before which there were competitors like WordPerfect and WordStar.

## [1:17:41](https://youtu.be/S4Mq0kEfmck?t=4661s) Three Threads for Document Editor

Overview: In this section, the speaker discusses the use of three threads in a document editor. One thread is responsible for keyboard inputs, another for updating the screen based on changes made by other threads, and the third for taking backups.

* The keyboard input thread handles new character insertion and deletion.
* The screen update thread updates the screen based on changes made by other threads.
* The backup thread takes backups without disrupting other threads.

### [1:19:03](https://youtu.be/S4Mq0kEfmck?t=4743s) Backup Priority

Overview: In this section, the speaker discusses how backup priority is handled in a document editor with multiple threads.

* Taking backups is second priority after handling keyboard input and updating the screen.
* Backups are taken only when the other two tasks are not running.

### [1:20:00](https://youtu.be/S4Mq0kEfmck?t=4800s) Sharing Data Between Threads

Overview: In this section, the speaker explains how sharing data between threads can be difficult when using multi-process architecture.

* All three threads share the same document data.
* It's difficult to share data between processes without loss of operating system up.

### [1:20:27](https://youtu.be/S4Mq0kEfmck?t=4827s) Benefits of Using Threads

Overview: In this section, the speaker highlights one example where using threads can be useful.

* Using multiple threads can make it easier to design, implement and test an application that requires parallel processing.

### [1:20:49](https://youtu.be/S4Mq0kEfmck?t=4849s) Quiz Time

Overview: In this section, the speaker announces that it's time for a quiz and leaves.
