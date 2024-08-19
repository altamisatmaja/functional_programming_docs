# Rekonstruksi Fungsi `map`

Fungsi `map` menerapkan fungsi yang diberikan ke setiap elemen dalam iterable dan mengembalikan iterable baru dengan hasilnya.

## Implementasi di Python

```python
def my_map(func, iterable):
    return [func(x) for x in iterable]

numbers = [1, 2, 3, 4]
squared = my_map(lambda x: x ** 2, numbers)
print(squared)  # Output: [1, 4, 9, 16]
```

## Implementasi di Dart

```dart
List<T> myMap<T>(T Function(T) func, List<T> iterable) {
  return iterable.map(func).toList();
}

void main() {
  var numbers = [1, 2, 3, 4];
  var squared = myMap((x) => x * x, numbers);
  print(squared);  // Output: [1, 4, 9, 16]
}
```
