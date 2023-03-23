# lecture 5

## [0:00:02](https://youtu.be/Datn43tf5RQ?t=2s) Abstraction of the CPU

Overview: The guest operating system running on a hypervisor tries to access memory management units, but it doesn't have the privilege to modify them. Whenever it tries to do so, an interrupt is caused and handled by the host operating system.

* The guest operating system runs as a regular application and can't modify the memory management unit or interrupt controller.
* The host operating system handles interrupts caused by the guest operating system trying to access privileged hardware.
* Installing a type 2 hypervisor on top of a host operating system grants some privileges, but the source operating system still has control.
* Users should install applications from trustworthy sources and recognize that there are only a handful of tested type 2 hypervisors available for Windows or Linux.

### [0:04:22](https://youtu.be/Datn43tf5RQ?t=262s) IO Devices

Overview: IO devices are complicated, and their electronic interfacing is done by controllers connected to the system bus. Each controller comes with its own software acting as a middle layer between it and the operating system.

* IO devices include keyboards, monitors, mice, etc.
* Controllers are connected to the system bus and require software interfacing between them and the operating system.
* Drivers act as middle layer software for device controllers provided by manufacturers.
* Users should always install software from trusted sources, especially drivers.

### [0:06:39](https://youtu.be/Datn43tf5RQ?t=399s) IO Methods

Overview: There are three types of IO methods used in computer hardware.

No bullet points were mentioned in this section.

## [0:08:01](https://youtu.be/Datn43tf5RQ?t=481s) Busy Waiting

Overview: In this section, the speaker discusses the concept of busy waiting and how it can be used to wait for data from a keyboard.

* Busy waiting involves running the CPU 100% of the time while waiting for data to become available.
* This approach is simple to implement but inefficient, especially for multi-programming purposes.
* Multi-processing systems switch to another process when one is busy waiting, making it better than busy waiting.
* Interrupts are a better way of doing I/O on typical computers. The CPU asks the controller for data and switches to another process while waiting. When the data is ready, an interrupt is generated, and the CPU stops whatever it was doing and handles the interrupt in kernel mode.

## [0:15:30](https://youtu.be/Datn43tf5RQ?t=930s) Introduction to Interrupts

Overview: This section discusses how interrupts work and the role of interrupt controllers in a computer system.

* A new device connected to the system bus can interrupt the CPU when necessary.
* There is a separate line between the CPU and the interrupt controller.
* Only the kernel mode CPU can program the interrupt controller.

### [0:16:27](https://youtu.be/Datn43tf5RQ?t=987s) Direct Memory Access (DMA)

Overview: This section explains how DMA works and its benefits for moving data between memory locations.

* DMA is responsible for moving data from one location to another without tying up the CPU.
* The CPU sets up the DMA chip with instructions on where to move data.
* Adding a DMA chip can increase the cost of a computer system, making it less desirable for embedded systems.

### [0:20:11](https://youtu.be/Datn43tf5RQ?t=1211s) Busy Waiting vs. Interrupts

Overview: This section discusses when busy waiting may be preferred over using interrupts or DMA.

* Busy waiting may be necessary if there are no interrupts or DMA available.
* In some cases, busy waiting may be more efficient than using interrupts or DMA due to context switching costs.
* Context switching is costly, but wasting CPU time in a busy loop is also costly.

## [0:23:26](https://youtu.be/Datn43tf5RQ?t=1406s) Tricks for Operating System Designers

Overview: The speaker discusses tricks that operating system designers use, such as switching to DMA interrupts if data is not ready.

* Use a few hundred loops/iterations before switching to DMA interrupts
* These tricks are used in CPU sensitive programming
* Busy waiting is helpful for branch prediction
* Efficiency is not important in busy waiting because the same question is asked repeatedly

### [0:24:55](https://youtu.be/Datn43tf5RQ?t=1495s) Branch Prediction and Busy Waiting

* Busy waiting can be efficient for branch prediction when there is a loop running and most of the time it runs in one way
* Invisibility usually wastes CPU time already, so efficiency isn't a concern
* Invalidating the pipeline doesn't matter when waiting for half a second

### [0:26:08](https://youtu.be/Datn43tf5RQ?t=1568s) Benefits of Busy Waiting

* When using busy waiting, there's no need for the operating system's help with I/O, so there won't be any context switching.

### [0:28:12](https://youtu.be/Datn43tf5RQ?t=1692s) Accessing Keyboard Controller Registers

Overview: The speaker explains how an ordinary program in user mode can access keyboard controller registers.

* I/O doesn't have to be done by user programs; it's done by the operating system.
* An operating system can do busy waiting too.

### [0:30:17](https://youtu.be/Datn43tf5RQ?t=1817s) Interrupts vs Traps for System Calls

Overview: The speaker compares interrupts and traps for system calls.

* Interrupts happen from the hardware side (e.g. keyboard or mouse controller)
* Traps are internal purposes that must be handled by the CPU

## [0:31:55](https://youtu.be/Datn43tf5RQ?t=1915s) Interrupts and System Calls

Overview: This section discusses interrupts and system calls in operating systems.

* Interrupts are mostly related to input/output devices.
* There is a way of getting how many interrupts a process is causing.
* System calls are another way to switch to the kernel.
* When executing a system call, the CPU switches to kernel mode.
* The kernel space is always executed in kernel mode and is only available for the operating system.

### [0:32:58](https://youtu.be/Datn43tf5RQ?t=1978s) How System Calls Work

* When executing a system call, the number of parameters is pushed onto the stack.
* The buffer address or pointer itself is pushed onto the stack.
* A special instruction called "system call" is executed, switching to kernel mode.
* The operating system looks up the corresponding system call function based on the code from register one.
* The data is read from user space and set up for input/output using DMA devices or other methods.

### [0:35:03](https://youtu.be/Datn43tf5RQ?t=2103s) Differences Between Interrupts and System Calls

* Both interrupts and system calls trap to the operating system's kernel space.
* Hardware interrupts are caused by controllers while software interrupts are caused by end users or programs making system calls.
* MIPS has its own set of primitive operating systems with less than 50 system calls available.

### [0:38:13](https://youtu.be/Datn43tf5RQ?t=2293s) MIPS System Calls

Overview: This section discusses how MIPS handles system calls.

* There are less than 50 MIPS system calls available, including printing integers, floats, doubles, and strings.
* To use a service, load its number into register zero and arguments into other registers using "set" operator before making a system call.
* An example of opening a file for writing mode using syscall number 13 was given.

## [0:40:04](https://youtu.be/Datn43tf5RQ?t=2404s) Operating Systems without Timer Interrupts

Overview: Some operating systems do not require a timer interrupt because they can switch processes during other types of interrupts.

* These operating systems rely on the fact that processors will eventually need help from the operating system and ask it to perform tasks.
* During this time, process switching can occur without the need for a timer interrupt.
* Other types of interrupts, such as disk and I/O interrupts, are used instead.

### [0:41:25](https://youtu.be/Datn43tf5RQ?t=2485s) Complex Computer Architecture

Overview: Real-world computer architecture is more complex than simplified models.

* Modern computers have multiple cores, L1 and L2 caches, GPU cores, memory controllers, and other components all on the same chip.
* Communication with GPUs requires fast communication speeds similar to shared cache speeds.
* Memory controllers are in a special place for speedy communication with RAM.
* The complexity of real-world computer architecture is important to consider when designing software.

### [0:42:46](https://youtu.be/Datn43tf5RQ?t=2566s) USB Bus

Overview: The USB bus was designed for hot-pluggable devices.

* Hot-pluggable devices can be plugged in without requiring a reboot.
* Early USB devices were slow (e.g. mice and keyboards), but later versions became faster than SCSI controllers (64 megabits per second).
* Controllers are still available for backward compatibility purposes.

### [0:43:56](https://youtu.be/Datn43tf5RQ?t=2636s) Basic Input Output System (BIOS)

Overview: BIOS is a primitive operating system that manages hardware during boot-up.

* BIOS is stored on read-only memory on the computer board and its task is to boot up the computer by checking basic input output devices and controllers.
* It scans PCIe devices to find mass storage devices like disks or SSDs to load the first sector from them as an operating system boot sector.
* BIOS provides services and manages complicated hardware but has limited user interaction capabilities since it's very primitive compared to modern OSes.

### [0:45:54](https://youtu.be/Datn43tf5RQ?t=2754s) Unified Extensible Firmware Interface (UEFI)

Overview: UEFI is an updated version of BIOS that offers faster boot times, better security features, and support for more hardware.

* Like BIOS, UEFI's main task is still to boot up the computer by loading an operating system from mass storage devices like disks or SSDs.
* However, UEFI provides additional features such as secure booting mechanisms that prevent unauthorized access during startup.

No new section created at 0:46:16 since there was no content.
