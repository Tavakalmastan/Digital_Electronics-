# Day 21 - Learning Session: Asynchronous and Synchronous Counters

## Overview

Todat, I studied the design and analysis of Asynchronous (Ripple) Counters and Synchronous Counters using JK and D Flip-Flops. The session covered Mod-N counter design, timing diagrams, state tables, transition tables, Karnaugh Map (K-Map) simplification, and logic implementation.

---

# Asynchronous (Ripple) Counter

An asynchronous counter is a sequential circuit in which only the first flip-flop receives the external clock signal. Each subsequent flip-flop is triggered by the output of the previous flip-flop, resulting in propagation delay.

## Design of a Mod-10 Asynchronous Counter

### Given

- Modulus (N) = 10

### Number of Flip-Flops Required

For a Mod-N counter,

```
2ⁿ ≥ N
```

Taking logarithm,

```
n = log₂(N)
```

For N = 10,

```
2⁴ = 16 ≥ 10
```

Therefore,

```
Number of Flip-Flops = 4
```

### Counter Operation

- Four JK Flip-Flops are connected in ripple configuration.
- Each Flip-Flop toggles on the falling edge of the previous Flip-Flop.
- Outputs are:
  - QA (LSB)
  - QB
  - QC
  - QD (MSB)
- Counter resets after reaching decimal 9 to create a Mod-10 sequence.

---

# Timing Diagram of Mod-10 Asynchronous Counter

The output waveforms show:

- QA toggles every clock pulse.
- QB toggles at half the frequency of QA.
- QC toggles at half the frequency of QB.
- QD toggles at half the frequency of QC.

Frequency division:

- QA = fc / 2
- QB = fc / 4
- QC = fc / 8
- QD = fc / 16

Counting sequence:

```
0000 → 0
0001 → 1
0010 → 2
0011 → 3
0100 → 4
0101 → 5
0110 → 6
0111 → 7
1000 → 8
1001 → 9
Reset → 0000
```

---

# Limitations of Asynchronous Counters

1. Functional hazards (Glitches).
2. Propagation delay increases with the number of Flip-Flops.
3. Not suitable for high-speed applications.
4. Delay accumulates through every Flip-Flop.
5. Temporary unwanted states may occur before settling.

For n Flip-Flops,

```
Total Delay = n × tp
```

where

- tp = Propagation delay of each Flip-Flop.

To ensure proper operation,

```
n × tp < Tclock
```

Maximum operating frequency depends on the propagation delay.

---

# Synchronous Counter

A synchronous counter is a sequential circuit in which all Flip-Flops receive the same clock signal simultaneously.

### Advantages

- No ripple delay.
- Higher operating speed.
- Better timing accuracy.
- Suitable for high-frequency digital systems.

---

# Steps to Design a Synchronous Counter

1. Identify the required Flip-Flop type.
2. Determine the number of Flip-Flops required.
3. Draw the Characteristic Table and Excitation Table.
4. Prepare the State Table.
5. Draw the State Diagram.
6. Construct the Transition Table.
7. Determine Flip-Flop input equations using K-Maps.
8. Implement the logic circuit.

---

# Design of Mod-8 Synchronous Counter Using JK Flip-Flops

### Given

```
N = 8
```

Number of Flip-Flops:

```
2³ = 8
```

Hence,

```
n = 3 Flip-Flops
```

Outputs:

- QA (LSB)
- QB
- QC (MSB)

---

# State Table

| Decimal | QC | QB | QA |
|---------:|:--:|:--:|:--:|
| 0 | 0 | 0 | 0 |
| 1 | 0 | 0 | 1 |
| 2 | 0 | 1 | 0 |
| 3 | 0 | 1 | 1 |
| 4 | 1 | 0 | 0 |
| 5 | 1 | 0 | 1 |
| 6 | 1 | 1 | 0 |
| 7 | 1 | 1 | 1 |

---

# State Diagram

State transitions:

```
000 → 001 → 010 → 011 → 100 → 101 → 110 → 111 → 000
```

---

# Transition Table

The transition table maps:

- Present State (PS)
- Next State (NS)
- Required JK inputs

It is used to derive the Flip-Flop excitation equations.

---

# K-Map Simplification

Using Karnaugh Maps, the JK input equations are simplified.

Final equations obtained:

```
JA = 1
KA = 1

JB = QA
KB = QA

JC = QA · QB
KC = QA · QB
```

These equations are implemented using AND gates and direct connections.

---

# Logic Circuit

The Mod-8 synchronous counter consists of:

- Three JK Flip-Flops.
- Common clock connected to all Flip-Flops.
- JA and KA tied HIGH.
- QB toggles when QA = 1.
- QC toggles when QA and QB are both HIGH.

---

# Timing Diagram

Output sequence:

```
QA : Toggle every clock pulse.
QB : Toggle every two clock pulses.
QC : Toggle every four clock pulses.
```

All outputs change simultaneously on the active clock edge because every Flip-Flop shares the same clock.

---

# Design of 3-Bit Gray Synchronous Counter Using D Flip-Flops

The design procedure includes:

1. Draw the Gray code sequence.
2. Prepare the State Table.
3. Draw the State Diagram.
4. Construct the Transition Table.
5. Determine D inputs using Characteristic Tables.
6. Simplify each D input using K-Maps.
7. Implement the logic circuit.

---

# State Diagram

Gray code follows the sequence where only one bit changes between consecutive states.

Example:

```
000 → 001 → 011 → 010 → 110 → 111 → 101 → 100 → 000
```

---

# Transition Table

The transition table contains:

- Present State
- Next State
- Required D inputs

Since,

```
Q(n+1) = D
```

the next-state bits directly determine the D inputs.

---

# K-Map Simplification

Boolean expressions for each D input are obtained by minimizing the K-Maps.

Final expressions:

```
DA = Simplified Boolean expression from K-Map

DB = Simplified Boolean expression from K-Map

DC = Simplified Boolean expression from K-Map
```

These expressions are implemented using combinations of AND, OR and NOT gates.

---

# Logic Implementation

The final Gray counter consists of:

- Three D Flip-Flops.
- Common clock.
- Combinational logic driving DA, DB and DC.
- Outputs follow the Gray code sequence.

---

## Key Concepts Learned

- Asynchronous (Ripple) and Synchronous Counters
- Mod-N, Mod-10, and Mod-8 Counter Design
- Gray Code Counter Design
- State Tables, State Diagrams, and Transition Tables
- JK and D Flip-Flop Based Counter Design
- Characteristic Tables and Excitation Tables
- K-Map Simplification and Boolean Expression Derivation
- Timing Diagrams, Frequency Division, Propagation Delay, and Glitches
