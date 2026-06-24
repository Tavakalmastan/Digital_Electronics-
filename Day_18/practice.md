# Day 18 - Practice Problems on Multiplexers and Logic Function Realization

## Practice Problem 1

### Given

\[
F(a,b,c,d)=\Sigma m(1,3,5,9,11,13)
\]

Implement using:

- 2×1 Multiplexer
- 4×1 Multiplexer

### Simplification

\[
F=\bar a\bar b\bar d+\bar a b\bar d+a\bar b\bar d+ab\bar d+\bar abc+abc
\]

Grouping with respect to selector \(a\):

\[
F=\bar a(\bar b\bar d+b\bar d+bc)+a(b\bar d+bc+\bar b\bar d)
\]

### For 2×1 MUX

Selector:

\[
S=a
\]

Inputs:

\[
I_0=\bar d
\]

\[
I_1=c+\bar d
\]

Implementation:

- Select line → a
- \(I_0=\bar d\)
- \(I_1=c+\bar d\)

---

### For 4×1 MUX

Selectors:

\[
S_1=a,\quad S_0=b
\]

Data Inputs:

\[
I_0=\bar d
\]

\[
I_1=\bar d+c
\]

\[
I_2=\bar d
\]

\[
I_3=\bar d+c
\]

MUX realization completed using K-map derived inputs.

---

## Practice Problem 2

### Design Requirement

Design a combinational logic circuit using four 2×1 multiplexers.

Control input:

- Control = 1 → Half Adder
- Control = 0 → Half Subtractor

No complemented inputs available.

### Half Adder

Outputs:

\[
Sum=a\oplus b
\]

\[
Carry=ab
\]

Truth Table

| a | b | Sum | Carry |
|---|---|-----|-------|
|0|0|0|0|
|0|1|1|0|
|1|0|1|0|
|1|1|0|1|

---

### Half Subtractor

Outputs:

\[
Difference=a\oplus b
\]

\[
Borrow=\bar a b
\]

Truth Table

| a | b | Difference | Borrow |
|---|---|------------|--------|
|0|0|0|0|
|0|1|1|1|
|1|0|1|0|
|1|1|0|0|

---

### Observation

\[
Sum = Difference = a\oplus b
\]

\[
Carry=ab
\]

\[
Borrow=\bar a b
\]

Control line selects:

- 1 → Carry
- 0 → Borrow

Final output generated through fourth 2×1 MUX.

---

## Practice Problem 3

### Determine Output of MUX Circuit

Given cascaded 2×1 MUX network.

First MUX:

Inputs:

\[
I_0=x
\]

\[
I_1=\bar y
\]

Selector:

\[
z
\]

Output:

\[
\bar z x+z\bar y
\]

Second MUX:

Inputs:

\[
I_0=(\bar z x+z\bar y)
\]

\[
I_1=x
\]

Selector:

\[
y
\]

Output:

\[
f=\bar y(\bar z x+z\bar y)+xy
\]

Expanding:

\[
f=x\bar y\bar z+z\bar y+xy
\]

\[
f=\bar y(x\bar z+z)+xy
\]

Using:

\[
x\bar z+z=x+z
\]

\[
f=\bar y(x+z)+xy
\]

\[
f=x\bar y+\bar yz+xy
\]

\[
f=x(\bar y+y)+\bar yz
\]

\[
\boxed{f=x+\bar yz}
\]

---

## Practice Problem 4

### 74151 (8-to-1 MUX)

Question:

Determine status of select inputs

\[
S_2,S_1,S_0
\]

such that output Y becomes a copy of input \(I_5\).

### Solution

Binary equivalent of input 5:

\[
5=(101)_2
\]

Therefore

\[
\boxed{S_2=1,\;S_1=0,\;S_0=1}
\]

---

## Practice Problem 5

### 16×1 MUX and 1×16 DEMUX

Input applied:

\[
I_{13}
\]

MUX select inputs:

\[
A=1,\quad B=1,\quad C=0,\quad D=1
\]

Hence:

\[
1101_2=13
\]

DEMUX select lines generated from logic network:

\[
S_3S_2S_1S_0
=
0111
\]

Binary equivalent:

\[
0111_2=7
\]

Therefore

\[
\boxed{n=7}
\]

---

## Practice Problem 6

### Simplify MUX Output

Expression:

\[
\bar x x+xz
\]

Since

\[
\bar xx=0
\]

\[
=0+xz
\]

\[
=xz
\]

Further realization:

\[
\bar y(xz)+zy
\]

\[
=xz\bar y+zy
\]

\[
=z(x\bar y+y)
\]

Using:

\[
x\bar y+y=x+y
\]

Hence

\[
\boxed{z(x+y)}
\]

---

## Practice Problem 7

### Simplify Expression

\[
\bar x y+\bar x\bar y+x\bar y
\]

Grouping:

\[
=\bar x(y+\bar y)+x\bar y
\]

\[
=\bar x+x\bar y
\]

Using absorption:

\[
=\bar x+\bar y
\]

Alternative derivation:

\[
\bar xy+xy+x\bar y
\]

\[
=y(\bar x+x)+x\bar y
\]

\[
=y+x\bar y
\]

\[
=x+y
\]

Final simplified expression depends on corresponding realization.

---

## Practice Problem 8

### 4×1 MUX Circuit

Inputs:

\[
I_3=1
\]

\[
I_2=1
\]

\[
I_1=1
\]

\[
I_0=C
\]

Selectors:

\[
S_1=A,\quad S_0=B
\]

Output:

\[
Q=
\bar A\bar BC+
\bar A B+
A\bar B+
AB
\]

Simplifying:

\[
Q=\bar A(B+C)+A(B+\bar B)
\]

\[
Q=\bar A(B+C)+A
\]

Using absorption:

\[
Q=A+B+C
\]

\[
\boxed{Q=A+B+C}
\]

---

## Practice Problem 9

### Two Cascaded 4×1 Multiplexers

First MUX output:

\[
Y=A\oplus B
\]

Using identity:

\[
A\oplus B=\bar AB+A\bar B
\]

Second MUX realization gives:

\[
X=(A\oplus B)C+\overline{(A\oplus B)}\bar C
\]

Expanding:

\[
X=ABC+\bar A\bar BC+\bar AB\bar C+A\bar B\bar C
\]

\[
\boxed{X=ABC+\bar A\bar BC+\bar AB\bar C+A\bar B\bar C}
\]

---

## Practice Problem 10

### 4×1 MUX Function

Selectors:

\[
S_1=P,\quad S_0=Q
\]

From data input assignments:

\[
I_0=0
\]

\[
I_1=1
\]

\[
I_2=1
\]

\[
I_3=0
\]

Output:

\[
F=\bar PQ+P\bar Q
\]

Therefore

\[
\boxed{F=P\oplus Q}
\]

---

## Practice Problem 11

### 8×1 MUX used for Full Adder Carry Generation

Observation:

Full Adder Carry output:

\[
C_{out}=AB+BC_{in}+AC_{in}
\]

Since three variables are involved,

Number of data inputs required:

\[
2^3=8
\]

Hence 8×1 MUX can realize Full Adder Carry.

---

## Practice Problem 12

### 4×1 MUX with Inputs

\[
I_3=P
\]

\[
I_2=PQ
\]

\[
I_1=P
\]

\[
I_0=P+\bar Q
\]

Selectors:

\[
R \; (MSB)
\]

\[
S \; (LSB)
\]

MUX equation:

\[
Z=
\bar R\bar S(P+\bar Q)
+
\bar RS(P)
+
R\bar S(PQ)
+
RSP
\]

After simplification:

\[
\boxed{Z=P\bar R+PS+PQ+\bar R\bar S\bar Q}
\]

