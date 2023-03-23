# lecture 6

## [0:00:05](https://youtu.be/Ta1r3FWBMpc?t=5s) Types of Operating Systems

Overview: In this section, we will discuss the different types of operating systems.

* Mainframe operating systems
* Server operating systems
* Multiprocessor operating systems
* Personal operating systems
* Embedded operating systems

### [0:01:16](https://youtu.be/Ta1r3FWBMpc?t=76s) Mainframe Operating Systems

* Used in government centers, agencies, and major corporate data centers.
* Room-sized computers with thousands of disks and millions of gigabytes of data.
* Used for batch processing, transaction processing, and time-sharing.

### [0:03:48](https://youtu.be/Ta1r3FWBMpc?t=228s) Server Operating Systems

* Serve multiple users at once over a network.
* Examples include print services and file services.
* Popular server operating systems include Linux, Windows Server, FreeBSD.

### [0:05:08](https://youtu.be/Ta1r3FWBMpc?t=308s) Multiprocessor Operating Systems

* Used to allocate processes to different processors.
* Many popular operating systems including Windows and Linux run on multiple processors nowadays.

### [0:06:26](https://youtu.be/Ta1r3FWBMpc?t=386s) Personal Operating Systems

* Interactivity and user satisfaction are the number one issue for personal computer operating systems.
* Examples include Windows 10/11, Linux, Apple's OS 10.

### [0:06:53](https://youtu.be/Ta1r3FWBMpc?t=413s) Embedded Operating Systems

No content.

## [0:07:51](https://youtu.be/Ta1r3FWBMpc?t=471s) Embedded Operating Systems

Overview: This section discusses the need for an operating system in embedded systems and why they do not require protection.

* A processor and operating system are needed for devices such as TVs, microwaves, and refrigerators.
* Embedded systems are used for specific tasks and have their own screen for interaction.
* Protection is not needed in embedded operating systems because they are designed to satisfy protection requirements during the design process.
* User programs are written by the manufacturer of the device, so there should be no issues with data access between applications.
* Skipping protection features makes hardware cheaper, which is important for simple computers with limited CPU power and memory.
* Specialized lightweight embedded operating systems like Embedded Unit Linux or VX Works are used on small processors like ARM processors.

### [0:12:23](https://youtu.be/Ta1r3FWBMpc?t=743s) Sensor Node Operating Systems

* Sensor node operating systems run in rural areas where they must run without intervention for months or even a year.
* They wake up when an event occurs, handle it, communicate with other computers around them, then go back to sleep.
* These systems cannot have powerful CPUs because that would require too much power. Tiny OS is an example of an operating system for sensor nodes.

### [0:13:25](https://youtu.be/Ta1r3FWBMpc?t=805s) Smart Card Operating Systems

* Smart card operating systems are found on credit cards and handle transactions when inserted into a card reader.
* They have severe processing power and memory constraints due to their small size.
* There is no talk of protection or multi-programming as these computers only perform a single task.
* Java virtual machines can be used to run Java programs on top of this small card operating system.
