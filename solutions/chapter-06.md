# Chapter 06
1. Yes, an algorithm is defined a step by step procedure that will terminate eventually. We can create a procedure that doesn't end with 3 basic constructs and won't be a algorithm. Here it is;
	1. x3000: AND R0 R0 #0
	2. x3001: BRZ #-1
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
5. 88 * 3. Because it needs less operation count.
6. Solution:
	1. First
		1. Start
		2. Operation
			1. Multiply two numbers
		3. Stop
	2. Second
		1. Start
		2. Initialize
		3. Operation
			1. Find smaller number
			2. Sum result with bigger number
			3. Decrement smaller number by 1
			4. If smaller number bigger than 0 return to instruction 2 before.
			5. Else you found the result
		4. Stop
	3. Third
		1. Start
		2. Initialize
			1. LDI R1 SEC_NUM
			2. LDI R2 FRS_NUM
			3. AND R0 R0 #0
			4. AND R4 R4 #0
			5. AND R5 R5 #0 (SMALL_NUM)
			6. AND R6 R6 #0 (BIG_NUM)
			7. AND R7 R7 #0 (RESULT)
		3. Operation
			1. NOT R4 R2
			2. ADD R4 R4 #1
			3. ADD R5 R1 R4
			4. BRn #7
			5. BRp #3
			6. ADD R6 R2 #0
			7. ADD R5 R1 #0
			8. BRnzp DETERMINE_IF_SMALLER_POSITIVE
			9. ADD R6 R1 #0
			10. ADD R5 R2 #0
			11. BRnzp DETERMINE_IF_SMALLER_POSITIVE
			12. ADD R6 R2 #0
			13. ADD R5 R1 #0
			14. [DETERMINE_IF_SMALLER_POSITIVE] BRn SMALLER_NEGATIVE_LOOP_START
			15. BRp SMALLER_POSITIVE_LOOP_START
			16. BRnzp RESULT (this means if smaller not positive or negative, so smaller is zero so the result is too.)
			17. [SMALLER_NEGATIVE_LOOP_START] ADD R7 R6 #0
			18. ADD R5 R5 #1 (increment negative smaller number)
			19. BRn [SMALLER_NEGATIVE_LOOP_START]
			20. BRnzp RESULT
			21. [SMALLER_POSITIVE_LOOP_START] ADD R7 R6 #0
			22. ADD R5 R5 #-1 (decrement positive smaller number)
			23. BRp [SMALLER_POSITIVE_LOOP_START]
			24. BRnzp [RESULT]
			25. [RESULT] (Result is R7)
		4. Exit
7. It sums correspending elements of specific lengthed two list (i guess) and store them.
8. R2 might be populated previously and result might be uncorrect due to this.
9. Solution:
	1. AND R0 R0 #0
	2. LD R0 [SOMEADDRESSHAVE100]
	3. [ITERATIVE_START] TRAP DISPLAY 'Z'
	4. ADD R0 R0 #-1
	5. BRzp [ITERATIVE_START]
	6. HALT
10. Solution:
	1. AND R0 R2 #1
	2. BRz [RESULT_EVEN]
	3. BRnp [RESULT_ODD]
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
12. Solution:
	1. a.
		1. TRAP GET_INPUT
		2. TRAP DISPLAY_INPUT
	2. b.
		1. TRAP GET_INPUT
		2. ADD INPUT INPUT #-6
		3. BRz DISPLAY_PREVIOUS_INPUT
13. Solution:
	1. AND R0 R0 #0
	2. AND R1 R1 #0
	3. LD R0 x3100
	4. [LOOP_START] ADD R0 R0 #-2
	5. BRnz [DONE]
	6. ADD R1 R1 #1
	7. BRnzp [LOOP_START]
	8. [DONE] ST R1 x3100
14. 9,10,11.