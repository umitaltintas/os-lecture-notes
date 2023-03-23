# lecture 3

## [0:00:02](https://youtu.be/bFIIthEyw2M?t=2s) Definition of Operating Systems

Overview: The definition of operating systems is simple enough. They are software that helps manage computer hardware and resources.

* Operating systems are not application software.
* They abstract the computer hardware and manage resources.
* They help to circulate the details of the hardware because hardware is complicated.

### [0:01:31](https://youtu.be/bFIIthEyw2M?t=91s) Kernel Mode

* Understanding kernel mode is important for understanding the history of operating systems.
* Most design decisions about operating systems were made in one of these generations.
* Decisions made in the past may not always be correct, but we still use them today.

### [0:03:30](https://youtu.be/bFIIthEyw2M?t=210s) History of Operating Systems

* In the early days, there were no operating systems because they had not been invented yet.
* Software was written in machine language using hexadecimal numbers in binary format.
* Later, programming languages and compilers were invented to help write and run software.
* Personal computers faced similar problems as vacuum tubes due to their smaller size and limited power.

### [0:06:32](https://youtu.be/bFIIthEyw2M?t=392s) Efficiency vs Responsiveness

* First-generation computers optimized efficiency, while modern computers optimize interactivity and responsiveness.

## [0:07:25](https://youtu.be/bFIIthEyw2M?t=445s) Importance of Interactivity, Security, and Battery Management in Mobile Operating Systems

Overview:

* When designing a mobile computer operating system, interactivity is important but so is security and battery management.
* The system should be interactive and responsive while also being secure in terms of keeping data safe and not running the CPU at 100% all the time to conserve battery life.

## [0:08:48](https://youtu.be/bFIIthEyw2M?t=528s) Review of Computer Hardware Concepts

Overview:

* This section provides a review of computer hardware concepts.
* The main system architecture consists of a CPU, memory, and communication over a bus.
* The memory management unit within the CPU virtualizes memory for each program to think it has its own memory starting from address number zero to some large number.
* Video controllers are hardware components connected to the CPU via the system bus that communicate with the CPU using kernel mode only.
* Special instructions can read special locations on keyboard controllers to communicate with them from the CPU.
* Communicating with monitor controllers involves modifying memory inside video controllers.

## [0:14:01](https://youtu.be/bFIIthEyw2M?t=841s) Communication with Controllers for I/O Devices

Overview:

* To communicate with I/O devices such as USB controllers or hard disk controllers, one communicates with their respective controllers.
* USB controllers are complicated because they have to communicate with many different types of USB devices.
* Hard disk control research multi-CPU computers sometimes use computers as the controller.

## [0:15:12](https://youtu.be/bFIIthEyw2M?t=912s) Can an Operating System Use Hardware Interchangeably?

Overview:

* The question asks if an operating system can use hardware interchangeably like how FPGA hardware can be programmed differently according to coding.

## [0:16:00](https://youtu.be/bFIIthEyw2M?t=960s) Introduction to FPGAs and Operating Systems

Overview: The speaker introduces FPGAs as specialized computers that can be programmed to change hardware configurations. They discuss the use of operating systems with FPGAs and virtualization.

* FPGAs are specialized computers that can be programmed to change hardware configurations.
* Regular operating systems like Windows and Unix may not work with FPGAs.
* Virtualization allows for a translation layer between the guest operating system and the host operating system, allowing for more capabilities without changing hardware.

### [0:17:03](https://youtu.be/bFIIthEyw2M?t=1023s) Virtualization Layer

* The virtualization layer is a software layer that accesses a primitive operating system to translate real operating systems.
* Different versions of the same operating system can run on top of this abstraction layer.
* Adding drivers to the virtualized machine adds more capabilities to this translation or virtualization layer.

### [0:18:17](https://youtu.be/bFIIthEyw2M?t=1097s) Example of Virtualization

* In an example of virtualization, there is real hardware at the bottom, followed by a type 2 hypervisor or VM box, then Linux running on top of it.
* When accessing devices like a mouse, the guest operating system sends requests to the type 2 hypervisor which translates them for the host operating system.
* Adding new devices requires adding drivers so that your type 2 hypervisor can handle those kinds of hardware requests.

### [0:20:04](https://youtu.be/bFIIthEyw2M?t=1204s) Understanding Virtual Operating Systems

Overview: The speaker discusses how understanding virtual operating systems is key to understanding how regular operating systems work. They also introduce application program design.

* Understanding virtualizing and containerizing is key to understanding how regular operating systems work.
* Application programs may be mistaken for another type of OS by the host OS.
* Memory management units allow applications to run as if memory is reserved even though it's not.

### [0:22:35](https://youtu.be/bFIIthEyw2M?t=1355s) Q\&A Session

Overview: The speaker answers questions about why hard drives don't connect directly to CPUs like main memory.

* A question is asked about why hard drives don't connect directly to CPUs like main memory.

## [0:23:15](https://youtu.be/bFIIthEyw2M?t=1395s) Hardware Architecture

Overview: The hardware architecture of a computer consists of various components such as CPU, GPU, memory, and platform controller hub. The communication between these components is designed to be efficient and fast for some components like memory and graphics while slower for others like USB 2.0 devices.

* CPUs have their own caches and there's a shared cache.
* Memory and graphics are connected more directly to the CPU for faster communication.
* USB 2.0 devices can stay slow to avoid increasing the cost of computer hardware.

### [0:26:07](https://youtu.be/bFIIthEyw2M?t=1567s) Processor

Overview: The processor is the brain of the computer that executes instructions by fetching them from memory, decoding them, and executing them in a fetch-decode-execute cycle.

* Registers are used inside CPUs.
* The same CPU design has been used since the 1940s.
* Something holding up the CPU can cause it to stop working properly.

### [0:28:11](https://youtu.be/bFIIthEyw2M?t=1691s) Operating System Processes

Overview: Operating system processes are separate processes that wait until they are asked to do something by the operating system. They can take up memory but don't use much CPU unless needed.

* Many operating system processes are not doing anything at a given time.
* Some operating system processes wait in memory until they are needed again.
* Killing unnecessary processes can improve computer performance.

## [0:31:23](https://youtu.be/bFIIthEyw2M?t=1883s) Handling System Calls and Registers

Overview: In this section, the speaker discusses how operating systems handle sleeping processes and the use of registers in CPUs.

* Sleeping processes are handled by the operating system, which wakes them up when there is a job to be done.
* Registers are special memory locations inside the CPU that are very fast to access and modify. They are not part of the memory and take only a single clock cycle to access.
* Programs should be written in a way that they use registers instead of referring to memory.

### [0:32:17](https://youtu.be/bFIIthEyw2M?t=1937s) Program Counter and Stack Pointer

* The program counter is like a pointer that points to some location in memory where an instruction is being executed. It increments by one after executing each line.
* The stack pointer keeps data about local variables, function return positions, etc.
* The program status word (PSW) keeps track of whether the CPU is running in kernel mode or user mode.

### [0:35:21](https://youtu.be/bFIIthEyw2M?t=2121s) Kernel Mode vs User Mode

* The kernel mode allows the CPU to do anything it wants, such as accessing any memory location or programming I/O registers.
* Regular programs run in user mode, which has limitations on what it can do.
* If a program tries to access memory management unit registers while running in user mode, an interrupt will occur and the operating system will take control.

### [0:36:50](https://youtu.be/bFIIthEyw2M?t=2210s) System Calls

* A system call is made by a regular program when it needs help from the operating system.
* When a system call is made, the CPU switches to kernel mode and gives control to the operating system.
* The operating system either performs the requested action or denies permission if it cannot be done.
