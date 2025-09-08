<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->

## How it works

Inputs: Two 4-bit numbers → A3 A2 A1 A0 and B3 B2 B1 B0

Outputs:

(A > B) → High when A is greater than B

(A < B) → High when A is less than B

(A = B) → High when A equals B

Working Principle:

Bit-by-Bit Comparison

The comparator starts from the most significant bit (MSB).

For example: if A3 = 1 and B3 = 0, then immediately A > B, without checking other bits.

If A3 = B3, the comparator moves to the next bit (A2 vs B2), and so on.

Equality Detection

XOR/XNOR gates check whether each bit of A equals the corresponding bit of B.

Final AND gate combines all equalities to produce (A = B).

Greater Than / Less Than

AND–OR logic is used:

(A > B) is high if the first different bit from the left has A = 1 and B = 0.

(A < B) is high if the first different bit from the left has A = 0 and B = 1.



## How to test
Truth Table (4-bit Comparator)

Since 4-bit numbers range from 0000 to 1111 (0 to 15 decimal), the full truth table has 256 combinations.
Here’s a simplified representation:

| A (decimal) | B (decimal) | A > B | A = B | A < B |
| ----------- | ----------- | ----- | ----- | ----- |
| 5 (0101)    | 3 (0011)    | 1     | 0     | 0     |
| 7 (0111)    | 12 (1100)   | 0     | 0     | 1     |
| 9 (1001)    | 9 (1001)    | 0     | 1     | 0     |
| 0 (0000)    | 15 (1111)   | 0     | 0     | 1     |
| 15 (1111)   | 0 (0000)    | 1     | 0     | 0     |


## External hardware

LED's are used
