# Day 10 - Digital Electronics Fundamentals: Number Systems and Complements

## Objective

Today's learning focused on the fundamentals of Digital Electronics, including number systems, number system conversions, complements, and solving problems involving different number bases.

---

## Topics Covered

### 1. Introduction to Digital Electronics

Digital Electronics deals with systems that process discrete (digital) signals.

Major topics in Digital Electronics:

1. Number Systems
2. Complements
3. Boolean Algebra
4. Combinational Logic Circuits
5. Sequential Logic Circuits

---

### 2. Combinational Logic Circuits

Medium Scale Integration (MSI) Circuits:

* Multiplexer (MUX)
* Demultiplexer (DEMUX)
* Arithmetic Circuits
* Encoders and Decoders
* Comparators

---

### 3. Sequential Logic Circuits

Components of Sequential Logic:

* Latch
* Flip-Flop
* Counters
* Registers
* Finite State Machine (FSM)

---

### 4. Digital System Overview

Basic Digital System Flow:

```text
Analog Input
     |
    ADC
     |
Digital System
     |
    DAC
     |
Analog Output
```

Digital systems may contain:

* CPU
* ALU
* Memory
* Registers
* Input/Output Devices

System Hierarchy:

```text
System
  ↓
Sub-System
  ↓
Modules
  ↓
Functional Blocks
  ↓
Logic Units
```

---

### 5. Electronic Devices

#### Passive Components

* Resistor
* Capacitor

#### Active Components

* Transistor

---

## Number Systems

### Decimal Number System

* Radix/Base = 10
* Digits: 0 to 9

Example:

```text
(123)₁₀
```

---

### Binary Number System

* Radix/Base = 2
* Digits: 0 and 1

Example:

```text
(1010)₂
```

---

### Octal Number System

* Radix/Base = 8
* Digits: 0 to 7

Example:

```text
(17)₈
```

---

### Hexadecimal Number System

* Radix/Base = 16
* Digits:

```text
0 1 2 3 4 5 6 7 8 9 A B C D E F
```

Example:

```text
(ABCD)₁₆
```

---

## Important Concepts

### Radix/Base

For any number system:

```text
Digits range from 0 to (r-1)
```

where:

```text
r = radix/base
```

Examples:

```text
Binary → 0 to 1
Octal → 0 to 7
Decimal → 0 to 9
Hexadecimal → 0 to F
```

---

## Number System Conversions

### Decimal to Binary

Example:

```text
(16)₁₀ = (10000)₂
```

Method:

* Repeated division by 2
* Read remainders from bottom to top

---

### Decimal Fraction to Binary

Example:

```text
(15.5)₁₀
```

Method:

* Integer part → divide by 2
* Fractional part → multiply by 2

---

### Decimal to Octal

Example:

```text
(64)₁₀ = (100)₈
```

Method:

* Repeated division by 8

---

### Decimal to Hexadecimal

Example:

```text
(64)₁₀ = (40)₁₆
```

Method:

* Repeated division by 16

---

## Base Related Problems

### Finding Minimum Base

Example:

```text
(21A)x
```

Since digit A = 10,

Minimum base:

```text
x = 11
```

Possible values:

```text
11, 12, 13, ...
```

---

### Finding Unknown Base

Example:

```text
(135)x + (144)₈ = (214)x + 2
```

Solution gives:

```text
x = 11
```

---

### Another Base Problem

Example:

```text
(136)r = (210)r
```

Solving the equation gives:

```text
r = 8
```

---

### Mixed Base Conversion

Example:

```text
(65)₈ = (?)₁₀
```

Convert octal to decimal using positional weights.

---

### Hexadecimal Conversion

Example:

```text
(AB)₁₆
```

Decimal Equivalent:

```text
(171)₁₀
```

Octal Equivalent:

```text
(253)₈
```

---

## Multi-Base Arithmetic Problems

Example:

```text
(x)₇ + (y)₈ + (w)₁₀ + (z)₅ = (241)₉
```

Solved by converting all numbers into decimal and finding the unknown value.

---

### Equality of Numbers in Different Bases

Example:

```text
(8u)x = (6u)y
```

Using positional expansion:

```text
8x + u = 6y + u
```

Result:

```text
8x = 6y
```

Possible valid solution:

```text
x = 9
y = 12
```

---

### Octal to Hexadecimal Conversion

Example:

```text
(104010400)₈
```

Convert:

```text
Octal → Binary → Hexadecimal
```

---

## Complements of Number Systems

Complements are used to:

* Represent negative numbers
* Perform subtraction using addition
* Simplify hardware implementation

---

## Decimal Number System Complements

### 10's Complement

Formula:

```text
rⁿ − N
```

For Decimal:

```text
10ⁿ − N
```

Example:

```text
10⁴ − 1234

10000 - 1234

= 8766
```

---

### 9's Complement

Formula:

```text
(10ⁿ − 1) − N
```

Example:

```text
9999 - 1234

= 8765
```

---

## Binary Number System Complements

### 2's Complement

Formula:

```text
2ⁿ − N
```

Method:

```text
1's Complement + 1
```

Example:

```text
N = 0110

1's Complement = 1001

2's Complement = 1010
```

---

### 1's Complement

Formula:

```text
(2ⁿ − 1) − N
```

Example:

```text
1111
-0110
-----
1001
```

---

## Octal Number System Complements

### 8's Complement

Formula:

```text
8ⁿ − N
```

Example:

```text
(44)₈
```

---

### 7's Complement

Formula:

```text
(8ⁿ − 1) − N
```

Example:

```text
77 - 44

= 33
```

---

## Hexadecimal Number System Complements

### 16's Complement

Formula:

```text
16ⁿ − N
```

---

### 15's Complement

Formula:

```text
(16ⁿ − 1) − N
```

Example:

```text
FFFF
-ABCD
-----
5432
```

16's Complement:

```text
5432 + 1

= 5433
```

---

## Complements in Arbitrary Base (x-base)

### r's Complement

Formula:

```text
rⁿ − N
```

---

### (r-1)'s Complement

Formula:

```text
(rⁿ − 1) − N
```

Example:

```text
10's complement of (843)₁₁

= 11³ - 843
```

---

## Key Learnings

* Understood the structure of digital systems.
* Learned different number systems and their bases.
* Practiced decimal, binary, octal, and hexadecimal conversions.
* Solved unknown base and mixed-base problems.
* Learned 1's, 2's, 7's, 8's, 9's, 10's, 15's, and 16's complements.
* Understood the role of complements in subtraction and negative number representation.
* Practiced base conversion and complement-based numerical problems.
