# lecture 1

## [0:00:11](https://youtu.be/fDEc7dHReIE?t=11s) Introduction

Overview: The instructor introduces the course and its requirements.

* CSE 312 and 544 is a joint course for undergrad and graduate students.
* Students should follow the class announcements, homework submissions, and announcements on the Teams page.
* The recommended textbook for the course is essential to follow along with the material.
* Students must know C programming language, computer architecture, and have passing grades from CSE102 and CSE331 to take this course.

### [0:02:23](https://youtu.be/fDEc7dHReIE?t=143s) Prerequisites

Overview: The instructor discusses prerequisites for taking this course.

* Undergrad students who do not meet prerequisites are not supposed to take this course.
* Graduate students should know C programming language or computer architecture before taking this course.
* Passing grades from CSE102 and CSE331 are required for undergrad students to take this course.

### [0:04:34](https://youtu.be/fDEc7dHReIE?t=274s) Questions

Overview: The instructor answers student questions about prerequisites.

* If a student has a good passing grade from CAC 102, they should be fine taking this course without having taken data structures and algorithms.
* Officially, passing grades from both courses are required but not necessary if a student has a good understanding of linked lists, stack, array structures taught in CAC 102.

### [0:05:53](https://youtu.be/fDEc7dHReIE?t=353s) Homework

Overview: The instructor explains how homework will be graded.

* Students will use G++ compilers or other programs specified in homework descriptions to compile their programs.
* Homework will be done on virtual machines provided by the instructors.
* Instructors will not fix code that does not compile or make changes to submitted code.
* It is important to use exact tools specified in homework descriptions as there may be compatibility issues between environments.

## [0:08:14](https://youtu.be/fDEc7dHReIE?t=494s) Grading and Instruction Methods

Overview: The grading for the course will depend on how the semester progresses. 30% of the grade will come from midterms, 40% from the final, and 30% from homework. However, this may change depending on whether instruction is online or face-to-face.

* Quizzes may be used more frequently if everything is online.
* Class attendance is important as quizzes will be given during lectures.
* Inverted class method will be implemented where students watch videos before class and ask questions during class.

### [0:11:25](https://youtu.be/fDEc7dHReIE?t=685s) Inverted Class Method

* Students are expected to watch videos before coming to class.
* During class, students ask questions and the professor answers them.
* The interactive nature of the class serves as a quiz grade.

### [0:13:53](https://youtu.be/fDEc7dHReIE?t=833s) Homework Rules

* Submitting less than 75% of homework results in a VF grade.
* Late submissions result in losing 10% of maximum grade per day up to four days late.
* Emergency situations can be discussed with professor or TA before due date.

### [0:15:30](https://youtu.be/fDEc7dHReIE?t=930s) Exam Plans

* No plans for online exams at this time.
* Plans are tentative and subject to change based on how the semester progresses.

## [0:16:49](https://youtu.be/fDEc7dHReIE?t=1009s) Attendance and Course Overview

Overview:

* Attendance is not compulsory but it is required for quizzes and questions during lectures.
* All classwork, announcements, homework, and submissions will be done through the Teams page.
* Honor code is strictly enforced.

### [0:20:14](https://youtu.be/fDEc7dHReIE?t=1214s) Honor Code

* Misrepresenting someone else's work as your own is not allowed.
* Cheating will be dealt with accordingly.

### [0:21:01](https://youtu.be/fDEc7dHReIE?t=1261s) Course Content Overview

Overview:

* The course covers general operating system ideas, processes and threads, memory management, file systems, and I/O devices.
* Operating systems are an abstraction of underlying hardware.

### [0:22:29](https://youtu.be/fDEc7dHReIE?t=1349s) Feedback and Exams

* Feedback will be given as soon as possible but may not always happen immediately.
* Exams are based on knowledge from the book. No deep mathematical problems will be solved in this course.

## [0:25:11](https://youtu.be/fDEc7dHReIE?t=1511s) Grading and Expectations

Overview: The homework will be graded, and the grading is not based on normal trading until the end of the semester. The target grade should be an A, not a CC. It is not acceptable to only know half of the chapters covered in class.

* Homework will be graded
* Target grade should be an A
* Knowing only half of the chapters covered in class is not acceptable

### [0:25:58](https://youtu.be/fDEc7dHReIE?t=1558s) Full Understanding Required

* Half knowledge is not acceptable
* You are supposed to know everything that is taught
* Aim for an A grade, not a CC

### [0:27:19](https://youtu.be/fDEc7dHReIE?t=1639s) Grades and Mistakes

* Mistakes can happen during exams and homework
* Creative AI will be given for overgrades of 80s or 75s
* It's possible to get an AA from this course without giving too much work

### [0:28:12](https://youtu.be/fDEc7dHReIE?t=1692s) Basic Understanding Required

Overview: The basic idea and main idea of operating systems should be understood.

* Getting high grades will result in an A for everyone.
* If everyone gets low grades, then FF may be given.
* Basic understanding of software operating systems is required.

## [0:29:16](https://youtu.be/fDEc7dHReIE?t=1756s) Camera Angle Change

No content.

## [0:30:39](https://youtu.be/fDEc7dHReIE?t=1839s) Mic Check

Overview: Checking if the mic works properly.

No bullet points needed.

## [0:31:20](https://youtu.be/fDEc7dHReIE?t=1880s) Campus Attendance

Overview: Checking who's near campus.

No bullet points needed.

## [0:33:05](https://youtu.be/fDEc7dHReIE?t=1985s) Operating Systems

Overview : Defining what operating systems are and their complexity.

* Operating systems are complex pieces of software that know hardware very well.
* They are difficult to understand but surprisingly some computer scientists don't fully understand them.

## [0:33:43](https://youtu.be/fDEc7dHReIE?t=2023s) Introduction to Operating Systems

Overview: The operating system is a complicated software system that abstracts computer hardware through interfaces and manages resources. It makes our life easier as computer users or software developers.

* 80 million lines of code make up the operating system, which is a very complicated system.
* A single line of code in a program can touch one million lines of operating system and library code due to the use of libraries and operating system services.
* Without an operating system, it would be impossible to develop software or use a computer efficiently.
* This course will teach us about the structure, components, abstractions, modularity, and iteration of an operating system.

## [0:52:18](https://youtu.be/fDEc7dHReIE?t=3138s) Abstraction of Computer Hardware

Overview: The operating system hides all messy details of the underlying hardware.

* Modern computers have many components such as processors, memory, disks (mechanical or solid-state), printers, input/output devices (mice, keyboard), network adapters, graphic interface.
* Managing all these components requires a layer of software that's the operating system.
* User programs communicate with hardware using the operating system services.
* The user interface program communicates with the OS which then communicates with IO devices.

## [0:53:49](https://youtu.be/fDEc7dHReIE?t=3229s) Role of Operating System

Overview: The role of the OS is to control all hardware components and provide services for user programs.

* The logical picture shows that the OS sits on top of CPU, memory and IO devices controlling them.
* User programs like web browsers or email readers communicate through hardware using OS services.
* As a programmer writing an email reader program I need to open files/close files etc., so I call functions in my program which are connected to the OS.
* Communication between user programs and IO devices gets very detailed and complicated.

## [0:56:45](https://youtu.be/fDEc7dHReIE?t=3405s) Managing Resources

Overview: The operating system manages all the components of a computer system, including interacting with them, reading data from them, and writing to them. It must be fair, protect resources, and be efficient.

* The operating system abstracts away the details of hardware.
* It virtualizes the underlying machine so that users think they have more than one CPU and memory resource.
* Hundreds of programs can run at once on a single CPU because it is virtualized.

### [0:57:47](https://youtu.be/fDEc7dHReIE?t=3467s) Virtualizing the Underlying Machine

* A single CPU means only one program can run at a time on a computer.
* Virtualizing the CPU allows multiple programs to run simultaneously.
* Users see multiple CPUs and memory resources but they are all shared.

### [0:59:13](https://youtu.be/fDEc7dHReIE?t=3553s) Managing Resources

Overview: The operating system manages resources such as processors, memory, timers, disk drives, network interfaces, printers and displays. It does this by sharing or multiplexing them in time or space.

* Timers are important for producing time signals and interrupting programs so that other programs can use the CPU.
* Sharing resources means being careful about protecting them while allowing multiple users to access them without knowing they are sharing.
* Space sharing involves dividing up resources like mechanical disks into sectors and tracks for different users.

### [1:03:06](https://youtu.be/fDEc7dHReIE?t=3786s) Time Sharing

* In time sharing, the CPU is shared between different processes in time intervals.
* Each process gets a certain amount of time before another process takes over.

### [1:03:50](https://youtu.be/fDEc7dHReIE?t=3830s) Space Sharing

* In space sharing, different parts of a resource like a mechanical disk are assigned to different users.
* Each user thinks they have exclusive access to their part of the resource.

## [1:05:12](https://youtu.be/fDEc7dHReIE?t=3912s) Managing Resources

Overview: This section discusses the concept of protection in resource management and how it is important for the security of the computer.

* Protection is necessary when switching from one process to another so that the second process cannot access the first process's resources.
* Memory, I/O devices, and other resources must be managed efficiently while also providing fairness and protection.
* The operating system is a piece of software that uses these resources too, so it must balance efficiency with fairness and protection.

### [1:05:28](https://youtu.be/fDEc7dHReIE?t=3928s) Protection

* When switching between processes, the interrupted process should be protected from being accessed by the new process.
* If a part of memory belongs to one user or process, it should not be accessible by another user or process.
* Providing protection is important for security as malicious individuals may try to hack into systems that lack proper protection.

### [1:06:03](https://youtu.be/fDEc7dHReIE?t=3963s) Resource Management

* Resource management involves managing CPU usage, memory allocation, I/O devices, etc.
* The operating system must provide fairness and efficient use of resources while also protecting them.
* Efficiency may sometimes require trade-offs between fairness and protection.

### [1:09:29](https://youtu.be/fDEc7dHReIE?t=4169s) Operating System Overview

Overview: This section provides an overview of what an operating system is and its components.

* An operating system includes shells, servers, graphical user interfaces (GUI), libraries, etc.
* Windows 10/11 has 50 million lines of code while OS 10 has 88 million lines of code.

### [1:10:34](https://youtu.be/fDEc7dHReIE?t=4234s) Narrow Definition of Operating System

Overview: This section discusses the narrow definition of an operating system which equates it with the kernel.

* The kernel is responsible for transmitting special privileges to software running on the CPU.
* Only parts of the operating system run in kernel mode where they have full access to all resources.
* User programs do not run in kernel mode as this would be too dangerous.
