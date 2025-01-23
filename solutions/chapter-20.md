# Chapter 20

1. Solution:

```cpp
void swap(bool &x, bool &y) {
  bool temp = x;
  x = y;
  y = temp;
}
```

2. Solution:

```cpp
void swap(int *x, int *y) {
  int *temp = x;
  x = y;
  y = temp;
}
```

3. Version C.

4. Solution:

| Address   | Name  | Type      | Size      |
| ---       | --    | --        | --        |
| 0xFF10    | t1    | Triangle  | 24 byte   |
| 0xFF28    | p     | double    | 8 byte    |
