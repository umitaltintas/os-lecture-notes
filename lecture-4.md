# lecture 4

## [0:00:07](https://youtu.be/lOGA6Cixpog?t=7s) Introduction

Overview: The processor is the most important component of a computer. System calls are important and most common CPUs have them. CPU pipelining can increase efficiency but branching can be problematic.

* CPUs are designed with three different units: fetch, decode, and execute.
* Pipelining allows for multiple instructions to be executed at the same time.
* Multi-core CPUs allow for multiple independent instructions to be executed simultaneously on different cores.

### [0:00:43](https://youtu.be/lOGA6Cixpog?t=43s) System Calls

Overview: System calls are important and most common CPUs have them.

* Some CPUs do not have system calls or instruction sets.
* A sequence example of a system call is NF image.

### [0:01:16](https://youtu.be/lOGA6Cixpog?t=76s) CPU Pipelining

Overview: CPU pipelining can increase efficiency but branching can be problematic.

* Pipelining allows for multiple instructions to be executed at the same time.
* Branching is bad for the CPU pipeline as it requires each instruction to fetch in the next execution.
* Compilers must be written in a way that knows about the CPU pipeline.

### [0:04:06](https://youtu.be/lOGA6Cixpog?t=246s) Hardware Features

Overview: Writing specialized operating system code is necessary for hardware features such as CPU pipelining.

### [0:04:35](https://youtu.be/lOGA6Cixpog?t=275s) Moore's Law and Multi-Core CPUs

Overview: Moore's Law predicts that the number of transistors on a CPU will double every 18 months. Multi-core CPUs allow for multiple independent instructions to be executed simultaneously on different cores.

* Intel was one of the first CPU makers.
* Moore's Law has continued since 1970, allowing for smaller, cheaper, and more efficient transistors.
* Adding more transistors does not necessarily make a CPU faster, so multi-core CPUs were developed.

## [0:08:22](https://youtu.be/lOGA6Cixpog?t=502s) Introduction to CPU and Multi-CPU Architecture

Overview:

* Difference between multi-cores and multi-cpus
* Multi-CPU architecture has more than one CPU connected to the system bus
* Single CPU multi-core system has multiple cores in a single CPU

### [0:09:31](https://youtu.be/lOGA6Cixpog?t=571s) GPUs and their Applications

* GPUs are Graphics Processing Units used for processing graphical stuff like pixels
* They are very primitive CPUs but have thousands of cores, making them efficient for parallelizing tasks
* GPUs are popularly used for screen updates, computer graphics, and machine learning applications

### [0:11:55](https://youtu.be/lOGA6Cixpog?t=715s) Memory Hierarchy

Overview:

* Memory should be fast, large, and cheap but it's not possible with current technology
* Registers are special memory locations inside CPUs that are as fast as the CPU can handle
* Cache is faster than main memory but slower than registers
* Main memory is 10 times slower than cache
* Magnetic disks are much larger but million times slower than main memory

### [0:14:02](https://youtu.be/lOGA6Cixpog?t=842s) Cost vs Speed Balance of Memory Components

Overview:

* Increasing the number of registers in a CPU makes it complicated and expensive
* Cache is cheaper than registers but not as cheap as main memory
* Main memory is 10 times slower than cache but cheaper
* Magnetic disks are much larger but million times slower than main memory

## [0:16:43](https://youtu.be/lOGA6Cixpog?t=1003s) Memory Hierarchy

Overview: This section discusses the memory hierarchy and why it is important to consider when designing operating system routines.

* The memory hierarchy consists of different levels of memory, each with varying speeds and costs.
* Accessing L1 cache is fast (half a nanosecond), while accessing main memory is slow (100 times slower than L1 cache).
* Context switching can be expensive because it invalidates the cache, causing data to be retrieved from main memory which is much slower.

### [0:17:00](https://youtu.be/lOGA6Cixpog?t=1020s) Importance of Memory Hierarchy in Operating System Design

* When designing operating system routines, it's important to consider the memory hierarchy.
* Context switching is necessary for multi-programming but should not be too frequent as it can slow down the system.
* Balancing context switching frequency requires knowledge of the numbers in the system.

### [0:20:11](https://youtu.be/lOGA6Cixpog?t=1211s) Branch Misprediction

* Branch misprediction occurs when pipelining makes a prediction about where code will execute next and it's incorrect.
* Mispredicting branching causes pipeline flushing, which slows down execution.
* Jumping to another location isn't expensive, but mispredicting branching causes pipeline flushing.

### [0:23:09](https://youtu.be/lOGA6Cixpog?t=1389s) Main Memory Reference

* Main memory reference is 100 times slower than L1 cache reference.
* Mutex locking and unlocking are used for process synchronization in an operating system.

## [0:25:04](https://youtu.be/lOGA6Cixpog?t=1504s) Memory Access Times

Overview: This section discusses the different memory access times for various types of storage devices.

* Reading from main memory takes 250 microseconds for one megabyte of data.
* Reading randomly from an SSD drive takes 150 microseconds, while reading sequentially takes longer.
* Reading from a mechanical hard drive takes 10 milliseconds, which is about a thousand times slower than reading from main memory.

### [0:27:08](https://youtu.be/lOGA6Cixpog?t=1628s) Why is SSD slower than main memory?

* Main memory is closer to the CPU and connected using a faster bus compared to an SSD drive.
* An SSD drive can be used as extra memory when the program size exceeds the main memory capacity.

### [0:29:16](https://youtu.be/lOGA6Cixpog?t=1756s) Memory Hierarchy

Overview: This section explains the different levels of memory hierarchy and their access times.

* Registers and cache (L1, L2, etc.) have nanosecond-level access times.
* Main memory has microsecond-level access times.
* SSD drives and network data have millisecond-level access times.

### [0:30:20](https://youtu.be/lOGA6Cixpog?t=1820s) CPU Cycles

Overview: This section discusses the number of CPU cycles required for different operations.

* Register operations take around one cycle, while branch mispredictions take ten cycles.
* Floating-point vector addition used to be slow but now takes three cycles at level two cache.
* Direct function calls take 20 cycles, while virtual function calls take up to three times more cycles.

### [0:32:01](https://youtu.be/lOGA6Cixpog?t=1921s) Exceptions and Thread Context Switches

Overview: This section explains the cost of using exceptions and thread context switches in programs.

* Using C++ exceptions should be limited to exceptional cases because they are expensive (5,000 - 10,000 cycles).
* Thread context switches take around 2,000 cycles, while thread context searches can take up to one million cycles.

### [0:33:04](https://youtu.be/lOGA6Cixpog?t=1984s) Registers and Cache

Overview: This section discusses registers and cache in CPUs.

* A 32-bit system has 32 registers while a 64-bit system has 64 registers.
* Cache sizes vary depending on the system but are generally larger nowadays compared to ten years ago.

## [0:33:39](https://youtu.be/lOGA6Cixpog?t=2019s) CPU Registers and Memory

Overview: The CPU has 32 registers, each of which is 32 bits. There is less than half a kilobyte of memory on a 64-bit CPU.

* L1 cache allows for efficient access to memory
* Writing code in assembly allows for better control over memory usage
* Python does not allow for control over memory usage like C++ or assembly

### [0:37:06](https://youtu.be/lOGA6Cixpog?t=2226s) Mechanical Disks vs SSDs

Overview: Mechanical disks are still used in larger servers due to their reliability, but SSDs are becoming more popular as they become cheaper and more reliable.

* Mechanical disks are slower due to being mechanical
* SSDs are becoming cheaper and more reliable
* Operating systems manage the location of data on disks and provide protection and security for the data stored on them

### [0:38:56](https://youtu.be/lOGA6Cixpog?t=2336s) Operating System Concerns with Disk Storage

Overview: The operating system manages the details of disk storage, regardless of whether it is a mechanical disk or an SSD.

* Opening, reading, and closing files is all that matters to the operating system
* The structure of a typical mechanical disk includes platters that rotate around a shaft and read/write heads that move in/out to desired positions
* Mechanical disks cannot beat the principles of physics, so there are limits to their speed and density

## 0:41:26 IO Devices and Controllers

Overview: This section discusses the different types of IO devices, such as cables and screens, and how they are connected to the system bus using controllers. The controllers are electronic devices that are programmed by drivers, which are parts of the operating system.

* IO devices include cables, screens, network cards, and mice.
* Controllers are electronic devices that connect IO devices to the system bus.
* Drivers are parts of the operating system that program controllers.
* Device drivers are written by manufacturers and allow the operating system to communicate with specific IO devices.

### 0:44:02 Device Drivers

Overview: This section explains why device drivers can cause issues with the operating system if they crash and how they function as a middle layer between the operating system and device controllers.

* Device drivers can cause an entire operating system to crash if they fail.
* Device drivers act as a middle layer between the operating system and device controllers.
* Without device drivers, an operating system would not know how to communicate with specific IO devices.

### 0:45:18 Importance of Introductory Chapter

Overview: This section emphasizes the importance of reading introductory chapters in textbooks before diving into details. It also encourages students to research computer history outside of class.

* Understanding introductory chapters is crucial for becoming a good computer engineer or scientist.
* Reading about computer history from various sources can help prepare for class discussions.

## [0:49:18](https://youtu.be/lOGA6Cixpog?t=2958s) Introduction

Overview: The speaker thanks the audience.

* The speaker expresses gratitude towards the audience.

### [0:49:23](https://youtu.be/lOGA6Cixpog?t=2963s) Greeting

* The speaker greets everyone.
