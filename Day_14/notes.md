# Day 14 - Karnaugh Maps, Code Converters and Logic Minimization

## Objective

Learn advanced Karnaugh Map (K-Map) simplification techniques, don't-care conditions, higher-order K-Maps, logic minimization methods, and the design of Binary ↔ Gray Code and BCD ↔ Excess-3 Code converters. The notes also covered practical implementation of combinational logic circuits. :contentReference[oaicite:0]{index=0}

---

## Topics Covered

### 1. Karnaugh Map with Don't Care Conditions

- Use don't care conditions (X) to obtain larger groups in K-Maps.
- Don't care terms may be treated as either 0 or 1 depending on simplification requirements.
- Larger groups lead to simpler Boolean expressions.
- Obtained minimal SOP and POS expressions using don't care entries.

### 2. Minimal SOP and POS using K-Maps

- Simplification of Boolean functions using:
  - Sum of Products (SOP)
  - Product of Sums (POS)
- Identification of:
  - Prime Implicants (PI)
  - Essential Prime Implicants (EPI)
  - Non-Essential Prime Implicants (NEPI)

### 3. XOR and XNOR Pattern Recognition

- Certain K-Map patterns directly represent:
  - XOR function
  - XNOR function
- Useful for faster simplification and circuit realization.

### 4. Limitations of Karnaugh Maps

- Suitable for small-variable functions.
- Becomes difficult for:
  - 5-variable functions
  - 6-variable functions
  - Higher-order Boolean expressions
- Mapping and grouping become increasingly complex.

### 5. 5-Variable and 6-Variable K-Maps

- Construction of:
  - 5-variable K-Maps
  - 6-variable K-Maps
- Grouping across multiple map sections.
- Deriving minimal expressions from higher-dimensional maps.

### 6. CAD-Based Logic Minimization Techniques

- Quine-McCluskey Method (Tabular Method)
- Map Entered Variable (MEV)
- Boolean Differentiation
- Espresso Algorithm

---

## Building Combinational Logic Circuits

### Components Used

#### Code Converters

- Binary Code
- Gray Code
- Excess-3 Code
- ASCII Code
- BCD Code
- Seven Segment Display

#### Arithmetic Circuits

- Half Adder (HA)
- Full Adder (FA)
- Parallel Adder (PA)
- Half Subtractor (HS)
- Full Subtractor (FS)
- Parallel Subtractor (PS)

#### MSI Devices

- Multiplexer
- Demultiplexer
- Encoder
- Decoder
- Converters

### Applications of Code Converters

- Reduce switching operations.
- Improve system reliability.
- Used in security applications.
- Reduce hardware complexity.
- Used in decimal arithmetic circuit implementations.

---

## Steps to Design a Combinational Logic Circuit

### Step 1

Understand the problem statement and requirements.

### Step 2

Represent the system using a block diagram.

### Step 3

Identify:
- Number of inputs
- Number of outputs

Construct the truth table.

### Step 4

Perform logic minimization using:
- K-Map
- Boolean Algebra
- Other minimization techniques

Obtain:
- Minimal SOP
- Minimal POS

### Step 5

Implement the simplified logic circuit.

---

## Binary to Gray Code Conversion

### 3-Bit Binary to Gray Code

Given inputs:

- b₂
- b₁
- b₀

Outputs:

- g₂
- g₁
- g₀

Equations:

```text
g₂ = b₂

g₁ = b₂ ⊕ b₁

g₀ = b₁ ⊕ b₀
```

### 4-Bit Binary to Gray Code

```text
g₃ = b₃

g₂ = b₃ ⊕ b₂

g₁ = b₂ ⊕ b₁

g₀ = b₁ ⊕ b₀
```

### General n-Bit Binary to Gray Conversion

```text
g(n-1) = b(n-1)

g(i) = b(i+1) ⊕ b(i)
```

for i = n-2 down to 0

### Example

```text
Binary : 10111

Gray   : 11100
```

---

## Gray Code to Binary Conversion

### 3-Bit Gray to Binary

```text
b₂ = g₂

b₁ = b₂ ⊕ g₁

b₀ = b₁ ⊕ g₀
```

### 4-Bit Gray to Binary

```text
b₃ = g₃

b₂ = b₃ ⊕ g₂

b₁ = b₂ ⊕ g₁

b₀ = b₁ ⊕ g₀
```

### Example

```text
Gray : 1100

Binary : 1000
```

---

## Gray Code Advantages

- Adjacent values differ by only one bit.
- Minimizes transition errors.
- Reduces glitches and switching noise.
- Widely used in:
  - Rotary Encoders
  - Asynchronous FIFOs
  - FSMs
  - High-speed digital systems

---

## BCD to Excess-3 Code Converter

### Design Procedure

1. Define BCD inputs:
   - b₃ b₂ b₁ b₀

2. Define Excess-3 outputs:
   - e₃ e₂ e₁ e₀

3. Construct truth table.

4. Treat invalid BCD inputs (10–15) as don't care conditions.

5. Simplify each output using K-Maps.

### Simplified Results

```text
e₀ = b̅₀

e₁ = b̅₁b₀ + b₁b̅₀
    = b₁ ⊕ b₀
```

Additional outputs were derived using K-Map simplification.

---

## Important Concepts Learned

### Prime Implicant (PI)

A group of adjacent 1's in a K-Map.

### Essential Prime Implicant (EPI)

A prime implicant containing at least one unique minterm.

### Non-Essential Prime Implicant (NEPI)

A prime implicant that can be replaced by another grouping.

### Redundant Prime Implicant

Prime implicant that does not contribute to the final minimal expression.

---

## Key Takeaways

- Learned K-Map simplification with don't-care conditions.
- Performed SOP and POS minimization using K-Maps.
- Studied 5-variable and 6-variable Karnaugh Maps.
- Designed Binary ↔ Gray Code converters using truth tables and K-Maps.
- Introduced BCD to Excess-3 code converter design and logic minimization.

---
