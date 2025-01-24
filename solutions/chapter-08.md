# Chapter 08

1. It works with last-in first-out mechanism. So when you insert an element, it adds to the top of the list, and when you get an element from the list, it gives you the last element you added.
---
2. Require way less operation to adding and removing data from stack.
---
3. Solution:
   1. POP R7
   2. POP R0
   3. PUSH R1
   4. PUSH R3
---
4. Solution:
   1. ST R1 S1
   2. ST R2 S2
   3. LD R1 EMPTY
   4. ADD R2 R6 R1
   5. BRz UNDERFLOW
   6. LDR R0 R6 #0
   7. RET
---
5. Partial solution:

```assembly
POP     AND	    R5,	R5,	#0
        ST	    R1,	Save1
        ST      R2, Save2
        ST      R3, Save3
        LDR	    R1,	TOP, #0
        NOT     R1, R1
        ADD     R1, R1, #1          ; NEGATIVE OF TOP
        LDR     R2, BOTTOM, #0
        ADD     R2, R1, R2          ; R2 will be 0 (which means stack full) or a
                                    ; positive value which means current stack
                                    ; element count.
        BRz     UNDERFLOW
                                    ; THE ACTUAL "POP" STARTS
        LDR     R0, TOP, #0         ; R0 holds value of TOP address. (Popped element)
        LD      R3, BOTTOM          ; R3 holds bottom address.
        ADD     R4, R3, #-1         ; Decrease by 1 address of the end of the stack
        ST	    R4,	BOTTOM,	#0      ; Store new end of stack address.

SHIFTLOOP                           ;
        LDR     R1, R3, #0          ; Load from end of the stack.
        STR     R1, R3, #-1         ; Move end of stack the previous address
        ADD     R3, R3, #-1         ; Decrease by 1 address of the end of the stack
        ADD     R2, R2, #-1         ; Decrease element count in stack.
        BRz     SHIFTENDED
        BRnzp   SHIFTLOOP

SHIFTENDED
        LD      R1, Save1           ; Restore original values
        LD      R2, Save2           ; Restore original values
        LD      R3, Save3           ; Restore original values
        RET

UNDERFLOW
        LD      R1, Save1           ; Restore original values
        LD      R2, Save2           ; Restore original values
        LD      R3, Save3           ; Restore original values
        ADD     R5, R5, #1          ; Failure

TOP     .FILL	xC000
BOTTOM  .FILL	xC005
Save1   .FILL	x0000
Save2   .FILL	x0001
Save3   .FILL	x0001
```

---
6. Solution:

```assembly
PUSH    ADD R6, R6, #-2
        STR R0, R6, #0
        STR R1, R6, #0

POP     LDR R0, R6, #0
        LDR R1, R6, #0
        ADD R6, R6, #2
```

---
7. Solution:

```assembly
POP             AND     R5,R5,#0 ; R5 <-- success
                ST      R1,Save1 ; Save registers that
                ST      R2,Save2 ; are needed by POP
                LD      R1, COUNT    ; R1 <-- Current element count
                LD      R2, CAPACITY ; R2 <-- Negative stack capacity
                ADD     R3, R1, R2
                NOT	    R3,	R3
                ADD     R3, R3, #1
                ADD	    R3,	R3,	R2  ; If count + (-capacity) + capacity = 0,
                                    ; it means stack is empty.
                BRz     fail_exit
                ;
                LDR     R0,R6,#0 ; The actual "pop"
                ADD     R6,R6,#1 ; Adjust stack pointer
                BRnzp   success_exit
                ;
PUSH            AND     R5,R5,#0
                ST      R1,Save1 ; Save registers that
                ST      R2,Save2 ; are needed by PUSH
                LD      R1, COUNT    ; R1 <-- Current element count
                LD      R2, CAPACITY ; R2 <-- Negative stack capacity
                ADD	    R3,	R1,	R2  ; If count + (-capacity) = 0,
                                    ; it means stack is full.
                ;
                ADD     R6,R6,#-1 ; Adjust stack pointer
                STR     R0,R6,#0 ; The actual "push"
success_exit    LD      R2,Save2 ; Restore original
                LD      R1,Save1 ; register values
                LD      R3,Save3
                RET
                ;
fail_exit       LD      R2,Save2 ; Restore original
                LD      R1,Save1 ; register values
                LD      R3,Save3
                ADD     R5,R5,#1 ; R5 <-- failure
                RET
                ;
BASE            .FILL   xC006   ; Start address of stack
COUNT           .FILL	xC007   ; Element count of stack at the moment
CAPACITY        .FILL   xC008   ; Negative stack capacity
Save1           .FILL   x0000
Save2           .FILL   x0000
Save3           .FILL   x0000
```

---
8. Solution:
   1. F and A.
   2. After PUSH J and PUSH K.
   3. Just M.
---
9. Solution:
   1. BDECJKIHLG
   2. PUSH Z, PUSH Y, POP, PUSH X, POP, PUSH W, PUSH V, POP, PUSH U, POP, POP, POP, PUSH T, PUSH S, POP, PUSH R, POP, POP
   3. Number of valid output permutations is determined by the Catalan number for the given input length. The Catalan number 5 is 14.
---
10. I couldn't understand how this question works.
---
11. Solution:
    1. 16.
    2. x400F
    3. Average of 4 consecutive values in memory.
---
12. I couldn't understand how this question works.
---
13. Solution:

```assembly
FACT    ST  R1,SAVE_R1
        ADD R1,R0,#0
        BRz ZERO
        ADD R0,R0, #-1
        BRz DONE
        BRnzp AGAIN
ZERO    ADD R0, R0, #1
        BRnzp DONE
AGAIN   MUL R1,R1,R0
        ADD R0,R0,#-1 ; R0 gets next integer for MUL
        BRnp AGAIN
DONE    ADD R0,R1,#0 ; Move n! to R0
        LD  R1,SAVE_R1
        RET
SAVE_R1 .BLKW 1
```

---
14. Partial Solution:
    1.  JSR X
    2.  LDR R1, R3, #1
    3.  LDR R2, R4, #1
    4.  ADD R1, R1, R0
    5.  STR R0, R5, #1
    6.  -
    7.  -
    8.  -
---
15. This problem would not belong to Chapter 08.
