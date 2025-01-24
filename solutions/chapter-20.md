# Chapter 20

1. Solution:

```cpp
void swap(bool &x, bool &y) {
  bool temp = x;
  x = y;
  y = temp;
}
```

---
2. Solution:

```cpp
void swap(int *x, int *y) {
  int *temp = x;
  x = y;
  y = temp;
}
```

---
3. Version C.

---
4. Solution:

| Address   | Name  | Type      | Size      |
| ---       | --    | --        | --        |
| 0xFF10    | t1    | Triangle  | 24 byte   |
| 0xFF28    | p     | double    | 8 byte    |

---
5. Solution:

```cpp
double Triangle::height() { return (2 * area()) / sideC; }
```

---
6. It won't compile because Triangle's methods will be out of scope of `main()`.

---
7. Solution:

```cpp
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

class Flight {
  int altitude;
  int longitude;
  int latitude;
  int heading;
  double airSpeed;
  // Pointer to next element
public:
  char ID[7];
  Flight *next;
  Flight(char *ID, int altitude, int longitude, int latitude, int heading,
         double airspeed);
  int AddFlight(Flight **list);
  void PrintAirspace(Flight *list);
};

Flight::Flight(char *ID, int altitude, int longitude, int latitude, int heading,
               double airspeed) {
  Flight *newFlight;
  newFlight = (Flight *)malloc(sizeof(Flight));
  strcpy(newFlight->ID, ID);
  newFlight->altitude = altitude;
  newFlight->longitude = longitude;
  newFlight->latitude = latitude;
  newFlight->heading = heading;
  newFlight->airSpeed = airspeed;
}
void Flight::PrintAirspace(Flight *list) {
  int count = 1;
  printf("Aircraft in Airspace --------------------------\n");
  while (list != NULL) {
    printf("Aircraft : %d\n", count);
    printf("ID: %s\n", list->ID);
    printf("Altitude : %d\n", list->altitude);
    printf("Longitude: %d\n", list->longitude);
    printf("Heading : %d\n", list->heading);
    printf("Airspeed : %f\n", list->airSpeed);
    printf("-----------------------------\n");
    count = count + 1;
    list = list->next;
  }
  printf("\n\n");
}

int Flight::AddFlight(Flight **list) {
  Flight *previous = NULL;
  Flight *current = *list;
  int IDcompare;
  while (current != NULL) {
    IDcompare = strcmp(this->ID, current->ID);
    // returns 0 if equal
    // < 0 if this->ID is less than current->ID
    // > 0 if this->ID is greater than current->ID
    if (IDcompare == 0)
      return -1;
    // Exists!
    else if (IDcompare < 0) {
      // Add this in between previous and current nodes
      this->next = current;
      if (previous == NULL)
        *list = this;
      // Add At Head
      else
        previous->next = this; // Add to Middle
      return 0;
    } else {
      // Continue traversing thru the list
      previous = current;
      current = current->next;
    }
  }
  this->next = NULL;
  if (previous == NULL)
    *list = this;
  // Empty List
  else
    previous->next = this;
  // Add At Tail
  return 0;
}

int DeleteFlight(char *planeID, Flight **list);

int main(void) {
  Flight *airspace = NULL;
  Flight newPlane("ZA123", 1000, 3233, 2516, 392, 3493.20);
  if (newPlane.AddFlight(&airspace) == 0)
    printf("Successful add of flight %s\n", newPlane.ID);
  if (DeleteFlight("ZA123", &airspace) == 0)
    printf("Successful removal of flight %s\n", "ZZ");
}
int DeleteFlight(char *planeID, Flight **list) {
  Flight *previous = NULL;
  Flight *current = *list;
  int IDcompare;
  while (current != NULL) {
    IDcompare = strcmp(planeID, current->ID);
    // returns 0 if equal
    // < 0 if Plane->ID is less than current->ID
    // > 0 if Plane->ID is greater than current->ID
    if (IDcompare == 0) {
      // Found node to remove!
      if (previous == NULL)
        *list = current->next;
      // Del At Head
      else
        previous->next = current->next; // Del from Mid/Tail
      free(current);
      return 0;
    } else if (IDcompare < 0)
      return -1;
    // Doesn't Exist
    else {
      // Continue traversing thru the list
      previous = current;
      current = current->next;
    }
  }
  // Traversed the whole list. Doesn't Exist
  return -1;
}
```

---
8. Solution:

```cpp
#include <iostream>
#include <math.h>
class Quadrilateral {
  double sideA;
  double sideB;
  double sideC;
  double sideD;

public:
  Quadrilateral(double a, double b, double c, double d);
  double area();
  double perimeter();
};
Quadrilateral::Quadrilateral(double a, double b, double c, double d) {
  sideA = a;
  sideB = b;
  sideC = c;
  sideD = d;
}
double Quadrilateral::perimeter() { return sideA + sideB + sideC + sideD; }
double Quadrilateral::area() {
  double s = perimeter() / 2;
  return sqrt((s - sideA) * (s - sideB) * (s - sideC) * (s - sideD));
}
int main(void) {
  Quadrilateral q1(2.0, 2.0, 3.0, 3.0);
  Quadrilateral *q2;
  q2 = new Quadrilateral(4.2, 7.8, 10.2, 5.6);
  std::cout << "Tri 1 Area " << q1.area() << std::endl;
  std::cout << "Tri 1 Perim " << q1.perimeter() << std::endl;
  std::cout << "Tri 2 Area " << q2->area() << std::endl;
  std::cout << "Tri 2 Perim " << q2->perimeter() << std::endl;
}
```

---
9. Solution:

```cpp
#include <iostream>
#include <math.h>

class RegularPentagon {
  double side;

public:
  RegularPentagon(double a);
  double area();
  double perimeter();
};
RegularPentagon::RegularPentagon(double a) { side = a; }
double RegularPentagon::perimeter() { return 5 * side; }
double RegularPentagon::area() {
  return 0.25 * (sqrt(5 * (5 + 2 * sqrt(5)))) * side * side;
}

int main(void) {
  RegularPentagon rp1(2.0);
  RegularPentagon *rp2;
  rp2 = new RegularPentagon(4.2);
  std::cout << "Tri 1 Area " << rp1.area() << std::endl;
  std::cout << "Tri 1 Perim " << rp1.perimeter() << std::endl;
  std::cout << "Tri 2 Area " << rp2->area() << std::endl;
  std::cout << "Tri 2 Perim " << rp2->perimeter() << std::endl;
}
```

---
10. Solution:

```assembly
ADD   R6, R6, #-6
LD    R0, TWO_VALUE
STR   R0, R6 #0
LD    R0, TWO_VALUE
STR   R0, R6 #-2
LD    R0, THREE_VALUE
STR   R0, R6 #-4
TWO_VALUE .FILL x0002
THREE_VALUE .FILL x0003
```

---
11. It is allocated in heap.

| x | y |
| - | - |
| intVector[0] | 1 |
| intVector[1] | 2 |
| intVector[2] | 3 |

---
12. Solution:

```cpp
#include <iostream>
#include <vector>
int main(void) {

  char inputChar;
  std::vector<char> inputVector;
  while (inputChar != '\n') {
    std::cin.get(inputChar);
    inputVector.push_back(inputChar);
  }
  for (int i = inputVector.size(); i >= 0; i--)
    std::cout << inputVector[i] << std::endl;
}
```

---
13. Solution:

```cpp
#include <cstdio>
#include <iostream>
#include <vector>

void ReadInput(std::vector<std::vector<char>> &inputVector);
void FindDuplicates(std::vector<std::vector<char>> &inputVector,
                    std::vector<std::vector<int>> &duplicateIndexes);
void PrintUniqueWords(std::vector<std::vector<char>> &inputVector,
                      std::vector<std::vector<int>> &duplicateIndexes);
int main(void) {
  std::vector<std::vector<char>> inputVector;
  std::vector<std::vector<int>> duplicateIndexes;

  ReadInput(inputVector);
  FindDuplicates(inputVector, duplicateIndexes);
  PrintUniqueWords(inputVector, duplicateIndexes);

  return 0;
}

void ReadInput(std::vector<std::vector<char>> &inputVector) {
  char inputChar;
  inputVector.push_back(std::vector<char>());
  int wordIndex = 0;

  while (inputChar != '\n') {
    std::cin.get(inputChar);
    if (inputChar == ' ' || inputChar == '\n') {
      inputVector.push_back(std::vector<char>());
      wordIndex++;
    } else {
      if (inputChar >= 'A' && inputChar <= 'Z')
        inputChar += 'z' - 'Z';
      inputVector[wordIndex].push_back(inputChar);
    }
  }
}

void FindDuplicates(std::vector<std::vector<char>> &inputVector,
                    std::vector<std::vector<int>> &duplicateIndexes) {
  bool isSame = true;
  for (int i = 0; i < inputVector.size(); i++) {
    for (int j = i + 1; j < inputVector.size(); j++) {
      if (inputVector[i].size() == inputVector[j].size()) {
        isSame = true;
        for (int k = 0; k < inputVector[i].size(); k++) {
          if (inputVector[i][k] != inputVector[j][k]) {
            isSame = false;
            break;
          }
        }

        bool isContainI = false;
        bool isContainJ = false;
        if (isSame) {
          for (int l = 0; l < duplicateIndexes.size(); l++) {
            for (int m = 0; m < duplicateIndexes[l].size(); m++) {
              if (duplicateIndexes[l][m] == i)
                isContainI = true;
              if (duplicateIndexes[l][m] == j)
                isContainJ = true;
            }
            if (isContainI && !isContainJ)
              duplicateIndexes[l].push_back(j);
            if (isContainJ && !isContainI)
              duplicateIndexes[l].push_back(i);
          }
          if (!isContainI && !isContainJ) {
            duplicateIndexes.push_back(std::vector<int>());
            duplicateIndexes.back().push_back(i);
            duplicateIndexes.back().push_back(j);
          }
        }
      }
    }
  }
}

void PrintUniqueWords(std::vector<std::vector<char>> &inputVector,
                      std::vector<std::vector<int>> &duplicateIndexes) {
  for (int i = 0; i < inputVector.size(); i++) {
    bool isDuplicate = false;
    for (int k = 0; k < duplicateIndexes.size(); k++) {
      for (int l = 1; l < duplicateIndexes[k].size(); l++) {
        if (i == duplicateIndexes[k][l])
          isDuplicate = true;
      }
    }

    if (!isDuplicate) {
      for (int j = 0; j < inputVector[i].size(); j++) {
        std::cout << inputVector[i][j];
      }
      std::cout << ' ';
    }
  }
  std::cout << std::endl;
}
```
---

> If you've made it this far, [Press F](https://en.wikipedia.org/wiki/Press_F_to_pay_respects#/media/File:PressFtoPayRespects.jpg).
