# Chapter 07

1. xA7FE
---
2. x23FF
---
3. "AND" is a reserved word for LC-3 assembler, so it can't be used for any other purposes. If it used, assembler takes AND as a opcode, not label; so it will throw an error in the second pass.
---
4. Solution:
   | SYMBOL | ADDRESS |
   | ------ | ------- |
   | SAVE3 | x3029 |
   | SAVE2 | x302A |
   | TEST | x301F |
   | FINISH | x3027 |
---
5. It multiply x0004 with x0803. Result will be x200C.
---
6. Solution:
   1. A: 0010 0010 0000 1000
   2. B: 0001 0010 0111 1111
   3. D: 0000 0011 1111 1101
   4. It sums odd numbers between 0 to E.
---
7. Solution:

```
                .ORIG   x3000
                AND     R4, R4, TOTALBITCOUNT
                AND     R3, R3, #0 (ONECOUNT)
                AND     R2, R2, #0 (TEMP)
                ADD     R1, R1, TESTNUMBER
                ADD     R0, R0, NUMBER
                BRn     NEGNUMLOOP
                BRzp    POSNUMLOOP
NEGNUMLOOP      ADD     R3 R3 #1
                ADD     R4 R4 #-1
                NOT     R0 R0
                BRnzp   POSNUMLOOP
POSNUMLOOP      ADD     R0 R0 R0
                ADD     R4 R4 #-1
                BRz     DONE
                AND     R2 R1 R0
                BRzp    POSNUMLOOP
                ADD     R3, R3, #1
                BRnzp   POSNUMLOOP
DONE            HALT
NUMBER          .BLKW   1
TOTALBITCOUNT   .FILL   x0010
TESTNUMBER      .FILL   x8000
```
---
8. Solution:
   1. R0: 0xA400
   2. R1: 0x23FF
   3. R2: 0xE1FF
   4. R3: 0xA402
---
9. .END pseudo-op is just for indicator to tell the assembler program ends at that point but it doesn't actually terminates the program it even won't existing in runtime. But halt terminates the program.
---
10. Literal #30, exceeds range of literal of ADD operation. ADD operation literal can be -16 to 15. Assembler will detect incorrect use of literal, so it will be detect when assembling.
---
11. Not try to solve. It'll take too much time.
---
12. It shifts left.
---
13. There is no SUM label and it will be detected at the assembly time because assembler wants to change this label with actual values. Also R1 is not initialized before being used. This will may occur wrong results and it will be debugable at the runtime.
---
14. Solution:
    1. a.
       1. 1011 0000 0000 0010
       2. 1111 0000 0010 0001
       3. 1111 0000 0010 0101
       4. 0000 0000 0010 0101
    2. Instead of use STI it should use LD. Because TRAP instruction uses register to display. STI uses for storing data from register to memory not to load data from memory to register to use for TRAP.
    3. Because of use STI, TRAP doesn't get any data for displaying. So it will be probably display nothing.
---
15. It checks the MSB of the numbers and if they are positive, it doubles and store backs to their original memory address.
---
16. It finds to if number is even or odd.
---
17. It won't be problem because each module has own symbol table and assembler only checks external modules if an address labeled as EXTERNAL.
---
18. Solution:
    1. a. LDR R3 R0 #0
    2. b. NOT R3 R3
    3. c. ADD R3 R3 #1
---
19. The DATA labeled address holds #11, and the loop cycle decrements by 3 in every loop, so it will be executed only 4 times.
---
20. First one dynamically initialize value in runtime, but the second one initialize value at the assembly time.
---
21. It counts negative numbers between x4000 and x400A and stores count at the x5000.
---
22. Not try to solve. It'll take too much time.
---
23. Solution :
    1. ADD R1 R1 #-1
    2. LDR R4, R1 #0
    3. ADD R0, R0, #1
    4. ADD R1, R1, #-1
    5. BRnzp LOOP
---
24. Because first line of LOOP doesn't check the R2 which is for tracking shift count. Lines of ADD R2, R2, #-1 and ADD R3, R3, R3 should change their positions.
---
25. It'll give assembly error because it exceed LC-3's memory address capacity.
---
26. They'll give same output. Only difference is label naming and this doesn't affect the execution of program.
---
27. Solution:
    1. Can't figure out
    2. Can't figure out.
    3. R1 shift count
    4. R6 holds shifted value/result.
---
28. Can't solve.
---
29. Solution:
    1. a: x1801, d: x1802, f: x1800, h: x1803, I: x0ffd
---
30. Can't solve.
---
31. It counts odd integers between x5000 and x6000 memory addresses.
---
32. Solution:
    1. x8006: 0010001000000011
    2. x8007: 0000010000000001
    3. x8008: 0011000000000010
    4. Line 10 sets #5 at assembly time, but line 7 sets #5 dynamically at runtime.
---
33. Solution:
    1. ADD R2, R2, #1
    2. ADD R0, R1, R0
    3. It is trying to divide a number to another number and find quotient.
    4. It shouldn't do BRnzp AGAIN, it should do BRp AGAIN and add BRn DONE and subtract quotient (result) by 1 at that branch for correct result.
---
34. Solution:
    1. NOT R2, R0
    2. ADD R2, R2, #1
    3. BRz DONE
    4. ADD R0, R0, #1
---
35. Solution:
	![Solution](_attachments/Pasted%20image%2020250110232306.png)
---
36. Solution:
    1. R0 = A, R1 = B, R2 = -B
    2. At the line 10, instead of ST it should be STI.
---
37. Solution:
    ![Solution](_attachments/Pasted%20image%2020250110234939.png)
