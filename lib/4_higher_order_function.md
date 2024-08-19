# Higher-Order Function

`Higher-Order Function` adalah fungsi yang dapat menerima fungsi lain sebagai argumen atau mengembalikan fungsi sebagai output.

Ini adalah elemen kunci dalam pemrograman fungsional

## Implementasi di Python

```python
def apply_function(func, value):
    return func(value)

def square(x):
    return x * x

print(apply_function(square, 5))  # Output: 25
```

## Implementasi di Dart

```dart
int applyFunction(int Function(int) func, int value) {
  return func(value);
}

int square(int x) {
  return x * x;
}

void main() {
  print(applyFunction(square, 5));  // Output: 25
}}
```
