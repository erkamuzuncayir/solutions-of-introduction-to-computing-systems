# Chapter 19

1. Missing memory allocation statement.
    `getdata = (struct node *)malloc(sizeof(struct node *));`

---
2. Solution:
```assembly
LDI R0 GETDATA_POINTER #0
LDR R1, R0, NEXT_PROPERTY_OFFSET
STR R1, R0, #0

GETDATA_POINTER       .BLKW 1
NEXT_PROPERTY_OFFSET  .FILL -3
```

---
3. Two nested loop with traversing all array, so n^2.

---
4. Solution:
        1. Frame pointer, return address of main, return value and 1 for parameter `Element *t`.
        2. 2972. 110 Element * Each of them holds 27 value = 2970 for `periodic_table`, 1 for `x`, 1 for `y`.
        3. `x = NobleElement(&periodic_table[y]);`

---
5. Solution:
        1. a.
            1. j
            2. i
            3. pat
            4. ptr
            5. saved frame pointer
            6. saved return address
            7. return value
    2. `NULL 1 2 3`

---
6. Can't solve !_!.
