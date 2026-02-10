# Day 05 – Multiplexers & Demultiplexers (Deep Dive)

## 1. What is a Multiplexer (MUX)?
A Multiplexer is a combinational circuit that selects **one of many input lines** and forwards it to a **single output line** based on the select inputs.

MUX is also called a **data selector**.

Examples:
- 2:1 MUX (2 inputs, 1 output)
- 4:1 MUX
- 8:1 MUX

General rule:
- Number of select lines = log2(Number of inputs)

---

## 2. 2:1 Multiplexer

Definition:
Selects one of two inputs (I0 or I1) based on select line S.

Truth Table:

S | Y  
0 | I0  
1 | I1  

Boolean Expression:
Y = S'·I0 + S·I1  

Implementation:
- 2 AND gates
- 1 OR gate
- 1 NOT gate

Applications:
- Data selection
- Conditional routing of signals

---

## 3. 4:1 Multiplexer

Definition:
Selects one of four inputs (I0, I1, I2, I3) using two select lines (S1, S0).

Truth Table (Functional Description):

S1 S0 | Y  
0  0  | I0  
0  1  | I1  
1  0  | I2  
1  1  | I3  

Concept:
- Can be built using three 2:1 MUXes
- Widely used in datapaths and control logic

---

## 4. What is a Demultiplexer (DEMUX)?
A Demultiplexer performs the reverse operation of a multiplexer.
It takes **one input** and routes it to **one of many outputs** based on select lines.

Also called a **data distributor**.

Examples:
- 1:2 DEMUX
- 1:4 DEMUX
- 1:8 DEMUX

---

## 5. 1:2 Demultiplexer

Definition:
Routes input D to one of two outputs based on select S.

Truth Table:

S | Y0 Y1  
0 | D  0  
1 | 0  D  

Boolean Expressions:
Y0 = S'·D  
Y1 = S·D  

Applications:
- Data routing
- Memory addressing (basic concept)

---

## 6. 1:4 Demultiplexer

Definition:
Routes input D to one of four outputs using two select lines (S1, S0).

Functional Description:

S1 S0 | Active Output  
0  0  | Y0  
0  1  | Y1  
1  0  | Y2  
1  1  | Y3  

---

## 7. Using MUX to Implement Logic Functions
A MUX can be used to implement any Boolean function by:
- Connecting inputs to 0, 1, or variables
- Using select lines as variables

Example:
Implement F(A, B) using a 2:1 MUX:
- Use A as select
- Set I0 = B
- Set I1 = B'

This realizes F = A ⊕ B

---

## 8. Cascading & Expansion
- Larger MUXes can be built using smaller MUXes  
- Example: 8:1 MUX using two 4:1 MUX + one 2:1 MUX  
- Similarly, larger DEMUXes can be constructed hierarchically

---

## 9. SOP/POS & K-Map Optimization
- MUX select logic and data paths can be optimized using K-Maps  
- Reduced logic improves:
  - Area  
  - Power  
  - Timing  

---
---

## 10. Implementing All Basic Logic Gates Using MUX

Using a 2:1 MUX, we can implement basic logic functions by choosing:
- Select line as one variable
- Inputs as 0, 1, or the other variable (or its complement)

Let select = A, input = B

1) AND Gate: F = A · B  
Set:
I0 = 0  
I1 = B  
Result: F = A·B  

2) OR Gate: F = A + B  
Set:
I0 = B  
I1 = 1  
Result: F = A + B  

3) NAND Gate: F = (A · B)'  
Set:
I0 = 1  
I1 = B'  
Result: F = (A·B)'  

4) NOR Gate: F = (A + B)'  
Set:
I0 = B'  
I1 = 0  
Result: F = (A + B)'  

5) XOR Gate: F = A ⊕ B  
Set:
I0 = B  
I1 = B'  
Result: F = A ⊕ B  

6) XNOR Gate: F = (A ⊕ B)'  
Set:
I0 = B'  
I1 = B  
Result: F = (A ⊕ B)'  

7) NOT Gate: F = A'  
Using 2:1 MUX with:
Select = A  
I0 = 1  
I1 = 0  
Result: F = A'

---

## 11. Implementing All Basic Logic Gates Using DEMUX

Using a 1:2 DEMUX:
- Input = 1 (logic HIGH)
- Select line = A
- Outputs = Y0, Y1

Y0 = A'  
Y1 = A  

So DEMUX can generate:
- NOT: A' (from Y0)
- Direct: A (from Y1)

Now combine DEMUX outputs with OR/AND gates to realize logic functions:

1) AND Gate: A · B  
- Use two DEMUX blocks for A and B  
- AND Y1 outputs of both DEMUXes  

2) OR Gate: A + B  
- OR Y1 outputs of both DEMUXes  

3) NAND Gate: (A · B)'  
- AND outputs then invert  

4) NOR Gate: (A + B)'  
- OR outputs then invert  

5) XOR Gate: A ⊕ B  
- Combine A'B + AB' using DEMUX outputs  

6) XNOR Gate: (A ⊕ B)'  
- Invert XOR result  

Note:
- DEMUX alone cannot directly implement all gates  
- DEMUX is mainly used for signal routing and decoding  
- Combining DEMUX with basic gates enables full logic realization  

---

## 12. Design & Interview Notes (Advanced)
- MUX can implement any Boolean function directly  
- MUX-based logic is common in datapaths and ALU control  
- DEMUX is primarily used for distribution and decoding  
- In VLSI, MUX-based implementations are preferred for structured logic  
- Understanding MUX/DEMUX implementations helps in logic synthesis and RTL optimization

## 13. Design & Verification Perspective

Design:
- MUXes are heavily used in datapaths, ALUs, and control logic  
- Excessive MUX levels increase delay and area  

Verification:
- Directed tests: check each select combination  
- Corner cases: rapid select toggling  
- Random tests: random select/data patterns  
- Assertions: one-hot output for DEMUX  
- Checkers: ensure correct input reaches output

---

## 14. Interview & GATE Points
- MUX selects one of many inputs to one output  
- DEMUX routes one input to one of many outputs  
- Number of select lines = log2(inputs)  
- MUX can implement any Boolean function  
- Large MUXes can be built using smaller ones  

---

## 15. Summary
Multiplexers and Demultiplexers are essential building blocks in digital systems.
They enable flexible data routing and logic implementation in datapaths and control units.
Understanding their logic, scalability, and verification considerations is important for digital design and VLSI roles.
