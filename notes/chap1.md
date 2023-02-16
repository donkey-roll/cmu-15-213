# Chapter 1 A tour of computer system

# 1.1 Bits + Context

text files: only contains ASCII characters

binary files: all other files

# 1.2 Programs are translated by other programs into different forms

![chap1-0.png](https://github.com/donkey-roll/cmu-15-213/blob/main/images/chap1-0.png)

C statement  (source file)—> Machine-language instructions (object file)

Machine-language instructions —> **Executable Object Program** (executable object files)

In the Unix system, the translation is performed by **compiler driver**

# The compilation system

## Preprocessing

e.g. modifies the files according to the directives beginning with `#`

```c
#include<studio.h>
```

## Compilation

Compiler translate C language —> Assembly language

## Assembly

Assembler translate Assembly language —> Machine-language instructions

Relocatable Object Program

**Binary File**

## Linking

Merging other precompiled object files into the program

e.g. printf.o → hello.o

# 1.3 Why?

## Optimizing program performance

## Understand link-time error

## Avoid security holes

buffer overflow vulnerability

# 1.4 Processors Read and Interpret Instructions
Stored in Memory

![chap1-1.png](https://github.com/donkey-roll/cmu-15-213/blob/main/images/chap1-1.png)

## 1.4.1 Hardware organization of a system

Buses

- Designed to transfer fixed-size chunks of bytes known as **words**
- Word sizes: 32bits or 64 bits

I/O devices (Chapter 6 and 10)

- I/O devices are connect to I/O buses through controller or adapter

Main memory (Chapter 6)

- Temporary storage device that holds both a program and the data it manipulates while the processor is executing the program.
- Consists of a collection of DRAM (dynamic random access memory) chips

Processor

- CPU (central processing unit)
- CPU core → word-size storage device (register) called the program counter (PC)
- The register file is a small storage device that consists of word-size registers, each with its own unique name
- At any time, PC points at some machine-language instruction in main memory.
- ALU arithmetic / logic unit

Simple operations

- Load
    - Copy a byte or a word form the main memory into a register
    - Overwriting the previous contents of the register
- Store
    - Copy a byte or a word from a register to a location in main memory
    - Overwriting the previous contents of that location
- Operate
    - Copy the contents of 2 registers to ALU, perform an arithmetic operation on the 2 words, and store the result in a register
    - Overwriting the previous contents of that register
- Jump
    - Extract a word form the instruction itself and copy that word into PC
    - Overwriting the previous value of the PC

## 1.4.2 Running the `hello` program

1. Reading the hello command from the keyboard
    1. USB controller
    2. I/O bridge
    3. CPU
    4. Main memory
2. Loading the executable form disk into main memory
    1. Disk
    2. Disk controller
    3. I/O bridge
    4. Main memory
3. Writing the output string from the memory to display
    1. Main memory
    2. I/O bridge
    3. CPU 
    4. Graphics adapter
    5. Display

## 1.5 Cache matters

![chap1-2.png](https://github.com/donkey-roll/cmu-15-213/blob/main/images/chap1-2.png)

Implemented by SRAM  (static random access memory)

![chap1-0.png](https://github.com/donkey-roll/cmu-15-213/blob/main/images/chap1-3.png)

## 1.7 Operating System manages the Hardware

![chap1-0.png](https://github.com/donkey-roll/cmu-15-213/blob/main/images/chap1-4.png)

Operating system 2 main purposes

1. protect the hardware from misuse by runaway applications
2. provide applications with simple and uniform mechanisms for manipulating complicated and often wildly different low-level hardware devices.


WIP
