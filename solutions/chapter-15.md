# Chapter 15

---
1. Solution:

    1.Instead of;

```c
while (i < 11) {
sum = sum + i;
++i;
printf("%d\n", sum);
}
```

>

```c
while (i < 11) {
sum = sum + i;
++i;
}
printf("%d\n", sum);
```

2. Instead of;

```c
for (int i = 0; i >= 10; ++i)
```

>

```c
for (int i = 0; i <= 10; ++i)
```

3. Instead of;

```c
while (i <= 11)
```

>

```c
while (i < 11)
```

4. Instead of;

```c
sum = sum + ++i;
```

>

```c
sum = sum + i++;
```
---
2. Solution:
    1. `i = j >> 1` => `i = j >> 1;`
    2. Missing curly braces in `if` and `else` statements.
    3. `#define LIMIT 5;` => `#define LIMIT 5`

---
3. Solution: The problem is smallestNumber assignment at the beginning as a 0, is already at least possible smallest number. So none of the inputs can possibly smaller than 0. It should add `smallestNumber = nextInput` statement after `scanf("%d", &nextInput);`.

---
4. Wrong use of logical operators. `if ((echo > 'a' || echo < 'z') && (echo > 'A' || echo < 'Z'))` => `if ((echo >= 'a' && echo <= 'z') || (echo >= 'A' && echo <= 'Z'))`

---
5. Solution:
    1. (2,3) (2,4) (3,4) (2,5) (3,5) (4,5) (2,6) (3,6) (4,6) (5,6)
    2. 22
    3. It can reduce by half with doing `for (int j = 2; j < i; j++)` => `for (int j = 2; j < (i/2); j++)`

---
6. Solution: a = 100, b = 1, c = 1

---
7. Solution: This `if (request == 'P')` statement should inside the block of `if (request == 'R')`
