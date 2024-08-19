# Rekonstruksi Fungsi `filter`

Fungsi `filter` menyaring elemen dalam iterable berdasarkan kondisi yang ditentukan oleh fungsi predicate.

## Implementasi di Python

```python
def my_filter(predicate, iterable):
    return [x for x in iterable if predicate(x)]

numbers = [1, 2, 3, 4, 5]
even_numbers = my_filter(lambda x: x % 2 == 0, numbers)
print(even_numbers)  # Output: [2, 4]
```

## Implementasi di Dart

```dart
List<T> myFilter<T>(bool Function(T) predicate, List<T> iterable) {
  return iterable.where(predicate).toList();
}

void main() {
  var numbers = [1, 2, 3, 4, 5];
  var evenNumbers = myFilter((x) => x % 2 == 0, numbers);
  print(evenNumbers);  // Output: [2, 4]
}
```
