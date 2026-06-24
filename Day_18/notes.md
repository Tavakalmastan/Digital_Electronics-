# Day 18 - Sequential Logic Circuits, Latches and Flip-Flops

## Overview

Today, I studied Sequential Logic Circuits and Basic Storage Elements. The session covered SR Latches using NOR and NAND gates, characteristic tables, memory state, set, reset and violation conditions, clock signals, gated SR latches, D latches, JK latches, race-around condition and D Flip-Flops. I also learned clock parameters such as period, frequency and duty cycle.

---

## Sequential Logic Circuits

Sequential circuits depend on:

- Present Inputs
- Previous State (Memory)

Unlike combinational circuits, sequential circuits store information.

### Basic Storage Element

- Latch
- Bi-stable Element
- Stores one bit of information

---

## SR Latch using NOR Gates

### Inputs

- S (Set)
- R (Reset)

### Outputs

- Q
- Q̅

### Operations

#### Memory State

S = 0, R = 0

Q(next) = Q(previous)

#### Reset State

S = 0, R = 1

Q = 0

Q̅ = 1

#### Set State

S = 1, R = 0

Q = 1

Q̅ = 0

#### Violation / Forbidden State

S = 1, R = 1

Q = 0

Q̅ = 0

Invalid condition.

### Characteristic Table

| S | R | Q(next) | Q̅(next) |
|---|---|----------|-----------|
| 0 | 0 | Qn | Q̅n |
| 0 | 1 | 0 | 1 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 0 |

### Notes

- Memory State → Previous state retained
- Set State → Q = 1
- Reset State → Q = 0
- Violation State → Invalid/Forbidden state

---

## Unreliable Condition in NOR Latch

When:

S = 1

R = 1

and both inputs return to zero simultaneously,

Possible outputs:

- Q = 0, Q̅ = 1
- Q = 1, Q̅ = 0

Final state depends on gate propagation delay.

Hence called:

- Unreliable State
- Race Condition

---

## SR Latch using NAND Gates

### Inputs

- S̅
- R̅

### Operations

#### Memory State

S̅ = 1, R̅ = 1

Qn retained

#### Set State

S̅ = 0, R̅ = 1

Q = 1

Q̅ = 0

#### Reset State

S̅ = 1, R̅ = 0

Q = 0

Q̅ = 1

#### Violation State

S̅ = 0, R̅ = 0

Q = 1

Q̅ = 1

Invalid state.

### Characteristic Table

| S̅ | R̅ | Q(next) | Q̅(next) |
|----|----|----------|-----------|
| 1 | 1 | Qn | Q̅n |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 0 | 1 |
| 0 | 0 | 1 | 1 |

### Notes

- Active Low Inputs
- First gate becoming faster may determine final state after violation.

---

## Clock Signal

A Clock is a periodic signal that varies with time.

### Parameters

#### Period

T = Ton + Toff

#### Frequency

f = 1/T

#### Duty Cycle

Duty Cycle = Ton / (Ton + Toff)

---

## Clocked SR Latch (Gated SR Latch)

Additional clock signal controls the SR latch.

### Operation

#### CLK = 0

Output remains unchanged.

Memory state.

#### CLK = 1

Latch responds to S and R inputs.

### Characteristic Table

| CLK | S | R | Q(next) | Q̅(next) |
|------|---|---|----------|-----------|
| 0 | X | X | Qn | Q̅n |
| 1 | 0 | 0 | Qn | Q̅n |
| 1 | 0 | 1 | 0 | 1 |
| 1 | 1 | 0 | 1 | 0 |
| 1 | 1 | 1 | Invalid | Invalid |

---

## Clocked Data Latch (D Latch)

### Inputs

- D
- Clock

### Outputs

- Q
- Q̅

### Characteristics

When CLK = 1

Q follows D

When CLK = 0

Previous value stored.

### Characteristic Table

| CLK | D | Q(next) | Q̅(next) |
|------|---|----------|-----------|
| 0 | X | Qn | Q̅n |
| 1 | 0 | 0 | 1 |
| 1 | 1 | 1 | 0 |

### Advantages

- Eliminates invalid state of SR latch.
- Only one data input.

---

## JK Latch / JK Flip-Flop

Improved version of SR latch.

### Inputs

- J
- K
- Clock

### Outputs

- Q
- Q̅

### Characteristic Table

| CLK | J | K | Q(next) |
|------|---|---|----------|
| 0 | X | X | Qn |
| 1 | 0 | 0 | Qn |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 1 |
| 1 | 1 | 1 | Toggle |

---

## Race Around Condition

Occurs in JK Flip-Flop when:

J = 1

K = 1

Clock pulse width is large.

Output toggles repeatedly during the same clock pulse.

### Result

- Unpredictable output
- Multiple transitions

### Solution

- Master Slave JK Flip-Flop
- Edge Triggered Flip-Flop

---

## D Flip-Flop

### Characteristics

- Stores one bit of data.
- Triggered by clock edge.
- Eliminates race-around condition.

### Operation

Q(next) = D

### Applications

- Registers
- Counters
- Shift Registers
- Memory Elements

---

## Key Takeaways

- Studied Sequential Logic Circuits and memory elements.
- Learned NOR and NAND based SR Latches.
- Understood Set, Reset, Memory and Violation states.
- Learned propagation-delay related unreliable conditions.
- Studied Clock signals, frequency, period and duty cycle.
- Implemented Clocked SR Latch and D Latch.
- Learned JK Latch operation and race-around condition.
- Studied D Flip-Flop and its advantages.
- Understood basic storage and synchronization concepts used in digital systems.
