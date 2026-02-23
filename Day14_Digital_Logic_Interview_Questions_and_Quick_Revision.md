# Day 14 – Digital Logic Interview Questions & Quick Revision (Deep Dive)

## 1. Logic Gates – Quick Revision
- AND: 1 only if all inputs are 1  
- OR: 1 if any input is 1  
- NOT: inverts input  
- NAND/NOR are universal gates  
- XOR = 1 if inputs differ  
- XNOR = 1 if inputs are same  

---

## 2. Boolean Algebra – Key Laws
- Identity: A + 0 = A, A·1 = A  
- Null: A + 1 = 1, A·0 = 0  
- Complement: A + A' = 1, A·A' = 0  
- Idempotent: A + A = A, A·A = A  
- De Morgan’s:
  - (AB)' = A' + B'  
  - (A + B)' = A'B'  

---

## 3. K-Map – Quick Tips
- Adjacent cells differ by one bit (Gray code)  
- Groups must be powers of 2  
- Use wrap-around grouping  
- Use don’t-cares to maximize grouping  
- SOP → group 1s; POS → group 0s  

---

## 4. Combinational Circuits – Key Points
- Half Adder: adds two bits (no carry-in)  
- Full Adder: adds three bits (with carry-in)  
- Ripple Carry Adder: simple but slow  
- Carry Look-Ahead Adder: faster, complex  
- MUX can implement any Boolean function  
- Decoder generates minterms  

---

## 5. Sequential Circuits – Key Points
- Flip-Flops store state (SR, JK, D, T)  
- Registers store multi-bit data  
- Counters sequence through states  
- Synchronous circuits use a global clock  
- Asynchronous circuits are event-driven  

---

## 6. Memory – Quick Facts
- ROM: non-volatile (PROM, EPROM, EEPROM, Flash)  
- RAM: volatile  
- SRAM: fast, no refresh  
- DRAM: dense, requires refresh  
- Address lines determine memory size  

---

## 7. Number Systems & Codes – Quick Facts
- Binary, Octal, Hex used in digital systems  
- 2’s complement for signed numbers  
- Gray code: one-bit change between adjacent values  
- BCD for decimal display  
- Parity for error detection  

---

## 8. Common Interview Questions (With Short Answers)

Q1. Why are NAND and NOR called universal gates?  
A: Any Boolean function can be implemented using only NAND or only NOR.

Q2. Difference between latch and flip-flop?  
A: Latch is level-sensitive; flip-flop is edge-triggered.

Q3. Why is CLA faster than RCA?  
A: CLA computes carries in parallel, reducing propagation delay.

Q4. What is metastability?  
A: Unstable output when sampling async signal near clock edge.

Q5. What is a priority encoder?  
A: Encoder that resolves multiple active inputs by priority.

Q6. Why is 2’s complement preferred?  
A: Single zero representation and easy subtraction using addition.

Q7. What is a Mod-N counter?  
A: Counter that cycles through N states and resets.

Q8. What is CDC?  
A: Clock Domain Crossing – transfer between different clock domains.

---

## 9. Quick Checklist (Before Interviews)
- Revise truth tables  
- Practice K-Maps  
- Understand flip-flop timing (setup/hold)  
- Revise adders and counters  
- Know memory types and differences  
- Be clear on 2’s complement and Gray code  

---

## 10. Summary
This quick revision sheet consolidates core Digital Electronics concepts and common interview questions.
Use this as a final-day refresher before exams or interviews in core ECE, VLSI, and DV roles.
