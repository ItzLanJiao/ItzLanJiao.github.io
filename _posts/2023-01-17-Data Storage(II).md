---
layout: post
title: Data Storage(II)
tags: 計算機概論
categories: 大學課堂筆記
date: '2023-01-17 01:35 +0800'
published: true
---
計算機概論-Data Storage(II)隨手記
{: .message }

# Data Storage(II)
## Fraction in binary
1. The rules is the same ![](https://i.imgur.com/pqwL1v6.png)
## Float-point notation and decoding
1. 8 bits representation![](https://i.imgur.com/6YrHIlt.png)![](https://i.imgur.com/BDVrmtA.png)
    * Ex (Use the table of binary): 10010101 -> 1(001)(0101) -> ($-2^{1}$)$\times$($\frac{1}{4}$+$\frac{1}{16}$)=-$\frac{5}{8}$
2. On the widely used 64-bit computers，the exponent takes 11 bits，and the mantissa takes 52 bits
## Truncation error
1. The precision is beyond the limitation of mantissa.
    * Ex (Use the table of binary): 2$\frac{5}{8}$ -> 10.101(base two，fixed point) -> .10101 $\times$  $2^{2}$ -> 0(010)(1010) -> 2$\frac{1}{2}$
## Normalized form
1. *  The first bit of mantissa is 1 
    * 0's floating-point representation is all 0
2. Normalization:
    * Ex (Use the table of binary): 00100011 -> 0(010)(0011) -> .0011 $\times$ $2^{2}$ -> .1100 $\times$ $2^{0}$ -> 0(000)(1100)
3. IEEE normalized form
    
    * The left-most bit in mantissa is always 1 (Ex: .0101 -> 1.0101)
    * Standard normalized form is (s)(eee)(mmmm) -> ($-1^{s}$) $\times$ 1.mmmm $\times$ $2^{(eee-4)}$
        * Ex(Use the table of binary): 01100011 -> (0)(110)(0011) -> $(-1)^{0}$ $\times$ 1.0011 $\times$ $2^{(6-4)}$
## Loss of digits
Ex (Use the table of excess): 
* 4 + $\frac{1}{4}$ + $\frac{1}{4}$ = (01111000 + 00111000) + 00111000 -> make the exponent the same (01111000 + 01110000) + 01110000 = 4 (the result is wrong)
* 4 + $\frac{1}{4}$ + $\frac{1}{4}$ = 01111000 + (00111000 + 00111000) = 4$\frac{1}{2}$
## Data compression
* Two types -> Lossy and Lossless
* Lossless
    1. Run-length encoding(RLE)
        * After the process of compressing ，wwwwwww is being recognized as 7w,      
    2. Frequency-dependent encoding -> Huffman encoding
    3. Dictionary encoding -> Adaptive dictionary encoding, LZW encoding
        * Defining the value by yourself 
* Lossy
    1. Relative / difference encoding
* Huffman encoding
    * Ex: AAABBBAABCAAAABD
        * Traditional encoding -> Code book: A -> 00; B -> 01; C -> 10; D -> 11, represent in 2 bits it will be 000000010101000001100000000111
        * Huffman encoding -> 
            1. Count the occurrences:  A(9); B(5); C(1); D(1)
            2. Build a huffman tree: 
                                           ![](https://i.imgur.com/nWxGAT7.png)
            According to the tree, the code book is A -> 0, B -> 10, C -> 110, D -> 111. Through the huffman encoding，the string will be transfered into 0001010100010110
* LZW encoding
    * Is a kind of dictionary encoding that does not need to store the dictionary
    * The concept is to generate more values to the dictionary(Usually we use the ascii code to represent numbers and words, so no addition dictionary is needed)
        * Code book: x -> 1, y -> 2, space -> 3    
            * Ex: xyx xyx xyx xyx
            -> 1
            -> 12
            -> 121
            -> 1213
            Then you append 1213 to the dictionary as 4
            -> 12134
            ->121343434
## Images, audios and videos
* Images: 
    1. GIF: 256 colors, dictionary encoding
    2. JPEG: Lossy / lossless encoding
* Audios: 
    1. MP3: Lossy encoding
* Videos: 
    1. MPEG: Lossy encoding
## Communication errors
* The reason of compressing data is to remove redundency
* To correct the communication error -> we add redundancy 
* Error detection -> instead of correcting errors, it can only check if the errors occurs
    * Applications(detection): 
        1. ID numbers
        2. ISBN
        3. Parity code 
* Error correcting -> Can correct errors to some degree
## Application of error detections / corrections
* Taiwan ID:![](https://i.imgur.com/GrBxbtA.png)
    1. Convert the first English letter into a number(xy):
    ![](https://i.imgur.com/MzCD1dk.png)
    2. $d_1$ = x + 9y
    3. $d_2$ = $\sum_{i = 1}^8$ i $\cdot$ $a_i$ = 1 $\cdot$ $a_1$ + 2 $\cdot$ $a_2$ ... +8 $\cdot$ $a_8$
    4. Check code -> $a_9$ = 10 - (($d_1$ + $d_2$) mod 10)
* ISBN-10
ISBN　template: 0-273-75139
1. Compute S = 0 $\cdot$ 10 + 2 $\cdot$ 9 +7 $\cdot$ 8 + 3 $\cdot$ 7 + 7 $\cdot$ 6 + 5 $\cdot$ 5 + 1 $\cdot$ 4 + 3 $\cdot$ 3 + 9 $\cdot$ 2 = 193
2. M = S mod 11 = 6 
3. N = 11 - M =5
    * If N = 10 the check code is X
    * If N = 11 the check code is 0
    * Otherwise, the check code is the number N
4. The ISBN code  0-273-75139-5
* Parity Bits
    1. Making the quantity of 1s odd
    ![](https://i.imgur.com/gaBDWYj.png)
    2. The technique is used in  communication and RAID 
* An error-correcting code(ECC)
    1. (3, 1) repetition code (can correct 1-bit errors) -> seperate the data into groups with 1 bit in each group, and add two bits to authenticate the data 
        ![](https://i.imgur.com/SOldZpS.png)
* Hamming distance
    1. Comparing two binary data， hamming distance is the amount of different bits.
* Error correction with hamming distance
    1. Maximizing hamming distance along the symbols
    Sample code book:
    ![](https://i.imgur.com/qvBxx5o.png)
        * Ex: received 010100
        Hammig distance:    ![](https://i.imgur.com/43W6zqv.png)
    According to the chart, we will correct 010100 to 011100(D)
* Generating (7, 4)Hamming code
    ![](https://i.imgur.com/3ugdiSq.png)


    






            
            
    





