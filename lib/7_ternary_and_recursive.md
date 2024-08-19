# Ternary Operator dan Rekursi

Ternary operator adalah bentuk singkat dari if-else statement. Digunakan untuk menentukan nilai berdasarkan kondisi. Rekursi dapat digabungkan dengan ternary operator untuk menyederhanakan kode yang melibatkan kondisi.

## Implementasi di Python

```python
def factorial(n):
    return 1 if n == 0 else n * factorial(n - 1)

print(factorial(5))  # Output: 120
```

## Implementasi di Dart

```dart
int factorial(int n) {
  return n == 0 ? 1 : n * factorial(n - 1);
}

void main() {
  print(factorial(5));  // Output: 120
}
```
