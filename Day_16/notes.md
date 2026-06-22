# Day 16 - Multiplexers, Demultiplexers and Decoders

## Overview

On Day 16, I studied MSI (Medium Scale Integration) circuits including Multiplexers (MUX), Demultiplexers (DEMUX), and Decoders. I learned function realization techniques using MUX, DEMUX, and Decoders, MUX reduction methods, MUX tree structures, Gray Code conversion, Full Adder and Full Subtractor implementation using MSI circuits, and configuration of larger circuits using smaller building blocks.

---

# Multiplexers (MUX)

A Multiplexer is a Data Selector that selects one input from multiple inputs and forwards it to a single output.

## General Equation

Y = S̅I₀ + SI₁

## Types Studied

- 2:1 MUX
- 4:1 MUX
- 8:1 MUX
- 16:1 MUX

---

## Implement AND Gate Using 2:1 MUX

Function:

Y = AB

Minterm Form:

Y = Σm(3)

Configuration:

- Select Line = A
- I₀ = 0
- I₁ = B

Output:

Y = A̅(0) + AB

Y = AB

---

## Implement OR Gate Using 2:1 MUX

Function:

Y = A + B

Minterm Form:

Y = Σm(1,2,3)

Configuration:

- Select Line = A
- I₀ = B
- I₁ = 1

Output:

Y = A̅B + A

Y = A + B

---

## Implement NAND Gate Using 2:1 MUX

Function:

Y = (AB)'

Configuration:

- Select Line = A
- I₀ = 1
- I₁ = B'

Output:

Y = A̅ + AB'

Y = (AB)'

---

# MUX Reduction Techniques

## MSB Reduction Technique

- Most Significant Bit selected as control variable.
- Remaining variables assigned to data inputs.
- Reduces implementation complexity.

### Procedure

1. Select MSB as Select Line.
2. Fill K-map.
3. Determine input functions.
4. Configure MUX.

---

## LSB Reduction Technique

- Least Significant Bit selected as control variable.
- Remaining variables assigned to data inputs.

### Procedure

1. Select LSB as Select Line.
2. Fill K-map.
3. Determine input functions.
4. Configure MUX.

---

# Function Realization Using Multiplexers

## Using 4:1 MUX

Function:

F(A,B,C) = Σm(1,2,4,7)

Procedure:

- Select A and B as Select Lines.
- Determine I₀, I₁, I₂ and I₃ from K-map.
- Connect constants and variables accordingly.

---

## Using 8:1 MUX

Function:

F(A,B,C) = Σm(1,2,4,7)

Configuration:

- Select Lines = A,B,C
- Inputs corresponding to minterms set to logic 1.
- Remaining inputs connected to logic 0.

---

## Function Realization Using 2:1 MUX

Implemented three-variable Boolean functions using:

- Shannon Expansion
- MSB Reduction
- LSB Reduction

---

# Full Adder Using MUX

## Sum

Sum = A ⊕ B ⊕ Cin

Σm(1,2,4,7)

## Carry

Carry = Σm(3,5,6,7)

Implemented using:

- 4:1 MUX
- 8:1 MUX

---

# Binary to Gray Code Conversion Using MUX

## 3-bit Binary to Gray

G₂ = B₂

G₁ = B₂ ⊕ B₁

G₀ = B₁ ⊕ B₀

Implemented using:

- 2:1 MUX
- 8:1 MUX

---

# MUX Tree Structures

## Configure 4:1 MUX Using 2:1 MUX

Required:

3 × (2:1) MUX

Structure:

Stage 1 → Two 2:1 MUX

Stage 2 → One 2:1 MUX

---

## Configure 8:1 MUX Using 2:1 MUX

Required:

7 × (2:1) MUX

Structure:

Stage 1 → 4 MUX

Stage 2 → 2 MUX

Stage 3 → 1 MUX

---

## Configure 16:1 MUX Using 2:1 MUX

Required:

15 × (2:1) MUX

Structure:

Stage 1 → 8 MUX

Stage 2 → 4 MUX

Stage 3 → 2 MUX

Stage 4 → 1 MUX

---

## Configure 5:1 MUX Using Only 2:1 MUX

Number of Select Lines:

⌈log₂(5)⌉ = 3

Constructed using cascaded 2:1 MUX blocks.

---

## Configure 6:1 MUX Using 2:1 MUX

Implemented by cascading multiple 2:1 MUX blocks and assigning unused inputs to logic constants.

---

## Configure 2:1 MUX Using 4:1 MUX

Method:

- S₁ = 0
- Use I₀ and I₁ only
- S₀ acts as select line

---

## Configure 8:1 MUX Using 4:1 MUX

Method:

- Two 4:1 MUX in first stage
- One 2:1 MUX in second stage

---

# Demultiplexers (DEMUX)

A Demultiplexer is a Data Distributor that routes one input to one of many outputs.

## Types Studied

- 1:2 DEMUX
- 1:4 DEMUX
- 1:8 DEMUX

---

## 1:2 DEMUX

Output Equations:

Y₀ = S̅I

Y₁ = SI

Truth Table:

| S | Y₀ | Y₁ |
|---|---|---|
| 0 | I | 0 |
| 1 | 0 | I |

---

## 1:4 DEMUX

Implemented using:

- Enable input
- Two select lines

Outputs:

Y₀, Y₁, Y₂, Y₃

---

## Function Realization Using 1:8 DEMUX

Function:

F(A,B,C) = Σm(1,2,4,7)

Method:

- Input connected to logic 1.
- Outputs Y₁, Y₂, Y₄ and Y₇ ORed together.

---

## Full Adder Using 1:8 DEMUX

Sum:

Σm(1,2,4,7)

Carry:

Σm(3,5,6,7)

Outputs combined using OR gates.

---

## 3-bit Gray to Binary Conversion Using 1:8 DEMUX

Equations:

B₂ = G₂

B₁ = G₂ ⊕ G₁

B₀ = G₂ ⊕ G₁ ⊕ G₀

Implemented using DEMUX outputs and OR gates.

---

## Configure 1:4 DEMUX Using 1:2 DEMUX

Required:

3 × 1:2 DEMUX

Structure:

Stage 1 → One DEMUX

Stage 2 → Two DEMUX

---

# Decoders

A Decoder is a Data Expander that converts n input lines into 2ⁿ output lines.

## Types Studied

- 1:2 Decoder
- 2:4 Decoder
- 3:8 Decoder
- 4:16 Decoder

---

# Active High Decoder

Selected output becomes logic 1.

Example:

2:4 Decoder

Y₀ = A'B'

Y₁ = A'B

Y₂ = AB'

Y₃ = AB

---

# Active Low Decoder

Selected output becomes logic 0.

Used extensively for function realization with NAND logic.

---

# Function Realization Using 3:8 Decoder

## Active High Decoder

Function:

F(A,B,C) = Σm(1,2,4,7)

Implementation:

F = Y₁ + Y₂ + Y₄ + Y₇

---

## Active Low Decoder

Function:

F(A,B,C) = Σm(1,2,4,7)

Implementation:

F = NAND(Y₁,Y₂,Y₄,Y₇)

---

# Full Subtractor Using 3:8 Decoder

Difference:

D = Σm(1,2,4,7)

Borrow:

B = Σm(1,2,3,7)

Implemented using decoder outputs and logic gates.

---

# Configure 2:4 Decoder Using 1:2 Decoder

Construction:

Stage 1 → One 1:2 Decoder

Stage 2 → Two 1:2 Decoders

Generates all four minterms.

---

# Practice Problems Solved

### Logic Gates Using 2:1 MUX

- AND Gate
- OR Gate
- NAND Gate

### Function Realization

- F(A,B,C)=Σm(1,2,4,7) using 2:1 MUX
- F(A,B,C)=Σm(1,2,4,7) using 4:1 MUX
- F(A,B,C)=Σm(1,2,4,7) using 8:1 MUX

### Full Adder Realization

- Using 4:1 MUX
- Using 8:1 MUX
- Sum and Carry realization

### Gray Code Conversion

- Binary to Gray using MUX
- Gray to Binary using DEMUX

### Decoder Applications

- Function realization using Active High Decoder
- Function realization using Active Low Decoder
- Full Subtractor realization using Decoder

### MUX Configurations

- 4:1 using 2:1 MUX
- 8:1 using 2:1 MUX
- 16:1 using 2:1 MUX
- 5:1 using 2:1 MUX
- 6:1 using 2:1 MUX
- 2:1 using 4:1 MUX
- 8:1 using 4:1 MUX

### DEMUX Configurations

- 1:4 DEMUX using 1:2 DEMUX

### Decoder Configurations

- 2:4 Decoder using 1:2 Decoder

---

# Key Learning Outcomes

- Studied Multiplexer, Demultiplexer and Decoder architectures.
- Implemented AND, OR and NAND gates using 2:1 MUX.
- Learned MSB and LSB Reduction Techniques.
- Realized Boolean functions using 2:1, 4:1 and 8:1 MUX.
- Implemented Full Adders using MUX and DEMUX.
- Designed Binary-to-Gray and Gray-to-Binary converters using MSI circuits.
- Constructed larger MUX structures using smaller MUX blocks.
- Implemented Boolean functions using 1:8 DEMUX and 3:8 Decoder.
- Studied Active High and Active Low Decoder operations.
- Implemented Full Subtractor using Decoder realization.
- Configured larger Decoders and DEMUX structures using smaller building blocks.
