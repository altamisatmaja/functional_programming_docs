# Pure Function

Pure Function adalah fungsi yang outputnya hanya `bergantung pada inputnya` dan `tidak menyebabkan efek samping`.

Fungsi ini selalu mengembalikan nilai yang sama untuk input yang sama dan tidak mengubah state di luar lingkupnya.

## Implementasi di Python

```python
def add(a, b):
    return a + b

# Selalu menghasilkan output yang sama untuk input yang sama
print(add(2, 3))  # Output: 5
```

## Implementasi di Dart

```dart
int add(int a, int b) {
  return a + b;
}

void main() {
  print(add(2, 3));  // Output: 5
}
```
