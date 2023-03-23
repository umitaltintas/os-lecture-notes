# lecture 8

## [0:00:03](https://youtu.be/qRsQT72k6WM?t=3s) Introduction to System Calls

Overview: In this chapter, we will be discussing system calls and their mechanisms. We will also look at the different types of system calls and how they are used in popular operating systems.

* Different CPUs have different mechanisms for system calls.
* When a system call is made, the CPU runs instructions in privileged mode and can do almost anything it wants.
* The operating system takes control when a process enters kernel mode, and only operating system code runs.
* The read function in C pushes integers and buffer addresses to the stack before calling the library function open.
* The library function read puts the code for reading into a special register and makes a trapped system call to the kernel.

### [0:04:45](https://youtu.be/qRsQT72k6WM?t=285s) Types of System Calls

Overview: There are about 100 procedure calls defined by POSIX that can be grouped into different types. One such group is Process Management, which includes making new processes, killing processes, getting information from processes, changing process cores, etc.

* Not many Process Management procedure calls exist in POSIX.
* The fork() system call creates an exact copy of a process with a new process ID.
* The parent process receives the child process ID as its return value while the child process receives 0 as its return value.

## [0:09:13](https://youtu.be/qRsQT72k6WM?t=553s) Forking Processes

Overview: This section explains how the fork is designed in Unix and how it creates new processes.

* The fork design may seem weird, but it's how the designers of Unix decided it should work.
* When a process is created with a digital ID, there are no other processes to go with it.
* Each new process created is independent and can continue running until it ends.

### [0:10:23](https://youtu.be/qRsQT72k6WM?t=623s) Changing Process Image

* To make a new process useful, we need to change its image using the `execve` system call.
* This procedure changes the code or image inside the process with a program on disk and starts running it.

### [0:11:50](https://youtu.be/qRsQT72k6WM?t=710s) Termination of Programs

* If you execute a program, you will terminate your current program.

### [0:12:10](https://youtu.be/qRsQT72k6WM?t=730s) Infinitely Forking Processes

* A loop that continuously forks processes will create infinitely many processes.
* Operating systems will either crash or stop due to insufficient memory if too many processes are created.
* Exponentially increasing numbers of processes can fill up memory quickly.

### [0:17:35](https://youtu.be/qRsQT72k6WM?t=1055s) Conclusion

Overview: In conclusion, this section warns against creating too many processes as they can fill up memory quickly. It also advises experimenting with forking to see how CPU and memory usage increases.

* Before running any programs that fork multiple times, check task manager to see how CPU and memory are utilized.

## [0:18:14](https://youtu.be/qRsQT72k6WM?t=1094s) Understanding System Calls

Overview: In this section, the speaker talks about the exit status of system calls and introduces a simple shell to make sense of them.

* The exit status can be obtained from the status location.
* A simple shell is introduced to issue commands that are executed by the system.

### [0:18:45](https://youtu.be/qRsQT72k6WM?t=1125s) Issuing Commands in a Simple Shell

* The speaker demonstrates how to use a simple shell to issue commands.
* Commands such as "list me my programs" and "CD downloads" are executed by the system.
* The speaker shows how to run Windows Explorer using the shell.

### [0:21:11](https://youtu.be/qRsQT72k6WM?t=1271s) Forking Processes in Unix

Overview: In this section, the speaker explains how forking processes work in Unix and demonstrates it using an infinite loop program.

* An infinite loop program is used to demonstrate forking processes in Unix.
* When a fork is made, a new process identical to the parent process is created.
* The parent process waits until its child terminates before continuing.

### [0:23:20](https://youtu.be/qRsQT72k6WM?t=1400s) Blocking Parent Process with Wait Command

Overview: In this section, the speaker explains how wait command blocks parent processes until their child processes terminate.

* The wait command is used to block parent processes until their child processes terminate.
* The parent process waits at this position until its child terminates.

## [0:28:06](https://youtu.be/qRsQT72k6WM?t=1686s) Redirecting Output to a File

Overview: In this section, the speaker demonstrates how to redirect output to a file using the command "la and um dot dot" and explains how it blocks input while waiting for the output.

* The process table is shown using the command "bash NPS".
* The speaker thanks someone for their input and adds it to their notes.
* The typical shell program is discussed, and examples are promised for later.

### [0:29:24](https://youtu.be/qRsQT72k6WM?t=1764s) Child Process Execution

* The parent side waits until the child process is finished executing.
* The code executed by the child process replaces the previous code.
* Any command given changes the core of the child process until it terminates.

### [0:32:06](https://youtu.be/qRsQT72k6WM?t=1926s) File Management System Calls

Overview: In this section, the speaker discusses system calls related to file management, such as opening, closing, reading, writing, seeking inside files, and getting status from open files or files on disk. These functions usually translate into system calls because regular user programs running in user mode do not have direct access to files.

## Summary

In this video segment, we learned about redirecting output to a file using commands like "la and um dot dot," blocking input while waiting for output. We also learned about child process execution where any command given changes the core of a child process until it terminates. Finally, we discussed system calls related to file management that translate into system calls because regular user programs running in user mode do not have direct access to files.
