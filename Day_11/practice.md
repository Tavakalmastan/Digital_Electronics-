# Day 11 Practice Problems

## 1. Advantages of 2's Complement System over 1's Complement System

- Higher degree of representation.
- High compatibility with hardware implementation.
- Only one representation for zero.
- Easier arithmetic operations.

---

## 2. Binary Addition

### Problem
\[
(1101)_2 + (110111)_2
\]

### Solution

```text
  0001101
+ 1101111
---------
 1111100
```

### Result

\[
(1111100)_2
\]

---

## 3. Subtraction Using (r-1)'s Complement

### (a)

\[
(1101)_2 - (110111)_2
\]

- Convert the subtrahend using 1's complement.
- Perform addition.
- Take complement of the result when required.

### Result

\[
-(110010)_2
\]

---

### (b)

\[
(77652)_8 - (76543)_8
\]

Using 7's complement:

```text
7's complement of 76543 = 01234
```

Add:

```text
 77652
+01234
------
100106
```

End-around carry:

```text
001106
+    1
------
001107
```

### Result

\[
(01107)_8
\]

---

## 4. Subtraction Using r's Complement

### (a)

\[
(110111)_2 - (1111)_2
\]

Using 2's complement:

```text
2's complement of 1111 = 0001
```

Add and discard carry.

### Result

\[
(111000)_2
\]

---

### (b)

\[
(652)_8 - (765)_8
\]

Using 8's complement:

```text
7's complement of 765 = 012
8's complement = 013
```

Add:

```text
 652
+013
----
 665
```

### Result

\[
(665)_8
\]

---

## 5. Signed Magnitude Representation

### Represent +25 and -25

```text
+25 → 011001
-25 → 111001
```

---

## 6. Binary Addition Practice

### Example

```text
 11001011
+01001011
----------
10110100
```

### Result

\[
(10110100)_2
\]

---

## 7. Complement Arithmetic

### Solve

\[
(12)_{10} - (14)_{10}
\]

Using 2's complement:

```text
12 = 1100
14 = 1110

2's complement of 1110:

0001
+   1
-----
0010
```

Add:

```text
1100
0010
-----
1110
```

### Result

\[
-(1110)_2
\]

---

## 8. Decimal Complement Arithmetic

### Find 9's Complement of 456

```text
999
456
---
543
```

### Result

\[
543
\]

---

## Topics Practiced

- Binary Addition
- Binary Subtraction
- 1's Complement Arithmetic
- 2's Complement Arithmetic
- 7's Complement Arithmetic
- 8's Complement Arithmetic
- Signed Number Representation
- Decimal Complement Arithmetic
- Positive and Negative Number Representation
- Numerical Problem Solving
