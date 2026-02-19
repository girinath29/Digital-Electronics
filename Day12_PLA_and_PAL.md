# Day 12 – PLA & PAL (Programmable Logic Devices) 

## 1. What are Programmable Logic Devices (PLDs)?
Programmable Logic Devices are digital ICs that can be programmed to implement custom logic functions.
They provide flexibility compared to fixed-function logic.

Examples:
- PLA (Programmable Logic Array)
- PAL (Programmable Array Logic)
- CPLD, FPGA (advanced PLDs)

---

## 2. PLA (Programmable Logic Array)

Definition:
A PLA consists of:
- Programmable AND plane  
- Programmable OR plane  

This allows implementation of **any Sum of Products (SOP)** Boolean function.

Characteristics:
- Highly flexible  
- Can implement multiple outputs with shared product terms  
- More complex and slightly slower than PAL  
- More area and power compared to PAL  

Applications:
- Custom logic functions  
- Control logic  
- Prototyping digital logic  

---

## 3. PAL (Programmable Array Logic)

Definition:
A PAL consists of:
- Programmable AND plane  
- Fixed OR plane  

This restricts flexibility but improves:
- Speed  
- Area  
- Power  

Characteristics:
- Faster than PLA  
- Limited number of product terms per output  
- Simpler structure  

Applications:
- Glue logic  
- Simple control logic  
- Cost-sensitive designs  

---

## 4. PLA vs PAL (Comparison)

Flexibility:
- PLA: High (AND + OR programmable)  
- PAL: Moderate (only AND programmable)  

Speed:
- PLA: Slower  
- PAL: Faster  

Area & Power:
- PLA: Higher  
- PAL: Lower  

Design Complexity:
- PLA: More complex  
- PAL: Simpler  

---

## 5. Programming & Implementation (Concept)
- Logic functions are programmed using fuse/EEPROM technology  
- Truth tables or Boolean equations define the logic  
- Development tools generate programming data for PLDs  

---

## 6. Design & Verification Perspective

Design:
- Useful for implementing small custom logic blocks  
- Faster prototyping compared to full ASIC flow  

Verification:
- Verify all input combinations  
- Check for unused product terms  
- Ensure no unintended logic sharing  

---

## 7. Interview & GATE Points
- PLA has programmable AND and OR planes  
- PAL has programmable AND and fixed OR plane  
- PLA is more flexible; PAL is faster  
- PLDs are precursors to CPLDs and FPGAs  
- Used for custom logic and control logic  

---

## 8. Summary
PLA and PAL are early programmable logic devices used to implement custom combinational logic.
They provide a foundation for understanding modern programmable devices like CPLDs and FPGAs.
