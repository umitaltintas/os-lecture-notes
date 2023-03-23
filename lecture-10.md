# lecture 10

## [0:00:11](https://youtu.be/sXXYGEnkTwk?t=11s) Introduction to Micro Kernels

Overview: The main idea of a micro kernel is to keep the kernel small, which reduces the chances of having bugs in the operating system. This section explains why this is important and how it works.

* Keeping the kernel small reduces the chances of bugs
* Human beings make mistakes every 10,000 lines of code
* A micro kernel operating system keeps its kernel to around 10,000 lines of code
* Minix 3 is an example of a micro kernel operating system

### [0:01:41](https://youtu.be/sXXYGEnkTwk?t=101s) What Does a Micro Kernel Do?

Overview: This section explains what functions are handled by a micro kernel and what runs in user mode.

* A micro kernel handles interrupts, process scheduling, and inter-process communication
* Drivers for networking, file systems, etc. run in user mode
* Accessing hardware requires a system call which can be expensive

### [0:04:21](https://youtu.be/sXXYGEnkTwk?t=261s) Client Server Model

Overview: This section introduces the client-server model used in micro kernels.

* High-level functions like file systems and drivers are kept outside the kernel
* Clients ask the kernel or servers to perform tasks
* Communication between clients and servers is done through message passing

### [0:05:36](https://youtu.be/sXXYGEnkTwk?t=336s) Message Passing and Inter-process Communication

Overview: This section explains how communication between clients and servers is done through message passing.

* Clients and servers can be on different computers or on the same computer
* Message passing is used for inter-process communication

## [0:08:40](https://youtu.be/sXXYGEnkTwk?t=520s) Introduction to VM370

Overview: The VM370 operating system is a simple operating system that only knows about traps and hardware access. It can do some memory management and process values, but most of the complicated operating system stuff is done in CMS.

* The idea of virtual machine environments was present from the beginning.
* In the 1970s, running three copies of CMS on top of a single hardware had advantages such as efficient use of CPU time and renting out unused resources to other companies.
* Virtual machines became popular in the PC world in the 2010s when Intel processors started supporting virtualization.

### [0:09:39](https://youtu.be/sXXYGEnkTwk?t=579s) Advantages of Running Multiple Copies of an Operating System

* Running multiple copies of an operating system on the same hardware allows for isolation between them. If one crashes, it does not affect the others.
* Efficient use of CPU time by renting out unused resources to other companies.

### [0:12:03](https://youtu.be/sXXYGEnkTwk?t=723s) Popularity of Virtual Machines in PC World

* Virtual machines became popular in the PC world in the 2010s when Intel processors started supporting virtualization.
* Windows operating systems now come with a Linux kernel running as a separate guest operating system on top of a hypervisor.

### [0:13:01](https://youtu.be/sXXYGEnkTwk?t=781s) Execution Modes and Privileged Instructions

* When an operating system running on a virtual machine executes a privileged instruction, it is trapped to the virtual machine monitor so that it can be emulated in software.
* There are two types of hypervisors - type 1 and type 2.

### [0:16:04](https://youtu.be/sXXYGEnkTwk?t=964s) Conclusion

Overview: A chapter about virtualization and containerization will be discussed at the end of the semester.

## [0:16:16](https://youtu.be/sXXYGEnkTwk?t=976s) User Mode vs Kernel Mode

Overview: This section discusses the limitations of using a single processor for multiple processes in kernel mode.

* In user mode, there is no problem with multiple users accessing the computer.
* However, in kernel mode, only one process and one operating system can use the CPU at a time due to the limitation of having only one processor.
* The machine handles this by scheduling processes between different processors and operating systems.

### [0:18:17](https://youtu.be/sXXYGEnkTwk?t=1097s) Extra Kernels

* Extra kernels are more efficient than cloning an actual machine because they partition resources such as processors and hard disks.
* This creates a lightweight virtual machine that maps layers for better efficiency.

### [0:19:56](https://youtu.be/sXXYGEnkTwk?t=1196s) Assembly Programming and C Programs

* Operating systems are written in C or assembly programming.
* Programs are passed through the C processor before being compiled into object files and linked with libraries to produce executable programs.
* Dynamic link libraries (DLLs) allow shared resources between processes, making programs smaller. However, customers must have access to these DLLs for them to work.

## [0:22:36](https://youtu.be/sXXYGEnkTwk?t=1356s) Chapter 2 - Processes and Threads

Overview: This chapter focuses on managing CPU resources through abstractions of running programs called processes.

### [0:23:35](https://youtu.be/sXXYGEnkTwk?t=1415s) Definition of a Process

* A process is a running program in execution.
* The operating system manages resources by abstracting away details of complicated hardware.

## [0:24:57](https://youtu.be/sXXYGEnkTwk?t=1497s) Introduction to Processors and Processes

Overview: In this chapter, we will learn about the importance of processors as an abstraction provided by operating systems. We will also understand how processes allow for multi-programming and the ability to share a computer with many programs.

* The process abstraction is one of the oldest and most important abstractions that operating systems provide.
* Using ideal processes, a single CPU can be turned into multiple virtual CPUs without which modern computers would not exist.
* Even if you have multiple CPU cores, scheduling and assigning which processor belongs to which process is still necessary when running thousands of processes on your computer.
* Scheduling is the decision of who gets to use the CPU at any given time slot.
* The operating system decides who gets to use the CPU based on scheduling decisions.
* Most of the time, CPUs stay idle because computers are designed for interactivity. However, this is not acceptable for Mainframe computers as they are very expensive and their operating systems need more data and processes to run efficiently.
* Processes do not know how to switch between themselves; it's up to the operating system with hardware interrupts or requests for hardware data (e.g., key button events) to stop processing from running and handle these events.

### [0:26:49](https://youtu.be/sXXYGEnkTwk?t=1609s) Understanding Scheduling

* When there are three processes on your computer along with an operating system, each process uses the CPU in different time slots decided by scheduling decisions made by the operating system.
* The picture shown in this section is misleading because it doesn't explicitly show that when switching from one process to another, the operating system comes in and makes a scheduling decision before letting go of the processor so that another process can take over.
* Sometimes CPUs stay idle; this isn't necessarily bad as computers are designed for interactivity. However, Mainframe computers require more data and processes than personal computers do.

### [0:30:22](https://youtu.be/sXXYGEnkTwk?t=1822s) Multi-programming Operating Systems

* Multi-programming allows for sharing a computer with many programs through scheduling decisions made by an operating system with hardware interrupts or requests for hardware data (e.g., key button events).
* Personal computers didn't have multi-programming in their early versions (e.g., Altair 8800), but Mainframe computers did due to their high cost.

## [0:32:52](https://youtu.be/sXXYGEnkTwk?t=1972s) Process Creation

Overview: This section discusses the creation of processes in Unix operating systems, including system initialization and running demons.

* Demons are special processes that mostly sleep and wait for a task to complete.
* Operating system services are also created during initialization but do not actively run.
* Processes can be created through system calls or API functions, such as fork for Unix and discrete process for Windows 32.
* There are different ways to terminate a process, including voluntary termination by the process itself, involuntary termination by the operating system due to an error or privilege violation, and killing by another process with permission.

## [0:41:39](https://youtu.be/sXXYGEnkTwk?t=2499s) Process Hierarchy and States

Overview: This section discusses the process hierarchy and states in operating systems.

* The init process is the parent of all processes in Unix-based systems.
* Windows does not have a concept of process hierarchy, as all processes are equal.
* Processes can be in one of three states: running, ready to run, or blocked.

### [0:42:04](https://youtu.be/sXXYGEnkTwk?t=2524s) Process States

* A running process is actively using the CPU and executing instructions.
* A ready-to-run process is waiting for the CPU to become available.
* A blocked process is waiting for data from the operating system before it can continue.

### [0:43:37](https://youtu.be/sXXYGEnkTwk?t=2617s) Process Creation and Scheduling

* When a process is created, it is initially in a ready state.
* The operating system makes scheduling decisions to determine which ready processes should run next.
* While a process is using the CPU, it can be interrupted by hardware interrupts or requests made to the operating system.

### [0:45:08](https://youtu.be/sXXYGEnkTwk?t=2708s) Waiting State

* If a process requests data from the disk or another resource from the operating system, it enters a waiting state until that data becomes available.
* Terminated, running, ready, and waiting are the main process states.

Overall, this section provides an overview of how processes work in an operating system. It covers important concepts such as process hierarchy and states while also discussing how processes are created and scheduled.
