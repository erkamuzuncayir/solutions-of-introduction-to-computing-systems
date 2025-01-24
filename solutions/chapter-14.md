# Chapter 14

1. All programs in written C has to starts from main function.

---
2. Solution:
    1. It holds start point of local variables of a function.
    2. It holds return address where callee function called in caller method (exact memory address of instruction calls callee), with that it always knows where it'll return.
    3. It holds return value for caller. In this way, data can transfer between functions and functions can make programs more modular.

---
3. Solution:
    1. Function declaration informs compiler about function so, compiler can create subroutine for based on those information.
    2. Function declaration, sometimes called as function prototype.
    3. Function definition is the actual source code for the function. It contains parameter list and orders of parameters.
    4. Arguments are inputs that are passed to the function.
    5. Parameter is a value provided by caller function to callee function.

---
4. Solution:
    1. Caller
    2. Callee.
    3. Callee.
    4. Callee.

---
5. `2 2`. In C, parameter values are passed to the function, not the parameters themselves. So changes to variables in `MyFunc()` will only make a difference in `MyFunc()` at that call, not anywhere, not at any time.

---
6. `1 2 6 3 4`

---
7. Solution:

| X | Y |
| - | - |
|               a                 | Local variable / Written by Bump |
| Caller function's frame pointer | Address of caller function / Written by Bump |
|Return address of caller function| Address of an instruction / Written by Bump |
|     Return value for caller     | Address of data / Written by Bump |
|               x                 | Parameter / Argument |

---
8. Same answer as in exercise 5. Plus, `Swap` doesn't return anything and `main` doesn't set anything to x and y again, so changes in `Swap` stay in `Swap`.

---
9. First arguments are placed on the stack, then the caller execute JSR instruction. Because parameters (arguments) in caller method, out of scope of callee, so caller must pass parameters before passing control to callee.

---
10. Solution:
    1. 4.
    2. Can't figured out.

---
11. Solution:
    1. a = 3 b = 4
    2. Local variables are not initialized. So `z` can have any value, but before `Unit()` is executed, `Init()` is executed, so `z` can have the value of `y`, because the memory address of z is the old memory address of `y`.

---
12. Solution:

```c
#include <stdio.h>

char ToUpper(char inchar); // Function Declaration
char ToLower(char inchar); // Function Declaration
// Prompt for a line of text, Read one character,
// convert to uppercase, print it out, then get another
int main(void)
{
    char echo = 'A';
    // Initialize input character
    char result;
    // Converted character
    printf("Type input: ");
    do {
        scanf("%c", &echo);

        result = echo > 'Z' ? ToUpper(echo) : ToLower(echo);

        printf("%c\n", result);
    } while (echo != '\n');
}
// If the parameter is lowercase, return
// its uppercase ASCII value
char ToUpper(char inchar)
{
    char outchar = inchar - 32;
    return outchar;
}

// If the parameter is uppercase, return
// its lowercase ASCII value
char ToLower(char inchar)
{
    char outchar = inchar + 32;
    return outchar;
}
```

---
13. Solution:

```c
#include <stdio.h>

int Sum(int opOne, int opTwo);
int ConvertBaseFour(int valueBaseTen);

int main(void)
{
    int numOne, numTwo;
    printf("Please enter first number: \n");
    scanf("%d", &numOne);
    printf("Please enter first number: \n");
    scanf("%d", &numTwo);

    int resultBaseTen = Sum(numOne, numTwo);
    int resultBaseFour = ConvertBaseFour(resultBaseTen);

    printf("%d\n", resultBaseFour);
}

int Sum(int opOne, int opTwo)
{
    return opOne + opTwo;
}

int ConvertBaseFour(int valueBaseTen)
{
    int valueBaseFour;
    int digitValue;
    int digit = 10;
    valueBaseFour = valueBaseTen % 4;
    do {
        valueBaseTen = valueBaseTen / 4;
        digitValue = valueBaseTen % 4;
        valueBaseFour += digit * digitValue;
        digit *= 10;
    }while (valueBaseTen >3);

    return valueBaseFour;
}
```

---
14. Solution:

```c
#include <stdio.h>

int IsDivisible(int dividend, int divisor);
int FindSmallestEvenlyDivisibleNumber(int limit);

int main(void)
{
    int smallestEvenlyDivisible = FindSmallestEvenlyDivisibleNumber(10);
    printf("The smallest number evenly divisible by all integers less than 10: %d\n", smallestEvenlyDivisible);
    return 0;
}

int IsDivisible(int dividend, int divisor)
{
    return (divisor != 0) && (dividend % divisor == 0);
}

int FindSmallestEvenlyDivisibleNumber(int limit)
{
    int testNum = 0;
    int isFound = 0;

    while (isFound == 0) {
        testNum++; // Increment to check the next number
        isFound = 1; // Assume it is found until proven otherwise
        for (int i = 1; i < limit; i++) {
            if (!IsDivisible(testNum, i)) {
                isFound = 0; // Not divisible by i
                break; // No need to check further
            }
        }
    }

    return testNum; // Found the number
}
```

---
15. Solution:

| X | Y |
| - | - |
| 16 | x1 |
| dynamic link for main | - |
| x3103 | return memory address of main |
| 0 | return value of f |
| 4 | a (arg) |
| 5 | b (arg) |
| 6 | c (arg) |
| 6 | c |
| 5 | b |
| 4 | a |

---
16. Solution:

  1.Code:

```c
#include <stdio.h>
#define IDLE_STATE 1 // Define IDLE_STATE as 1 to represent idle machines

int FindBusyMachineCount(int machineState);
int main(void) {
  int input;
  scanf("%d", &input);

  int busyMachineCount = FindBusyMachineCount(input);

  printf("%d\n", busyMachineCount);
}

int FindBusyMachineCount(int machineState) {
  int count = 0;

  for (int i = 0; i < 32; i++) {
    if (IDLE_STATE & (machineState >> i))
      count++;
  }

  return count;
}
```
2. Code:

```c
#include <stdio.h>

int DetermineStateChangesOnMachines(int stateBefore, int stateAfter);
int main(void) {
  int firstNum;
  scanf("%d", &firstNum);

  int secondNum;
  scanf("%d", &secondNum);

  int stateChanges = DetermineStateChangesOnMachines(firstNum, secondNum);

  for (int i = 1; i <= 32; i++) {
    printf("%d", 1 & (stateChanges >> (32 - i)));
  }
  printf("%d\n", stateChanges);
}

int DetermineStateChangesOnMachines(int stateBefore, int stateAfter) {
  int stateChanges = 0;

  for (int i = 1; i <= 32; i++) {
    int bitBefore = 1 & (stateBefore >> i);
    int bitAfter = 1 & (stateAfter >> i);

    if (bitBefore == bitAfter)
      stateChanges &= ~(1 << (i));
    else
      stateChanges |= (1 << (i));
  }

  return stateChanges;
}
```
3. Code:

```c
#include <stdio.h>
#define IDLE_STATE 1 // Define IDLE_STATE as 1 to represent idle machines

int DetermineStateChangesOnMachines(int stateBefore, int stateAfter);
int FindBusyMachineCount(int machineState);
int main(void) {
  float inputCount = 0;
  int currentMachineState = 0;
  int lastMachineState = 0;
  int totalBusyCount = 0;
  int totalStateChanges = 0;

  printf("Please enter input count: ");
  scanf("%f", &inputCount);

  for (int i = 0; i < inputCount; i++) {
    scanf("%d", &currentMachineState);
    totalBusyCount += FindBusyMachineCount(currentMachineState);
    if (i != 0) {
      totalStateChanges += FindBusyMachineCount(DetermineStateChangesOnMachines(
          lastMachineState, currentMachineState));
    }
    printf("%d", totalStateChanges);
    lastMachineState = currentMachineState;
  }

  float averageBusyStateCount = totalBusyCount / inputCount;
  float averageStateChangeCount =
      (inputCount > 1) ? totalStateChanges / (inputCount - 1) : 0;
  printf("Average busy state count is: %f", averageBusyStateCount);
  printf("Average state change count is: %f", averageStateChangeCount);
}

int DetermineStateChangesOnMachines(int stateBefore, int stateAfter) {
  int stateChanges = 0;

  for (int i = 1; i <= 32; i++) {
    int bitBefore = 1 & (stateBefore >> i);
    int bitAfter = 1 & (stateAfter >> i);

    if (bitBefore == bitAfter)
      stateChanges &= ~(1 << (i));
    else
      stateChanges |= (1 << (i));
  }

  return stateChanges;
}

int FindBusyMachineCount(int machineState) {
  int count = 0;

  for (int i = 1; i <= 32; i++) {
    if (IDLE_STATE & (machineState >> i))
      count++;
  }

  return count;
}
```

---
17. Solution:

  1.Code:

```c
int Multiplexer(int firstInput, int secondInput, int thirdInput,
                int fourthInput, int select) {
  switch (select) {
  case 0:
    return firstInput;
    break;
  case 1:
    return secondInput;
    break;
  case 2:
    return thirdInput;
    break;
  case 3:
    return fourthInput;
    break;
  default:
    return 0;
    break;
  }
}
```
2. Code:
```c
#define ADD_OPCODE 0
#define SUB_OPCODE 1
#define AND_OPCODE 2
#define OR_OPCODE 3
#define NOT_OPCODE 4

int ALU(int firstOp, int secondOp, int opcode) {
  switch (opcode) {
  case ADD_OPCODE:
    return firstOp + secondOp; // Addition
  case SUB_OPCODE:
    return firstOp - secondOp; // Subtraction
  case AND_OPCODE:
    return firstOp & secondOp; // Bitwise AND
  case OR_OPCODE:
    return firstOp | secondOp; // Bitwise OR
  case NOT_OPCODE:
    return ~firstOp; // Bitwise NOT (only operand1 is used)
  default:
    printf("Invalid opcode\n");
    return 0; // Return 0 for invalid opcode
  }
}
```

---
18. Solution:
```c
#include <stdio.h>

void PrintInput(char ch);
int main(void) {
  int input = 0;
  int lastInput = -1; // Preventing first comparison check to wrongfully true.
  int inputRepeatCount = 1;
  char lastPrintedChar = '\0';
  char printChar;

  for (int i = 0; i < 8; i++) {
    scanf("%d", &input);

    if (input == lastInput) {
      inputRepeatCount++;
      printChar++;

      if (inputRepeatCount == 4 && (input == 7) || (input == 9)) {
        PrintInput(printChar);
        lastPrintedChar = printChar;
      } else if (inputRepeatCount == 3) {
        PrintInput(printChar);
        lastPrintedChar = printChar;
      }
    } else {
      if (i != 0 && lastPrintedChar != printChar) {
        lastPrintedChar = printChar;
        PrintInput(printChar);
      }
      inputRepeatCount = 1;
      switch (input) {
      case 2: // ABC
        printChar = 'A';
        break;
      case 3: // DEF
        printChar = 'D';
        break;
      case 4: // GHI
        printChar = 'G';
        break;
      case 5: // JKL
        printChar = 'J';
        break;
      case 6: // MNO
        printChar = 'M';
        break;
      case 7: // PQRS
        printChar = 'P';
        break;
      case 8: // TUV
        printChar = 'T';
        break;
      case 9: // WXYZ
        printChar = 'W';
        break;
      }
    }

    lastInput = input;
  }
}

void PrintInput(char ch) { printf("%c\n", ch); }
```
---
19. Solution:

```
A: The variable z equals 3
B: The variable z equals 5
C: The variable z equals 7
D: The variable z equals 4
```

