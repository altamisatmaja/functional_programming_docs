# Immutable

Immutable `(tak berubah)` adalah properti dari objek yang, setelah dibuat, tidak bisa diubah lagi.

Contoh yang umum adalah tipe data tuple di Python, yang tidak dapat diubah setelah dibuat.

Dalam fungsional programming, konsep immutability penting karena menghindari efek samping `(side effects)` dari perubahan data yang tidak disengaja, sehingga membuat program lebih mudah diprediksi dan bebas dari bug.

## Implementasi di Python

```python
# Contoh Tuple yang Immutable
my_tuple = (1, 2, 3)
# my_tuple[0] = 10  # Akan menghasilkan error karena tuple bersifat immutable
```

## Implementasi di Dart

```dart
// Contoh List yang Immutable dengan konstanta
final List<int> myList = const [1, 2, 3];
// myList[0] = 10;  // Akan menghasilkan error karena List bersifat immutable
```
