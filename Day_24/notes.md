# Day – Learning Session

## Objective

Today's session focused on **Finite State Machines (FSMs)** and their practical implementation in digital systems. The topics included the classification of FSMs, Mealy and Moore models, designing an Up/Down Mod-5 counter using a state machine, and designing sequence detectors for both non-overlapping and overlapping sequences using the Mealy model. The complete design flow from state diagram to logic implementation was also covered.

---

# 1. Finite State Machine (FSM)

A **Finite State Machine (FSM)** is a sequential logic system whose output depends on the current state and, in some cases, the current input. It changes from one state to another based on the input and clock signal.

To implement an FSM:

- If the number of states is **N**, the required number of flip-flops is

```
n = ⌈log₂(N)⌉
```

Examples:

- 3 states → 2 Flip-Flops
- 8 states → 3 Flip-Flops
- 100 states → 7 Flip-Flops

FSMs are widely used in controllers, communication systems, digital protocols, and embedded applications.

---

# 2. Types of Finite State Machines

Finite State Machines are classified into two categories.

## a) Implicit State Machine

In an implicit state machine, the state is not explicitly defined by the designer. The hardware naturally moves through states.

Examples:

- Latches
- Flip-Flops
- Binary Counters
- Shift Registers

---

## b) Explicit State Machine

In an explicit state machine, every state and state transition is designed by the user.

Examples:

- Traffic Light Controller
- Washing Machine Controller
- Communication Protocol Controller
- Elevator Controller
- User Interface Controller
- Robotics Control System

---

# 3. Mealy and Moore Models

## Mealy Model

Characteristics:

- Output depends on:
  - Present State (PS)
  - Present Input (X)

```
Output = f(Present State, Input)
```

Advantages:

- Faster response
- Requires fewer states
- Output changes immediately with input

---

## Moore Model

Characteristics:

- Output depends only on the Present State.

```
Output = f(Present State)
```

Advantages:

- Stable outputs
- Easier to design
- Better noise immunity

---

# 4. Design of Up/Down Mod-5 Counter using FSM

An Up/Down counter was designed using a State Machine.

Control Input:

```
M = 0 → Up Counter
M = 1 → Down Counter
```

State Sequence

### Up Counting

```
000 → 001 → 010 → 011 → 100 → 000
```

### Down Counting

```
100 → 011 → 010 → 001 → 000 → 100
```

Design Steps:

- Draw the State Diagram
- Prepare the Transition Table
- Determine Next States
- Generate Flip-Flop Input Table
- Simplify equations using Karnaugh Maps
- Implement the logic circuit

Derived Logic Equations:

```
DC = MQ̅CQ̅BQ̅A + M̅QBQA

DB = MQ̅C + M̅Q̅CQB + M̅Q̅CQA

DA = MQ̅C + Q̅BQA + M̅Q̅CQ̅B
```

The complete logic implementation was verified using D Flip-Flops and combinational logic.

---

# 5. Sequence Detector

A Sequence Detector is a digital circuit that continuously monitors a serial input stream and produces an output whenever a predefined binary pattern is detected.

Applications:

- Communication Systems
- Error Detection
- Pattern Recognition
- Protocol Detection
- Digital Signal Processing

---

# 6. Non-Overlapping Sequence Detector

A **1101** sequence detector was designed using the Mealy Model.

Target Pattern:

```
1101
```

Characteristics:

- Once the sequence is detected,
- Detection starts again from the initial state.
- Previously detected bits are not reused.

Example

```
Input:

1101001101...

Output:

0001000010...
```

---

# 7. Designing a Mealy Sequence Detector

Design Procedure:

### Step 1

Identify the required sequence.

Example:

```
1101
```

### Step 2

Determine the number of required states.

Since four bits are being tracked,

```
Number of States = 4
```

Required Flip-Flops:

```
n = log₂4 = 2 Flip-Flops
```

---

### Step 3

Draw the State Diagram.

Each state represents the number of correctly matched bits.

Example:

- S0 → No bits matched
- S1 → "1"
- S2 → "11"
- S3 → "110"

When the final bit is received,

```
Output = 1
```

otherwise,

```
Output = 0
```

---

### Step 4

Assign Binary Codes to States.

Example:

```
S0 = 00
S1 = 01
S2 = 10
S3 = 11
```

---

### Step 5

Prepare the Transition Table.

The table contains:

- Present State
- Input
- Next State
- Flip-Flop Inputs
- Output

---

### Step 6

Simplify the Flip-Flop equations using Karnaugh Maps.

Derived equations:

```
DA = Q̅BX + QBQ̅AX̅

DB = Q̅BQ̅A + Q̅BX

Output:

Z = QBQAX
```

---

### Step 7

Implement the Logic Circuit.

The circuit consists of:

- Two D Flip-Flops
- AND Gates
- OR Gates
- Inverters
- Clock Input

---

# 8. Overlapping vs Non-Overlapping Detection

## Non-Overlapping Detection

After detecting the pattern,

- The machine returns to the initial state.
- Previously matched bits are discarded.

Example

```
Input:

1101101

Detected:

1101
```

The next detection starts from the beginning.

---

## Overlapping Detection

Previously matched bits are reused.

Example

```
Input:

1101101

Detected:

1101
   1101
```

This improves efficiency because common bits are not discarded.

---

# 9. State Diagram Analysis

During the design process, state diagrams were created for:

- Up Counter
- Down Counter
- Mealy Sequence Detector
- Non-Overlapping Detector
- Overlapping Detector

Each transition was labelled with

```
Input / Output
```

which clearly represents the behaviour of the Mealy Machine.

---

# 10. Karnaugh Map Simplification

K-Maps were used to minimize:

- DA
- DB
- Output Logic

This reduced the total number of logic gates required for implementation.

---

# Key Concepts Learned

- Finite State Machine (FSM)
- Implicit and Explicit State Machines
- Mealy and Moore FSM Models
- Up/Down Mod-5 Counter Design using FSM
- State Diagrams, Transition Tables and State Assignment
- Sequence Detector Design using Mealy Model
- Non-Overlapping and Overlapping Sequence Detection
- Karnaugh Map Simplification and Logic Circuit Implementation
