# Day 07 – Flip-Flops (SR, JK, D, T) – Deep Dive

## 1. What are Flip-Flops?
Flip-flops are **sequential circuits** that store **1-bit of data**.
Unlike combinational circuits, their output depends on:
- Current inputs
- Previous state (memory)
- Clock signal

Flip-flops are edge-triggered and form the basis of:
- Registers
- Counters
- State machines
- Memory elements

---

## 2. Latches vs Flip-Flops
- Latches are **level-sensitive** (transparent when enable is active)  
- Flip-flops are **edge-triggered** (triggered on rising/falling edge of clock)  
- Flip-flops are preferred in synchronous digital systems

---

## 3. SR Flip-Flop

Definition:
- Inputs: S (Set), R (Reset), Clock  
- Outputs: Q, Q'

Truth Table (Clocked SR FF):

S R | Q(next)  
0 0 | Q(prev)  
0 1 | 0  
1 0 | 1  
1 1 | Invalid / Forbidden  

Key Point:
- S = R = 1 leads to an invalid state (for basic SR FF)

Applications:
- Simple memory storage
- Set/Reset logic

---

## 4. JK Flip-Flop

Definition:
- Inputs: J, K, Clock  
- Outputs: Q, Q'

Truth Table:

J K | Q(next)  
0 0 | Q(prev)  
0 1 | 0  
1 0 | 1  
1 1 | Toggle  

Key Advantage:
- No invalid state  
- J = K = 1 toggles the output  

Applications:
- Counters
- Toggle operations

---

## 5. D Flip-Flop

Definition:
- Input: D (Data), Clock  
- Output: Q

Operation:
- Q(next) = D at the active clock edge

Truth Table:

D | Q(next)  
0 | 0  
1 | 1  

Key Properties:
- Simplest flip-flop  
- Widely used in registers and pipelines  
- Eliminates invalid states

Applications:
- Registers  
- Pipelining  
- Data storage  

---

## 6. T Flip-Flop

Definition:
- Input: T (Toggle), Clock  
- Output: Q

Truth Table:

T | Q(next)  
0 | Q(prev)  
1 | Toggle  

Relation to JK FF:
- T FF can be derived from JK by setting J = K = T  

Applications:
- Counters  
- Frequency division  

---

## 7. Timing Parameters (Important)

- Setup Time: Input must be stable before clock edge  
- Hold Time: Input must be stable after clock edge  
- Propagation Delay: Time taken for Q to change after clock edge  
- Clock Skew: Difference in arrival time of clock at different FFs  

These parameters affect:
- Maximum clock frequency  
- Reliable operation of sequential circuits  

---

## 8. Common Issues in Sequential Logic

- Metastability:
  Occurs when setup/hold times are violated  
- Race conditions:
  Especially in level-sensitive designs  
- Glitches due to asynchronous inputs  

Mitigation:
- Synchronizers  
- Proper timing constraints  
- Edge-triggered FF usage  

---

## 9. Design & Verification Perspective

Design:
- D FFs are preferred in synchronous RTL  
- Reset strategy (sync vs async) must be defined  
- FF choice impacts area and power  

Verification:
- Check reset behavior  
- Test setup/hold violations (CDC checks)  
- Directed tests for toggle and hold conditions  
- Assertions for illegal states (SR FF)  

---

## 10. Interview & GATE Points
- SR FF has invalid state (S = R = 1)  
- JK FF removes invalid state and toggles when J = K = 1  
- D FF captures input at clock edge  
- T FF toggles output  
- Setup/hold time violations cause metastability  
- Flip-flops are basic storage elements  

---

## 11. Summary
Flip-flops are the fundamental storage elements in synchronous digital systems.
Understanding different FF types, their timing constraints, and verification aspects is essential for digital design and VLSI roles.
