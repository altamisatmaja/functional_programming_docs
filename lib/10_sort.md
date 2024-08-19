# Rekonstruksi Fungsi `sort`

Fungsi `sort` mengurutkan elemen dalam iterable berdasarkan kriteria yang diberikan.

## Implementasi di Python

```python
def my_sort(iterable, key=None, reverse=False):
    return sorted(iterable, key=key, reverse=reverse)

numbers = [5, 2, 9, 1, 5, 6]
sorted_numbers = my_sort(numbers, reverse=True)
print(sorted_numbers)  # Output: [9, 6, 5, 5, 2, 1]
```

## Implementasi di Dart

```dart
List<T> mySort<T>(List<T> iterable, [int Function(T, T)? compare]) {
  var sortedList = List<T>.from(iterable);
  sortedList.sort(compare);
  return sortedList;
}

void main() {
  var numbers = [5, 2, 9, 1, 5, 6];
  var sortedNumbers = mySort(numbers, (a, b) => b.compareTo(a));
  print(sortedNumbers);  // Output: [9, 6, 5, 5, 2, 1]
}
```
