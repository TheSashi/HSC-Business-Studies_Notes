---
tags: [software-engineering, year-11, hsc, numbering-systems, binary, hexadecimal, twos-complement, conversions]
aliases: [SE Numbering, Binary, Hex, 2s Complement, Conversions]
subject: Software Engineering
syllabus_ref: HSC Software Engineering — Year 11 Programming Fundamentals
created: 2026-07-15
updated: 2026-07-15
---

# Numbering Systems — Year 11 SE

> Self-contained note on decimal, binary, hexadecimal, how to convert between them, and 1s/2s complement. Every worked conversion is reproduced exactly from PF6 and PF7. No external content added.

---

## 1. Decimal (base 10)

"has a maximum of ten digits between 0 and 9. Each column increments from right to left in powers of ten." (10³=1000, 10²=100, 10¹=10, 10⁰=1). "leading zeros … are not written."

---

## 2. Binary (base 2)

"has a maximum of two digits between 0 and 1. This is the default numbering system of computers and electric circuits, where 0 is off and 1 is on. Each column increments from right to left in powers of two." (2³=8, 2²=4, 2¹=2, 2⁰=1). "in binary, leading zeros are written."

---

## 3. Hexadecimal (base 16)

"also known as base 16 … for each column, there are 16 digits available, 0-9 then A-F. Each column increments from right to left in increments of powers of 16." (16³=4096, 16²=256, 16¹=16, 16⁰=1).

Digit mapping (decimal to hex): 10=A, 11=B, 12=C, 13=D, 14=E, 15=F, 16=10.

---

## 4. Method 1 — Binary to Decimal

Take each bit x its place value, sum.

- `0011` → 0x8 + 0x4 + 1x2 + 1x1 = 2+1 = **3**
- `1010` → 1x8 + 0x4 + 1x2 + 0x1 = 8+2 = **10**
- `0101` → 0x8 + 1x4 + 0x2 + 1x1 = 4+1 = **5**
- `1111` → 8+4+2+1 = **15**
- `0010` → 0+0+2+0 = **2**
- `1110` → 8+4+2+0 = **14**

---

## 5. Method 1 — Decimal to Binary

"only turn on the bits (i.e. put a 1) which you need to make up the number."

- 14 → `1110` (8+4+2)
- 13 → `1101` (8+4+1)
- 10 → `1010` (8+2)
- 8 → `1000`
- 5 → `0101` (4+1)
- 9 → `1001` (8+1)

---

## 6. Method 1 — Hexadecimal to Decimal

Each hex digit x 16^position, summed.

- `11` → 1x16¹ + 1x16⁰ = 16+1 = **17**
- `1A` → 1x16 + 10x1 = **26**
- `DEAF` → 13x4096 + 14x256 + 10x16 + 15 = 53248+3584+160+15 = **57007**
- `FEED` → 15x4096 + 14x256 + 14x16 + 13 = 61440+3584+224+13 = **65261**
- `0F0F` → 0 + 15x256 + 0 + 15x1 = 3840+15 = **3855**
- `BC` → 11x16 + 12x1 = 176+12 = **188**

---

## 7. Method 1 — Decimal to Hexadecimal

- `24` → 1x16 + 8x1 = **18₁₆**
- `999` → 3x256 + 14x16 + 7 = **3E7₁₆** (result shown)

---

## 8. Hex to Binary: straight substitution

"each hexadecimal digit corresponds to four binary digits (bits). Therefore, converting from hex to binary simply requires … a straight substitution." Process: (1) take the hex digit; (2) convert its value into decimal; (3) convert that into binary.

- `3AB2₁₆` → `3`=0011, `A`=1010, `B`=1011, `2`=0010 ⇒ **0011 1010 1011 0101₂**

Hex to Binary exercises (answers):
- `F` → `1111`
- `FEED` → `1111 1110 1110 1101`
- `DEAF` → `1101 1110 1010 1111`
- `0F0F` → `0000 1111 0000 1111`
- `BC` → `1011 1100`

Memorisation table (decimal / binary / hex): 0=0000=0 … 15=1111=F. "it is customary to give binary numbers in groups of 4, as 8 binary digits (bits) = 1 byte, the most basic unit of storage measurement on a computer."

Mixed exercises (answers):
- `ABCDE₁₆` = `1010 1011 1100 1101 1110₂`
- `1111 1110 0001 1100₂` = `FE1C₁₆`
- `256₁₀` = `10000000₂`
- `ABCDE₁₆` = `703710₁₀`
- `100₁₆` = `256₁₀`
- `15₁₀` = `1111₂`
- `1100 0000 0000 1111₂` = `C00F₁₆`

---

## 9. Method 2 — "Additional Exercises" (answers only; explanatory steps not in source)

The PF6 references "Number Conversions Method 2" videos but the explanatory steps are not in the extracted text. Faithful reproduction of the exercise answers:

- **A. Binary to Decimal:** `11001011`=203; `00110101`=53; `10000011`=131; `10001111`=143; `11100011`=227
- **B. Hex to Binary** (note `0x` prefix is not converted): `45`=0100 0101; `FA`=1111 1010; `0x5D`=0101 1101; `0x99`=1001 1001; `0x03`=0000 0011
- **C. Decimal to Binary:** `213`=11010101; `9`=1001; `67`=1000011; `99`=1100011; `23`=10111
- **D. Binary to Hex:** `11001100`=CC; `11110001`=F1; `00110001`=31; `11000010`=C2; `10100100`=A4
- **E. Hex to Decimal:** `0x5A`=90; `0xCC`=204; `0x97`=151; `0x40`=64; `0x07`=7

---

## 10. 1s and 2s Complement (PF7 — worked answers only, no prose definitions in source)

### Convert to binary using 2's complement
- `-127` → `1 0000001`
- `-63` → `1 1000001`
- `-5` → `1 011`
- `-128` → `1 00000000`

### Represent signed decimals in 2's complement (8 bits total)
- `+32` → `0 0100000`
- `-14` → `1 1110010`
- `+63` → `0 0111111`
- `-104` → `1 0011000`

### Binary addition (check in decimal)
- `1010 + 1011` → `10101` (10 + 11 = 21)
- `1111 + 0011` → `10010` (15 + 3 = 18)
- `1011.1101 + 11.1` → `1111.0101`

### 8-bit two's complement subtraction
- `01010111 − 00011100` → `00110011`
- `00011001 − 11111011` → `00011110`
- `100010111 − 1101` → `000011010`

### Binary division (Quotient / Remainder)
- `110 / 111010` → Q: `1001`, R: `100`
- `1101 / 1010101` → Q: `110`, R: `111`
- `1110101 ÷ 1010` → Q: `1011`, R: `111`
- `1010011 ÷ 101` → Q: `1000`, R: `11`

---

> **See also:** [[SE_Algorithms_and_Desk_Checks]] | [[SE_Software_Dev_Process]] | [[SE_Programming_Paradigms]] | [[SE_Object_Oriented_Programming]] | [[SE_Mechatronics]]
