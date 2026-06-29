# Day 23 – Learning Session

## Objective

Today's learning focused on advanced sequential circuit concepts, including clock generation, frequency division using Mod-N counters with 50% duty cycle, edge detector circuits, transition gates, and practical applications of counters in digital systems. The session also covered how to improve duty cycle using additional hardware and the difference between combinational and sequential edge detectors.

---

# 1. Clock Generation in Digital Systems

A crystal oscillator generates a stable clock signal which is distributed to different modules inside an SoC (System-on-Chip).

Example:

- Crystal Oscillator = 10 MHz
- CPU = 5 MHz
- Memory = 2.5 MHz
- USB = 5 MHz
- Display Controller = 3.33 MHz
- I/O = 1 MHz

Clock dividers are used to generate different operating frequencies from a single clock source.

---

# 2. Clock Timing Parameters

Important timing parameters discussed:

- Clock Pulse Width (PW)
- Clock Period
- Setup Time (Tsetup)
- Hold Time (Thold)
- Propagation Delay

These parameters determine the reliable operation of synchronous digital circuits.

---

# 3. Frequency Division using Counters

For an N-bit binary counter,

```
Output Frequency = Input Frequency / 2ⁿ
```

Examples:

| Flip-Flops | Counter | Output Frequency |
|------------|----------|-----------------|
|1|Mod-2|f/2|
|2|Mod-4|f/4|
|3|Mod-8|f/8|
|4|Mod-16|f/16|

Power-of-two counters naturally generate a 50% duty cycle.

---

# 4. Duty Cycle in Counters

Duty Cycle is calculated as

```
Duty Cycle = TON / (TON + TOFF)
```

Observations:

- Mod-2, Mod-4, Mod-8, Mod-16 counters provide nearly 50% duty cycle.
- Odd Mod counters (Mod-3, Mod-5, Mod-7...) do not naturally generate a 50% duty cycle.
- Additional hardware is required to obtain a symmetric output waveform.

---

# 5. Mod-3 Counter Design

A synchronous Mod-3 counter was designed.

### Counting Sequence

```
00 → 01 → 10 → 00
```

Steps followed:

- Draw State Diagram
- Prepare Present State and Next State Table
- Determine Flip-Flop Inputs
- Simplify using Karnaugh Maps
- Implement the Logic Circuit

Derived equations:

```
DB = QA
DA = Q̅B Q̅A
```

Timing diagrams were used to verify the operation.

---

# 6. Generating 50% Duty Cycle for Mod-3 Counter

A normal Mod-3 counter produces a duty cycle of

```
1/3 = 33.33%
```

To obtain a 50% duty cycle,

- An additional D Flip-Flop is connected to the output.
- Extra combinational logic combines the counter output and delayed output.
- The resulting waveform becomes nearly symmetric.

---

# 7. Mod-5 Counter Design

A synchronous Mod-5 counter was designed.

### Counting Sequence

```
000
001
010
011
100
000
```

Design Procedure:

- State Diagram
- Transition Table
- Flip-Flop Excitation Table
- Karnaugh Map Simplification
- Logic Circuit Implementation

Derived equations:

```
DC = QB QA
DB = Q̅C (QB ⊕ QA)
DA = Q̅C Q̅A
```

---

# 8. 50% Duty Cycle for Mod-5 Counter

Since a Mod-5 counter naturally produces an asymmetric waveform,

an additional D Flip-Flop and OR gate were introduced to generate a nearly 50% duty cycle output.

This method is useful for clock generation applications.

---

# 9. Mod-6 Counter with 50% Duty Cycle

The Mod-6 counter timing diagram was analyzed.

Observations:

- QA has approximately 50% duty cycle.
- QB and QC have different ON/OFF durations.
- Additional hardware was added to produce a clean 50% output waveform.

---

# 10. Edge Detector Circuits

Three types of edge detectors were studied.

### Positive Edge Detector

Produces a pulse only during the rising edge.

Applications:

- Clock triggering
- Event detection
- Synchronization

---

### Negative Edge Detector

Produces a pulse only during the falling edge.

Used in circuits triggered by negative clock edges.

---

### Either Edge Detector

Produces a pulse on both rising and falling edges.

Useful for detecting any transition of a signal.

---

# 11. Edge Detector Implementation

Two implementation methods were discussed.

### Using Combinational Logic

- Delay the input signal.
- Compare the original signal with its delayed version.
- XOR or logic gates generate a short pulse.

Advantages:

- Simple
- Fast

---

### Using Sequential Logic

- Delay is created using a D Flip-Flop.
- Current and previous values are compared.
- Generates clean edge pulses synchronized with the clock.

Advantages:

- Reliable
- Synchronous operation
- Better noise immunity

---

# 12. Timing Diagram Analysis

Timing diagrams were analyzed for:

- Positive Edge Detection
- Negative Edge Detection
- Either Edge Detection

The diagrams showed how output pulses are generated only during signal transitions.

---

# 13. Transition Gate (Transmission Gate)

A transmission gate acts as a bidirectional switch.

Construction:

- One NMOS
- One PMOS
- Complementary control signals

Operation:

| Enable | Input | Output |
|---------|-------|--------|
|0|X|High Impedance (Z)|
|1|0|0|
|1|1|1|

Applications:

- Multiplexers
- Bus Switching
- Sample-and-Hold Circuits
- Data Routing

---

# Key Concepts Learned

- Clock Generation using Crystal Oscillator
- Clock Timing Parameters
- Frequency Division using Mod-N Counters
- Duty Cycle Analysis
- Mod-3 Counter Design
- Mod-5 Counter Design
- Mod-6 Counter Timing Analysis
- 50% Duty Cycle Generation
- State Diagram and Transition Table Design
- Karnaugh Map Based Logic Simplification
- Positive Edge Detector
- Negative Edge Detector
- Either Edge Detector
- Combinational Edge Detector
- Sequential Edge Detector
- Timing Diagram Analysis
- Transmission Gate Operation and Applications
