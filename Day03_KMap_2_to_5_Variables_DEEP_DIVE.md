# Day 03 – Karnaugh Map (K-Map: 2 to 5 Variables)

## 1. Why K-Map?
Karnaugh Maps are used to simplify Boolean expressions visually.
They help in:
- Reducing gate count
- Lowering power consumption
- Improving timing (shorter logic depth)
- Producing cleaner RTL that is easier to verify

---

## 2. Core Principles (Applies to All K-Maps)
- Cells are arranged in Gray code order
- Adjacent cells differ by only one variable
- Allowed adjacency: horizontal, vertical, and wrap-around edges
- Diagonal adjacency is not allowed
- Groups must be in sizes of 1, 2, 4, 8, 16, ...
- Groups should be as large as possible
- Groups may overlap
- Every 1 must be covered at least once
- Don’t-cares (X) can be used to form larger groups

---

## 3. 2-Variable K-Map (A, B)

Layout:

      B
      0   1
    ---------
A 0 | m0 | m1 |
  1 | m2 | m3 |

Example:
F(A, B) = Σm(1, 3)

      B
      0   1
    ---------
A 0 |  0 |  1 |
  1 |  0 |  1 |

Simplified Result:
F = B

---

## 4. 3-Variable K-Map (A, B, C)

Layout (Gray code on BC):

          BC
        00  01  11  10
      -----------------
A  0  | m0 | m1 | m3 | m2 |
A  1  | m4 | m5 | m7 | m6 |

Example:
F(A, B, C) = Σm(1, 3, 5, 7)

          BC
        00  01  11  10
      -----------------
A  0  |  0 |  1 |  1 |  0 |
A  1  |  0 |  1 |  1 |  0 |

Simplified Result:
F = C

---

## 5. 4-Variable K-Map (A, B, C, D)

Layout (AB vs CD, Gray code on both):

              CD
            00  01  11  10
          -----------------
AB 00     | m0 | m1 | m3 | m2 |
AB 01     | m4 | m5 | m7 | m6 |
AB 11     | m12| m13| m15| m14|
AB 10     | m8 | m9 | m11| m10|

Example:
F(A, B, C, D) = Σm(0, 1, 2, 3, 8, 9, 10, 11)

These occupy rows AB = 00 and AB = 10.

Simplified Result:
F = B'

---

## 6. 5-Variable K-Map (Conceptual Method)

A 5-variable K-Map is represented using two 4-variable K-Maps:
- One for E = 0
- One for E = 1

Adjacency is allowed:
- Within each 4-variable map
- Between corresponding cells across the two maps (only E differs)

This allows forming larger groups across both maps.

---

## 7. How to Derive Expression from a Group

For each group:
- If a variable is always 1 → include the variable
- If a variable is always 0 → include the complemented variable
- If a variable changes → eliminate it

Example:
If A varies, B = 1, C = 0, D varies, E varies
→ Term = B · C'

---

## 8. SOP vs POS
- SOP (Sum of Products): group 1s
- POS (Product of Sums): group 0s

---

## 9. Limitations
- K-Maps become complex for 5+ variables
- Manual grouping becomes error-prone
- In practice, tools use algorithmic minimization

---

## 10. Design & Verification Perspective
- Minimized logic reduces area and power
- Cleaner RTL is easier to verify and debug
- Fewer corner cases and faster coverage closure

---

## 11. Common Mistakes
- Grouping diagonally
- Missing wrap-around groups
- Using non-power-of-2 group sizes
- Ignoring don’t-cares

---

## 12. Interview & GATE Points
- Gray code ordering ensures one-bit adjacency
- Groups must be powers of 2
- Wrap-around grouping is allowed
- 5-variable K-Maps use two 4-variable maps
- Synthesis tools perform minimization for large designs

---

## 13. Summary
K-Maps are a visual and intuitive way to minimize Boolean expressions.
They are practical up to 4 variables and conceptually useful for 5 variables.
Understanding K-Maps helps in writing efficient RTL and debugging optimized logic.
