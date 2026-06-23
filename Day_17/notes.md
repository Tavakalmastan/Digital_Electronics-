# Day 17 – Encoders and Comparators

## Overview
On Day 17, I studied advanced MSI circuits including Encoders, Priority Encoders, Comparators, Decoder Configurations, Code Converters, and Magnitude Comparators. I learned the design, truth tables, Boolean expressions, K-Map simplifications, and hardware implementations of encoder and comparator circuits.

---

## Decoder Applications

### BCD to Excess-3 Code Using 4:10 Decoder

Output Equations:

E0 = Σm(0,2,4,6,8)

E1 = Σm(0,3,4,7,8)

E2 = Σm(1,2,3,4,9)

E3 = Σm(5,6,7,8,9)

Implemented using a 4:10 decoder and decoding logic.

---

## Decoder Configurations

### Configure 3:8 Decoder Using 2:4 Decoder

- Used two 2:4 decoders
- One decoder enabled when MSB = 0
- Another decoder enabled when MSB = 1
- Generates 8 output lines from 3 input variables

### Configure 5:32 Decoder Using 3:8 and 2:4 Decoders

- 2:4 decoder used for enabling
- Four 3:8 decoders used for output generation
- Total outputs = 32

---

# Encoders

### Definition

Encoder is a Data Compressor.

Converts:

2ⁿ Inputs → n Outputs

Examples:

- 2:1 Encoder
- 4:2 Encoder
- 8:3 Encoder
- 16:4 Encoder

---

## 4:2 Encoder

Inputs:

I0, I1, I2, I3

Outputs:

Y1, Y0

### Truth Table

| I3 | I2 | I1 | I0 | Y1 | Y0 |
|----|----|----|----|----|----|
| 0 | 0 | 0 | 1 | 0 | 0 |
| 0 | 0 | 1 | 0 | 0 | 1 |
| 0 | 1 | 0 | 0 | 1 | 0 |
| 1 | 0 | 0 | 0 | 1 | 1 |

### Boolean Expressions

Y0 = I1 + I3

Y1 = I2 + I3

---

## 4:2 Higher Order Priority Encoder

Priority Order:

I3 > I2 > I1 > I0

Outputs:

Y1, Y0, Valid

### Simplified Equations

Y0 = I3 + I̅2 I1

Y1 = I2 + I3

Valid = I3 + I2 + I1 + I0

### Features

- Highest priority input dominates
- Generates valid signal
- Used when multiple inputs may become active simultaneously

---

## 4:2 Lower Order Priority Encoder

Priority Order:

I0 > I1 > I2 > I3

Outputs:

Y1, Y0, Valid

### Simplified Equations

Y1 = I̅1 I̅0 (I2 + I3)

Y0 = I1 I̅0 + I3 I̅2 I̅0

Valid = I3 + I2 + I1 + I0

---

## Octal to Binary Encoder

### 8:3 Priority Encoder

Inputs:

O0 – O7

Outputs:

b2, b1, b0

Additional Output:

Valid

### Function

Converts octal inputs into equivalent binary code.

---

# Comparators

## Types of Comparators

- 1-bit Comparator
- 2-bit Comparator
- Multi-bit Comparator

---

## 1-bit Comparator

Inputs:

A, B

Outputs:

- A > B
- A = B
- A < B

### Boolean Expressions

A > B = AB̅

A < B = A̅B

A = B = A ⊙ B (XNOR)

### Truth Table

| A | B | A>B | A=B | A<B |
|---|---|-----|-----|-----|
| 0 | 0 | 0 | 1 | 0 |
| 0 | 1 | 0 | 0 | 1 |
| 1 | 0 | 1 | 0 | 0 |
| 1 | 1 | 0 | 1 | 0 |

---

## 2-bit Comparator

Inputs:

A1 A0

B1 B0

Outputs:

- A > B
- A = B
- A < B

### Expressions

A > B

= A1B̅1 + (A1 ⊙ B1)A0B̅0

A < B

= A̅1B1 + (A1 ⊙ B1)A̅0B0

A = B

= (A1 ⊙ B1)(A0 ⊙ B0)

---

## Design 2-bit Comparator Using 1-bit Comparator

Intermediate Variables:

X1 = A1 ⊙ B1

X0 = A0 ⊙ B0

### Final Expressions

A = B

= X1 X0

A > B

= A1B̅1 + X1(A0B̅0)

A < B

= A̅1B1 + X1(A̅0B0)

---

# 4-bit Magnitude Comparator

Inputs:

A3 A2 A1 A0

B3 B2 B1 B0

Outputs:

- A > B
- A = B
- A < B

### Equality

A = B

= (A3 ⊙ B3)(A2 ⊙ B2)(A1 ⊙ B1)(A0 ⊙ B0)

### Greater Than

A > B

= A3B̅3
+ X3A2B̅2
+ X3X2A1B̅1
+ X3X2X1A0B̅0

### Less Than

A < B

= A̅3B3
+ X3A̅2B2
+ X3X2A̅1B1
+ X3X2X1A̅0B0

Where:

X3 = A3 ⊙ B3

X2 = A2 ⊙ B2

X1 = A1 ⊙ B1

---

## IC 7485 – 4-bit Magnitude Comparator

Features:

- Compares two 4-bit binary numbers
- Provides outputs:
  - A > B
  - A = B
  - A < B
- Supports cascading for larger comparators

---

## 8-bit Comparator Using IC 7485

- Two IC 7485 comparators connected in cascade
- One comparator handles upper 4 bits
- Second comparator handles lower 4 bits
- Used to compare 8-bit binary numbers

---

## Standard Logic ICs Studied

| IC Number | Function |
|------------|-----------|
| 7400 | NAND Gate |
| 7402 | NOR Gate |
| 7404 | NOT Gate |
| 7408 | AND Gate |
| 7432 | OR Gate |
| 7486 | XOR Gate |
| 7483 | 4-bit Parallel Adder/Subtractor |
| 7485 | 4-bit Magnitude Comparator |

---

## Key Takeaways

- Studied Encoder and Priority Encoder design.
- Learned 4:2 Encoder and 8:3 Priority Encoder.
- Designed Higher and Lower Priority Encoders.
- Implemented BCD to Excess-3 code conversion using Decoder.
- Configured larger Decoders using smaller Decoders.
- Designed 1-bit and 2-bit Comparators.
- Implemented 2-bit Comparator using 1-bit Comparators.
- Studied 4-bit and 8-bit Magnitude Comparators.
- Learned IC 7485 comparator and standard logic ICs.
