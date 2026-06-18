# Day 12 - Boolean Algebra, Logic Gates and CMOS Logic

## Topics Covered

### 1. Digital System Hierarchy

Digital systems can be represented in a hierarchical manner:

```text
System
│
├── Subsystems
│   ├── CPU
│   ├── Memory
│   └── I/O
│
├── Modules
│   ├── ALU
│   ├── Registers
│   └── Control Units
│
├── Functional Blocks
│   ├── Arithmetic Circuits
│   ├── Code Converters
│   ├── Encoders
│   ├── Decoders
│   ├── Registers
│   └── Counters
│
├── Logic Units
│
├── Circuits
│
└── Devices
    ├── Active Devices
    └── Passive Devices
```

---

## 2. Combinational and Sequential Logic Circuits

### Combinational Logic Circuits

- Output depends only on present inputs.
- No memory element is used.

### Examples

- Arithmetic Circuits
- Code Converters
- Multiplexers (MUX)
- Demultiplexers (DEMUX)
- Comparators
- Encoders
- Decoders

---

### Sequential Logic Circuits

- Output depends on present inputs and previous outputs (memory).
- Contains storage elements.

### Examples

- Registers
- Counters
- Finite State Machines (FSM)

---

## 3. Introduction to Boolean Algebra

### George Boole

- George Boole introduced Boolean Algebra.
- Boolean Algebra works with two logic values:

```text
0 → Logic Low
1 → Logic High
```

---

## 4. Logic Levels

### Positive Logic

```text
0 → 0V
1 → 5V
```

### Negative Logic

```text
0 → 5V
1 → 0V
```

---

## 5. Boolean Expressions

Example:

```text
Y = A.B
```

where:

```text
.  → AND operation
+  → OR operation
'  → NOT operation
```

---

## 6. Logic Gates

A logic gate is an electronic circuit that accepts one or more inputs and produces a single output.

### Classification of Gates

#### Basic Gates

- AND
- OR
- NOT

#### Universal Gates

- NAND
- NOR

#### Application Gates

- XOR
- XNOR

---

## 7. Basic Logic Gates

### NOT Gate

Expression:

```text
Y = A'
```

### AND Gate

Expression:

```text
Y = A.B
```

### OR Gate

Expression:

```text
Y = A + B
```

---

## 8. Universal Gates

### NAND Gate

Expression:

```text
Y = (A.B)'
```

### NOR Gate

Expression:

```text
Y = (A + B)'
```

---

## 9. Gate Count Formula

### NAND Gate Realization

Number of NAND gates required:

```text
(2n - 2) + k
```

Where:

- n = Number of variables
- k = Number of complemented inputs

---

### NOR Gate Realization

Number of NOR gates required:

```text
(3n - 3) - k
```

Where:

- n = Number of variables
- k = Number of complemented inputs

---

## 10. Double Complement Method

A Boolean function can be converted into NAND-only realization by applying double complements.

Example:

```text
Y = A'B + AB'
```

Apply double complement:

```text
Y = ((A'B + AB')')'
```

This helps in implementing the circuit using only NAND gates.

---

## 11. Why NAND Gate is Preferred

Advantages:

- Easier hardware implementation.
- Symmetrical charging and discharging characteristics.
- Lower manufacturing complexity.
- Faster implementation in VLSI circuits.

---

## 12. Number System Conversions

### Binary to Gray Code

Procedure:

```text
MSB remains unchanged.
Each next bit = XOR of adjacent binary bits.
```

Example:

```text
Binary : 01110
Gray   : 01001
```

---

### Gray to Binary

Procedure:

```text
MSB remains unchanged.
Next binary bit = Previous binary bit XOR current gray bit.
```

Example:

```text
Gray   : 01001
Binary : 01110
```

---

## 13. Excess-3 Code

### Decimal to Excess-3

Add 3 to each decimal digit.

Example:

```text
4 → 0111
3 → 0110
```

Therefore:

```text
43 → 0111 0110
```

---

## 14. BCD Representation

Example:

```text
84
```

BCD:

```text
8 → 1000
4 → 0100

BCD = 10000100
```

---

## 15. Parity Bits

Parity bits are used for error detection during data transmission.

### Even Parity

- Total number of 1's should be even.

### Odd Parity

- Total number of 1's should be odd.

---

## 16. Duality Principle

Duality operation:

```text
AND ↔ OR
0 ↔ 1
```

Example:

```text
A + BC
```

Dual:

```text
A(B + C)
```

---

## 17. Self-Dual Functions

A Boolean function is self-dual if the dual of the function equals the complement of the original function.

Example:

```text
F = Σm(0,1,2,4)
```

Self-dual property can be verified through dual transformation.

---

## 18. Minterm and Maxterm Expansion

### Minterm Expansion

Example:

```text
F = Σm(2,3,6,7)
```

Represents all combinations where output is 1.

---

### Maxterm Expansion

Example:

```text
F = ΠM(0,1,4,5)
```

Represents all combinations where output is 0.

---

## 19. Complement of Boolean Functions

### Example

Given:

```text
F(x,y,z) = y + x'z
```

Complement:

```text
F' = (y + x'z)'
```

Applying DeMorgan's theorem:

```text
F' = y'(x + z')
```

---

## 20. CMOS Logic

### CMOS Inverter

Consists of:

- PMOS Pull-Up Network (PUN)
- NMOS Pull-Down Network (PDN)

Operation:

```text
Input = 0
PMOS ON
NMOS OFF
Output = 1
```

```text
Input = 1
PMOS OFF
NMOS ON
Output = 0
```

---

## 21. CMOS NAND Gate

### Pull-Up Network

- PMOS connected in parallel.

### Pull-Down Network

- NMOS connected in series.

Expression:

```text
Y = (A.B)'
```

Truth Table:

| A | B | Y |
|---|---|---|
| 0 | 0 | 1 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

---

## 22. CMOS NOR Gate

### Pull-Up Network

- PMOS connected in series.

### Pull-Down Network

- NMOS connected in parallel.

Expression:

```text
Y = (A+B)'
```

Truth Table:

| A | B | Y |
|---|---|---|
| 0 | 0 | 1 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 0 |

---

## 23. Realization of XOR Using NAND Gates

Expression:

```text
Y = A'B + AB'
```

Steps:

1. Draw SOP implementation.
2. Introduce double complements.
3. Replace AND/OR gates with NAND gates.
4. Use NAND gate realization throughout.
5. Obtain final NAND-only implementation.

---

## Key Takeaways

1. Understood the hierarchy of digital systems from devices to complete systems and the role of combinational and sequential logic circuits.

2. Learned Boolean algebra fundamentals, logic levels (positive and negative logic), and the operation of basic, universal, and application logic gates.

3. Studied NAND and NOR gates as universal gates and learned how to realize Boolean expressions using only NAND or only NOR gates through the double complement method.

4. Explored important coding techniques including Binary, Gray Code, Excess-3 Code, BCD representation, and parity generation for error detection.

5. Gained knowledge of CMOS logic design, including CMOS inverter, CMOS NAND gate, CMOS NOR gate, and the implementation of XOR functions using NAND gates.
