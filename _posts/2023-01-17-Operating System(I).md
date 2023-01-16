---
layout: post
title: Operating System(I)
tags: 計算機概論
date: '2023-01-17 01:35 +0800'
published: true
---
計算機概論-Operating System(I)隨手記
{: .message }

# Operating System(I)
## Batch processing(early era)
* The process of computer operators entering data to the computers and give the result back to you.
    ![](https://i.imgur.com/mVRCkv6.png)

## Interactive processing(early era)
* OS with remote terminals
    ![](https://i.imgur.com/Kovmajm.png)
* Types of operating system
    * Batch(批次)
    * Interactive
    * Real-time 
        * Response time is critical.
    * Time-sharing and multitasking
        * Dividing time into intervals.
        * Only one task is being performed at any given time.
    * Multiprocessor
        * Load balancing
        * Scaling 
    * http://www.chwa.com.tw/TResource/VS/book1/ch3/3-2.htm
* Software classification
![](https://i.imgur.com/WyObhvz.png)
* Shells
    * Communication with users
        * Text based
        * GUI(Graphical user interface )
## Kernel
* File manager
    * Directory/folder path
* Device drivers
* Memory manager
    * Allocating main memory
    * Paging, virtual memory  
* Schedular
    * The component which selects process to execute.
* Dispatcher
    * The component which gives control of CPU to execute the process selected by Schedular. 
## Linux
* Made by Linus Torvalds
* Freeware and open-source
* Many distribution (Ex: Ubuntu，Kali)
* Linux only means the kernel
## How is OS being loaded?
![](https://i.imgur.com/2CzC6fw.png)
* BIOS(Basic Input/Output Sytem)is usually stored on a EEPEROM chip(Electrically-Erasable Programable Read-Only Memory)
## Process
* The activity of executing a program
* Process state
    * Program counter
    * General purpose registers
    * Associated memory cells
* Process table
    * Memory area assigned to the process
    * Priority
    * Ready/waiting(One process for each core)
## Process Administration
* Schedular
    * Use: Maintaining the process table
    * Introducing new process
    * Removing completed process
    * Deciding whether a process is ready or waiting
* Dispatcher
    ![](https://i.imgur.com/ae6Hv5z.png)

    * Use: Getting the process to running state.
    * Controling the allocation of time to the process in the process table.
    * Process switch(interrupt)
    ![](https://i.imgur.com/vvtyj1e.png)
    Multiprogramming between two processes.
## Semaphores
* Meaning of semaphore: A visual sinaling appratus with flags, lights...
* Test-and-set: Uninterruptible process, it will change the status of false to true and return it.
* Critical region(臨界區段): A region that is only accessible to a program.
    * Mutual exclusion(互斥鎖): A process that prevents simultaneous access to a shared resource.
## Prerequisites for Deadlock
* Deadlock may occur only if all three of the following conditions(necessary but insufficient) are satisfied
    1. Competition for non-shareable resources
    2. Resources are requested on a partial basis, receiving some resources and return later to request more.
    3. Once a resource has been allocated, it cannot be forcibly retrieved. 

![](https://i.imgur.com/LWgDTY9.png)
* To prevent Deadlock from happening, we have to avoid the conditions mentioned above being satisfied.
## The Consequence of Preventing Deadlock from Happening
![](https://i.imgur.com/HxCTDOU.png)

* Starvation: Process cannot get the resources needed for a long time because the resources keep being allocated to other processes.
* The solution to starvation -> (Aging): Adding an aging factor to the priority of each request.
