## Practice Problems

### 1. 2:1 Multiplexer

A 2:1 Multiplexer selects one of two inputs based on the select line.

**Output Equation**

Y = S'I₀ + SI₁

**Operation**

* S = 0 → Y = I₀
* S = 1 → Y = I₁

---

### 2. Function Realization Using 2:1 Multiplexers

Implemented Boolean functions using cascaded 2:1 multiplexers.

**Method**

* Express the function in terms of a selected variable.
* Use Shannon's Expansion Theorem.
* Determine I₀ and I₁ values.
* Connect them to the multiplexer inputs.

Example:

F(a,b,c) realized using multiple 2:1 multiplexers by selecting variable **c** as the select line.

---

### 3. 2-to-4 Decoder

A 2-to-4 decoder generates four minterms from two input variables.

**Inputs**

* a
* b

**Outputs**

* Y₀ = a'b'
* Y₁ = a'b
* Y₂ = ab'
* Y₃ = ab

Applications:

* Function realization
* Address decoding
* Memory selection

---

### 4. Function Realization Using Decoder

Boolean functions can be implemented using a decoder and OR/NAND gates.

Example Function:

F(a,b) = a'b' + ab

This represents the XNOR function.

Equivalent POS Form:

F(a,b) = (a + b')(a' + b)

---

### 5. Binary to Gray Code Conversion

For a 4-bit binary number:

G₃ = B₃

G₂ = B₃ ⊕ B₂

G₁ = B₂ ⊕ B₁

G₀ = B₁ ⊕ B₀

Example:

Binary = 0110

Gray Code = 0101

---

### 6. Number System Conversions

Practiced conversion of decimal numbers into:

* Binary
* Gray Code
* BCD
* Excess-3 Code
* Hexadecimal

Example:

Decimal 1

Binary = 0001

BCD = 0001

Excess-3 = 0100

Hexadecimal = 1

---

### 7. BCD to Excess-3 Code Converter

Designed a BCD to Excess-3 converter using a 4-to-10 decoder and minimum logic gates.

**Procedure**

* Generate BCD minterms using a decoder.
* Identify required Excess-3 outputs.
* Combine decoder outputs using logic gates.
* Minimize the resulting expressions.

---

### 8. Excess-3 Code Detection Circuit

Designed a detector circuit for valid Excess-3 code combinations.

Valid Excess-3 representations:

0 → 0011

1 → 0100

2 → 0101

3 → 0110

4 → 0111

5 → 1000

6 → 1001

7 → 1010

8 → 1011

9 → 1100

Unused states were treated as Don't Care conditions and simplified using Karnaugh Maps.

---

### 9. Gray Code Generator Using Logic Gates

Implemented Gray Code generation using XOR gates.

Key Relations:

G₃ = B₃

G₂ = B₃ ⊕ B₂

G₁ = B₂ ⊕ B₁

G₀ = B₁ ⊕ B₀

---

### Key Learning Outcomes from Practice

* Implemented Boolean functions using Multiplexers.
* Realized logic functions using Decoders.
* Practiced Binary, BCD, Excess-3 and Gray Code conversions.
* Designed BCD to Excess-3 converters using decoder-based implementation.
* Learned Excess-3 code detection using K-Maps and logic simplification.
* Applied Shannon Expansion for Multiplexer-based design.
* Reinforced MSI circuit concepts through practical examples.
