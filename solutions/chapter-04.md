# Chapter 04

1. Solution:
	1. Input: Where data imported into the computer. It can be keyboard, mouse, touchscreen etc.
	2. The Control Unit: Where the computer controls processes' orders and timings.
	3. The Processing Unit: Where the computations happen.
	4. Memory: Where the data and program stored.
	5. Output: Where the data exported to the user.
---
2. When memory read enabled, processing unit gets data with read operation in MAR, and fetch data from that address and put into MDR. And when after made operation, it writes output to another MDR or an address specified with MAR in memory.
---
3. Because it doesn't count the program, it is keeping the memory address of the next instruction to process.
---
4. Solution:
	1. Word length of a computer is a size of a data that a ALU can do an operation with it.
	2. If word length longer, computer can compute more data with a single instruction. It makes computer faster.
	3. Actually not, it means it can be faster while computing same amount of data.
---
5. Solution:
	1. Solution:
		1. Location 3: 0000 0000 0000 0000
		2. Location 6: 1111 1110 1101 0011
	2. Solution:
		1. Location 0: 7747. Location 1: -4509
		2. Location 4: 65
		3. 1.0110011111111011010011 * 2^-114
		4. Solution:
			1. 7747
			2. 61477
	3. ADD R1 to R3 and store value to R7
	4. It stores 6 as a decimal data which is the location 6: 1111 1110 1101 0011.
---
6. Opcode and operands. Opcode is what the instruction will do (operation) and, operands which memory addresses it use the operation and result.
---
7. -32768 to 32767.
---
8. Solution:
	1. 8 bits.
	2. 7 bits.
	3. 3 bits.
---
9. Updating the PC(Program counter). Program counter incremented to point to memory address of next instruction. So at the next cycle the next instruction will be processed.
---
10. Solution:
	![Solution](_attachments/Pasted%20image%2020241129160151.png)
---
11. Solution:
	1. Fetch: Load the next instruction address from PC to MAR and simultaneously increment PC. After interrogate memory address from MAR and put data into MDR and load IR (instruction register) with this MDR.
	2. Decode: It examines opcode of operation and figure out what microarchitecture wants from CPU with this operation.
	3. Evaluate Address: Computes address of memory location needed for instruction.
	4. Fetch Operands: Obtains needed operands of instruction. It obtained from MDR or memory.
	5. Execute: Complete execution of instruction.
	6. Store Result: Writing result into a MDR or into memory.
---
12. Solution:
	1. ADD:
		1. Fetch: Load the next instruction address from PC to MAR and simultaneously increment PC. After interrogate memory address from MAR and put data into MDR and load IR (instruction register) with this MDR.
		2. Decode: Look first 4 bits which is opcode to figure out which operation requested and look remaining bits to which register will use for result and where is the source of operands.
		3. Evaluate Address: Nothing needed.
		4. Fetch Operands: Get operands from register or memory.
		5. Execute: Complete execution in ALU (and for most today processors write result to MDR).
		6. Store Result: Write result to register.
	2. LDR:
		1. Fetch: Load the next instruction address from PC to MAR and simultaneously increment PC. After interrogate memory address from MAR and put data into MDR and load IR (instruction register) with this MDR.
		2. Decode: Look first 4 bits which is opcode to figure out which operation requested and look remaining bits to which register will use for loaded data and where is the source of data.
		3. Evaluate Address: Find address of source data with adding offset bits to address in PC (program counter).
		4. Fetch Operands: Get source data from evaluated address in previous phase.
		5. Execute: Complete execution with writing obtained data from memory address to result register.
		6. Store Result: Nothing at all.
	3. JMP:
		1. Fetch: Load the next instruction address from PC to MAR and simultaneously increment PC. After interrogate memory address from MAR and put data into MDR and load IR (instruction register) with this MDR.
		2. Decode: Look first 4 bits which is opcode to figure out which operation requested and, look 3 bits after that for if is condition satisfied. If it is not satisfied instruction won't do anything at all. If it is satisfied there will be an execution phase.
		3. Evaluate Address: Nothing at all.
		4. Fetch Operands: Nothing at all.
		5. Execute: Add offset bits to memory address of next instruction in PC.
---
13. Solution:
	1. X86: 303
		1. Fetch: 100
		2. Decode: 1
		3. Evaluate Address: 1
		4. Fetch Operands: 100
		5. Execute: 1
		6. Store Result: 100
	2. LC-3: 104
		1. Fetch: 100
		2. Decode: 1
		3. Evaluate Address: -
		4. Fetch Operands: 1
		5. Execute: 1
		6. Store Result: 1
---
14. Wrong example. Not updated question
---
15. Any instruction. It is not about instruction, it is about clock cycle.
---
16. Solution:
	1. 5 * 10^8
	2. 0.625 * 10^8
	3. 5 * 10^8
---
17. Solution:
	![Solution](_attachments/Pasted%20image%2020241129213750.png)
---
18. Solution:
	![Solution](_attachments/Pasted%20image%2020241129220058.png)

	[falstad link | Live Circuit](https://www.falstad.com/circuit/circuitjs.html?ctz=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)
---
19. Solution:
	![Solution](_attachments/Pasted%20image%2020241129220756.png)
