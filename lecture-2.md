# lecture 2

## [0:00:03](https://youtu.be/zz\_DUqlCgv8?t=3s) Introduction

Overview: The video continues the history of operating systems, looking at the main idea and problems they tried to solve.

* Operating systems got very complex nowadays.
* Original operating systems are better to look at because they explain a lot.
* First generation computers did not have operating systems because software wasn't invented yet.
* They didn't have enough memory or CPU to hold more than one program at the same time.

### [0:00:52](https://youtu.be/zz\_DUqlCgv8?t=52s) Why didn't first generation computers use operating systems?

* They were not powerful enough to run both an operating system and programs at the same time.
* They simply didn't have enough memory to hold more than one program at the same time.

### [0:03:11](https://youtu.be/zz\_DUqlCgv8?t=191s) Second Generation Computers

Overview: Second-generation computers started using transistors, which made them faster and more capable.

* Transistors enabled smaller, more reliable chips that consumed less power.
* Expensive second-generation computers took input from an input tape, outputting data for computation on an output tape.
* The assistant tape contained libraries for competition and compilers.
* The Fortran compiler was used whenever the computer saw a card with specific information.
* This was not an exact operating system but rather a limited version of it.

## [0:07:52](https://youtu.be/zz\_DUqlCgv8?t=472s) Introduction to Programming

Overview: In the early days of computing, programs were run directly on the computer. Later, people realized they could use computers to write programs and invented the assembler.

* The assembler is a program that takes an assembly program and produces machine code.
* Assembly language is very close to machine code but more understandable by humans.
* Third-generation computers had operating systems that allowed for multi-programming, time-sharing, and multi-tasking.
* Multics was an ancestor of Unix and introduced many ideas despite not being commercially successful.

### [0:13:15](https://youtu.be/zz\_DUqlCgv8?t=795s) Multi-Programming

Overview: Multi-programming means having more than one program in memory at once. Operating systems manage this by time-sharing the CPU between programs.

* Programs must share the CPU in a multiplexed way.
* The operating system interrupts each program using a timer to switch between processes.
* While one program is running, it uses the CPU exclusively.

## [0:16:32](https://youtu.be/zz\_DUqlCgv8?t=992s) Hardware Hub and Interrupts

Overview: In order for the operating system to regain control after an infinite loop, a hardware hub is needed. Interrupts are a hardware feature that allow the operating system to take control when a timely interrupt occurs.

* Interrupts are triggered by hardware features, especially timer interrupts.
* When a timely interrupt happens, the CPU stops whatever it's doing and the operating system takes control again.
* The operating system then decides which job to give the CPU to next.
* This is what multi-programming is - programs use the CPU in turn with lots of switching back and forth between the operating system and jobs.

### [0:18:34](https://youtu.be/zz\_DUqlCgv8?t=1114s) Expensive Switching

Overview: Switching from one job to another or from an operating system to a job is expensive because it causes cache misses.

* Cache entries become invalidated when switching from one job to another, causing cache misses.
* Cache misses are expensive, so it's more efficient to keep running the same program.
* Multi-programming allows for multiple programs to run on a computer but requires finding a balance between switching too often or too late.

### [0:21:12](https://youtu.be/zz\_DUqlCgv8?t=1272s) Timer Interrupts

Overview: The timer device causes interrupts that allow the operating system to regain control of the CPU at regular intervals.

* Accessing the timer can only be done in privileged mode or kernel mode.
* The task of the timer is to cause interrupts that interrupt whatever the CPU is doing and give control back to the operating system.
* Only the operating system can program the timer, guaranteeing that it has control of the CPU at regular intervals.

## [0:24:16](https://youtu.be/zz\_DUqlCgv8?t=1456s) Timer Interrupts and Multi-Programming

Overview: In this section, the professor explains how timer interrupts and multi-programming work in operating systems.

* Timer interrupts are critical values assigned by the operating system to ensure system performance.
* Multi-programming allows for multiple programs to be loaded into memory, so when one program is blocked, another can run instead.
* This saves CPU time and reduces the need for expensive IO computers.

### [0:25:10](https://youtu.be/zz\_DUqlCgv8?t=1510s) Designers vs Administrators

* Operating system designers usually assign interrupt and timer values because they are critical for system performance.
* Some operating systems allow administrators to adjust primary interrupts or CPU usage.

### [0:25:39](https://youtu.be/zz\_DUqlCgv8?t=1539s) The Invention of Multi-Programming

* Multi-programming was invented in the 1960s when computers had enough memory to hold many programs at once.
* Although it looks like a computer is running many programs at once, only one program can run on a single CPU.

### [0:26:18](https://youtu.be/zz\_DUqlCgv8?t=1578s) Blocking Programs

* When a program needs data from an IO device (e.g. disk), it asks the operating system to retrieve it.
* Since reading data from an IO device is much slower than reading from memory, the operating system switches to another program while waiting for the data to be retrieved.
* This way, most of the time, timer interrupts are not needed because programs stop themselves when they ask the operating system to do something for them.

### [0:29:46](https://youtu.be/zz\_DUqlCgv8?t=1786s) Saving CPU Time with Multi-Programming

* With multi-programming, more than one program can be loaded into memory. When one program is blocked, another can run instead.
* This saves CPU time and reduces waste on expensive computers.

## [0:31:52](https://youtu.be/zz\_DUqlCgv8?t=1912s) Multi-Programming and Efficiency

Overview: This section discusses the benefits of multi-programming, which allows for multiple jobs to be done on one computer simultaneously. The CPU is always busy with something, whether it's input/output jobs or useful jobs.

* Mechanical devices are slower than computers, so they may cause some programs to wait.
* Multi-programming allows for all jobs to be done on one computer, including input/output jobs and useful jobs.
* Memory protection is important in multi-programming to prevent one job from accessing another job's memory.
* Operating systems run in privileged mode and can access whatever they want, while other programs are restricted to their own space.
* Early operating systems were not very robust and caused system crashes due to lack of hardware support for memory protection.

### [0:37:13](https://youtu.be/zz\_DUqlCgv8?t=2233s) Interrupts

Overview: This section discusses interrupts, which occur when hardware needs attention. The operating system takes over the CPU and handles the interrupt.

* Interrupts can be caused by simple keystrokes on a keyboard or more complex events like disk or network interrupts.

### [0:38:29](https://youtu.be/zz\_DUqlCgv8?t=2309s) Virtual Memory

Overview: This section discusses virtual memory, which allows each job running on a computer to think that it has its own memory starting at address number zero.

* Address number zero is a special address that cannot be written to.
* All variables are stored at upper locations after address number zero.
* Programs behave this way because it makes it easier for programmers to write code.

## [0:39:28](https://youtu.be/zz\_DUqlCgv8?t=2368s) Memory Management

Overview: In this section, the professor explains how memory is managed in an operating system.

* Java memory can be divided into two pieces, page one and page two.
* In physical memory, they are stored in a non-contiguous way but in logical memory, the program thinks that it has contiguous memory.
* The operating system virtualizes the underlying hardware to extend or virtualize the memory.
* Each program thinks that it has its own contiguous memory.

### [0:55:54](https://youtu.be/zz\_DUqlCgv8?t=3354s) Hardware Capabilities

Overview: The professor discusses the invention of new ideas such as memory protection, virtual memory, and interrupts.

* With the invention of these ideas, we need a Memory Management Unit for both Memory Protection and Virtual Memory.
* For Interrupts, we have interrupt generation hardware and interrupt handling hardware.
* Only the operating system is authorized to use all those functions and hardware capabilities.

### [0:56:48](https://youtu.be/zz\_DUqlCgv8?t=3408s) Multi-programming

Overview: The professor explains multi-programming and how it allows running several programs at once.

* Multi-programming allows running several programs at once.
* Programs are protected from each other's memories through Memory Protection.
* When a program needs to do IO (input/output), it cannot continue until IO is complete.
* Preemptive CPU scheduling is used when a program needs lots of CPU time.
  * This means that another program will use the CPU even though it still needs to use it.
  * This demonstrates the idea of demons which are used for spooling.

### [0:59:06](https://youtu.be/zz\_DUqlCgv8?t=3546s) Demons

Overview: The professor explains what demons are and how they work in an operating system.

* Demons are special processes belonging to the operating system that wait without doing anything until something happens.
  * They handle specific tasks such as printing or input/output operations.
  * They allow other programs to use CPU time while waiting for their task to complete.

Note: The professor shows his task manager with hundreds of programs running on his computer as an example of multi-programming in action.

## 1:02:38 Information Statistics Bookkeeping

Overview: The operating system needs to know how much CPU, memory, disk and network connections are being used by each program. This is important for fair allocation of resources.

* The operating system assigns CPUs and memory to tasks based on the statistics it collects.
* Memory usage can be divided into cache memory and usable memory.
* Closing an application may not immediately free up its memory usage due to virtualization.
* Modern operating systems are sophisticated enough to keep only required parts in memory, with the rest on disk.
* Memory protection, virtualization, and multitasking were invented during the third generation of operating systems in the 1960s.

## 1:08:28 Large-Scale Integration Transistor

Overview: With computers becoming cheaper, small businesses and home users can now buy computers. This has led to a change in the type of applications that need to be run.

* IBM released the IBM PC in the 1980s which needed an operating system.
* Bill Gates of Microsoft bought another operating system and sold it to IBM for $75,000.

## [1:11:00](https://youtu.be/zz\_DUqlCgv8?t=4260s) History of Operating Systems

Overview: This section discusses the history of operating systems, starting from the invention of graphical user interfaces in the 1960s to the development of personal computers and mobile devices.

* In the 1960s, a man invented the graphical user interface with Windows icons, menus, and mouse.
* Expensive computers were needed to run these ideas at that time.
* In the 1980s and 1990s, personal computers became cheaper and more powerful, running versions of Unix on touch computers and Windows computers.
* Today we have Windows and Mac OS for personal computers. Mobile devices came up in the 1990s with Nokia's idea to combine a cell phone with a small computer.
* The term "smartphone" was coined by Ericsson in 1997. Blackberry OS was developed for business users while Apple's IOS with iPhone or Google's Linux-based Android were developed for general use.
* Battery management and security are key issues for mobile devices.

### [1:16:27](https://youtu.be/zz\_DUqlCgv8?t=4587s) Repeating Problems

Overview: This section talks about how each new generation of computers faces similar problems as previous generations.

* When personal computers first appeared, they had to solve similar problems as initial computers due to their lack of power.
* Similarly, when mobile devices first appeared, interactivity suffered due to their lack of power.
* Each new generation has to solve similar problems over again such as crashes or lack of protection hardware.
* Even today we face similar problems that existed in the 1950s and 1960s for certain types of computers.

## [1:19:34](https://youtu.be/zz\_DUqlCgv8?t=4774s) Introduction to Lincoln Laboratory

Overview: The video introduces Lincoln Laboratory, a research organization in Massachusetts that played an important role in developing the US Defense System since World War II.

* Lincoln Laboratory is known for its work in radar and advanced warning systems.
* The laboratory was established in the 1950s.

## [1:20:03](https://youtu.be/zz\_DUqlCgv8?t=4803s) Sketch Pad and the TX2 Mainframe

Overview: The section discusses the TX2 Mainframe computer and its use of sketch pad technology, which allowed users to communicate with the computer using graphics.

* The TX2 Mainframe was a large computer without a keyboard.
* Sketch pad technology used a light pen to communicate with the computer through graphics.
* Ivan Sutherland invented graphical user interfaces in 1960 and developed sketch pad technology.
* Light pens were connected to CRT operations and could draw straight lines and circles.
* Users could position a bright spot on desired locations on the screen and command the computer to draw lines from one point to another.
* These ideas were revolutionary at the time, similar to those seen in sci-fi movies.

## [1:24:01](https://youtu.be/zz\_DUqlCgv8?t=5041s) Computer-Aided Design with Sketch Pad

Overview: This section discusses how sketch pad technology was used for computer-aided design.

* Users could select blank pieces of paper for their designs.
* Drawing on the scope reinforced what users had in mind for their designs.
* This was an early version of computer aided design software.

## [1:26:46](https://youtu.be/zz\_DUqlCgv8?t=5206s) Introduction to Moore's Law and Personal Computers

Overview: This section discusses the origins of Moore's Law and personal computers.

* Intel Corporation founder Gordon Moore predicted that CPU power would double every two years or 18 months.
* This trend continued from 1970 to the 2010s, but has slowed down due to limitations in transistor sizes.
* In the 1970s, when Intel began producing CPUs, there was no market for personal computers.
* Bill Gates wrote the first interpreter for a personal computer, which ran on the Altair 8800 in 1974.

### [1:27:06](https://youtu.be/zz\_DUqlCgv8?t=5226s) What is Moore's Law?

* Every two years or 18 months, CPU power doubles or the number of transistors doubles.
* Gordon Moore founded Intel Corporation and made this prediction in the 1970s.

### [1:28:21](https://youtu.be/zz\_DUqlCgv8?t=5301s) The Limitations of Transistor Sizes

* Transistors cannot be smaller than a certain size, which limits further growth in CPU power.
* This has slowed down the trend predicted by Moore's Law.

### [1:29:18](https://youtu.be/zz\_DUqlCgv8?t=5358s) The Origins of Personal Computers

* When Intel began producing CPUs in the 1970s, there was no market for personal computers.
* Bill Gates wrote an interpreter for a personal computer that ran on the Altair 8800 in 1974.

### [1:31:20](https://youtu.be/zz\_DUqlCgv8?t=5480s) The Altair 8800

* The Altair 8800 was released in 1974 and used an Intel CPU.
* It did not have an operating system and was programmed using switches.
* Bill Gates wrote an interpreter for it that became the first interpreter running on a personal computer.

## [1:35:22](https://youtu.be/zz\_DUqlCgv8?t=5722s) Computer Hardware Review

Overview: This section discusses the hardware requirements for running an operating system.

* A computer with a budget of $1500 can run a nice computer without an operating system.
* Operating systems came later when there was enough memory available.
* The width of the bus is dependent on the CPU and memory capabilities, usually 8 or 16 bits.
* The CPU communicates with electronic devices through the bus, such as video controllers, keyboard controllers, and hard disk controllers.
* The operating system has the privilege to control these controllers, not ordinary programs.

### [1:36:17](https://youtu.be/zz\_DUqlCgv8?t=5777s) Simplified Architecture of a Computer System

* A basic architecture of a computer system includes central processing units (CPU), memory, and a bus that connects them.
* Memory is collected by a system bus that communicates over this bus.
* There is also a memory management unit inside the CPU used for virtualizing memory so any program running on the CPU would think they have their own CPU.
* Everything in the computer system is connected to this bus controlled by both hardware and CPU.

### [1:40:08](https://youtu.be/zz\_DUqlCgv8?t=6008s) Operating System Design

Overview: This section discusses how operating systems are designed for specific hardware.

* Operating systems are designed on top of hardware abstraction layers which make it possible to design modular or portable operating systems.
* Some parts of an operating system are portable while others must be specific to that hardware.
* Virtualization makes it even more portable by making guest operating systems think they are running on specific hardware.

## [1:43:34](https://youtu.be/zz\_DUqlCgv8?t=6214s) Virtualization and Operating Systems

Overview: This section discusses virtualization and how it is an extension of the operating system idea.

* Virtualization is an extension of the operating system idea.
* The hypervisor abstracts the details of how the rings are done, making it irrelevant whether it is running on software or hardware.
* The guest operating system thinks that it is running on real hardware, but it is not actually.
* All three - hypervisor, guest operating system, and host operating system - have to run physically on the hardware, which makes virtual boxes run a little bit slow.
* Virtualization, containerization, and Dockers are hot topics nowadays.

### [1:45:03](https://youtu.be/zz\_DUqlCgv8?t=6303s) Virtual Machine or Virtualization

Overview: This section briefly mentions a chapter in their book about virtual machine or virtualization.

* There is a chapter in their book called "Virtual Machine or Virtualization."
* If there's time at the end of the semester, they will talk about it; otherwise, students should read it themselves.
