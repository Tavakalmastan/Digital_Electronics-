# Day 19/90 - Practice Session (Hazards, Decoder & MUX Implementations)

## Overview

Today's practice session focused on implementing Boolean functions using Decoders and Multiplexers, along with studying Hazards in Digital Circuits. I learned the different types of hazards, their causes, timing behavior, and methods to eliminate them. I also practiced solving decoder-based logic implementation problems and analyzed waveform behavior caused by propagation delays.

---

# 1. Boolean Function using Decoder

## 2:4 Decoder

A 2:4 Decoder converts 2 input lines into 4 output lines.

Inputs:
- C
- D

Outputs:
- C̅D̅
- C̅D
- CD̅
- CD

---

## Implementing 4-variable Function using Two 2:4 Decoders

Variables:
- A
- B
- C
- D

Procedure:

- First decoder is enabled for A̅B̅.
- Second decoder is enabled for AB.
- Required output lines are ORed together.
- Final OR output gives the desired Boolean function.

---

# 2. Decoder Output Verification

For every minterm:

- Convert ABCD into binary.
- Select the corresponding decoder output.
- OR the required outputs.
- Verify the result using NOR implementation if required.

---

# 3. Hazards

## Definition

A Hazard is an unwanted switching condition that occurs because of unequal propagation delays in a digital circuit.

A temporary unwanted output change is called a **Glitch**.

---

# 4. Types of Hazards

Hazards are classified into:

- Static Hazard
- Dynamic Hazard

---

## Static Hazard

A hazard that disturbs the expected constant output of a circuit.

### Static-0 Hazard

Expected Output:

0

Actual Output:

0 → 1 → 0

The output temporarily becomes HIGH due to propagation delay.

Example:

A · A̅ = 0

---

### Static-1 Hazard

Expected Output:

1

Actual Output:

1 → 0 → 1

The output temporarily becomes LOW because of propagation delay.

Example:

A + A̅ = 1

---

# 5. Causes of Static Hazards

- Different propagation delays of logic gates
- Improper K-map grouping
- Missing redundant terms
- Implementation using non-consecutive literals

---

# 6. Static Hazard Timing Analysis

During input transitions:

- One path reaches the output earlier.
- Another path is delayed.
- Temporary incorrect output (glitch) appears.
- Output settles after propagation delay.

Waveforms demonstrate this short-duration glitch.

---

# 7. Dynamic Hazard

A Dynamic Hazard occurs when the output changes multiple times before reaching its final value.

Example:

Instead of:

0 → 1

The output becomes:

0 → 1 → 0 → 1

---

## Causes of Dynamic Hazards

- Improper power supply
- Sudden interruption of power
- Improper circuit connections
- Setup time violations
- Hold time violations

---

# 8. Elimination of Hazards

## Method 1

Balance propagation delay by adding suitable gate delays.

---

## Method 2

Proper K-map grouping.

Include redundant groups to eliminate glitches.

Example:

Original Expression

A̅C + AB

Hazard-free Expression

A̅C + AB + BC

(The redundant term removes the static hazard.)

---

## Method 3

Use Flip-Flops

Register the intermediate output using a Flip-Flop before the next logic stage to eliminate glitches caused by combinational delays.

---

# 9. Timing Diagram Analysis

Observed timing waveforms for:

- Clock
- Inputs (A, B, C)
- Intermediate Output (Y)
- Final Output (Z)

The waveforms illustrate:

- Gate propagation delay
- Static hazards
- Dynamic hazards
- Corrected output after hazard elimination

---

# Key Takeaways

- Practiced Boolean function implementation using 2:4 Decoders.
- Learned decoder output selection and logic realization.
- Studied Hazards and temporary glitches in digital circuits.
- Understood Static-0 and Static-1 Hazards with timing behavior.
- Learned Dynamic Hazards and their causes.
- Practiced hazard elimination using redundant K-map grouping and Flip-Flops.
- Analyzed timing diagrams showing propagation delay and glitch behavior.
