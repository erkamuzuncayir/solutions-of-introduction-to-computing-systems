# Chapter 18

1. Solution:

```c
#include <stdio.h>
#define NAME_MAX_CHAR 10

int main(void) {
  // 1.
  printf("%d, %s, %f\n", 123, "hey", 2.3);
  // 2.
  printf("(%d)-%d-%d\n", 123, 456, 7890);
  // 3.
  printf("%s-%s-%s", "123", "456", "7890");
  // 4.
  int studentNumOne, studentNumTwo, studentNumThree;
  scanf("%d%d%d", &studentNumOne, &studentNumTwo, &studentNumThree);
  printf("%d - %d - %d\n", studentNumOne, studentNumTwo, studentNumThree);
  // 5.
  char lastName[NAME_MAX_CHAR];
  char firstName[NAME_MAX_CHAR];
  int age;
  char sex;
  scanf("%s %s %d %c", lastName, firstName, &age, &sex);
  printf("Last Name: %s\nFirst Name: %s\nAge: %d\nSex: %c\n", lastName,
         firstName, age, sex);
}
```

---
2. It represents how many input successfully processed and assigned to variables.

---
3. With buffering user can modify their entered input before sending to computer.

---
4. Program will stop and wait input from user.

---
5. Because program tries to interpret x as an integer instead of float.

---
6. Integer values.

---
7. Solution:

```
46 29 BlueMoon
46 0 BlueMoon
111 999 888
```

---
8. Solution:

```c
#include <stdio.h>
#define MAX_INPUT 1000

int main(void) {

  FILE *inFile;
  FILE *outFile;

  char fileData[1000];
  inFile = fopen("dummyWithWhitespaces.c", "r");
  outFile = fopen("dummyWithoutWhitespaces.c", "w");

  int i = 0;
  if (inFile != NULL) {
    while (fscanf(inFile, "%s", fileData) != EOF && i < MAX_INPUT) {
      i++;
      fprintf(outFile, "%s", fileData);
      printf("Reading %d\n", i);
    }
  } else {
    printf("Unsuccesfull.");
  }
}
```

---
9. Solution: I did not solve it because I found the answer too long to solve but insufficient in terms of benefit.
