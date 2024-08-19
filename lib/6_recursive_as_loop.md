# Rekursi sebagai Perulangan

Rekursi adalah teknik di mana sebuah fungsi memanggil dirinya sendiri untuk menyelesaikan sub-tugas yang lebih kecil dari masalah utama.

Rekursi dapat digunakan sebagai pengganti perulangan (loop) untuk menyelesaikan masalah yang dapat dipecah menjadi sub-masalah serupa.

## Implementasi di Python

```python
def factorial(n):
    if n == 0:
        return 1
    else:
        return n * factorial(n - 1)

print(factorial(5))  # Output: 120
```

## Implementasi di Dart

```dart
int factorial(int n) {
  if (n == 0) {
    return 1;
  } else {
    return n * factorial(n - 1);
  }
}

void main() {
  print(factorial(5));  // Output: 120
}
```
