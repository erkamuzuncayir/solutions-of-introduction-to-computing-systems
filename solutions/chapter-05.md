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
    NOT R4 R3
    ADD R4 R4 #1
    ADD R5 R4 R2
    BRZ ZERO (101)
    BRN R3 (1)
    BRP R2 (10)
    ADD R1 R3 #0
    BRNZP DONE (1)
    ADD R1 R2 #0
    HALT DONE
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
	1. LD R1 #2
	2. STR R0 R1 #0
---
29. Solution:
	1. LDR R0 R1 #0
	2. MAR <- SR + OFFSET. MDR <- Memory[MAR]. DR <- MDR.
---
30. Both R1 and R2 is 0.
---
31. 0001 101 100 000 110
---
32. Solution:
	1. BRp #2
	2. Skip
	3. Skip
	4. AND R0 R0 #2
	5. ADD R0 -1
	6. RESULT: N=1, Z=0, P=0
---
33. R5 is 1.
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
		1. x3001: 0000 001 0 0010 0111
		2. x3002: 0000 100 0 0100 1110
	2. Program never halts, it just endless setting 0 to R0 and increment one loop.
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
50. BR sends PC, LEA and LD sends DR.
---
51. Solution:
	1. Solution:
	![Solution](_attachments/Pasted%20image%2020241230143957.png)
---
52. Solution:
	![Solution](_attachments/Pasted%20image%2020241230144355.png)
---
53. Solution:
	![Solution](_attachments/Pasted%20image%2020241230145543.png)
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
