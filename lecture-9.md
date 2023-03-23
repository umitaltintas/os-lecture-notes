# lecture 9

## [0:00:11](https://youtu.be/WftVVTree5w?t=11s) Introduction to POSIX

Overview: In this section, the speaker introduces POSIX, which is the operating system standard for Unix defined in the 1980s. The speaker explains that there are about 100 procedure calls in POSIX, and each procedure call may or may not be converted to a system call.

* Procedure calls might be handled in user space if possible to avoid context switches.
* System calls are expensive, so they try to avoid contact switches.

### [0:01:30](https://youtu.be/WftVVTree5w?t=90s) Process Management Procedure Calls

Overview: In this section, the speaker discusses process management procedure calls such as torque and exit. They also mention that there are variations of these procedures that will be covered in a systems programming course.

* There are variations of process management procedure calls.
* These procedures can be converted into system calls.
* Torque and exit are examples of process management procedure calls.

### [0:01:58](https://youtu.be/WftVVTree5w?t=118s) Simple Shell

Overview: In this section, the speaker talks about a simple shell like Bash or seashell that only accepts a command and parameters from the terminal and executes it with a child process.

* A simple shell only executes one command at a time.
* This type of shell is not very useful because it cannot handle multiple commands.

### [0:04:01](https://youtu.be/WftVVTree5w?t=241s) File Management Procedure Calls

Overview: In this section, the speaker discusses file management procedure calls such as opening files for reading/writing/creating/closing them. They also talk about file descriptors being an index into open files data structure in your process table.

* Opening files can have different parameters depending on what you want to do with them.
* Closing files is important to free up resources.
* File descriptors are just integers used as an index into open files data structure.

### [0:05:29](https://youtu.be/WftVVTree5w?t=329s) Linking Files

Overview: In this section, the speaker talks about linking two files together by creating an inventory name pointing to name one. They explain how linking works using unique inode numbers assigned to each file.

* Linking creates a pointer from one file to another without copying it.
* Unique inode numbers identify each file in Unix directories.

Overall, this video covers some basic concepts related to POSIX operating systems such as process management and file management procedures. It also touches on linking files together using unique inode numbers assigned to each file.

There is no content in this section.

## [0:17:16](https://youtu.be/WftVVTree5w?t=1036s) Issues with CD command

Overview: The speaker is discussing the issue of not finding a command for CD on their file system.

* Speaker couldn't find a program for CD on their file system.
* They found programs for LS, RM, and CAT.
* The shell being used can't handle CDI because it's a simple shell.
* CD is a built-in command in the shell that changes the current routing directory.

### [0:20:50](https://youtu.be/WftVVTree5w?t=1250s) Why doesn't CD have a standalone program?

* CD is a shell building command that changes the current routing directory.
* It needs to be built into the shell because it changes its own working directory and terminates, not changing the user's working directory.
* Running a separate CD command wouldn't make sense because it would change that command's working directory, not the user's.

## [0:22:26](https://youtu.be/WftVVTree5w?t=1346s) Exit Command

Overview: The speaker discusses how exit works in shells and shell programs.

* When executing an exit command, it terminates that program only, not the user's program.
* There is no standalone executable program for exit since it only terminates that specific program.
* Typing exit will terminate that specific shell instance.

## [0:23:27](https://youtu.be/WftVVTree5w?t=1407s) Memory Layout

Overview: The speaker explains memory layout in Unix systems.

* Addresses start from zero and grow to large numbers depending on machine structure.
* At the bottom of memory space are code instructions to execute; at the top are stacks.
* Data grows upwards while stack rolls downwards.
* Physical memory does not keep empty spaces as there is sophisticated hardware support and operating system support.

## [00:26:31](https://youtu.be/WftVVTree5w?t=1591s) Core Memory

Overview: This section discusses core memory, which was used in the early days of computing. It was built by hand and used magnetic cores to store data.

* Magnetic core memory was a 32x32 grid, with a total of 1024 bits or 128 bytes of data.
* Cores were magnets that could be changed by applying current to the appropriate line.
* Each bit could be physically seen, making them large in size but small in terms of the number of bits they could hold.
* Core memory has not been used for the last 60-70 years, except for space programs where proven technologies are preferred.
* Even current satellites still use computers built with core memory technology.

## [00:31:26](https://youtu.be/WftVVTree5w?t=1886s) Windows Operating System

Overview: This section compares Unix/Linux operating systems to Windows operating system and its API (Application Programming Interface).

* Windows uses specified procedure calls or APIs instead of system calls like Unix/Linux.
* There is no Fork command in Windows; instead, it uses Create Process command which creates a new process without copying anything from the parent process.
* Linking and mounting are not available in Windows kernel.
* The mode of a file (read/write/execute) is supported at the model level but not at the kernel level.

## [0:35:27](https://youtu.be/WftVVTree5w?t=2127s) User Permissions in Unix and Windows

Overview: The user permissions in Unix and Windows are different. In Unix, permissions are assigned using octal numbers, while in Windows, permissions are assigned using groups.

* In Unix, a user can read, write, and execute as a group they belong to.
* Octal 7 (111) means that everyone can read, write, and execute the file.
* Windows NT supports this capability but not earlier versions of Windows.
* Signals are not supported by the Windows operating system.

### [0:36:27](https://youtu.be/WftVVTree5w?t=2187s) System Calls in Operating Systems

* Windows has hundreds of procedure calls while Unix has thousands.
* Graphical user interfaces run as a separate process on Unix but are part of the kernel on Windows.
* System calls on Windows can do whatever they want with hardware and are more efficient than those on Unix.

### [0:38:25](https://youtu.be/WftVVTree5w?t=2305s) Design Decisions in Operating Systems

Overview: Design decisions for operating systems are based on historical events.

* Unix was designed after Multics to simplify multiple operating systems and address some problems of Matrix.
* Backwards compatibility is always kept alive when introducing newer versions of Windows.
* Our book has two chapters about the design of the Unix and Windows operating systems.

### [0:40:02](https://youtu.be/WftVVTree5w?t=2402s) Monolithic Approach to Operating System Architecture

Overview: The monolithic approach is writing an entire operating system as a single program.

* Millions of lines of code run as a single program making it very efficient but difficult to upgrade or debug.
* There is some structuring to it with main procedures using service procedures under them that have utility procedures.

### [0:42:18](https://youtu.be/WftVVTree5w?t=2538s) Layered Approach to Operating System Architecture

Overview: The layered approach involves writing an operating system in layers with each layer having specific tasks.

* Layer 0 is the most basic layer responsible for task processing allocation and multi-programming scheduling.
* Each layer has its own level of hardware protection with level 0 being the most privileged.

## [0:43:31](https://youtu.be/WftVVTree5w?t=2611s) Layered Approach

Overview: This section discusses the layered approach used in operating systems.

* The operating system is written in a way that follows a layered approach.
* Different layers are supported, and some parts of the operating system run in layer zero while others run on layer one.
* Not all parts of the operating system can do whatever they want; they have to be at the appropriate level.

### [0:44:21](https://youtu.be/WftVVTree5w?t=2661s) Micro Kernels

Overview: This section discusses micro kernels and their structure.

* A micro kernel structure keeps the kernel very small, with only a few thousand lines of code.
* With such limited code, input/output and file systems cannot be done within the kernel.
* In a micro kernel operating system, drivers or servers are kept as separate user mode processes.
* Whenever these processes need to do something privileged, they will ask the kernel to do it for them.
