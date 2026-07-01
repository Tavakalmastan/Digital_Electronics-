# Day 25 – Learning Session: Advanced FSM Design & Sequence Detector Implementation

## Overview

Today's session focused on advanced Finite State Machine (FSM) design using both Mealy and Moore models. Multiple sequence detector problems, counter design using FSMs, circuit optimization, state assignment, and FSM implementation using flip-flops were covered. The emphasis was on translating specifications into state diagrams, transition tables, and final logic implementations.

---

## 1. Introduction to State Machines

A Finite State Machine (FSM) is a sequential circuit whose output depends on the present state and the current input.

Two FSM models were discussed:

- **Mealy Machine**
  - Output depends on Present State and Input.
  - Faster response.
  - Generally requires fewer states.

- **Moore Machine**
  - Output depends only on Present State.
  - Outputs are more stable.
  - Usually requires one extra state compared to Mealy.

---

## 2. Pattern (Sequence) Detection

Pattern detection is one of the most common applications of FSMs.

Covered:

- Mealy sequence detector
- Moore sequence detector
- State transition rules
- Output generation
- Overlapping detection
- Non-overlapping detection

---

## 3. MOD-6 Counter using Mealy FSM

Designed a MOD-6 synchronous counter using the Mealy model.

Procedure followed:

- Determined number of states (N = 6)
- Calculated required flip-flops (3 flip-flops)
- Drew the complete state diagram
- Added state transitions for both input conditions
- Generated the FSM representation

---

## 4. MOD-5 Counter with 50% Duty Cycle

Designed a MOD-5 counter capable of generating approximately a 50% duty cycle output using a Mealy FSM.

Covered:

- State sequence
- Output assignment
- State diagram construction
- Output generation for each transition

---

## 5. FSM Design from Given Conditions

Solved FSM problems based on functional specifications.

Examples included:

- Output becomes HIGH when the number of 0's exceeds the number of 1's in a 3-bit input sequence.
- Output remains LOW after detecting two consecutive logic 1's.
- Developed state diagrams and transition paths according to the given conditions.

---

## 6. Moore Machine Design

Designed a complete Moore FSM.

Steps followed:

- State diagram
- State assignment
- Transition table
- Output assignment
- Flip-flop input table
- Final implementation block diagram

---

## 7. Circuit Optimization Problems

Solved optimization-based design questions.

Covered:

- Number of flip-flops required
- Number of states required
- Clock period calculations
- Traffic Light Controller (TLC) implementation
- State reduction concepts

Example:

- Total traffic light duration = 120 seconds
- Clock period = 5 seconds
- Total states required = 24
- Required flip-flops = 5

---

## 8. Mealy Sequence Detector (10110)

Designed an overlapping Mealy sequence detector for detecting the binary pattern **10110**.

Covered:

- State diagram
- Transition paths
- Output generation
- Gate-level implementation

---

## 9. Moore Sequence Detector (1001)

Designed a non-overlapping Moore FSM for detecting the sequence **1001**.

Discussed:

- Number of states required
- State transitions
- Output state
- Comparison with Mealy implementation

---

## 10. FSM Output Analysis

Practiced solving FSM output questions.

Procedure:

1. Start from the initial state.
2. Apply each input bit sequentially.
3. Follow the state transitions.
4. Record the output generated after each input.
5. Count the total number of detections.

---

## 11. FSM Implementation using JK Flip-Flops

Implemented an FSM using JK flip-flops.

Procedure:

- Created Present State and Next State table
- Used JK excitation table
- Derived J and K inputs
- Simplified equations using K-Maps
- Implemented the final sequential circuit

---

## 12. Detection of Three Consecutive 1's

Designed an overlapping sequence detector for detecting **111**.

Covered:

- State diagram
- State transitions
- Overlapping detection
- Mealy implementation

---

## 13. State Diagram from Sequential Circuits

Learned how to derive a state diagram directly from a given sequential circuit.

Steps:

- Identify the flip-flop type.
- Derive the next-state equation.
- Prepare the state table.
- Draw the corresponding state diagram.
- Verify all state transitions.

---

## 14. State Diagram Analysis

Practiced solving state diagram questions involving multiple inputs and outputs.

Covered:

- Present State (PS)
- Input combinations
- Next State (NS)
- Output generation
- Transition table preparation
