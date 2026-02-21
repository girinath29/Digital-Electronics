# Day 13 – Number Systems & Codes (Deep Dive)

## 1. Number Systems (Overview)
Digital systems represent and process data using different number systems.

Common number systems:
- Binary (Base-2)
- Decimal (Base-10)
- Octal (Base-8)
- Hexadecimal (Base-16)

Key points:
- Binary is used internally by digital hardware  
- Octal and Hex are compact representations of binary  
- Base = number of symbols used  

---

## 2. Base Conversions

### 2.1 Decimal to Binary
Method:
- Repeated division by 2  
- Read remainders from bottom to top  

Example:
(13)₁₀ = (1101)₂  

---

### 2.2 Binary to Decimal
Method:
- Weighted sum of powers of 2  

Example:
(1011)₂ = 1·2³ + 0·2² + 1·2¹ + 1·2⁰ = (11)₁₀  

---

### 2.3 Binary ↔ Octal / Hex
- Group binary digits in 3s for octal  
- Group binary digits in 4s for hex  

Example:
(110101)₂ = (65)₈  
(11101011)₂ = (EB)₁₆  

---

## 3. Signed Number Representations

### 3.1 Sign-Magnitude
- MSB indicates sign  
- Two representations for zero (+0, -0)  
- Rarely used in practice  

---

### 3.2 1’s Complement
- Negative number formed by bitwise inversion  
- Two representations for zero  
- End-around carry required in addition  

---

### 3.3 2’s Complement (Most Common)
- Negative number = invert bits + 1  
- Single representation for zero  
- Simplifies subtraction as addition  

Range (n bits):
- -2^(n-1) to +2^(n-1) - 1  

---

## 4. Binary Codes

### 4.1 BCD (Binary Coded Decimal)
- Each decimal digit encoded using 4 bits  
- Valid codes: 0000 to 1001  
- Used in digital clocks, calculators  

---

### 4.2 Gray Code
- Adjacent values differ by only one bit  
- Minimizes transition errors  
- Used in encoders, K-Maps  

Binary → Gray:
G = B ⊕ (B >> 1)  

---

### 4.3 Excess-3 Code
- Decimal digit + 3 encoded in binary  
- Self-complementing code  
- Used in some arithmetic circuits  

---

## 5. Error Detection Codes (Basic)

### 5.1 Parity Bit
- Even parity / Odd parity  
- Detects single-bit errors  
- Cannot correct errors  

---

### 5.2 Hamming Code (Concept)
- Can detect and correct single-bit errors  
- Uses redundant parity bits  
- Used in memory systems and communication  

---

## 6. Design & Verification Perspective

Design:
- 2’s complement simplifies ALU design  
- Gray code reduces glitches in encoders  
- BCD used in human-readable displays  

Verification:
- Directed tests for conversion correctness  
- Corner cases: sign extension, overflow  
- Random tests for stress patterns  

---

## 7. Interview & GATE Points
- 2’s complement is most widely used  
- Gray code changes only one bit between adjacent values  
- BCD represents decimal digits with 4 bits  
- Parity detects errors; Hamming can correct single-bit errors  
- Hexadecimal simplifies representation of binary data  

---

## 8. Summary
Number systems and codes form the foundation of data representation in digital systems.
Understanding conversions, signed representations, and coding schemes is essential for digital design, computer architecture, and VLSI roles.
