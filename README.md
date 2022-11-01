# Processor Architecture

This document aims at explaining what really is a processor in the simplest and most abstract way possible.

## 1. Numbers

You may think that a processor is built from transistors and logic gates, but there are many counter examples out there.
To fully explain the whole picture we need another level of abstraction.  

When it comes to processors and similar modern components, you often hear the terms "numeric" and "digital".  
This hints us what they are really made out of: numbers, that are themselves made out of digits.  

So that is the essence of a processor right here: you shove numbers into a processor and it outputs new ones, this is why you also come across the term "computer" because at the end, all it does is applying various computations (we commonly prefer the term "operations") onto a set of numbers.  

Also within the processor itself numbers are a core aspect of its structure, all the parts are just numbers going in and out.  
Keep in mind that the actual nature of those numbers doesn't really matter in essence, as long as the rules are well defined. Which means that the same number may mean different things to different parts of the processor, or even different inputs of the same part.

## 2. Intelligence

Being able to perform operations on numbers isn't enough to be a processor, another requirement is the ability to behave differently depending on those numbers, something that you might call "intelligence".

This can be done in all sorts of different ways that are only limited to your imagination so there isn't much left to tell in this chapter without having to explain every possible solutions.

## 3. Data and Programs

As previously mentioned, a processor performs operations on given numbers and the nature, order and amount of those operations may differ depending on the same or other given numbers.

So the third property required for being a processor is to be able to be told what operation to do in which case.  
This is done by giving to the processor another set of numbers as its input and to differentiate them we call the set of numbers being processed "data" and the set of numbers defining the behavior of the processor "program".

For the sake of simplicity in the following chapters we will only consider the most common way programs are made: an ordered list of instructions with each instruction being a single number.

## 4. Executing a Program
