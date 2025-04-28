 <p align="center">
   <strong>ARCHIVE OF ALL FILES ARE ABOVE IN MAIN BRANCH</strong>
    


<h2> <div align="center"><b> revision materials for Computer Science </b></div> </h2>

<h1>About</h1>

- <strong>Covers OCR computer science GCSE</strong>
- <strong>If u need anything adding create an issue [(Here)](https://github.com/AceAdxm/CS-STUFF/issues) </strong>
- <strong>*NOTE: CURRENTLY DOESENT HAVE ALL TOPICS BUT I AM WORKING ON ADDING THEM*</strong>

<h1>About The author</h1>
- <Strong> @AceAdxm on all socials</Strong>
- <strong>@Adxm.fr on insta</strong>

##### Checklist

- [ ] Architecture
- [ ] Memory
- [ ] Storage
- [ ] Wi-fi and wired networks
- [ ] Networks
- [ ] Network Security
- [ ] Systems Software
- [ ] Ethical and Legal
- [ ] Algorithms
- [ ] Programming Techniques
- [ ] Producing robust programs
- [ ] Computational logic
- [ ] Translators and facilities of languages
- [ ] Data representation

[TOC]

# Computing

## Architecture

### Computer System

A **computer system** uses a set of digital ***inputs***, ***processes them*** and creates a set of ***outputs*** using ***hardware*** (physical parts) and ***software***.

- Hardware is a physical part of a computer system.


- Inputs are provided by an **input device.** For example: Keyboard, Microphone, Touch Screen, Mouse...
- Outputs are provided by an **output device**. For example: Computer Monitor, Printer, Speakers...
- Output and Input devices are both examples of hardware.

##### Process

- The processing of data occurs in the **CPU** (Central Processing Unit) which is the "brain" of the computer.
  - It is also known as a **microprocessor**.


- The instructions in order to process the information are provided to the CPU by a **computer program**.
  - **Software** is a computer program that contains the set of instructions needed by the CPU in order to perform a specific task.

There are 2 main types of software:

- **System software** which manage the operation of the computer. Aka Operating Systems such as Windows, Mac OS X, Linux
- **Application software** which are written for a specific purpose. For example a Music Player, Photo Editor, Word Editor...

##### Storage
- Instead of the CPU sending data directly to an output device, often it is instead (or also) stored.
 - Data can be stored in: 1. RAM, 2. Hard Disk, 3. Secondary Storage Device (mobile phones use this).

##### How does data move about in the computer system?
- A **bus** allows data to be transported. It is a set of wires laid down on a printed circuit board.

Types of "bus":

- **Data bus** carries actual data around the computer system.
- **Address bus** carries information on where the actual data needs to go in the system.
- **Control bus** carries signals to control various components (e.g. DVD drive, Hard disk...)

**Embedded computer systems** are designed to carry out a specific purpose. For example:

- Smart phone, cars and lorries

They can also be used for **computer control** such as Traffic Light systems, Elevators...
                                                                           

## Data Representation

### Units
- A single **bit** is the smallest size of digital data and has only two values (Base-2): 0, 1.

- A **nibble** is a group of 4 bits.

- A **byte** contains 8 bits, for example 1 1 1 0 1 0 0 1 is a byte because it has 8 bits...
  - A single character requires 1 byte or 8 bits

# The Binary Search Algorithm

In computer science, binary search, also known as half-interval search, logarithmic search, or binary chop, is 
a search algorithm that finds the position of a target value within a sorted array. Binary search compares the 
target value to the middle element of the array. If they are not equal, the half in which the target cannot lie is 
eliminated and the search continues on the remaining half, again taking the middle element to compare to the target value, 
and repeating this until the target value is found. If the search ends with the remaining half being empty, 
the target is not in the array.

## Characteristics

- Data must be sorted!
- Chooses the element in the middle of the array and compares it against the search value
- If element is equal to the value, we are done
- If element is grater than the value, search the left half of the array
- If the element is less than the value, search the right half of the array
- At some point, there will be only one element in the partition you're checking, but it does not have to get to that point
- Can be implemented recursively
- O(log n) - keeps dividing the array in half

## Time complexity

Worst-case performance: O(log n)<br>
Best-case performance: O(1)<br>
Average performance: O(log n)<br>
Worst-case space complexity: O(1)

## Implementation

```java
final class BinarySearch {

    static int iterative(final int[] in, final int value) {
        var start = 0;
        var end = in.length;
        while (start < end) {
            final int midpoint = (start + end) / 2;
            if (in[midpoint] == value) {
                return midpoint;
            } else if (in[midpoint] < value) {
                start = midpoint + 1;
            } else {
                end = midpoint;
            }
        }

        return -1;
    }

    static int recursive(final int[] in, final int value) {
        return recursive(in, 0, in.length, value);
    }

    private static int recursive(final int[] in, final int start, final int end, final int value) {
        if (start >= end) {
            return -1;
        }

        final var midpoint = (start + end) / 2;
        if (in[midpoint] == value) {
            return midpoint;
        } else if (in[midpoint] < value) {
            return recursive(in, midpoint + 1, end, value);
        } else {
            return recursive(in, start, midpoint, value);
        }
    }
}
```

## Links

* [Binary Search Algorithm](https://en.wikipedia.org/wiki/Binary_search_algorithm)
  

  
 

