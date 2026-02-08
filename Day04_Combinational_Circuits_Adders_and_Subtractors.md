# Day 04 – Combinational Circuits: Adders & Subtractors (Deep Dive)

## 1. What are Combinational Circuits?
Combinational circuits are digital circuits whose output depends only on the current inputs.
They do not have memory elements and do not depend on past inputs.

Examples:
- Adders
- Subtractors
- Multiplexers
- Encoders / Decoders
- Comparators

Key properties:
- No clock required
- No feedback loops
- Output changes immediately with input (after propagation delay)

---

## 2. Half Adder

Definition:
A Half Adder adds two 1-bit binary numbers and produces:
- Sum (S)
- Carry (C)

Truth Table:

A B | S C  
0 0 | 0 0  
0 1 | 1 0  
1 0 | 1 0  
1 1 | 0 1  

Boolean Expressions:
S = A ⊕ B  
C = A · B  

Logic Implementation:
- XOR gate for Sum
- AND gate for Carry

Applications:
- Basic building block for full adders
- Used in arithmetic units

---

## 3. Full Adder

Definition:
A Full Adder adds three 1-bit inputs:
- A, B
- Carry-in (Cin)

Outputs:
- Sum (S)
- Carry-out (Cout)

Truth Table:

A B Cin | S Cout  
0 0  0  | 0  0  
0 0  1  | 1  0  
0 1  0  | 1  0  
0 1  1  | 0  1  
1 0  0  | 1  0  
1 0  1  | 0  1  
1 1  0  | 0  1  
1 1  1  | 1  1  

Boolean Expressions:
S = A ⊕ B ⊕ Cin  
Cout = AB + BCin + ACin  

Implementation:
- Two Half Adders + OR gate
- Widely used in multi-bit adders

---

## 4. Ripple Carry Adder (RCA)

Definition:
A Ripple Carry Adder is formed by cascading multiple Full Adders.
The carry output of each stage feeds the next stage.

Example:
4-bit RCA = 4 Full Adders connected in series

Characteristics:
- Simple design
- Large propagation delay (carry ripples through stages)
- Delay increases linearly with number of bits

Use:
- Simple processors
- Low-speed arithmetic units

---

## 5. Subtractor Circuits

### 5.1 Half Subtractor

Definition:
Subtracts two 1-bit numbers:
- Inputs: A (minuend), B (subtrahend)
- Outputs: Difference (D), Borrow (B_out)

Truth Table:

A B | D Borrow  
0 0 | 0  0  
0 1 | 1  1  
1 0 | 1  0  
1 1 | 0  0  

Boolean Expressions:
D = A ⊕ B  
Borrow = A' · B  

---

### 5.2 Full Subtractor

Definition:
Subtracts three 1-bit inputs:
- A, B, Borrow-in (Bin)

Outputs:
- Difference (D)
- Borrow-out (Bout)

Boolean Expressions:
D = A ⊕ B ⊕ Bin  
Bout = A'B + (A ⊕ B)'Bin  

---

## 6. Adder-Subtractor (Using 2’s Complement)

Concept:
Subtraction can be implemented using addition:
A - B = A + (2’s complement of B)

Method:
- Invert B using XOR with control signal M
- Add 1 to B using Cin = M
- When M = 0 → Addition
- When M = 1 → Subtraction

Applications:
- ALU (Arithmetic Logic Unit)
- Processors

---

## 7. Carry Look-Ahead Adder (CLA) – Concept

Problem with RCA:
- Slow due to carry propagation delay

CLA Idea:
- Generate (G) and Propagate (P) signals
- Carries are computed in parallel

Benefit:
- Faster addition
- More complex hardware

---

## 8. SOP/POS & K-Map Optimization
- Adder and subtractor logic can be optimized using K-Maps
- Reduced gate count improves:
  - Area
  - Power
  - Timing

---

## 9. Design & Verification Perspective

Design:
- Adders are critical paths in processors and DSPs
- Adder choice impacts performance and power

Verification:
- Directed tests: 0 + 0, max + max, carry boundary cases
- Random tests: random operands
- Corner cases: overflow, underflow
- XOR is often used in checkers/scoreboards

---

## 10. Interview & GATE Points
- Half adder cannot handle carry-in
- Full adder handles carry-in
- RCA delay increases with bit-width
- CLA reduces carry delay using parallel carry computation
- Subtraction can be done using 2’s complement addition
- Adders are part of ALU

---

## 11. Summary
Combinational arithmetic circuits like adders and subtractors form the core of arithmetic logic units in digital systems.
Understanding their logic, performance trade-offs, and verification aspects is essential for digital design and VLSI roles.
