# Chapter 16

1. Solution:

```c
#include <stdio.h>

int main() {
  char input[20];

  printf("Input a word (less than 20 characters): ");
  scanf("%s", input);

  char pigLatinOutput[22];

  for (int i = 0; i < 22; i++) {
    pigLatinOutput[i] = input[i + 1];
    if (input[i + 1] == '\0') {
      pigLatinOutput[i] = input[0];
      pigLatinOutput[i + 1] = 'a';
      pigLatinOutput[i + 2] = 'y';
      break;
    }
  }
  printf("%s\n", pigLatinOutput);
}
```

---
2. Solution:

```c
#include <stdio.h>

int main() {
  int lastNumber = -1;
  int inputNumber = 0;
  int sumOfNumbers = 0;

  while (lastNumber != inputNumber) {
    lastNumber = inputNumber;
    printf("Input a number: ");
    scanf("%d", &inputNumber);
    sumOfNumbers += inputNumber;
  }

  printf("Sum of entered numbers are: %d\n", sumOfNumbers);
}
```

---
3. Solution: `x = 7`. Because `*px` is pointer of global variable `x`.

---
4. Solution:

```c
#include <stdio.h>

int StringCompare(char firstString[], char secondString[]);
int main(void) {
  char inputA[20];
  char inputB[20];

  printf("Enter first word: \n");
  scanf("%s", inputA);
  printf("Enter second word: \n");
  scanf("%s", inputB);

  int result = StringCompare(inputA, inputB);

  switch (result) {
  case 1:
    printf("%s is before %s\n", inputA, inputB);
    break;
  case 2:
    printf("%s is before %s\n", inputB, inputA);
    break;
  case 0:
    printf("They're same.\n");
    break;
  default:
    printf("Unhandled case!\n");
  }
}

int StringCompare(char firstString[], char secondString[]) {
  int i = 0;
  while (firstString[i] != '\0' || secondString[i] != '\0') {
    if (firstString[i] < secondString[i]) {
      return 1;
    } else if (firstString[i] > secondString[i]) {
      return 2;
    }
    i++;
  }

  return 0;
}
```

---
5. Solution:

```c
void InsertionSort(int list[]) {
  int unsorted;
  int sorted;
  int unsortedItem;

  for (unsorted = 1; unsorted < MAX_NUMS; unsorted++) {
    unsortedItem = list[unsorted];
    for (sorted = unsorted - 1; (sorted >= 0) && (StringCompare(list[sorted], unsortedItem) == 2);
         sorted--)
      list[sorted + 1] = list[sorted];
    list[sorted + 1] = unsortedItem;
  }
}
```

---
6. Solution:

```assembly
        LEA R0 ARR_A
        AND R1 R1 #0
        ADD R1 R1 #4 ; Variable 'i'.
LOOP    BRn DONE
        ADD R2 R1 #0
        STR R2 R0 #0
        ADD R1 R1 #-1
        BRnzp LOOP
DONE    HALT
ARR_A   .BLKW 5
```

---
7. Solution:

| MemAddr | What contains       | Value  |
| ------- | ------------------- | ------ |
| 0xEFF1 | ind                  | 0xEFF3 |
| 0xEFF2 | ptr                  | 0xEFF3 |
| 0xEFF3 | apple                |  124   |
| 0xEFF4 | saved frame pointer  | ------ |
| 0xEFF5 | saved return address | ------ |
| 0xEFF6 | return value         | ------ |

---
8. Solution: Stack has 4 elements. One for parameter, one for main's frame pointer, one for return address and one for return value to main.

---
9. Solution:

```c
#include <stdio.h>

int main(void) {
  int input = 0;
  int count = 0;
  int numbers[10];
  int arrIndex = 0;

  printf(
      "Enter desired count of numbers: (-1 for terminate, max 10 numbers): ");
  while (input != -1 && count <= 10) {
    scanf("%d", &input);
    _Bool isContain = 0;
    for (int i = 0; i < 10; i++) {
      if (input == numbers[i])
        isContain = 1;
    }

    if (!isContain) {
      numbers[arrIndex] = input;
      arrIndex++;
    }

    count++;
  }

  printf("Array\n");
  for (int i = 0; i < arrIndex; i++) {
    printf("%d\n", numbers[i]);
  }
}
```

---
10. Solution:

```c
#include <stdio.h>
#define MAX_NUMS 10

void InsertionSort(int list[]);
int main(void) {
  int input = 0;
  int count = 0;
  int numbers[10];

  printf("Enter 10 numbers: ");
  while (count <= 10) {
    scanf("%d", &input);
    if (input == -1)
      break;
    numbers[count] = input;
    count++;
  }

  InsertionSort(numbers);

  int medianIndex = count / 2;

  printf("Median number of list is: %d\n", numbers[medianIndex]);
}

void InsertionSort(int list[]) {
  int unsorted;
  int sorted;
  int unsortedItem;
  for (unsorted = 1; unsorted < MAX_NUMS; unsorted++) {
    unsortedItem = list[unsorted];
    for (sorted = unsorted - 1; (sorted >= 0) && (list[sorted] > unsortedItem);
         sorted--)
      list[sorted + 1] = list[sorted];
    list[sorted + 1] = unsortedItem;
  }
}
```

---
11. Solution:
    1. a.
        1. main: Stack has 13 elements. One for frame pointer, one for return address and one for return value, 13 for local variable.
        2. FindLen: Stack has 5 elements. One for parameter, one for main's frame pointer, one for return address and one for return value to main, one for local variable. 
    2. b. I skipped this.
    3. c. It cause stack overflow and override main's frame pointer, return address and return value and cause unknown behaviour.

---
12. Solution: It returns memory address of local variable of function `*LowerCase` which meaning is when function returned, value of return is `NULL` because stack cleaned from `*LowerCase` when returned.

---
13. Solution:

```c
#include <stdio.h>

#define STACK_SIZE 100

int stack[STACK_SIZE];
int topOfStack = 0;

int Push(int item);
int Pop(int *pItem);

int main(void) {
  int poppedItem;
  int *pItem = &poppedItem;
  int input;
  int result = 0;

  while (input != 999) {
    scanf("%d", &input);
    if (input == -1) {
      result = Pop(pItem);
      if (result == 1) {
        printf("Stack overflow!");
      } else {
        printf("%d\n", poppedItem);
      }
    } else if (input != 999) {
      result = Push(input);
      if (result == 1) {
        printf("Stack underflow!");
      }
    }
  }
}

int Push(int item) {
  if (topOfStack < STACK_SIZE) {
    stack[topOfStack] = item;
    topOfStack++;
    return 0;
  } else
    return 1;
}

int Pop(int *pItem) {
  if (topOfStack > 0) {
    *pItem = stack[--topOfStack];
    return 0;
  } else
    return 1;
}
```
---
14. Solution:

```c
#include <stdio.h>

#define WIDTH_PIXEL 10
#define HEIGHT_PIXEL 2
#define DISTINCT_DATA_COUNT 16

void CollectHistogramDataFromSources(int image[WIDTH_PIXEL][HEIGHT_PIXEL],
                                     int data[DISTINCT_DATA_COUNT]);
void DrawHistogram(int data[DISTINCT_DATA_COUNT]);

int main(void) {
  int imageData[WIDTH_PIXEL][HEIGHT_PIXEL] = {
      {1, 2}, {2, 2}, {4, 2}, {5, 2}, {3, 2},
      {2, 2}, {1, 2}, {1, 0}, {1, 2}, {1, 2},
  };

  int histogramData[DISTINCT_DATA_COUNT] = {0, 0, 0, 0, 0, 0, 0, 0,
                                            0, 0, 0, 0, 0, 0, 0, 0};
  CollectHistogramDataFromSources(imageData, histogramData);
}

void CollectHistogramDataFromSources(int image[WIDTH_PIXEL][HEIGHT_PIXEL],
                                     int data[DISTINCT_DATA_COUNT]) {
  for (int i = 0; i < WIDTH_PIXEL; i++) {
    for (int j = 0; j < HEIGHT_PIXEL; j++) {
      data[image[i][j]]++;
    }
  }

  for (int k = 0; k < 16; k++) {
    printf("%d\n", data[k]);
  }
}
```
