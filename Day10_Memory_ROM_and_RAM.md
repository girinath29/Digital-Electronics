# Day 10 – Memory: ROM & RAM (Deep Dive)

## 1. What is Memory?
Memory stores binary information (data/instructions) in digital systems.
It provides read/write access to stored data and is essential for processors, controllers, and embedded systems.

Key points:
- Organized as locations addressed by address lines  
- Accessed using control signals (Read/Write, Enable)  
- Performance measured by access time, latency, bandwidth  

---

## 2. ROM (Read-Only Memory)

Definition:
ROM stores fixed data that does not change during normal operation.

Types of ROM:
- Mask ROM: programmed during fabrication  
- PROM: programmable once  
- EPROM: erasable with UV light  
- EEPROM: electrically erasable  
- Flash Memory: block-wise erase (widely used)

Characteristics:
- Non-volatile (retains data without power)  
- Used for firmware, bootloaders, lookup tables  

---

## 3. RAM (Random Access Memory)

Definition:
RAM stores data that can be read and written during operation.

Types of RAM:
- SRAM (Static RAM):
  - Faster, lower density  
  - No refresh required  
  - Used in caches and registers  
- DRAM (Dynamic RAM):
  - Higher density, lower cost  
  - Requires periodic refresh  
  - Used as main memory  

Characteristics:
- Volatile (data lost on power off)  
- Accessed by address + control signals  

---

## 4. Memory Organization & Addressing

- Memory size = 2^n locations (n = number of address lines)  
- Each location stores a word (e.g., 8-bit, 16-bit)  
- Chip select (CS) enables a specific memory device  
- Read/Write control selects operation  

---

## 5. Timing & Control Signals

Common signals:
- Address bus  
- Data bus  
- Chip Select (CS)  
- Read Enable (RE) / Output Enable (OE)  
- Write Enable (WE)  

Timing aspects:
- Access time  
- Setup and hold times  
- Read/write cycle time  

---

## 6. Memory Interfacing (Concept)

- Larger memories can be built using smaller memory ICs  
- Address decoding selects the target memory chip  
- Used in microprocessors and microcontrollers  

---

## 7. Design & Verification Perspective

Design:
- Memory access often lies on critical path  
- SRAM used for performance-critical storage  
- DRAM used for capacity  

Verification:
- Directed tests: read/write patterns  
- March tests (basic concept)  
- Corner cases: boundary addresses  
- Assertions: no read/write conflicts  
- Random tests for stress patterns  

---

## 8. Interview & GATE Points
- ROM is non-volatile; RAM is volatile  
- SRAM is faster than DRAM  
- DRAM requires refresh  
- Flash is a type of EEPROM  
- Memory size depends on address lines  
- Access time impacts performance  

---

## 9. Summary
ROM and RAM form the core memory components in digital systems.
Understanding memory types, organization, timing, and verification aspects is essential for digital design and VLSI roles.
