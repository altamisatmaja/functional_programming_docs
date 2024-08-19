# Rekonstruksi Fungsi `sort`

Fungsi `reduce` mengakumulasi elemen-elemen dalam iterable menggunakan fungsi biner, yang biasanya memerlukan dua argumen dan mengembalikan satu nilai.

## Implementasi di Python

```python
from functools import reduce

def my_reduce(function, iterable, initializer=None):
    it = iter(iterable)
    if initializer is None:
        value = next(it)
    else:
        value = initializer
    for element in it:
        value = function(value, element)
    return value

numbers = [1, 2, 3, 4, 5]
sum_of_numbers = my_reduce(lambda x, y: x + y, numbers)
print(sum_of_numbers)  # Output: 15
```

## Implementasi di Dart

```dart
T myReduce<T>(T Function(T, T) combine, List<T> iterable, [T? initialValue]) {
  var iterator = iterable.iterator;
  if (!iterator.moveNext()) {
    if (initialValue == null) {
      throw StateError("No initial value provided and iterable is empty");
    }
    return initialValue;
  }
  var value = initialValue ?? iterator.current;
  while (iterator.moveNext()) {
    value = combine(value, iterator.current);
  }
  return value;
}

void main() {
  var numbers = [1, 2, 3, 4, 5];
  var sumOfNumbers = myReduce((x, y) => x + y, numbers);
  print(sumOfNumbers);  // Output: 15
}
```
