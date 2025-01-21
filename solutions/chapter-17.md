# Chapter 17

1. Solution: 
    1. 9
    2. n - 1
    3. 15
    4. (2^n) - 1
    5. 1024
    6. 2^n
    7. No it is for 'X' or 'V' mark.

2. No, it doesn't. With each recursive call, another copy of the function is pushed into the stack frame.

3. Total number of squares - 1.

4. 1 2 3 4 5 6 7 8 9 10 11.

5. Solution:
    1. 0, 2, 0.
    2. It calculates how many times the 1st number is the 2nd number.
    3. Solution:
        1. frame pointer
        2. return address to power
        3. 1 (argument)
        4. 7 (argument)
        5. return value

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

    2. Solution: 80.
    
7. Solution:
    1. 16 KB = 16384 Byte / 4 Byte (1 for frame pointer, 1 for return address, 1 for return value, 1 for argument = 4096
    2. 4 KB = 4096 Byte / 4 Byte (1 for frame pointer, 1 for return address, 1 for return value, 1 for argument = 1024

8. Solution:

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
