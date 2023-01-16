---
layout: post
title: Data Storage(I)
tags: 計算機概論
date: '2023-01-17 01:35 +0800'
published: true
---
計算機概論-Data Storage(I)隨手記
{: .message }

# Data Storage(I)
## Binary world
1. Simple, logical and unambiguous
2. Boolen operation and gates
    * AND: ![](https://i.imgur.com/f40BHRy.png)
    * OR: ![](https://i.imgur.com/iHu0uCp.png)
    * Exclusive OR(XOR): ![](https://i.imgur.com/Kt4lWeG.png)
    * NOT: ![](https://i.imgur.com/naddbwe.png)
## Flip-Flop(正反器)
1. Purpose -> To store 0/1
2. 2 inputs
3. One -> set 0
4. The other -> set 1
5. It will preserve 0/1 if there is no inputs
6. ![](https://i.imgur.com/CM0A35v.png)    
* Simple SR Flip-Flop Circuit 
    ![](https://i.imgur.com/UxaHn8a.png)
* Another Simple SR Flip-Flop Circuit
    ![](https://i.imgur.com/eHtGv2l.png)
## Hexadecimal(Hex，十六進位)
1. Reason of using Hex ->
    * Binary is too long for human to remember
    * Binary to Hex is straightforward
2. ![](https://i.imgur.com/4SckAD3.png)
## Main memory cell
1. 8 bits -> 1 cell -> 1 byte
2. ![](https://i.imgur.com/0tHCICX.png)
## Memory
1. One dimensional
2. Random accessible
3. Access the content via the address
4. ![](https://i.imgur.com/848KpU9.png)
## Memory techniques
1. Random access memory (Ram): Memory in which individual cells can be easily accessed in any order
    * Type: Static Memory(SRAM), Dynamic Memory(DRAM), Synchronous DRAM(SDRAM)
    * Double Date Rate(DDR)->Faster when reading data
    * Dual/Triple channel
2.  * Kilobyte: $2^{10}$ = 1024 bytes $\simeq$ $10^{3}$ bytes
    * Megabyte: $2^{20}$ = 1038576 bytes $\simeq$ $10^{6}$ bytes
    * Gigabyte: $2^{30}$ = 1073741824 bytes $\simeq$ $10^{9}$ bytes
## Mass Storage
1. Properties:
    * Larger capacity
    * Less volatility
    * Slower
    * On-line or off-line
2. Types:
    * Magnetic systems(HDD，Floppy Disk)
    * Optical systems(CD，DVD)
    * Flash drives(SSD)
3. Magnetic storage:
    * ![](https://i.imgur.com/FaS4kFn.png)
    * ![](https://i.imgur.com/Blqj4wl.png)
    * Access time = seek time(To reach the right track) + rotation delay(latency time，To reahc the right sector)
    * Transfer rate(SATA)
4. Optical storage
    * ![](https://i.imgur.com/4CxHApt.png)
5. Physical and logical records
    * ![](https://i.imgur.com/dUAwIy8.png)
6. Buffer(緩衝區)
    * Purpose: To synchronize different read/write mechanisms and rates
    * An area used to temporarily store data
## Representing text
1. ASCII: 7 bits (or 8 bits starts with 0)
2. Unicode: 16 bits
3. ISO: 32 bits
## Representing numbers
1. 901 (decimal): 
    ![](https://i.imgur.com/gUkyMRy.png)
2. 11 (binary):
    ![](https://i.imgur.com/yCSMAtg.png)
3. From binary to decimal
    ![](https://i.imgur.com/77twv7u.png)
4. From decimal to binary
        ![](https://i.imgur.com/CxpuQ3J.png)
## Representing img
1. Bit map techniques:
    * Pixel: the element of a picture
    * Colors: RGB，HSV，etc.
2. Vector techniques:
    * Properties: Scalable
    * Truetype，Postscript，SVG(scalable vector graphic)  
## Representing sound
1. Sampling
    * Sample rate and bit resolution
    * Bit rate(sampling rate $\times$ bit resolution)
2. MIDI(synthesis)
    * A protocol designed for recording and playing back music on digital synthesizers that is supported by many makes of personal computer sound cards
## Binary system revisited
1. Addition
    * 0+0=0
    * 1+0=1，0+1=1https://hackmd.io/A5aFWyc1TOKNUz-eVRrM2g#
    * 1+1=10
2. Subtraction
    * Define negative numbers first(Two's Complement Notation)
## Two's complement notation and encoding
1. ![](https://i.imgur.com/SisdfNh.png) 
2. Encoding(method 1): ![](https://i.imgur.com/yCIZs08.png)
After finishing the process，you can directly do the addition and get the right answer
3. Encoding(method 2): Do it as usual binary way![](https://i.imgur.com/qHhHYH7.png)
4. Encoding(method 3): ![](https://i.imgur.com/35BXAa6.png)
 

## Excess notation
1. ![](https://i.imgur.com/3cyVdYJ.png)
2. Addition: After the calculation, u have to add 4 to get the right answer
## Overflow
Using the table from Two's complement:
1. Occurs when the result is out of range(not in table)
2. Addition of two positive numbers -> 2+3=5 $\equiv$ -3(mod 8)
3. Addition of two negative numbers -> (-2)+(-3)=-5 $\equiv$ -3(mod 8)



 
     
 
