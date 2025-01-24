# Chapter 13

1. Solution:

| Identifier | Type | Location | Scope |
| ---------- | ---- | -------- | ----- |
| operand1   | int  | 0        | main  |
| operand2   | int  | -1       | main  |
| result     | int  | -2       | main  |
| operation  | char | -3       | main  |

---
2. Solution:

	1. a.

```c
if (VERO)
    printf("True!");
else
    printf("False!");
```

2. b. Prints true.
3. c. Doesn't change because when first condition is satisfied processor exits if-else block.

---
3. Solution:

```c
if(a)
    x = b;
else
    x = c;
```

---
4. Solution:

	1. a.
		1. 1. 1. x = 1: `printf("x does not equal 0\n");`
		2. 1. 2. x = 0: `printf("x equals 0\n");`
	2. b.
		1. 2. 1. x = 1: `printf("x does not equal 0\n");`
		2. 2. 2. x = 0: `printf("x equals 0\n");`
	3. c.
		1. 3. 1. x = 1: `A`
		2. 3. 2. x = 0: `D`
	4. d.
		1. 4. 1. x = 1: `4`
		2. 4. 2. x = 0: `4`

	5. e. Default condition'll satisfied and `y` will be 5.

---
5. Solution:

```assembly
                LDR R0, R5, #0 ; Gets x
                LDR R1, R5, #-1 ; Gets y
                
                AND R2, R2, #0
                ADD R2, R0, R2
                BRz CASE_ZERO_OK
                BRnzp CASE_ONE_CHECK
CASE_ZERO_OK    AND R3, R3, #0
                ADD R3, R3, #3
                STR R3, R5, #-1 ; Sets 3 to y.
CASE_ONE_CHECK  AND R2, R2, #0
                ADD R2, R2, #-1
                ADD R2, R0, R2
                BRz CASE_ONE_OK
CASE_ONE_OK     AND R3, R3, #0
                ADD R3, R3, #4
                STR R3, R5, #-1 ; Sets 4 to y.
                BRnzp DONE
CASE_DEF        AND R3, R3, #0
                ADD R3, R3, #5
                STR R3, R5, #-1 ; Sets 5 to y.
                BRnzp DONE
DONE            HALT
```

---
6. Solution:

	2. b. Program:

```c
#include <stdio.h>

int main()
{

	int n = 0;
	int input;
	int nMinusOne = 1;
	int nMinusTwo = 1;

	scanf("%d", &input);

	for(int i = 2; i <= input; i++)
	{
		n = nMinusOne + nMinusTwo;
		nMinusTwo = nMinusOne;
		nMinusOne = n;
	}

	printf("%d", n);
	return 0;
}
```

---
7. No, due to not using literal in comparison `else if (x == y)` statement can't convert to a switch condition.

---
8. Solution:

	1. 0.
	2. 1.
	3. 0.
	4. 1.

---
9. Solution:

	1. 0.
	2. 0.
	3. 11 4.

---
10. Solution:

```c
_Bool isLess = count < terms;

switch(isLess)
{
    case true:
        // Evaluate another term
        // count ++;
        break;
    case false:
        break;
}
```

---
11. Solution:

```C
#include <stdio.h>
#include <stdbool.h>

int main()
{
	char nextChar;
    bool firstAlphabetic = false, secondAlphabetic = false, thirdAlphabetic = false;
    bool gotAt = false, gotDot = false, isValid = false;

	printf("Enter your e-mail address: ");

	do {
		scanf("%c", &nextChar);

		if (nextChar >= 'a' && nextChar <= 'z' || nextChar >= 'A' && nextChar <= 'Z') {
			if (!firstAlphabetic) {
				firstAlphabetic = true;
			} else if (gotAt && !secondAlphabetic) {
				secondAlphabetic = true;
			} else if (gotDot && !thirdAlphabetic) {
				thirdAlphabetic = true;
				isValid = true;
			}
		} else if (nextChar == '@' && firstAlphabetic && !gotAt) {
			gotAt = true;
		} else if (nextChar == '.' && gotAt && !gotDot) {
			gotDot = true;
		}
	} while (!isValid && nextChar != ' ' && nextChar != '\n');

	if(isValid)
		printf("Your e-mail address appears to be valid.\n");
	else
		printf("Your e-mail address is not valid!\n");
}
```
---
12. Solution:

	1. False.
	2. Because it will cause integer overflow and x will be a negative number and condition will eventually be unsatisfied.
	3. 4

---
13. Solution:

```c
#include <stdio.h>

int main()
{
	int sum;
	int i = 0;

	do {
		if (i % 4 == 0)
			sum = sum + 2;
		else if (i % 4 == 1)
			sum = sum - 6;
		else if (i % 4 == 2)
			sum = sum * 3;
		else if (i % 4 == 3)
			sum = sum / 2;
		i++;
	}
	while (i <= 100);

	printf("%d\n", sum);
}
```

---
14. Solution: 

```c
#include <stdio.h>

int main()
{
	int input;
	printf("Please enter a number: ");
	scanf("%d", &input);

	for(int i = 1; i <= input; i++)
	{
		for(int j = 0; j < i; j++)
		{
			printf("%d", i);
		}
		for(int k = input - i; k < 0; k--)
		{
			printf("/t");
		}
		printf("\n");
	}
}
```

---
15. Solution:

	1. a.

```c
for(true; condition; true)
    // loopBody;
```

2. b.

```c
// init
int i = 0;

while(condition)
{
    // loopBody
    
    // update
    i++;
}
```

---
16. sum + 650

---
17. It counts 1's in binary representation of an integer number.

---
18. `******` - `**********` - `*****` - `*********`

---
19. C doesn't allow declaring a variable based on a condition, because it doesn't know if the condition will be satisfied at runtime, because the compiler converts C code to machine code before runtime, so it has to know that this variable will exist. And in `for` loops variable declaration is made before condition is checked, so it is not depend on condition.
