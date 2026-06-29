# Chapter 05

1. Solution:
	1. Operate instructions: ADD, NOT.
	2. Data movement instructions: LEA.
	3. Control instructions: JMP.
---
2. MAR have to hold 64 bits to store memory address. Same also apply for MDR.
---
3. Sentinel. Sentinel is not allowed as input and indicates the termination of loop.
---
4. Solution:
	1. 8 bits.
	2. 6 bits.
	3. 10 - (3 + 1) = 6
---
5. Solution:
	1. Addressing mode is a mechanism for specifying where the operand is located.
	2. Literal, register, memory.
	3. Where is the data stored:
		1. Immediate, as a literal in instruction.
		2. Register, is in one of the register.
		3. PC-relative, in memory.
		4. Indirect, in memory.
		5. Base+offset, in memory but its address can be calculated with offset.
	4. Register mode.
---
6. Solution:
	1. 0101 011 010 1 00100
	2. 0101 011 010 1 01100
	3. 0101 011 010 1 11111
	4. We can't because we don't have enough literal value.
---
7. [15:12] bits are used for specifying operation. [11:09] bits are used for destination register. [8:6] bits are used first operand register. [5] bit used for, if is literal value used for second operands. [4:0] bits are used for literal value. So in five bits, as a 2's compliment, the largest positive number we can represent is 15.
---
8. We don't have enough bits to represent that much register address. 32 register require 5 bits and for possible 3 register (two as an operand, one as a result) we'll need 15 bits but we just have (16-4) 12 bits for addressing registers.
---
9. Solution:
	1. A is an ADD operation and it sums with R1 and 0, and put result to the R1 again. So it doesn't change anything. So it can be used as NOP.
	2. B is an BR operation with 111 for it's NZP value. So every result will be make this branch happen, so it can't be used as NOP.
	3. C is an BR operation too with 000 for it's NZP value. So non-of the result will be make this branch happen, so it can be used as NOP.
---
10. Don't teach 0100 opcode in the book yet. It might be residue from old edition.
---
11. We can't because LC-3 ADD operation with using two register, can represent literal from -16 to 15.
---
12. If R0[15], R1[15] and R2[15] are = 0. We can trust the result
---
13. Solution:
	1. (ADD)0001 (R3)011 (R2)010 (IS LITERAL)1 (LITERAL)00000
	2. b.
		1. (AND)0101 (R1)001 (R1)001 (IS LITERAL)1 00000
		2. (NOT)1001 (R3)011 (R3)011 11 1111
		3. (ADD)0001 (R3)011 (R3)011 (IS LITERAL)1 00001
		4. (ADD)0001 (R1)001 (R2)010 (IS LITERAL)0 000 (R3)011
	3. ADD(0001) (R1)001 (R1)001 (IS LITERAL)0 00000
	4. Can't. Never gonna be a number both negative and zero at the same time.
	5. (AND)0101 (R2)010 (R2)010 (IS LITERAL)1 00000
---
14. Solution: De Morgan's Law = (NOT A) AND (NOT B) = A OR B
	1. (NOT)1001 (R4)100 (R1)001 111111
	2. (NOT)1001 (R5)101 (R2)010 111111
	3. (AND)0101 (R6)110 (R4)100 000 (R5)101
	4. (NOT)1001 (R3)011 (R6)110 111111
---
15. Solution: R1 store 3132 which is memory address. R2 stores value of the memory address which x3122 holds that 4566. R3 stores value of the memory address which x4567 holds that ABCD. R4 stores value of the memory address which x4567 that xABCD.
	1. x3100 = (LEA)1110 (R1)001 (#32)000100000
	2. x3101 = (LD)0010 (R2)010 (#32)000100000
	3. x3102 = (LDI)1010 (R3)011 (#32)000100000
	4. x3103 = (LDR)0110 (R4)100 (R2)010 0000001
---
16. Solution:
	1. LD
	2. LDI
	3. LDR OR LD (If address less than -+2^8 bit away.)
---
17. Solution:
	1. LD: 1 read for while fetching data from offset literal value.
	2. LDI: 1 read for while fetching data from offset literal value + 1 read from the fetching data from that offset literal value stores memory address.
	3. LEA: 1 read for while fetching data from offset literal value.
---
18. Solution:
	1. LDR: First read access for fetching instruction from instruction address. Second read access for taking value from offset value address.
	2. STI: Second read access for getting real memory address of in instruction. Third read access for taking value from this real memory address.
	3. TRAP: First read access for fetching instruction from instruction address. First write access to PC a specific address of operating system.
---
19. 63 to -64
---
20. 7 bits for 65 places.
---
21. trapvector consists 8 bits from [7] to [0]. So LC-3 can support up to 256 bits.
---
22. R6: x123B. LDI R6 x3F
---
23.  It will be x1482.
---
24. Largest one is 4030 while sign extended and 4050 while zero extended. Smallest one is 4011 while zero extended.
---
25. Solution:

| Label | Binary Instruction | Assembly | Description |
| --- | --- | --- | --- |
|  | `1001 100 011 111111` | `NOT R4, R3` | Bitwise NOT of R3 $\rightarrow$ R4 |
|  | `0001 100 100 1 00001` | `ADD R4, R4, #1` | Two's complement: R4 $\leftarrow$ -R3 + 1 $\rightarrow$ R4 = -R3 |
|  | `0001 001 100 0 00 010` | `ADD R1, R4, R2` | R1 $\leftarrow$ -R3 + R2 (i.e., R2 - R3) |
|  | `0000 010 000000101` | `BRz Done` | If R1 == 0 $\rightarrow$ branch to `Done` |
|  | `0000 100 000000001` | `BRn Reg3` | If R1 < 0 $\rightarrow$ branch to `Reg3` |
|  | `0000 001 000000010` | `BRp Reg2` | If R1 > 0 $\rightarrow$ branch to `Reg2` |
| **Reg3:** | `0001 001 011 1 00000` | `ADD R1, R3, #0` | Copy R3 to R1 |
|  | `0000 111 000000001` | `BRnzp Done` | Unconditional branch to `Done` |
| **Reg2:** | `0001 001 010 1 00000` | `ADD R1, R2, #0` | Copy R2 to R1 |
| **Done:** | `1111 0000 0010 0101` | `TRAP x25` | HALT (TRAP x25 halts the program) |

---
26. Solution:
	1. Can't see any problem.
	2. 16 bits.
	3. 2^7 for trapvector and 5 bits for shifting = 2^12
	4. 16 bits - 4 bits for opcode + 2bits for destination register + 2bits for source register + 1 bit for specifying bit for register or literal = 7 bits
---
27. Solution: x3102, x0000, x0005
---
28. Solution:
    
| Address | Binary | Assembly | Description |
| :--- | :--- | :--- | :--- |
| **x3000** | `0010 0000 0000 0011` | `LD R0, #3` | Load the value `x0048` (now at `x3004`) into R0. |
| **x3001** | `0010 0010 0000 0011` | `LD R1, #3` | Load the pointer `xF3FF` (now at `x3005`) into R1. |
| **x3002** | `0111 0000 0100 0000` | `STR R0, R1, #0` | Store R0 into the memory address held in R1. |
| **x3003** | `1111 0000 0010 0101` | `TRAP x25` | Halt execution. |
| **x3004** | `0000 0000 0100 1000` | `.FILL x0048` | Original data. |
| **x3005** | `1111 0011 1111 1111` | `.FILL xF3FF` | Original pointer. |

---
29. Solution:
	1. LDR R0 R1 #0
	2. MAR <- SR + OFFSET. MDR <- Memory[MAR]. DR <- MDR.
---
30. Both R1 and R0 is 0.
---
31. 0001 101 000 1 11000
---
32. Solution:
	1. BRp #2
	2. Skip
	3. Skip
	4. AND R0 R0 #0
	5. ADD R0 -1
	6. RESULT: N=1, Z=0, P=0
---
33. R5 is 0000 0000 0001 1111.

- Behavior of the loop (x3002–x3008):
	- R6 Doubling Sequence:
		- Starts at 0000 0000 0000 0001 (1).
		- Each iteration:
			- x3005: R6 ← R6 + R6 (left-shift by 1 → 0000 0000 0000 0010, 0000 0000 0000 0100, etc.).
	- R0 Increment:
		- Begins at x0000, increments by 1 at x3004 (ADD R0, R0, #1) when the AND result is non-zero.
	- Branch Condition (x3003):
		- Branches to x3005 only when R5 AND R6 = 0.
		- This occurs when R6’s set bit (e.g., 0010 0000) does not overlap with R5’s bits.
		- If R5 = 0000 0000 0001 1111 (31), the AND yields zero only when R6 =0000 0000 0010 0000 (32).
		- Thus, R0 increments only 5 times (for R6 = 1, 2, 4, 8, 16), stopping when R6 = 32 (since AND results in zero, skipping x3004).
	- Later Iterations:
		- For R6 = 0100 0000 (64), 1000 0000 (128), etc., R5 AND R6 remains zero (no further R0 increments).

- Key Conclusions
	- Final R0 = 5: Matches the count of non-zero AND results before R6 reaches 0010 0000.
	- R5 Value: Must be 0001 1111 (31) to ensure:
		- AND is non-zero for R6 = 1, 2, 4, 8, 16.
		- AND is zero for R6 ≥ 32.


| Address | Binary | Assembly | Description |
| --- | --- | --- | --- |
| **x2FFF** | `0101 0000 0010 0000` | `AND R0, R0, #0` | Clears R0 ( R0 $\leftarrow$ 0 ). |
| **x3000** | `0101 1111 1110 0000` | `AND R7, R7, #0` | Clears R7 ( R7 $\leftarrow$ 0 ). |
| **x3001** | `0001 1101 1110 0001` | `ADD R6, R7, #1` | Adds 1 to R7, stores result in R6 ( R6 $\leftarrow$ R7 + 1 ). |
| **x3002** | `0101 1001 0100 0110` | `AND R4, R5, R6` | Bitwise AND of R5 and R6, stores result in R4 ( R4 $\leftarrow$ R5 AND R6 ). |
| **x3003** | `0000 0100 0000 0001` | `BRz x3005` | Branches to x3005 if last result was zero. |
| **x3004** | `0001 0000 0010 0001` | `ADD R0, R0, #1` | Increments R0 by 1 ( R0 $\leftarrow$ R0 + 1 ). |
| **x3005** | `0001 1101 1000 0110` | `ADD R6, R6, R6` | Doubles R6 ( R6 $\leftarrow$ R6 + R6 ). |
| **x3006** | `0001 1111 1110 0001` | `ADD R7, R7, #1` | Increments R7 by 1 ( R7 $\leftarrow$ R7 + 1 ). |
| **x3007** | `0001 0011 1111 1000` | `ADD R1, R7, #-8` | Subtracts 8 from R7, stores result in R1 ( R1 $\leftarrow$ R7 - 8 ). |
| **x3008** | `0000 1001 1111 1001` | `BRn x3002` | Branches back to x3002 if last result was negative. |
| **x3009** | `0101 1111 1110 0000` | `AND R7, R7, #0` | Clears R7 again ( R7 $\leftarrow$ 0 ). |

---
34. NOT
     ![Solution](_attachments/Pasted%20image%2020241229181429.png)
---
35. ADD
     ![Solution](_attachments/Pasted%20image%2020241229175612.png)
---
36. LD
     ![Solution](_attachments/Pasted%20image%2020241229183323.png)
---
37. LDI
     ![Solution](_attachments/Pasted%20image%2020241229184325.png)
---
38. LDR
     ![Solution](_attachments/Pasted%20image%2020241229191445.png)
---
39. LEA
     ![Solution](_attachments/Pasted%20image%2020241229182441.png)
---
40. To be able to tell if branching is possible depending on the last loaded value.
---
41. Solution:
	1. Y is provide P condition of the NZP values.
	2. For the signal X is 1 for 0000 opcode. This make gated D latch write enabled.
---
42. I guess MUL Ri, Rj, Rk. Because multiplication is very common operation in use of computer programming. If there is an operation, it makes lots of programmers' life easier.
---
43. For both instructions; nothing but just PC incremented by 1.
---
44. Solution:
	1. a.
		1. x3001: 0000 001 0 0011 1110  Offset9 = 000111110 = +62 → jumps to x3001+1+62 = x3040
		2. x3002: 0000 100 0 0111 1101  Offset9 = 001111101 = +125 → jumps to x3002+1+125 = x3080
	2. Program halts when R0 = x8000 = 1000 0000 0000 0000 which will be considered negative by BR instruction at x3002.
---
45. PC put contents to MAR because it is how instruction loaded into LC-3. In this way we know which data where read or stored with, which operation. Microarchitecture increment PC to pointing to next instruction to read next instruction at next cycle.
---
46. Instruction is ADD, R0, R0, R1. So, R1 should contain enough value to get lowercase version of R0. In ASCII 'a' has 97 and 'A' has 65. So R1 should contain offset value of 32 which is 0000 0000 0010 0000.
---
47. Can't solve.
---
48. If R0 contains zero or positive value which sums of R1 and R2.
---
49. If next instruction 010 of NZP met, we can say R0 is the base register.
---
50. BR sends to PC, LEA sends to DR, LD sends to MAR.
---
51. Solution:
	1. Solution:
	![Solution](_attachments/Pasted%20image%2020241230143957.png)
---
52. Solution:
	![Solution](_attachments/Pasted%20image%2020241230144355.png)
---
53. Solution:
    
	![Solution](_attachments/5.53%20reg%20file.png)
---
54. TRAP, 0000.
---
55. Can't solve.
---
56. Solution:
	![Solution](_attachments/Pasted%20image%2020241230220118.png)
---
57. Solution:
	1. ST, STI, STR
	2. From IR[5]
	3. TRAP instruction
---
58. Can't solve.
---
59. ADD = 9. AND = 9. LD = 15. LEA = 9. LDI = 21. NOT = 9. BRnzp = 10. TRAP = 15
---
60. Solution:
	1. ALL
	2. None of what I've seen so far.
	3. ADD, AND, NOT, LEA, LD, LDI, LDR,
	4. It indicates result of ADD operation occur overflow.
---
61. Didn't try to solve.
