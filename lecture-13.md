# lecture 13

## [0:00:02](https://youtu.be/zkWUcLhe8Y0?t=2s) Modifying Code

Overview: The speaker talks about modifying code found on the web to resemble a call from a book.

* Modified code found on the web to resemble a call from a book.
* Created a function that sleeps for one second and prints the given parameter as an integer.
* Used a thread pool of 10 threads, where each thread sleeps, prints its message, and terminates.
* When run multiple times, the starting order of threads is unpredictable due to sleeping for one second each.

### [0:01:17](https://youtu.be/zkWUcLhe8Y0?t=77s) Unpredictable Behavior

Overview: The speaker discusses how running multiple threads can lead to unpredictable behavior.

* Running multiple threads can lead to unpredictable behavior due to sleeping for one second each.
* The starting order of threads is unpredictable due to sleeping for one second each.

### [0:03:00](https://youtu.be/zkWUcLhe8Y0?t=180s) Same Output

Overview: The speaker talks about getting the same output when running the code without sleep.

* Running the code without sleep leads to more predictable starting times but still produces different outputs.
* Starting times are not guaranteed to be in order due to multi-programming applications and operating system decisions.

### [0:04:56](https://youtu.be/zkWUcLhe8Y0?t=296s) Thread Library

Overview: The speaker mentions that this course is not about systems programming but rather implementing thread libraries and support from an operating system.

* This course is not about systems programming but rather implementing thread libraries and support from an operating system.
* Implementing thread libraries can be done in two ways - user level or kernel level.
* User level implementation involves doing all scheduling without telling the operating system, while kernel level implementation involves using the operating system's scheduler.

## [0:08:28](https://youtu.be/zkWUcLhe8Y0?t=508s) User Space vs Kernel Space Threads

Overview: This section discusses the two different ways of implementing thread support, either in user space or kernel space. The advantages and disadvantages of each approach are explored.

* To create a new thread, a system call is made to the operating system in kernel space.
* In user space, thread creation, destruction, and scheduling are done at the user level by libraries.
* Thread tables are used to keep track of threads in both approaches.
* Context switching is very light in user space threads as there is no involvement of the operating system.
* Implementing threads in user space does not require any system calls or context switching, making it more efficient than kernel space threads.
* Specialized scheduling algorithms for applications like web servers can be implemented with user space threads.

### [0:09:53](https://youtu.be/zkWUcLhe8Y0?t=593s) Advantages of User Space Threads

* No need for operating system support, making it compatible with any kind of operating system.
* Context switching is very light as there is no involvement of the operating system.
* Specialized scheduling algorithms can be implemented for specific applications like web servers.
* No need for hardware memory cache flushing or copying data across protection boundaries.

### [0:11:25](https://youtu.be/zkWUcLhe8Y0?t=685s) Disadvantages of Kernel Space Threads

* System calls are required to create new threads and switch between them, making it less efficient than user space threads.
* Context switching requires changing CPU mode from user mode to kernel mode which can be expensive.

### [0:13:13](https://youtu.be/zkWUcLhe8Y0?t=793s) Advantages of Kernel Space Threads

* The operating system can manage threads more efficiently than user space libraries.
* Kernel space threads are better suited for general-purpose applications.

### [0:14:12](https://youtu.be/zkWUcLhe8Y0?t=852s) Creating User Space Threads

* To create a thread in user space, storage for stack program control state must be allocated.
* Thread tables are used to keep track of threads in user space.
* The thread library saves everything in the thread table and the thread scheduler runs in user space.

## [0:15:49](https://youtu.be/zkWUcLhe8Y0?t=949s) Advantages of User Level Threads

Overview: This section discusses the advantages and disadvantages of user level threads.

* Allows for customized scheduling algorithms
* Can have as many threads as memory allows

### [0:16:40](https://youtu.be/zkWUcLhe8Y0?t=1000s) Disadvantages of User Level Threads

* Blocking system calls is the main disadvantage
* Inability to benefit from multi-processor CPUs
* Kernel can't automatically grow per thread stacks

### [0:22:35](https://youtu.be/zkWUcLhe8Y0?t=1355s) Advantages of Kernel Level Threads

Overview: This section discusses how kernel level threads differ from user level threads.

* Each thread holds its own thread table and scheduler
* Kernel manages thread creation, destruction, and scheduling

## [0:24:09](https://youtu.be/zkWUcLhe8Y0?t=1449s) User Level Threads vs Kernel Level Threads

Overview:

* Multi-CPU case can be handled easily, but context switching is expensive.
* Implementing user level threads and kernel level threads can allow for market traded applications without operating system support.

### [0:24:32](https://youtu.be/zkWUcLhe8Y0?t=1472s) Implementation of User Level Threads and Kernel Level Threads

* Using appropriate libraries without telling much to the operating system can allow for market traded applications.
* Running into issues without operating system support.

### [0:25:14](https://youtu.be/zkWUcLhe8Y0?t=1514s) Forking Processes and Addressing Thread Issues

* When a process forks, the new process will have the same number of threads.
* Issues with signals, files, etc. need to be addressed depending on design philosophy.

### [0:26:07](https://youtu.be/zkWUcLhe8Y0?t=1567s) Hybrid Solution for User Level Threads and Kernel Level Threads

* A hybrid solution involves having both kernel level thread support and a thread table in the kernel.
* The kernel thinks there are two threads happening inside a process, but in fact they are shared by different user level threads.

### [0:27:14](https://youtu.be/zkWUcLhe8Y0?t=1634s) Solutions for Multiplexing User Level Threads with Kernel Level Threads

* One solution is to have the kernel aware only of the kernel level threads and schedule those while user level threads are multiplexed.
* Another solution is scheduler applications and activations using up calls where the operating system reports an event to a user level process.

### [0:29:31](https://youtu.be/zkWUcLhe8Y0?t=1771s) Up Calls and Changing the Operating System Structure

* Up calls involve the kernel calling a user level process to report an event.
* This changes the operating system structure where the application becomes more complicated with both program and operating system information.

## [0:31:56](https://youtu.be/zkWUcLhe8Y0?t=1916s) Understanding Thread Blocking

Overview: This section discusses how the operating system handles thread blocking and unblocking. When a thread is blocked, the operating system allows it to continue but schedules another thread until the data is ready. The application can mediate itself as a scheduler and schedule another thread when the data is ready.

* The operating system doesn't block immediately but lets the program continue.
* When data is ready, an up call is made to activate the scheduler.
* The originally blocked thread can be rescheduled using schedule activations.
* Writing multi-threaded code requires handling unblocking calls.

### [0:34:00](https://youtu.be/zkWUcLhe8Y0?t=2040s) Hybrid Translated Activations

Overview: This section briefly mentions hybrid translated activations as another way to find solutions for user-level threads and kernel-level threads.

* No content available.

### [0:34:50](https://youtu.be/zkWUcLhe8Y0?t=2090s) Writing Multi-threaded Code

Overview: This section explains that writing multi-threaded code differs from writing single-threaded code. It also discusses how local variables and parameters do not cause any trouble because they are in the stack for each thread. However, global variables that are not constant can cause problems.

* Writing multi-threaded code differs from writing single-threaded code.
* Local variables and parameters do not cause any trouble because they are in the stack for each thread.
* Global variables that are not constant can cause problems.
* One solution is to prohibit non-constant global variables or have each thread have its own global variable.

### [0:37:08](https://youtu.be/zkWUcLhe8Y0?t=2228s) Using Threads with C Programming

Overview: This section discusses how some functions in C programming, such as Str tokenize, use static variables to remember the original string. However, static variables are global variables and can cause problems when multiple threads are running the function at the same time.

* Str tokenize uses static variables to remember the original string.
* Static variables are global variables and can cause problems when multiple threads are running the function at the same time.
* Reentrant routines should be used instead of static or global variables.
* Many C libraries use static or global variables, which is not recommended for multi-threaded applications.

## [0:40:38](https://youtu.be/zkWUcLhe8Y0?t=2438s) Introduction to Local Time

Overview: In this section, the speaker discusses local time and its conversion from a given time value.

* The function `localtime()` converts a given time into a calendar time expressed in local time.
* The result is stored in static storage and a pointer to that static theology is returned.
* This method is not thread-safe and can cause issues for multi-threaded applications.

### [0:41:47](https://youtu.be/zkWUcLhe8Y0?t=2507s) Differences Between `localtime()` and `localtime_r()`

* `localtime_r()` returns an internal object on success or null pointers.
* It may be shared between GM time Etc.
* Unlike `localtime()`, it is thread-safe as there is no internal static data involved.
* `localtime_r()` requires the user to provide memory to store the results.

### [0:44:21](https://youtu.be/zkWUcLhe8Y0?t=2661s) Global Variables

* Global variables are used for interprocess communication between threads.
* Care must be taken when using global variables as they require synchronization access.
* Interprocess communication should be valid but we must be careful about it.

## [0:45:33](https://youtu.be/zkWUcLhe8Y0?t=2733s) Future Topics

Overview: In this section, the speaker outlines future topics that will be discussed in upcoming lectures.

* Inter-process communication
* Scheduling processes and threads
* CPU abstraction
* Memory
