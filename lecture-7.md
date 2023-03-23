# lecture 7

## [0:00:02](https://youtu.be/5wEG5\_nss3Q?t=2s) Introduction

Overview: This chapter covers operating system concepts, including the difference between a program and a process, CPU usage, memory allocation, and the process table.

* A program is a static piece of code that can be run.
* A process is a running program.
* When a program runs, it becomes a process in the computer's memory.
* The CPU uses registers to execute programs.
* Each process has its own logical address space in memory.
* The operating system keeps track of processes using a process table.

### [0:00:53](https://youtu.be/5wEG5\_nss3Q?t=53s) Programs vs Processes

* A program is a formal representation of an algorithm in non-programming language.
* A program becomes a process when it runs on the computer's memory.
* Programs are static pieces of code while processes are running programs.

### [0:01:26](https://youtu.be/5wEG5\_nss3Q?t=86s) Memory Allocation

* Each running program has its own logical address space in memory.
* The bottom of the memory contains text instructions while data or heap is at the top.
* Data grows upwards while stack grows downwards.

### [0:02:32](https://youtu.be/5wEG5\_nss3Q?t=152s) CPU Usage

* When a program runs, the CPU uses registers to execute it.
* Each running program has its own set of registers.
* The stack pointer points to somewhere in memory at the top of the stack.

### [0:05:03](https://youtu.be/5wEG5\_nss3Q?t=303s) Process Table

* The operating system keeps track of processes using a process table.
* Each entry in the table contains information about each process such as open files and register values.
* The process table is kept in memory by the operating system.

## [0:09:16](https://youtu.be/5wEG5\_nss3Q?t=556s) Introduction to Process Tables

Overview: This section introduces the concept of process tables and their importance in operating systems.

* Context switches involve saving data to a location and loading it up to the CPU.
* Process tables contain more than just registers, they also store time keeping data such as CPU usage statistics.
* Operating systems use process tables to make scheduling decisions based on this data.

### [0:09:42](https://youtu.be/5wEG5\_nss3Q?t=582s) Viewing Processes in Windows

* Windows processes can be viewed by opening the task manager.
* The task manager displays all running processes, including both application and operating system processes.
* Additional information such as CPU usage percentage and memory usage is also available for each process.

### [0:10:55](https://youtu.be/5wEG5\_nss3Q?t=655s) Adding More Data to Process Tables

* Additional data such as CPU usage percentage can be added to process tables.
* This information is useful for making scheduling decisions based on which processes are using the CPU most efficiently.
* Priority levels can also be adjusted in the process table to give certain processes higher priority during scheduling.

### [0:13:48](https://youtu.be/5wEG5\_nss3Q?t=828s) Understanding Single vs Multiple Processes

Overview: This section explains the difference between single and multiple processes running on a computer.

* A computer with only one process running is simple, with only one set of registers needed.
* When multiple processes are running, only one can use the CPU at a time while others wait or are blocked.
* In this case, data from each process's registers is stored in the process table when not actively running.

### [0:15:48](https://youtu.be/5wEG5\_nss3Q?t=948s) Understanding CPU Usage Percentage

Overview: This section explains what CPU usage percentage means and how it relates to overall system performance.

* CPU usage percentage refers to how much of the total available processing time is being used by a specific task or set of tasks over a given period (usually one second).
* High percentages indicate that a particular task or set of tasks is using more processing power than others, potentially causing slower overall system performance.
* Idle percentages indicate that no tasks are currently using processing power.

## [0:17:55](https://youtu.be/5wEG5\_nss3Q?t=1075s) CPU and Process Blocking

Overview: The CPU usage is determined by the amount of time it spends idle or busy. When processes are blocked, they may be waiting for disk data or mouse input.

* Programs may take a backup or waste their idle time.
* CPU usage is 72% idle and 28% busy.
* If CPU usage becomes 100%, the computer may appear slow due to context switching.

### [0:19:20](https://youtu.be/5wEG5\_nss3Q?t=1160s) Memory Utilization and Trashing

Overview: Memory utilization can affect computer performance, especially when there isn't enough space to switch between processes. This can lead to trashing, where the computer spends most of its time going back and forth between memory and secondary storage.

* Writing stuff to disk takes millions of times more time than context switching.
* Trashing makes the computer seem slower as it goes back and forth between memory and disk.
* CPU may be idle during trashing instead of doing useful work.

### [0:23:47](https://youtu.be/5wEG5\_nss3Q?t=1427s) Importance of Memory Space

Overview: Having enough memory space is crucial for fast process switching. Opening too many windows or adding more data can cause trouble if there isn't enough space.

* Large empty memory space allows for faster process switching without trashing.
* Adding more data or opening more windows can cause trouble if there isn't enough space.

## [0:26:25](https://youtu.be/5wEG5\_nss3Q?t=1585s) Inter-Process Communication

Overview: In this section, the speaker discusses inter-process communication and how it works.

* Processes communicate with each other by sharing data in memory.
* This is called inter-process communication.
* Although the communication is simple, there are many problems that can arise from data sharing, such as race issues.
* Synchronization is necessary to avoid chaos when multiple processes are accessing shared data.

### [0:31:16](https://youtu.be/5wEG5\_nss3Q?t=1876s) Files and Secondary Storage

Overview: In this section, the speaker talks about files and secondary storage.

* Memory is volatile and cannot store all data permanently. Secondary storage is needed for permanent storage.
* Files are a way of organizing related data on secondary storage.
* Directories or folders group related files together.
* The address of a file on secondary storage is known by its path name.

### [0:33:31](https://youtu.be/5wEG5\_nss3Q?t=2011s) The Rule of Embryonic Development

Overview: In this section, the speaker explains the rule of embryonic development and how it applies to computer science.

* The rule states that each new computer type or operating system goes through the same development as its ancestors.
* Mainframes in the 1960s had only 128 kilobytes of memory available, which limited their ability to run multiple processes simultaneously.

## [0:35:19](https://youtu.be/5wEG5\_nss3Q?t=2119s) The Evolution of Computers and Assembly Programming

Overview: In this section, the speaker discusses how computers have evolved over time and how assembly programming was used to write programs for older systems with limited memory. He also talks about how modern smart cars still require assembly programming due to their small CPUs and memory limitations.

* Older computer systems had limited memory and required assembly programming.
* Smart cars still require assembly programming due to their small CPUs and memory limitations.
* Each new type of computer goes through the same development as its ancestors.
* Many embedded systems lack protection mechanisms, requiring an operating system without protection.

### [0:37:17](https://youtu.be/5wEG5\_nss3Q?t=2237s) Protection Mechanisms in Computers

Overview: The speaker discusses the importance of protection mechanisms in computers, which prevent processes from using other processes' memory or resources. He explains that hardware provides this protection mechanism, even if someone intentionally tries to modify another process's data.

* Protection mechanisms prevent processes from using other processes' memory or resources.
* Hardware provides this protection mechanism, even if someone intentionally tries to modify another process's data.

### [0:38:56](https://youtu.be/5wEG5\_nss3Q?t=2336s) Learning About Computer History Through Operating Systems

Overview: The speaker talks about how learning about operating systems can teach us about computer history and where the main concepts of computer science come from. He mentions that going back in history helps us understand why we face similar issues with each new type of computer.

* Learning about operating systems can teach us about computer history and where the main concepts of computer science come from.
* Going back in history helps us understand why we face similar issues with each new type of computer.

### [0:39:31](https://youtu.be/5wEG5\_nss3Q?t=2371s) Altair Computers

Overview: The speaker briefly talks about Altair computers, which were named after a bright star in the sky. These computers did not have any operating systems, so users had to program everything themselves.

* Altair computers did not have any operating systems, so users had to program everything themselves.

### [0:42:32](https://youtu.be/5wEG5\_nss3Q?t=2552s) Using Tapes on Altair Computers

Overview: The speaker explains how tapes were used on Altair computers to store programs. Users needed a program that could read the data on the tape before they could run it on the computer.

* Tapes were used on Altair computers to store programs.
* Users needed a program that could read the data on the tape before they could run it on the computer.

## [0:43:51](https://youtu.be/5wEG5\_nss3Q?t=2631s) Checksum Loader

Overview: In this section, the speaker talks about a more sophisticated loader called the checksum loader that reads in the rest of BASIC off of tape.

* The bootstrap loader loads a very simple loader at the beginning.
* The simple loader reads the more sophisticated checksum loader from the tape.
* The checksum loader then loads the rest of BASIC.

### [0:44:17](https://youtu.be/5wEG5\_nss3Q?t=2657s) Loading Bootstrap Loader

* The bootstrap loader would have been provided in the manual from Altair.
* For their particular configuration, they are loading BASIC version 3.2 4K and using an SIO port.
* They load it starting at location zero.

### [0:44:36](https://youtu.be/5wEG5\_nss3Q?t=2676s) Programming Computer Using Machine Code

* To program your computer using machine code, you enter numbers provided by the manufacturer of this computer.
* This is not assembly but machine code.
* You enter these numbers to load your program from paper tape.

### [0:45:26](https://youtu.be/5wEG5\_nss3Q?t=2726s) Entering Numbers for Machine Code

Overview: In this section, the speaker explains how to know if you made a mistake when entering numbers for machine code.

* If you make a mistake, you don't do three and one; you have to do from the third number.
* They provide two sets of numbers (17 and 61), which should be stored as bytes or 22 and zero.

### [0:46:25](https://youtu.be/5wEG5\_nss3Q?t=2785s) Bootloader

Overview: In this section, the speaker talks about how to load a program using bootloader.

* That's all there is to loading a program with bootloader.

### [0:47:10](https://youtu.be/5wEG5\_nss3Q?t=2830s) Setting Serial Port for Basic Version 4.2

Overview: In this section, they explain how to set up serial port for Basic version 4.2.

* The first six positions were used to tell later versions of Basic and Loader what type of Serial Port was used.
* These four told Basic what type of Serial Port was used while these four told Loader what port number it needs to use to load data.
* They are using an SIO board in their case so all bits have to be zero for version 4.2 of 4K Basic.

### [0:47:27](https://youtu.be/5wEG5\_nss3Q?t=2847s) Starting Teletype Paper Tape Reading

Overview :In this section, they explain how to start teletype paper tape reading before running on location zero after resetting it.

* Before inputting search paper tape reading, they need to tell Loader and Basic what type of Serial Port they're using and in 4K Basic the first six positions or so were used to tell that in later versions of basic and the loader these four told basic what type of Serial Port was used these four told the load it's basically are basically attending the loader what port number you need to use to load data we're using an sio board in that case these bits all have to be zero for version four point uh I mean version three point two of four K basic so now it's ready to run however instructions say start teletype paper tape reading first before hitting run on program and we're going want run from location zero so I'm going do reset get us back location zero

### [0:48:21](https://youtu.be/5wEG5\_nss3Q?t=2901s) Running Checksum Loader

Overview :In this section, they talk about running checksum loaders which read rest part of BASIC interpreter off paper tapes.

* When downloading bootstrap loaders we'll see light pattern change when it jumps into checksum loaders that then turns around and reads rest part BASIC interpreter worth by time goes into leader letter okay they're just switched so Savage from bootloader small more sophisticated bootloader had read terabyte point second stage loaders running now continue read rest tape has basic on it

\##\[0.49.31] ( https://www.youtube.com/watch?v = 50E8tefJYvI\&t = ) Loading Basics

Overview :In this section ,they talk about loading basics

* It takes about seven-eight minutes at ten characters per second rate .
* It will end up putting quite pile paper on floor .

There is no content for this section.
