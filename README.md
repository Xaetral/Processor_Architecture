# Processor Architecture

This document aims at explaining what really is a processor in the simplest and most abstract way possible.  

## 1. Numbers

You may think that a processor is built from transistors and logic gates, but there are many counter examples out there. To fully explain the whole picture we need another level of abstraction.  

When it comes to processors and similar modern components, you often hear the term "digital".  
This hints us what they are really made out of: numbers, themselves composed of digits.  

So that is the essence of a processor right here: you shove numbers into a processor and it outputs new ones, this is why you also come across the term "computer" because at the end, all it does is applying various computations (we commonly prefer the term "operations") onto a set of numbers.  

Also within the processor itself numbers are a core aspect of its structure, all the parts are just numbers going in and out.  
Keep in mind that the actual nature of those numbers doesn't really matter in essence, as long as the rules are well defined. Which means that the same number may mean different things to different parts of the processor, or even different inputs of the same part.  

## 2. Intelligence

Being able to perform operations on numbers isn't enough to be a processor, another requirement is the ability to behave differently depending on those numbers, something that you might call "intelligence".

This can be done in all sorts of different ways that are only limited to your imagination so there isn't much left to tell in this chapter without having to explain every possible solutions.  

## 3. Data and Programs

As previously mentioned, a processor performs operations on given numbers and the nature, order and amount of those operations may differ depending on the same or other given numbers.  

So the third property required for being a processor is to be able to be told what operation to do in which case.  
This is done by giving the processor another set of numbers as its input, and to differentiate them we call the set of numbers being processed "data" and the set of numbers defining the behavior of the processor "program".  

For the sake of simplicity in the following chapters we will only consider the most basic and common way programs are structured: an ordered list of instructions with each instruction being a single number.  

## 4. Executing a Program

Following the 3 mandatory principles stated in the previous chapters, a processor requires 3 parts to be able to execute code:
- The program memory
- The instruction decoder
- The program counter

### 4.1. Program Memory

The program memory is the component holding the program to be executed by the processor.  
It has one number as input which is called the address, referring to the unique identifier of the instruction that has to be currently executed.  
It also has one number as output called the instruction, which is just the content of the memory at the given address.  

### 4.2. Instruction Decoder

The instruction decoder translates the given instruction into a whole lot of signals that are controlling the entire processor.  
So it has one input for the instruction to be decoded, and has many outputs directly defined by the value of the instruction and often other signals from the processor.  

### 4.3. Program Counter

The program counter is in charge of computing the next program address, it has to be able to add one to the current address, load a completely arbitrary one, and many more features if so desired.  
In any case this component is (like most other components) under the direct control of the instruction decoder.  

## 5. Actual Computing

Being able to run through a program is not enough to be able to be a processor, although it has already lots of usages (like a Jacquard machine for example).  
As already mentioned the processor has to perform operations on given numbers so we are still missing a few components to:
- Store numbers
- Compute arithmetic or logic operations on these numbers
- Move the numbers between both, and with the outside world

### 5.1. Registers and I/O

Registers are a core component of many parts of a processor but this chapter only refers to the ones that are directly usable by the program.  
A register is a component that holds a single value and is able to store another one over it if asked to.  
So the program will use them to memorize and remember data during the processing.  

Since we also need to be able to read input numbers and write output numbers, we can use a trick to simplify the architecture by simply "splitting open" a register. The idea is to just wire the output of the register to an output of the processor and wire an input of the processor to what was supposed to be the output of the register internally.  
Thus reading the register will in reality read the input of the processor and writing to it will save and output that value to the output of the processor.  

### 5.2. Arithmetic and Logic Unit

As said previously, the processor has to process numbers and perform operations on them, and thus the ALU is a collection of many different types of operations in a single part. This is obviously not mandatory but it helps having a clean and easily understandable architecture.  
A typical ALU needs nothing more than:
- 2 inputs for operations requiring 2 operands (like addition and multiplication) though it may use only one of them for operations requiring only 1 operand (like negation)
- 1 input to select the required operation
- 1 ouput to give out the result of the operation

### 5.3. Databus

A databus in itself is nothing but a part that routes numbers from/to other parts of the processor, as such it can be viewed as a big selector switch.  
Only writing on the databus has to be monitored to avoid data collision but as many parts as needed may read from it.  
If the register trick is not used the databus may also access stuff outside of the processor in order to handle its inputs/outputs.  
