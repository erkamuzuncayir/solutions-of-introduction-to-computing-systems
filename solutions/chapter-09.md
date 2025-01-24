# Chapter 09

1. Solution:
   1. Device register is a register for used I/O operations of that specific I/O device.
   2. Device data register is a register that holds relevant data of that specific I/O device. It uses for storing or loading data from/to device.
   3. Device status register is a register that holds operational status of that specific device. That stores information of availability or state of the operation. It needed for synchronization of I/O device and processor.
---
2. Because if synchronous I/O is used, processor will always be ready for new data from I/O device at the moment when I/O device send new data, so there is no need for ready bit.
---
3. At least 303030304/minute.
---
4. Solution:
   1. Synchronous
      1.
   2. Asynchronous
   3. Synchronous
   4. If the subject of the interaction is able to respond to the interaction instantaneously, we are talking about a synchronous interaction. but if the response of the subject to the interaction depends on a cue left by the first subject, this is an asynchronous interaction.
---
5. It is ready bit of keyboard device. It represents validity the current value of KBDR. If KBSR[15] is 1 that means value in KBDR is the ASCII code of last struck key, if it is 0 that means value in KBDR is not valid.
---
6. It can re-read data that has already been read on the previous input.
---
7. Memory mapped and polling. Memory mapped because KBDR load/saved from a specific address and processor continuously checks the KBSR value to see if there has been an input.
---
8. Solution:

```assembly
        LDR     R0, MEMADDR, #0
        LDI     R1, MASK
        AND	R2, R0, R1
        BRnp    INVALID
        ADD     R3, R0 #-32
        BRnz    INVALID
        TRAP    x25
INVALID TRAP	HALT

MEMADDR         .FILL   x4000
MASK            .FILL   xFF00
```

---
9. It may overwrite input that previously entered and not processed by the processor yet.
---
10. It may overwrite output that previously send and not showed the user yet.
---
11. Interrupt-driven way more efficient. Because in polling, processor have to constantly check for specific register (ready bit) for that I/O device to not miss any I/O operation from that device and this costs lots of processor cycle. But in interrupt-driven it doesn't have to that. Instead, it's just doing other instructions until get an interrupt signal from I/O device.
---
12. Solution:

```assembly
START   LDI     R1, KBDR ; Test for
        BRz     START ; character input
        LDI     R0, KBDR
        AND     R1, R1, #0
        STI     R1, KBDR
        BRnzp   NEXT_TASK ; Go to the next task
KBDR    .FILL   xFE02 ; Address of KBDR
```

---
13. They are missing interrupt enable (IE) bits for both devices. So LC-4 have to use polling method for resolving I/O operations and as explained previously this is not as efficient as interrupt-driven method which requires interrupt enable bits for I/O devices.
---
14. LC-3 has memory-mapped I/O and xFE02 is mapped to use the I/O operations of the KBDR. Therefore, every load operation from xFE02 means as load from KBDR.
---
15. It is abstract complexity of I/O operations and make I/O operations easier for user programmer.
---
16. Solution:
    1.  256. Because LC-3 uses 8 bits trap vector for reaching addresses of service routines and, we can address 256 distinct service routine for 8 bits.
    2.  Because RET instructions pops two values on system stack and, one of the values holds the PC containing the following address of the TRAP instruction and using this PC the processor returns to where it needs to continue. TRAP instructions stores at start of the memory, so the distance between TRAP instructions and where TRAP instruction executed may exceed the range of BR instruction.
    3.  First access while getting address of service routine from TRAP instruction. Second access when this service routine gets control and starts fetch phase of instruction.
---
17. Solution:
    1.  Only an external mechanism can start the clock after the machine is HALTed.
    2.  Setting 0 to MCR[15], halts the machine.
    3.  It'll start from after line 13 where HALT actually happen, line 18.
    4.  It'll return where HALT instruction executed and continue from following instruction.
---
18. Solution:
    1.  1111 0000 0010 0001
    2.  0011 0010 0000 0111
    3.  1100 0001 1100 0000
    4.  HookemHorns
---
19. FUN.
---
20. Solution:

```assembly
        .ORIG   x3000
        LD      R2,UPSTART ; Load uppercase start
        LD      R3,ASCII ; Load ASCII difference
        LD      R4,ALPCOUNT ; Load negative alphabet character count
AGAIN   TRAP    x23 ; Request keyboard input
        ADD     R1,R2,R0 ; Test for uppercase start
        BRn     EXIT ; character
        ADD     R1,R1,R4 ; Subtract alphabet character count
        BRp     EXIT ; If larger than alphabet character
        ADD     R0,R0,R3 ; Change to lowercase
        TRAP    x21 ; Output to the monitor
        BRnzp   AGAIN ; ... and do it again!
UPSTART .FILL   xFFBF ; FFBF is negative of ASCII 41
ALPCOUNT.FILL   xFFE5 ; FFE5 is negative of ASCII 25
ASCII   .FILL   x0020
EXIT    TRAP    x25 ; Halt
        .END
```

---
22. Solution:
    1. a.

```assembly
        .ORIG   x3000
        ST	    R0, SR0
        ST	    R1, SR1
        ST      R2, SR2
        AND	    R1,	R0,	#FFFF
        BRz     NOBUSY
        BRnzp   BUSY
NOBUSY  ADD     R2, R2, #1
BUSY    ST      R2, RESULT
        RET
        LD	    R0,	SR0
        LD	    R1,	SR1
        LD	    R2,	SR2
SR0     .FILL   x0000
SR1     .FILL	x0000
SR1     .FILL	x0000
RESULT  .BLKW	1
        .END
```
2. b.

```assembly
        .ORIG   x3000
        ST	    R0, SR0
        ST	    R1, SR1
        AND     R1, R1, #0
        ADD	    R0,	R0,	#1
        BRz     ALLBUSY
        BRnzp   NOTBUSY
ALLBUSY ADD     R1, R1, #1
NOTBUSY ST      R1, RESULT
        RET
        LD	    R0,	SR0
        LD	    R1,	SR1
SR0     .FILL   x0000
SR1     .FILL	x0000
RESULT  .BLKW	1
        .END
```
3. c.

```assembly
        .ORIG   x3000
        ST	    R0, SR0
        ST	    R1, SR1
        ST	    R2, SR2
        ST      R3, SR3
        ST      R4, SR4
        AND     R3, R3, #0
        AND     R4, R4, #0
        ADD     R4, R4, #16
        LDR     R0, NUMADDR, #0
        LD      R1, MASK
LOOP    AND     R2, R0, R1
        BRn     BUSY
        BRnzp   LOOP
BUSY    ADD     R3, R3, #1
        ADD     R4, R4, #-1
        BRz     DONE
        ADD     R0, R0, R0
        BRnzp   LOOP
DONE    ST      R3, RESULT
        RET
        LD	    R0,	SR0
        LD	    R1,	SR1
        LD	    R2,	SR2
        LD	    R3,	SR3
        LD	    R4,	SR4
SR0     .FILL   x0000
SR1     .FILL	x0000
SR2     .FILL	x0000
SR3     .FILL	x0000
SR4     .FILL	x0000
MASK    .FILL   x8000
NUMADDR .FILL   x4001
RESULT  .BLKW	1
        .END
```
4. d.

```assembly
        .ORIG   x3000
        ST	    R0, SR0
        ST	    R1, SR1
        ST	    R2, SR2
        ST      R3, SR3
        ST      R4, SR4
        AND     R3, R3, #0
        AND     R4, R4, #0
        ADD     R4, R4, #16
        LDR     R0, NUMADDR, #0
        LD      R1, MASK
LOOP    AND     R2, R0, R1
        BRzp    FREE
        BRnzp   LOOP
FREE    ADD     R3, R3, #1
        ADD     R4, R4, #-1
        BRz     DONE
        ADD     R0, R0, R0
        BRnzp   LOOP
DONE    ST      R3, RESULT
        RET
        LD	    R0,	SR0
        LD	    R1,	SR1
        LD	    R2,	SR2
        LD	    R3,	SR3
        LD	    R4,	SR4
SR0     .FILL   x0000
SR1     .FILL	x0000
SR2     .FILL	x0000
SR3     .FILL	x0000
SR4     .FILL	x0000
MASK    .FILL   x8000
NUMADDR .FILL   x4001
RESULT  .BLKW	1
        .END
```
5. e.

```assembly
        .ORIG   x3000
        ST	    R0, SR0
        ST	    R1, SR1
        ST	    R2, SR2
        ST      R3, SR3
        ST      R4, SR4
        AND     R3, R3, #0
        AND     R4, R4, #0
        ADD     R4, R4, #16
        LDR     R0, NUMADDR, #0
        NOT     R5, R5
        ADD     R5, R5, #1
        ADD     R4, R4, R5
        LD      R1, MASK
LOOP    ADD     R0, R0, R0
        ADD     R4, R4, #-1
        BRz     CHECK
        BRnzp   LOOP
CHECK   AND     R2, R0, R1
        BRn     BUSY
        BRnzp   DONE
BUSY    ADD     R3, R3, #1
DONE    ST      R3, RESULT
        RET
        LD	    R0,	SR0
        LD	    R1,	SR1
        LD	    R2,	SR2
        LD	    R3,	SR3
        LD	    R4,	SR4
SR0     .FILL   x0000
SR1     .FILL	x0000
SR2     .FILL	x0000
SR3     .FILL	x0000
SR4     .FILL	x0000
MASK    .FILL   x8000
NUMADDR .FILL   x4001
RESULT  .BLKW	1
        .END
```
6. f

```assembly
        .ORIG   x3000
        ST	    R0, SR0
        ST	    R1, SR1
        ST	    R2, SR2
        ST      R3, SR3
        AND     R3, R3, #0
        LDR     R0, NUMADDR, #0
        LD      R1, MASK
LOOP    ADD     R3, R3, #-1
        AND     R2, R0, R1
        BRn     BUSY
        BRnzp   LOOP
BUSY    AND     R2, R2, #0
        ADD     R2, R2, #16
        ADD     R2, R2, R3
        BRz     DONE
        ADD     R0, R0, R0
        BRnzp   LOOP
DONE    ST      R2, RESULT
        RET
        LD	    R0,	SR0
        LD	    R1,	SR1
        LD	    R2,	SR2
        LD	    R3,	SR3
SR0     .FILL   x0000
SR1     .FILL	x0000
SR2     .FILL	x0000
SR3     .FILL	x0000
MASK    .FILL   x8000
NUMADDR .FILL   x4001
RESULT  .BLKW	1
        .END
```
---
23. Solution:
    1.  We can use 256 bit memory addresses for TRAP instructions. In total, if each instruction will use at most 16 bit addresses, we can have at most 16 trap instructions in total. In this case we can reduce the trap vector from 8 bits to 4 bits. By shifting the trap vector 4 bits to the left we can find the starting address of the routine of each instruction.
---
24. BUFFER will override CADDR address and OADDR because program starts from x3000 and buffer take #1001 amount of address.
---
25. It is bubble sort algorithm with ascending order. DATA'll be sorted in ascending order.
---
26. JSR return address is didn't store in R7. JSR have to has return address for returning subroutine. That's way program not working.
---
27. If there is an external mechanism re-run the clock, processor can restore previous data of registers that used in HALT instruction and return the where HALT instruction called. This can be used for debugging and troubleshooting.
---
28. Solution:
    1.  TRAP x72
    2.  It'll work, but it can overwrite R0. Because it doesn't save and restore R0 in routine.
---
29. Solution:
    1.  Assembler can't put x30000 instead of VALUE, it exceeds memory bits limit of LC-3, so it'll be detected in assembly time.
    2.  R0 isn't reset by AND operation in SQRT, so each operation can return by adding the result with the previous value.
---
30. Solution:
    1.  ADD R1, R1, #1
    2.  Can't solve.
    3.  Can't solve.
    4.  BRzp K
---
31. Solution:
    1.  It is set the interrupt enable (IE) bit to 1 and '2' is repeatedly printed to screen.
    2.  Input echoed 2 times to screen.
    3.  Couple of times '2' printed and then struck key printed and then continue to print '2'.
    4.  Because IE bit is set to 1 and this makes getting new input inconsistent between two input.
---
32. I don't want to show any example but, when processor returned an interrupt routine and following instruction is BR and if condition codes didn't save, program may continue incorrectly.
---
33. Solution:

```
|   x6311               |
|   PSR for device C    |
|   x6203               |
|   PSR for device B    |
|   x3007               |
|   PSR of program A    |
|   ////////////////    |
```
---
39. Solution:

```assembly
            .ORIG	x3000
            LDI     R1, BUFFPOINT
            LD      R2, BUFFEND
            ADD     R3, R1, R2
            BRp     BUFFERFULL
            LDI     R0, KBDR
            STR     R0, BUFFPOINT
            ADD     R1, R1, #1
            ST      R1, BUFFPOINT
            BRnzp   DONE
BUFFERFULL  LEA	    R0,	FULLPROMPT
            TRAP    x22
            BRnzp   DONE
DONE        RTI
BUFFSTART   .FILL   x4000
BUFFEND     .FILL   x-40FE
BUFFPOINT   .FILL   x40FF
KBDR        .FILL	xFE02
FULLPROMPT  .STRINGZ "Character cannot be accepted; input buffer full."
.END
```

---
41. If an interrupt routine occurs and at the beginning of the interrupt, the routine saves the number of characters in the buffer, x40FD, so as not to lose it, and also uses this buffer and at the end of the interrupt reloads the first saved value of x40FD, the wrong value will be loaded.
---
42. Solution:
    1.  Processor may not work from where the interrupt service call occurs due to not getting PC from supervisor stack.
    2.  Also, if there is a BR instruction at the point where the interrupt service call occurs, it cannot keep the correct condition codes because it has not received a PSR.
---
43. Solution:
    1.  AND R2, R2, R1
    2.  ADD R2, R2, R2
    3.  ADD R2, R2, R2
    4.  LDI R0, R0, #0
---
44. Solution: (The statement of this problem is incorrect.)
    1.  At the x009A: JSR #1FBB
    2.  ST R0, SaveR0
    3.  ADD R0, R1, R0
    4.  LD R0, SaveR0
    5.  .FILL xFFE0
    6.  SaveR0
---
45. Solution:
    1.  LEA R0, INPUT
    2.  ADD R6, R6, R0
    3.  LDR R0, R6, #2
    4.  S0
    5.  S1
    6.  x0063
---
46. Solution:
    1.  Mem Addr: x0050 and x0060. Content: x1000 and x2000
