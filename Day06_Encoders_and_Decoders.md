# Day 06 – Encoders & Decoders (Deep Dive)

## 1. What is a Decoder?
A Decoder is a combinational circuit that converts an n-bit binary input into **2^n distinct output lines**.
Only one output is active for any valid input combination.

Examples:
- 2-to-4 Decoder
- 3-to-8 Decoder

Key points:
- Number of outputs = 2^n  
- Often includes an Enable (EN) signal  
- Used for selection and addressing

---

## 2. 2-to-4 Decoder

Definition:
Takes 2 input bits (A, B) and activates one of four outputs (Y0–Y3).

Truth Table:

A B | Y0 Y1 Y2 Y3  
0 0 | 1  0  0  0  
0 1 | 0  1  0  0  
1 0 | 0  0  1  0  
1 1 | 0  0  0  1  

Boolean Expressions:
Y0 = A'B'  
Y1 = A'B  
Y2 = AB'  
Y3 = AB  

Applications:
- Memory address decoding  
- Chip select logic  
- Instruction decoding

---

## 3. What is an Encoder?
An Encoder is the reverse of a decoder.
It converts **one active input line** into an n-bit binary code.

Examples:
- 4-to-2 Encoder  
- 8-to-3 Encoder  

Key limitation:
- Assumes only one input is active at a time

---

## 4. 4-to-2 Encoder

Definition:
Converts one of four active inputs (D0–D3) into a 2-bit output (A, B).

Truth Table (Assuming one-hot input):

D3 D2 D1 D0 | A B  
0  0  0  1  | 0 0  
0  0  1  0  | 0 1  
0  1  0  0  | 1 0  
1  0  0  0  | 1 1  

Boolean Expressions:
A = D2 + D3  
B = D1 + D3  

---

## 5. Priority Encoder

Problem with Normal Encoder:
If multiple inputs are active, output becomes ambiguous.

Priority Encoder Solution:
- Assigns priority to inputs (e.g., D3 > D2 > D1 > D0)
- Highest-priority active input is encoded

Features:
- Valid output signal (V) indicates at least one input is active  
- Widely used in interrupt controllers and arbiters

---

## 6. Cascading & Expansion

- Larger decoders can be built using smaller decoders  
  Example: 3-to-8 using two 2-to-4 decoders + enable logic  
- Encoders can also be cascaded with priority handling

---

## 7. Using Decoder to Implement Logic Functions
A decoder can be used to implement Boolean functions by:
- Generating all minterms  
- OR-ing selected minterms to form required logic

Example:
To implement F(A, B) = Σm(1, 3)
- Use 2-to-4 decoder to generate m1 and m3  
- OR Y1 and Y3 to get F

---

## 8. Design & Verification Perspective

Design:
- Decoders used for address decoding, chip select, instruction decode  
- Priority encoders used for arbitration (interrupts, bus requests)

Verification:
- Directed tests for each input combination  
- Corner case: multiple active inputs (priority encoder behavior)  
- Assertions: one-hot output for decoders  
- Random tests for robustness

---

## 9. Interview & GATE Points
- Decoder outputs = 2^n  
- Encoder is reverse of decoder  
- Priority encoder resolves multiple active inputs  
- Decoders generate minterms  
- Used in memory addressing and instruction decoding  

---

## 10. Summary
Encoders and decoders are essential combinational circuits used for encoding, decoding, selection, and addressing in digital systems.
Understanding their behavior, limitations, and practical usage is important for digital design and VLSI roles.
