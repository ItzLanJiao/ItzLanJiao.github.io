---
layout: post
title: Data Manipulation(I)
tags: 計算機概論
date: '2023-01-17 01:35 +0800'
published: true
---
計算機概論-Data Manipulation(I)隨手記
{: .message }

# Data Manipulation(I)
## The communication between CPU and memory
![](https://i.imgur.com/sEBH2IU.png)
Register -> CPU Cache
* Adding values in memory
    1. Get value A from the memory and put it in a register.
    2. Get value B from the memory and put it in another register.
    3. Activate the additional circuit and put the final value into another register.
    4. Store the result the memory.
* Machine instruction
    1. Data transfer
        * load, store, I/O
    2. Arithmetic/logic
        * and, or, add, sub...
        * shift, halt
    3. Control
        * jump, halt
    4. RISC -> Reduced instruction set computing
        * Ex: PRC, SPRC
    5. CISC -> Complex instruction set computing
        * Ex: x86，x64
## Example of machine instruction
![](https://i.imgur.com/UYGKbh0.png)
* 3 -> store
* 5 -> register No.5
* A7 -> memory cell A7
-> Store the content of register No.5 to memory cell A7.
## The machine instruction of adding two values
![](https://i.imgur.com/Xa7EtHE.png)
## Program execution
* Machine cycle
    ![](https://i.imgur.com/N1Jiuk9.png)
* Fetch
    ![](https://i.imgur.com/pJF8QS9.png)

* Clock -> how many machine cycle a cpu is able to do in one second
## Arithmetic and logic unit(ALU)
* Arithmetic operations
* Logic/bit operations
* ![](https://i.imgur.com/pfBxlEH.png)
## Shift/Rotation
* Logic shift
    * 10100000 -> 01010000(right)
      10100000 -> 01000000(left)
      Both moving left and right add a 0
* Arithmetic shift
    * 10100000 -> 11010000(right, the number is divided by 2)
      Moving right，copy the leftest bit.
      10100000 -> 11000000(left, the number is multiplied by 2)
      Moving left，add a 0 to the right.
* Rotation 
    * 10100000 -> 01010000(right)
      10100000 -> 01000001(left)
## Controllers and peripheral devices
![](https://i.imgur.com/AZ4fwQH.png)
* Specialized -> SATA...
* General -> USB, HDMI...
## Memory-mapped I/O
* The periphral devices are recognized as part of the memory.
![](https://i.imgur.com/YFL6td3.png)
## Communication
* DMA(direct memory access)
    * Authorized controllers can access data directly from main memory without notifying CPU
* Hand shaking
    * Two way communication
    * Coordinating activities
* Parallel/Serial
* Transfer rate unit -> bit per second 
## Pipelining(accelerating the process)
ex -> pre-fetching![](https://i.imgur.com/gPsrUkp.png)
* Throughput -> Total amount of work accomplished in a given amount of time
* Pre-fetching issus -> conditional jump
## Parallel/distributed computing
* Parallel
    * Multiprocessor
    * MIMD，SISD，SIMD，MISD(M->Multiple，S->Single，I->Instruction, D->Dataset)
* Distributed
    * Linking computers via network
    * Seperate processors and memory
* Issues
    * Data dependency
    * Load balancing
    * Synchronization
    * Reliability
## How to parallelize?
![](https://i.imgur.com/xrTQCOL.png)
## Speed up and Scaling
* Amdahl's law(阿姆達爾定律)
* Gain = $\frac{1}{\frac{P}{M}+(1-P)}$(P -> proportion that is parallelizable, S -> proportion that is serial only)












