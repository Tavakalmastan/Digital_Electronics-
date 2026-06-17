# Day 11 - Signed Number Representation and Complement Arithmetic

## Objective

Today's learning focused on signed number representation, 1's complement and 2's complement number systems, arithmetic operations using complements, overflow handling, and subtraction techniques in binary, decimal, octal, and hexadecimal number systems.

---

## Topics Covered

### 1. Signed Number Representation

A signed binary number uses the Most Significant Bit (MSB) to represent the sign.

- MSB = 0 → Positive Number
- MSB = 1 → Negative Number

Examples:

```text
+5  = 0101
-5  = 1101
```

For a 4-bit signed magnitude representation:

```text
Range = -7 to +7
```

Key Learnings:

- Sign bit identifies positive and negative numbers.
- Signed magnitude representation is simple but not hardware efficient.
- Arithmetic operations become difficult using signed magnitude.

---

### 2. 1's Complement Number System

Negative numbers are represented by inverting all bits of the positive number.

Formula:

```text
1's Complement = (2ⁿ - 1) - N
```

Examples:

```text
+5 = 0101
-5 = 1010

+7 = 0111
-7 = 1000
```

4-bit Range:

```text
-7 to +7
```

Key Learnings:

- Obtained by flipping all bits.
- Medium hardware compatibility.
- Contains two zeros:

+0 = 0000
-0 = 1111

---

### 3. 2's Complement Number System

Negative numbers are represented using:

```text
2's Complement = 1's Complement + 1
```

Formula:

```text
2's Complement = 2ⁿ - N
```

Examples:

```text
+5 = 0101
-5 = 1011

+7 = 0111
-7 = 1001
```

Ranges:

```text
n = 4 → -8 to +7
n = 5 → -16 to +15
```

Key Learnings:

- Most widely used representation.
- Eliminates dual zero problem.
- High degree of hardware compatibility.
- Simplifies arithmetic operations.

---

### 4. Binary Subtraction Using Complements

#### Case 1: Minuend > Subtrahend

Example:

```text
14 - 12
```

Using 1's Complement:

```text
14 → 1110
12 → 1100

1's Comp(12) = 0011

1110
0011
----
10001

Carry generated.
Add carry to LSB.

Result = 0010₂ = 2
```

Using 2's Complement:

```text
12 → 1100

2's Comp(12) = 0100

1110
0100
----
10010

Discard carry.

Result = 0010₂ = 2
```

---

#### Case 2: Minuend < Subtrahend

Example:

```text
12 - 14
```

Using 1's Complement:

```text
12 → 1100
14 → 1110

1's Comp(14) = 0001

1100
0001
----
1101

No carry.

Take 1's complement of result.

0010

Result = -2
```

Using 2's Complement:

```text
14 → 1110

2's Comp(14) = 0010

1100
0010
----
1110

Take 2's complement.

0010

Result = -2
```

Key Learnings:

- Carry is added back in 1's complement arithmetic.
- Carry is discarded in 2's complement arithmetic.
- No carry indicates a negative result.

---

### 5. Decimal Complement Arithmetic

#### 10's Complement

Formula:

```text
10ⁿ - N
```

Example:

```text
10's Comp(1234)

10000
-1234
-----
8766
```

#### 9's Complement

Formula:

```text
(10ⁿ - 1) - N
```

Example:

```text
9999
-1234
-----
8765
```

Key Learnings:

- Used to perform decimal subtraction through addition.
- Simplifies hardware implementation.

---

### 6. Octal Complement Arithmetic

#### 8's Complement

Formula:

```text
8ⁿ - N
```

Example:

```text
(44)₈

100₈
-44₈
-----
34₈
```

#### 7's Complement

Formula:

```text
(8ⁿ - 1) - N
```

Example:

```text
77₈
-44₈
----
33₈
```

Key Learnings:

- Octal subtraction can be implemented using complements.
- Similar approach as decimal and binary complements.

---

### 7. Hexadecimal Complement Arithmetic

#### 16's Complement

Formula:

```text
16ⁿ - N
```

#### 15's Complement

Formula:

```text
(16ⁿ - 1) - N
```

Example:

```text
FFFF₁₆
-ABCD₁₆
--------
5432₁₆
```

Adding 1:

```text
5433₁₆
```

Key Learnings:

- Widely used in computer architecture and digital systems.
- Useful for hexadecimal subtraction and arithmetic operations.

---

### 8. Binary Sign Extension

For signed binary numbers:

4-bit representation:

```text
a3 a2 a1 a0
```

8-bit representation:

```text
a3 a3 a3 a3 a3 a2 a1 a0
```

Key Learnings:

- Sign bit is replicated during extension.
- Preserves signed value when increasing bit width.

---

## Commands / Problems Practiced

### Binary Complement Representation

```text
+5 → 0101
-5 → 1010 (1's Comp)
-5 → 1011 (2's Comp)

+7 → 0111
-7 → 1000 (1's Comp)
-7 → 1001 (2's Comp)
```

### Binary Subtraction

```text
14 - 12
12 - 14
-5 - (-7)
+7 - (-5)
```

### Decimal Complement Problems

```text
54 - 25 using 9's complement
54 - 25 using 10's complement
```

### Hexadecimal Complement Problems

```text
(470.56)₁₆ - (297.55)₁₆

Using:
15's Complement
16's Complement
```

### Octal Complement Problems

```text
(271.05)₈ - (475.235)₁₆
```

### Sign Extension Practice

```text
4-bit to 8-bit signed extension
MSB replication
```

---

## Practical Learning Outcomes

- Understood signed magnitude representation.
- Learned 1's complement and 2's complement systems.
- Performed binary subtraction using complements.
- Understood carry and overflow handling.
- Learned decimal complement arithmetic.
- Practiced octal and hexadecimal complement operations.
- Learned sign extension for signed numbers.
- Understood why 2's complement is preferred in digital systems.
- Solved multiple arithmetic problems using complement techniques.

---

## Key Takeaways

- 2's complement is the most commonly used signed number representation.
- Complement arithmetic converts subtraction into addition.
- Carry handling differs between 1's and 2's complement methods.
- Sign extension preserves signed values across different bit widths.
- Complement arithmetic is widely used in processors, ALUs, and digital systems.
