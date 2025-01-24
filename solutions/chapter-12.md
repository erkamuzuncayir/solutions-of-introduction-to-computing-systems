# Chapter 12

1. Solution:

| Identifier | Type   | Location | Scope |
| ---------- | ------ | -------- | ----- |
| ff         | double | 0        | block |
| cc         | char   | -1       | block |
| ii         | int    | -2       | block |
| dd         | char   | -3       | block |
| zz         | bool   | -4       | block |

---
2. Solution:
   1. It won't initialize a default value due to local scope.
   2. It will be initialized as a '0' due to `int` type of variable.
---
3. Solution:
   1. -2,147,483,648 to 2,147,483,647
   2. 0 to 4,294,967,295
---
4. Solution:
   1. 0.00000000111
   2. -2.1
   3. 101.101
---
5. Solution:

```assembly

LDR R0 ASCII_a #0
STR R0 R5 #0 ; char c

AND R0, R0, #0
ADD R0, R0, #3 ; int x
STR R0, R5, #-1

AND R0, R0, #0
ADD R0, R0, #10 ; int z
STR R0, R5, #-3

```

---
6. 2, 2, 3, 3

---
7. Solution:
   1. 15
   2. 1 or TRUE
   3. 0
   4. 1 or TRUE
   5. 0 or FALSE
   6. 6
   7. 1
   8. 9
   9. 5
   10. a = 7, b = 8
   11. 10
   12. 3072
---
8. Solution:
   1. `(letter >= '0' && letter <= '9' || letter >= 'letter' && letter <= 'Z' || letter >= 'letter' && letter <= 'z')`
   2. `!(letter >= '0' && letter <= '9' || letter >= 'letter' && letter <= 'Z' || letter >= 'letter' && letter <= 'z')`
---
9. Solution:
   1. It checks if the letter is lowercase and if it is, it assigns '!' to it, otherwise it assigns itself again.
   2. `letter = ((letter >= 'a' && letter <= 'z') ? letter - 32 : letter);`
---
10. Solution:

```c
#include <stdio.h>

int main()
{
	int input;

	printf("Please enter an input:\n");
	scanf("%d", &input);

	_Bool result = (input % 3) == 0 ? 1 : 0;

	printf("%d", result);
}
```

---
11. Solution:

    1. i = 2, j = 1. First assign `i` to `j` and then increment `i`.
    2. i = 2, j = 2. First increment `i` then assign `i` to `j`.
    3. i = 2, j = 1. First assign `i` to `j` and then increment `i`.
    4. i = 2, j = 0. Increment `i`.
    5. i = 2, j = 2. First increment `i` then assign `i` to `j`.

---
12. Solution:

---
13. 1.

```assembly
AND R0, R0, #0
AND R1, R1, #0

LDR R0, R5, #0
LDR R1, R5, #-1

ADD R0, R0, R1
STR R0, R5, #-2
```

---
12. 2.

```assembly
AND R0, R0, #0
AND R1, R1, #0

LDR R0, R5, #0
LDR R1, R5, #-2

ADD R0, R0, R1
STR R0, R5, #-4

LDR R0, R5, #-1
LDR R1, R5, #-3

ADD R0, R0, R1
STR R0, R5, #-4

```

---
13. All the same except result is 6.

---
14. Solution:

    1. `machineBusy &= ~(1 << 4)`
    2. `machineBusy |= (1 << 9)`
    3. `machineBusy &= ~(1 << (input - 1))`
    4. `(machineBusy >> 2) & 1`
    5.

```c
#include <stdio.h>

int main()
{
	int machine = 61166;
    int idleMachineCount = 0;
    for (int i = 0; i < 16; i++)
        idleMachineCount += (machine >> i) & 1;

	printf("%d", idleMachineCount);
}
```

---
15. Semicolon terminates statement in C.

---
16. Solution:

    1. `((((w @ x) # y) $ z) U)`
    2. `((w @ (x # y)) ($ (z U)))`
    3. `((((w @ x) # y) $ z) U)`
    4. `(w @ (x # (y $ (z U))))`

---
17. Solution:

    1. It will remain unchanged.
    2. `x = (x + 1)`

---
18. Solution:

```c
#include <stdio.h>

int main(void)
{
    int counter;
	char startPoint;
	char stopPoint = '!';

	printf("Enter a character: ");
	scanf("%c", &startPoint);

	for (counter = startPoint; counter >= stopPoint; counter--)
		printf("%c\n", counter);
}
```
---
19. Solution:

```c
#include <stdio.h>

int main(void)
{
	float amountOfPurchase;
	float taxRate;

	printf("Enter amount of purchase: ");
	scanf("%f", &amountOfPurchase);

	printf("Enter tax rate: ");
	scanf("%f", &taxRate);

	float amountOfTax = amountOfPurchase * (taxRate / 100);
	float totalAmountIncludingTax = amountOfPurchase + amountOfTax;

	printf("Amount of tax is %f and total amount of purchase including tax is %f",
	        amountOfTax, totalAmountIncludingTax);
}
```

---
20. Solution
    1. a.

```c
#include <stdio.h>

int main(void)
{
	int x = 3;
	int y = 4;
	int temp = 0;

	temp = y;
	y = x;
	x = temp;
	printf("x: %d, y: %d", x, y);
}
```
2. b.

```c
#include <stdio.h>

int main(void)
{
	int x = 3;
	int y = 4;

	x++;
    y--;
	printf("x: %d, y: %d", x, y);
}
```
