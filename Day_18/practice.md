# Day 18 - Practice Problems on Multiplexers and Logic Function Realization

---

## Practice Problem 1

### Problem

Implement the following function using:

- 2×1 Multiplexer
- 4×1 Multiplexer

F(a,b,c,d) = Σm(1,3,5,9,11,13)

---

### Expansion

F = a'b'd + a'bd + ab'd + abd + a'bc + abc

---

### Using 2×1 MUX

Choose:

Select = a

Then,

F = a'(b'd + bd + bc) + a(b'd + bc + b'd)

Simplifying,

I0 = d'

I1 = c + d'

#### Final Connections

- Select = a
- I0 = d'
- I1 = c + d'

Output = F

---

### Using 4×1 MUX

Choose:

- S1 = a
- S0 = b

From K-Map,

- I0 = d'
- I1 = c + d'
- I2 = d'
- I3 = c + d'

#### Final Connections

| Select Lines | Value |
|-------------|--------|
| S1 | a |
| S0 | b |

| Data Input | Value |
|------------|--------|
| I0 | d' |
| I1 | c + d' |
| I2 | d' |
| I3 | c + d' |

Output = F

---

## Practice Problem 2

### Problem

Design a combinational circuit using four 2×1 multiplexers such that:

- Control = 1 → Half Adder
- Control = 0 → Half Subtractor

No complemented inputs are available.

---

### Half Adder

Sum = a XOR b

Carry = ab

| a | b | Sum | Carry |
|---|---|-----|-------|
| 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 1 |

---

### Half Subtractor

Difference = a XOR b

Borrow = a'b

| a | b | Difference | Borrow |
|---|---|------------|--------|
| 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 1 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 0 |

---

### Observation

Common Output:

Sum = Difference = a XOR b

Other Outputs:

Carry = ab

Borrow = a'b

Use Control Signal:

- Control = 1 → Carry
- Control = 0 → Borrow

Final output selected through a 2×1 MUX.

---

## Practice Problem 3

### Problem

Find the output of the given cascaded 2×1 MUX circuit.

---

### First MUX

Inputs:

- I0 = x
- I1 = y'

Select = z

Output:

M = z'x + zy'

---

### Second MUX

Inputs:

- I0 = M
- I1 = x

Select = y

Output:

f = y'(z'x + zy') + xy

Expanding,

f = xy'z' + zy' + xy

Taking y' common,

f = y'(xz' + z) + xy

Using Boolean identity:

xz' + z = x + z

Therefore,

f = y'(x + z) + xy

= xy' + y'z + xy

= x(y' + y) + y'z

### Final Answer

f = x + y'z

---

## Practice Problem 4

### Problem

For a 74151 (8×1 Multiplexer), determine the select inputs required so that output Y becomes a copy of input I5.

---

### Solution

Input number:

I5

Binary representation of 5:

5 = 101

Therefore,

| Select Line | Value |
|------------|--------|
| S2 | 1 |
| S1 | 0 |
| S0 | 1 |

### Final Answer

S2 = 1

S1 = 0

S0 = 1

---

## Practice Problem 5

### Problem

A 16×1 MUX is connected to a 1×16 DEMUX.

Input applied at:

I13

Find the output line number n.

---

### Solution

MUX select inputs:

A = 1

B = 1

C = 0

D = 1

Therefore,

1101₂ = 13

DEMUX select inputs evaluate to:

0111₂

Decimal equivalent:

0111₂ = 7

### Final Answer

n = 7

---

## Practice Problem 6

### Problem

Simplify the output expression.

---

Given:

f = x'x + xz

Since,

x'x = 0

Therefore,

f = xz

Further,

f = y'(xz) + zy

= xzy' + zy

Taking z common,

= z(xy' + y)

Using identity:

xy' + y = x + y

### Final Answer

f = z(x + y)

---

## Practice Problem 7

### Problem

Simplify:

f = x'y + x'y' + xy'

---

### Solution

Taking x' common,

f = x'(y + y') + xy'

= x' + xy'

Using absorption law,

= x' + y'

### Final Answer

f = x' + y'

---

## Practice Problem 8

### Problem

Find the output of the 4×1 MUX.

Inputs:

- I3 = 1
- I2 = 1
- I1 = 1
- I0 = C

Selectors:

- S1 = A
- S0 = B

---

### MUX Equation

Q = A'B'C + A'B + AB' + AB

Taking A' common,

Q = A'(B + C) + A(B + B')

Q = A'(B + C) + A

Using absorption,

### Final Answer

Q = A + B + C

---

## Practice Problem 9

### Problem

Find the output of the cascaded 4×1 MUX circuit.

---

### Solution

First MUX output:

Y = A XOR B

Y = A'B + AB'

Second MUX output:

X = (A XOR B)C + (A XOR B)'C'

Expanding,

X = ABC + A'B'C + A'BC' + AB'C'

### Final Answer

X = ABC + A'B'C + A'BC' + AB'C'

---

## Practice Problem 10

### Problem

Find the logic function implemented by the given 4×1 MUX.

---

Given:

| Input | Value |
|--------|--------|
| I0 | 0 |
| I1 | 1 |
| I2 | 1 |
| I3 | 0 |

Selectors:

- S1 = P
- S0 = Q

---

### Solution

MUX equation:

F = P'Q + PQ'

### Final Answer

F = P XOR Q

---

## Practice Problem 11

### Problem

An 8×1 MUX is used to generate the carry output of a Full Adder.

Why is an 8×1 MUX sufficient?

---

### Solution

Full Adder Carry:

Carry = AB + BCin + ACin

Number of variables:

- A
- B
- Cin

Total variables = 3

Required MUX inputs:

2³ = 8

### Final Answer

An 8×1 MUX is sufficient because the carry output depends on 3 variables.

---

## Practice Problem 12

### Problem

Find the output expression Z for the given 4×1 MUX.

Inputs:

- I3 = P
- I2 = PQ
- I1 = P
- I0 = P + Q'

Selectors:

- R = MSB
- S = LSB

---

### Solution

MUX equation:

Z = R'S'(P + Q')
  + R'S(P)
  + RS'(PQ)
  + RSP

Simplifying,

Z = PR' + PS + PQ + R'S'Q'

### Final Answer

Z = PR' + PS + PQ + R'S'Q'
