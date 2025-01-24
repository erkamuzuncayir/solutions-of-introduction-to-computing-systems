# Chapter 17

1. Solution: 
    1. 9
    2. n - 1
    3. 15
    4. (2^n) - 1
    5. 1024
    6. 2^n
    7. No it is for 'X' or 'V' mark.

---
2. No, it doesn't. With each recursive call, another copy of the function is pushed into the stack frame.

---
3. Total number of squares - 1.

---
4. 1 2 3 4 5 6 7 8 9 10 11.

---
5. Solution:
    1. 0, 2, 0.
    2. It calculates how many times the 1st number is the 2nd number.
    3. Solution:
        1. frame pointer
        2. return address to power
        3. 1 (argument)
        4. 7 (argument)
        5. return value

---
6. Solution:
    1. Solution: 
```c
int SigmaIterative(int k) {
  int sum = 0;
  while (k > 0) {
    sum += k;
    k--;
  }

  return sum;
}
```

2.Solution: 80.

---
7. Solution:
    1. 16 KB = 16384 Byte / 4 Byte (1 for frame pointer, 1 for return address, 1 for return value, 1 for argument = 4096
    2. 4 KB = 4096 Byte / 4 Byte (1 for frame pointer, 1 for return address, 1 for return value, 1 for argument = 1024

---
8. Solution: Because the recursive implementation needs many extra calls compared to the iterative implementation.

```c
#include <stdio.h>
int Fib(int k);
int main(void) { Fib(6); }

int Fib(int k) {
  int sum = 0;
  int last = 1;
  int beforeLast = 0;
  int count = 0;
  while (count <= k) {
    sum = beforeLast + last;
    beforeLast = last;
    last = sum;
    count++;
  }

  printf("%d\n", sum);
  return sum;
}
```

---
9. Solution: Just convert `else if (item < list[middle])` to `else if (item > list[middle])`.

---
10. Solution: 3, 2, 2. Find the greatest divisor that can divide both numbers. We should probably test every number that is smaller than the smaller of the two numbers.

---
11. Solution:

```c
int M() {
  int num = 1;
  int x = 0;
  while (num > 0) {
    printf("Type a number: ");
    scanf("%d", &num);
    if (num > x)
      x = num;
  }
  return x;
}
```

---
12. Solution:
    1. None.
    2. 6.
    3. Recursive call count.

---
13. Solution: Can't solve.

---
14. Solution:

```
9
7
5
3
1
2
4
6
8
10
```
