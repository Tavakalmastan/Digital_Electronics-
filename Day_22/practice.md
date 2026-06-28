# Day 22 – Practice Session

## Objective

Today's practice session focused on strengthening the concepts learned in sequential circuits through problem-solving. The practice included designing counters, analyzing frequency division circuits, studying flip-flop behavior, converting Binary to Gray code, and deriving logic equations using excitation tables and Karnaugh Maps.

---

## 1. Mod-6 Counter using JK Flip-Flops

A 3-bit ripple counter was modified to work as a Mod-6 counter.

### Key Points

- All JK flip-flops have J = K = 1.
- When J = K = 1, a JK flip-flop behaves like a T flip-flop.
- A normal 3-bit counter counts from 0 to 7.
- To obtain Mod-6 operation, the counter is asynchronously reset when it reaches decimal 6 (110).

### Counting Sequence

```
000 → 001 → 010 → 011 → 100 → 101
                     ↓
                  Reset
                     ↓
                   000
```

Hence,

- Number of states = 6
- Modulus = 6

---

## 2. Frequency Division using Counters

The output frequency of a counter decreases after every flip-flop stage.

Example:

```
Input Clock = 100 kHz

Stage 1 Output = 50 kHz
Stage 2 Output = 25 kHz
Stage 3 Output = 12.5 kHz
```

Each stage divides the incoming frequency by 2.

General Formula:

```
fout = fin / 2ⁿ
```

where,

- fin = Input frequency
- fout = Output frequency
- n = Number of flip-flops

---

## 3. Frequency Divider Techniques

Frequency division can be implemented using:

- D Flip-Flops
- T Flip-Flops
- Ripple Counters
- Ring Counters
- Johnson Counters

Each method reduces the input frequency while maintaining predictable output timing.

---

## 4. Frequency Division using D Flip-Flop

A D flip-flop can be configured as a frequency divider by connecting

```
D = Q̅
```

Working:

- The output toggles at every clock pulse.
- Output frequency becomes half of the input frequency.

Mathematically,

```
Toutput = 2 × Tclock

foutput = fin / 2
```

This also produces a 50% duty cycle.

---

## 5. Frequency Division using T Flip-Flop

For a T flip-flop,

```
T = 1
```

The output toggles on every active clock edge.

Therefore,

```
Output Frequency = Input Frequency / 2

Toutput = 2 × Tclock
```

Again,

```
foutput = fin / 2
```

This is one of the simplest methods of dividing clock frequency.

---

## 6. Binary to Gray Code Conversion

Binary numbers were converted into Gray code.

Example:

| Binary | Gray |
|--------|------|
|000|000|
|001|001|
|010|011|
|011|010|
|100|110|

### Observation

Gray code changes only one bit between two consecutive states, making it useful in encoders, counters, and systems where transition errors must be minimized.

---

## 7. Excitation Table of T Flip-Flop

The excitation table determines the required T input for a desired state transition.

| Present State | Next State | T |
|---------------|------------|---|
|0|0|0|
|0|1|1|
|1|0|1|
|1|1|0|

Rule:

- T = 0 → No Toggle
- T = 1 → Toggle

This table is widely used while designing sequential circuits.

---

## 8. Sequence Generator Design

A sequence generator producing

```
0 → 1 → 2 → 4 → 7 → 0
```

was analyzed.

Design Procedure:

1. Draw the state diagram.
2. Prepare the state table.
3. Determine the next state for every present state.
4. Fill the excitation table.
5. Find flip-flop input equations.
6. Simplify the equations using Karnaugh Maps.
7. Implement the logic circuit.

One simplified Boolean equation obtained during practice was

```
D₂ = Q̅₂Q̅₁ + Q₁Q̅₀
```

Similar equations can be derived for D₁ and D₀.

---

## 9. Johnson Counter Revision

The Johnson counter (Twisted Ring Counter) was revised.

### Important Points

- Constructed using D Flip-Flops.
- The complement of the last flip-flop output is connected to the input of the first flip-flop.
- For N flip-flops, the counter generates 2N unique states.

Example:

```
4 Flip-Flops

↓

8 States
```

Applications include

- Sequence generators
- Frequency dividers
- Digital timing circuits
- Finite State Machines

---

# Key Concepts Practiced

- Designing a Mod-6 Counter using JK Flip-Flops
- JK Flip-Flop operating as a T Flip-Flop
- Frequency Division using D Flip-Flops
- Frequency Division using T Flip-Flops
- Counter-based Frequency Division
- Binary to Gray Code Conversion
- T Flip-Flop Excitation Table
- Johnson Counter Working Principle
- Sequence Generator Design
- State Table Construction
- Next-State Analysis
- Boolean Equation Derivation
- Karnaugh Map Simplification
