# Chapter 06

1. Yes, an algorithm is defined a step by step procedure that will terminate eventually. We can create a procedure that doesn't end with 3 basic constructs and won't be a algorithm. Here it is;
	1. x3000: AND R0 R0 #0
	2. x3001: BRZ #-1
---
2. Solution:
	1. a.
		1. Start
		2. Subtract 2 number
		3. Stop
	2. b.
		1. Start
		2. Initialize
		3. Subtract 2 number
		4. Stop
	3. c.
		1. Start
		2. Initialize
			1. R0 <- first number
			2. R1 <- second number
			3. R2 <- 0 (will be result)
		3. Operation
			1. NOT R1 R1
			2. ADD R1 R1 #1
			3. ADD R2 R1 R0
		4. Stop
---
3. Solution: De Morgan's Law = (NOT A) AND (NOT B) = A OR B
	1. x3000: LDI R0 NEW_BUSY
	2. x3001: LDI R1 BUSY_MACHINES
	3. x3002: AND R2 R2 #0
	4. x3003: AND R3 R3 #0
	5. x3004: AND R4 R4 #0
	6. x3005: NOT R1 R0
	7. x3006: NOT R3 R2
	8. x3007: AND R4 R3 R2
	9. x3008: STI R4 BUSY_MACHINES
---
4. Solution:
	1. LDI R1 SEC_NUM
	2. LDI R2 FRS_NUM
	3. AND R0 R0 #0
	4. AND R4 R4 #0
	5. AND R5 R5 #0
	6. NOT R4 R2
	7. ADD R4 R4 #1
	8. ADD R5 R1 R4
	9. BRn #4
	10. BRp #1
	11. ADD R0 R0 #0
	12. BRnzp HALT
	13. ADD R0 R0 #1
	14. BRnzp HALT
	15. ADD R0 R0 #-1
	16. HALT
---
5. 88 * 3. Because it needs less operation count.
---
6. Solution:
	1. Flowchart:
![Solution](_attachments/6.6%20multiplication.png)
	2. Assembler code in image:
![Solution](_attachments/6.6.%20asm%20code.png)
	3. Actual assembler code:
		AND R3, R3, #0
     		ADD R6, R0, #0
		ADD R7, R1, #0
		AND R4, R7, #-1
       		BRz DONE
      		AND R4, R6, #-1
		BRz DONE
       		BRn NEG1
       		AND R4, R7, #-1
       		BRp POS2
      		NOT R7, R7
       		ADD R7, R7, #1
      		BRnzp NMULT
	NEG1    NOT R6, R6
     		ADD R6, R6, #1
       		AND R4, R7, #-1
      		BRn POS1
	NMULT   NOT R2, R6
      		ADD R2, R2, #1
       		ADD R4, R7, R2
      		BRn COUNT1
		ADD R5, R6, #0
	LOOP1   ADD R3, R3, R7
     		ADD R5, R5, #-1
      		BRp LOOP1
      		NOT R3, R3
      		ADD R3, R3, #1
       		BRnzp DONE
	COUNT1  ADD R5, R7, #0
	LOOP2   ADD R3, R3, R6
      		ADD R5, R5, #-1
      		BRp LOOP2
		NOT R3, R3
      		ADD R3, R3, #1
		BRnzp DONE
	POS1    NOT R7, R7
      		ADD R7, R7, #1
	POS2    NOT R2, R6
      		ADD R2, R2, #1
      		ADD R4, R7, R2
      		BRn COUNT2
      		ADD R5, R6, #0
	LOOP3   ADD R3, R3, R7
      		ADD R5, R5, #-1
      		BRp LOOP3
      		BRnzp DONE
	COUNT2  ADD R5, R7, #0
	LOOP4   ADD R3, R3, R6
      		ADD R5, R5, #-1
      		BRp LOOP4
     		BRnzp DONE
	DONE    TRAP x25
    .END
---
7. It sums correspending elements of specific lengthed two list (i guess) and store them.
---
8. R2 might be populated previously and result might be uncorrect due to this.
---
9. Solution:
	1. AND R0 R0 #0
	2. LD R0 [SOMEADDRESSHAVE100]
	3. [ITERATIVE_START] TRAP DISPLAY 'Z'
	4. ADD R0 R0 #-1
	5. BRzp [ITERATIVE_START]
	6. HALT
---
10. Solution:
	1. AND R0 R2 #1
	2. BRz [RESULT_EVEN]
	3. BRnp [RESULT_ODD]
---
11. Solution:
	1. AND R0 R0 #0
	2. AND R1 R1 #0
	3. AND R2 R2 #0
	4. AND R3 R3 #0
	5. LD R0 [x3100]
	6. LD R1 [x3101]
	7. [LOOP_START] AND R2 R1 R0
	8. BRz [DONE]
	9. LDR R3 R0 #0
	10. ADD R3 R3 #1
	11. STR R3 R0 #0
	12. ADD R0 R0 #1
	13. BRnzp [LOOP_START]
	14. [DONE] HALT
---
12. Solution:
	1. a.
		1. TRAP GET_INPUT
		2. TRAP DISPLAY_INPUT
	2. b.
		1. TRAP GET_INPUT
		2. ADD INPUT INPUT #-6
		3. BRz DISPLAY_PREVIOUS_INPUT
---
13. Solution:
	1. AND R0 R0 #0
	2. AND R1 R1 #0
	3. LD R0 x3100
	4. [LOOP_START] ADD R0 R0 #-2
	5. BRnz [DONE]
	6. ADD R1 R1 #1
	7. BRnzp [LOOP_START]
	8. [DONE] ST R1 x3100
---
14. 9,10,11.
---
15. STR R2 R4 #7
---
16. Can't solve. Some instructions are not taught in the book.
---
17. BRnZp #15. I guess?
---
18. Solution:
	1. First
		1. Initialize
		2. Find small number
		3. Sum small number with itself and count quotient
		4. When you found quotient, subtract from bigger number you'll found remainder
	2. Second
		1. Initialize
			1. AND R0 R0 #0
			2. AND R1 R1 #0
			3. AND R2 R2 #0
			4. AND R3 R3 #0
			5. AND R4 R4 #0
			6. AND R5 R5 #0
			7. LDI R0 [MEMORY_ADDRESS_CONTAIN_FIRST_NUM]
			8. LDI R1 [MEMORY_ADDRESS_CONTAIN_SEC_NUM]
		2. Operation
			1. NOT R2 R0
			2. ADD R2 R2 #1
			3. ADD R2 R2 R1
			4. BRn [FIRST_NUM_IS_SMALL_LOOP_START]
			5. BRp [SEC_NUM_IS_SMALL_LOOP_START]
			6. BRz [QUOTIENT_IS_1_REMAINDER_IS_0]
			7. [FIRST_NUM_IS_SMALL_LOOP_START] ADD R3 R3 R0
			8. ADD R2 R2 #1
			9. NOT R4 R3
			10. ADD R4 R4 #1
			11. ADD R5 R4 R1
			12. BRp [FIRST_NUM_IS_SMALL_LOOP_START]
			13. BRz [NO_REMAINDER]
			14. ADD R2 R2 #-1
			15. ADD R4 R4 R0
			16. NOT R4 R4
			17. ADD R4 R4 #1
			18. AND R3 R3 #0
			19. ADD R3 R1 R4
			20. STI R2 #[ADDRESS_CONTAIN_5000]
			21. STI R3 #[ADDRESS_CONTAIN_5001]
			22. BRnzp [DONE]
			23. [SEC_NUM_IS_SMALL_LOOP_START] ADD R3 R3 R1
			24. ADD R2 R2 #1
			25. NOT R4 R3
			26. ADD R4 R4 #1
			27. ADD R5 R4 R0
			28. BRp [SEC_NUM_IS_SMALL_LOOP_START]
			29. BRz [NO_REMAINDER]
			30. ADD R2 R2 #-1
			31. ADD R4 R4 R1
			32. NOT R4 R4
			33. ADD R4 R4 #1
			34. AND R3 R3 #0
			35. ADD R3 R0 R4
			36. STI R2 [ADDRESS_CONTAIN_5000]
			37. STI R3 [ADDRESS_CONTAIN_5001]
			38. BRnzp [DONE]
			39. [NO_REMAINDER] STI R2 [ADDRESS_CONTAIN_5000]
			40. AND R5 R5 #0
			41. STI R5 [ADDRESS_CONTAIN_5001]
			42. BRnzp [DONE]
			43. [QUOTIENT_IS_1_REMAINDER_IS_0] ADD R3 R3 #1
			44. STI R3 [ADDRESS_CONTAIN_5000]
			45. STI R4 [ADDRESS_CONTAIN_5001]
			46. [DONE] TRAP HALT
		3. Exit
---
19. Solution:
	1. Doesn't load from x4000.
	2. Doesn't save to x5000
	3. Doesn't increment by 4.
	4. Store encrypted data to wrong place.
	5. LEA R0 x5000
	6. LD R1 x4000
	7. LDR R2 R1 #0
	8. BRn HALT
	9. [LOOP_START] ADD R2 R2 #4
	10. STR R2 R0 #0
	11. ADD R0 R0 #1
	12. ADD R1 R1 #1
	13. BRnzp [LOOP_START]
	14. [HALT] TRAP
---
20. only the negative number check in exercise 6 should be added to the answer in exercise 18.
---
21. Solution:
	1. x3003: R1 <- R0 - 15
	2. x3009: R0 <- R0 + 1
---
22. Solution:
	1. x3004: BRz x300D
	2. x3008: AND R5 R2 R3
	3. x300A: ADD R0 R0 #1
	4. x300B: ADD R1 R1 #1
	5. x300D: ADD R5 R5 #1
	6. If password stored as negative number, instructions at x3007 and x3008 can be removed.
---
23. Solution: R0 = A52D, R1 = 1010
    |    PC    |  MAR  |  MDR   |    IR     |    R0    |     R1    |
    | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- |
    | x3000 | ---------- | ---------- | ---------- | x0000 | x0000 |
    | x3001 | x3006 | xB333 | x2005 | xB333 | x0000 | 0010 0000 0000 0101 : LD R0 #5
    | x3002 | x3001 | x0601 | x0601 | xB333 | x0000 | 0000 0110 0000 0001 : BRzp #1
    | x3003 | x3002 | x1261 | x1261 | xB333 | x0001 | 0001 0010 0110 0001 : ADD R1 R1 #1
    | x3004 | x3003 | x1000 | x1000 | x6666 | x0001 | 0001 0000 0000 0000 : ADD R0 R0 R0
    | x3005 | x3004 | x0BFC | x0BFC | x6666 | x0001 | 0000 1011 1111 1100: BRnp #-4
---
24. 0110 0000 0100 0001: LDR R0 R1 #1
---
25. at this point assembly coding has not yet been taught. but since the operation is done through registers and there is no memory access, the answer will be like this: the answer will result = result + 1 because the necessary bit insertion has not been done.
---
26. Solution:
	1. a.
	    | Cycle |  State  |  Bus   |    Signals     |
	    | --------- | ---------- | ---------- | ---------- |
	    |     T    | ---------- | x3010 | LD.MAR = 1, LD.PC =1, PCMux = PC + 1, GatePC = 1 |
	    |  T+4  | ---------- | xA202 | LD.MDR = 1, Gate.MDR = 1, LD.IR = 1 |
	    |  T+6  | ---------- | x3013 | ADDR1MUX = PC, ADDR2MUX = SEXT(IR[8:0]), MARMUX = ADDR.ADD, Gate.MARMUX = 1 |
	    | T+10 | ---------- | x4567 | LD.MAR = 1, MDRMUX = Memory, LD.MDR = 1 |
	    | T+14 | ---------- | x0000 | LD.REG = 1, LD.CC = 1, GateMDR = 1, DR = 001 |
	2. LDI R1 #2
	3. x3010
	4. 3 clock cycles
	5. e.
		1. x3010 = xA202
		2. x3013 = x4567
		3. x4567 = 0
---
27. Solution:
	![Solution](_attachments/Pasted%20image%2020250104210625.png)

