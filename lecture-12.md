# lecture 12

## [0:00:10](https://youtu.be/s-9yJLL6EPM?t=10s) Introduction to Threads

Overview: In this section, the instructor introduces the concept of threads and explains how they differ from processes.

* A process always has a single execution occurring, while threads allow for multiple executions happening in the same process.
* Threads appear to run in parallel even though there is only one CPU, thanks to context switching done by the scheduler of the thread transactor.
* Threads are preferred over processes for some applications because they are lighter and faster due to their advantages in context switching and shared data space.

### [0:01:33](https://youtu.be/s-9yJLL6EPM?t=93s) Advantages and Disadvantages of Threads

* The advantage of threads is that inter-thread communication is simple since they share the same address space.
* The disadvantage of threads is that there is no way to achieve protection between different threads in the same process, which can be important for parallel tasks.

### [0:03:30](https://youtu.be/s-9yJLL6EPM?t=210s) Cooperation Between Threads

* Unlike processes, threads cooperate rather than compete with each other in a multithreaded application.
* Multithreaded applications are simpler to write and debug than single-threaded ones.

### [0:04:01](https://youtu.be/s-9yJLL6EPM?t=241s) Single Threaded Word Processor Example

* A single threaded word processor can handle keyboard input, update the screen, and take backups one after another using a loop.
* The biggest disadvantage of such a single threaded word processor is wasting time since other units have to wait for one unit to finish before starting.

### [0:05:06](https://youtu.be/s-9yJLL6EPM?t=306s) Advantage of Multithreaded Word Processor

* Even if there is only one CPU available, a multithreaded word processor can handle keyboard input, update the screen, and take backups simultaneously by assigning each task to a separate thread.
* This allows for better utilization of CPU time without wasting time waiting for other units to finish.

## [0:08:12](https://youtu.be/s-9yJLL6EPM?t=492s) Single Threaded Applications

Overview: The main problem with single-threaded applications is that they lose interactivity while performing tasks such as taking backups or updating the screen. This is because the operating system blocks the process until the task is complete.

* While a thread is blocked, other threads cannot execute.
* Multithreaded applications have an advantage in that they can continue executing other threads while one thread is blocked.

### [0:10:00](https://youtu.be/s-9yJLL6EPM?t=600s) Multithreaded Web Servers

Overview: Multithreaded web servers use a dispatcher thread to distribute requests to worker threads. This architecture simplifies the task of handling multiple requests and sharing data between them.

* The dispatcher thread waits for incoming requests and distributes them to worker threads.
* Worker threads are blocked until they receive work from the dispatcher thread.
* Requests may ask for the same data, so it's worth having multiple processes to share data efficiently.
* The dispatcher thread should have the highest priority in terms of scheduling.

## [0:15:45](https://youtu.be/s-9yJLL6EPM?t=945s) Introduction

Overview: The speaker introduces the concept of threads and how they differ from processes. They explain how threads cooperate with each other, while processes compete for resources.

* Threads help each other, while processes compete for resources.
* Different threads belonging to different processes do not cooperate with each other.
* Operating systems manage resources and distribute them fairly between different processes.

### [0:16:14](https://youtu.be/s-9yJLL6EPM?t=974s) Cooperation Between Threads

* Threads are lightweight processes that share many things, including heap space.
* There is no protection between threads because they are supposed to be within the same process and share the same address space.
* All threads can share the same set of open files, charts, alarm signals, etc.

### [0:18:17](https://youtu.be/s-9yJLL6EPM?t=1097s) Classical Thread Model

* Processes group together resources such as data, code, tag and heap space.
* Threads are lightweight processes that share many things but have their own program counters and registers.
* Each thread has its own stack where local variables are kept.

### [0:21:03](https://youtu.be/s-9yJLL6EPM?t=1263s) State of a Thread

* The state of a thread can be active or non-active (running or waiting).
* Each thread has its own stack which is important for running functions without any problems.

## [0:23:43](https://youtu.be/s-9yJLL6EPM?t=1423s) Global Variables in Multithreaded Applications

Overview: In multithreaded applications, global variables should be used with caution as they are shared between threads and can cause issues when updated. Constant global variables are okay to use as they cannot be updated.

* Global integers are not in the heap or stack and are shared between threads.
* Per-thread items are inside each process and not shared.
* Shared items include open files, processes, signals, accounting information, and disk space.
* Dynamically allocated memory is stored in the heap which is shared but it's okay to use as long as each thread has its own dynamically allocated position.

### [0:27:18](https://youtu.be/s-9yJLL6EPM?t=1638s) Dynamically Allocated Memory in Multithreaded Applications

* Using `new` operator to get a character array is valid but should be used with caution.
* Each thread will create its own dynamically allocated position and hold a different pointer to them.
* It is not expensive compared to single-threaded applications using dynamic aggregated memory.

## [0:31:53](https://youtu.be/s-9yJLL6EPM?t=1913s) Global Variables and Race Conditions

Overview: The speaker discusses the importance of being careful when using global variables in multi-threaded applications due to the possibility of race conditions.

* Race conditions occur when multiple threads access a shared resource without proper synchronization, leading to unpredictable results.
* To avoid race conditions, it is important to use protection mechanisms such as critical regions and thread libraries.

### [0:34:11](https://youtu.be/s-9yJLL6EPM?t=2051s) Thread Libraries

Overview: The speaker introduces POSIX threads (pthreads), a standard library for dealing with threads in Unix-based operating systems.

* Pthreads provide functions for creating, terminating, and waiting for threads.
* The `pthread_yield()` function allows a thread to voluntarily release the CPU to let other threads run.
* Unlike processes, there are no clock interrupts enforcing multi-programming in threads. Threads voluntarily release their CPUs or block when waiting for input/output operations.

### [0:37:47](https://youtu.be/s-9yJLL6EPM?t=2267s) Initializing and Destroying Thread Data Structures

Overview: The speaker discusses the importance of initializing and destroying thread data structures properly.

* Proper initialization and destruction of thread data structures ensure that memory is allocated correctly and prevent memory leaks.
* Clock interrupts do not enforce multi-programming in threads; instead, threads voluntarily release their CPUs or block when waiting for input/output operations.

## [0:39:58](https://youtu.be/s-9yJLL6EPM?t=2398s) Void Pointers and Type Checking

Overview: When void pointers are involved, the C compiler turns off type checking. For scalar functions like `printf`, the compiler doesn't know how to type check it and it is turned off all the time.

* The function `pthread_exit` is called with a void pointer.
* The null can be used as a void pointer.

### [0:40:31](https://youtu.be/s-9yJLL6EPM?t=2431s) Running Threads

* 10 threads are created using a data structure `p_thread`.
* A loop runs from 0 to 10, creating each thread with `pthread_create`.
* A function pointer is passed to `pthread_create` along with a parameter that is sent as an avoid pointer.
* As soon as the line of code for creating the thread is executed, the thread starts running and prints "Hello World greetings from thread number X".
* The order of execution of threads cannot be predicted due to scheduling in multi-threaded applications.

### [0:43:08](https://youtu.be/s-9yJLL6EPM?t=2588s) Thread Execution Order

Overview: In multi-threaded applications, scheduling determines which thread executes first. It may appear random due to its complexity.

* If an application depends on the order of execution of threads, inter-process communication must be implemented.

## [0:44:09](https://youtu.be/s-9yJLL6EPM?t=2649s) Function Parameters in Threads

Overview: Each thread has its own stack.

* Each thread has its own unique stack.
* The process stack is used for all threads if there is only one thread executing.

## [0:48:13](https://youtu.be/s-9yJLL6EPM?t=2893s) Inspecting Variables

Overview: In this section, the speaker suggests writing a simple program to inspect global variables, dynamically allocated variables, and local variables by printing their addresses on the screen.

* Write a simple program that includes global variables, dynamically allocated variables, and local variables.
* Print the addresses of these variables on the screen to compare them.

### [0:48:42](https://youtu.be/s-9yJLL6EPM?t=2922s) Experimenting on Different Operating Systems

Overview: The speaker recommends performing the same experiment on both Windows and Unix operating systems.

* Conduct the same variable inspection experiment on Windows.
* Conduct the same variable inspection experiment on Unix.

### [0:48:52](https://youtu.be/s-9yJLL6EPM?t=2932s) Break Time

Overview: The speaker announces a break before continuing with further discussion.

No bullet points for this section.
