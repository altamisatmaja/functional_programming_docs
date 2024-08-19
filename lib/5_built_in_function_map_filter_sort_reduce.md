# Built-in Function - Operasi List (map, filter, sort, reduce)

Operasi list seperti map, filter, sort, dan reduce adalah fungsi bawaan yang memungkinkan manipulasi dan pemrosesan list secara deklaratif.

## Implementasi di Python

- `map`: Menerapkan fungsi ke setiap elemen dalam list.
- `filter`: Memilih elemen dari list berdasarkan kondisi tertentu.
- `sort`: Mengurutkan elemen dalam list
- `reduce`: Mengurangi list menjadi satu nilai dengan mengakumulasi hasil dari operasi pada elemen-elemen list.

```python
from functools import reduce

numbers = [1, 2, 3, 4, 5]

# map
squared = list(map(lambda x: x ** 2, numbers))

# filter
even = list(filter(lambda x: x % 2 == 0, numbers))

# sort
sorted_numbers = sorted(numbers, reverse=True)

# reduce
sum_of_numbers = reduce(lambda x, y: x + y, numbers)

print(squared)         # Output: [1, 4, 9, 16, 25]
print(even)           # Output: [2, 4]
print(sorted_numbers) # Output: [5, 4, 3, 2, 1]
print(sum_of_numbers) # Output: 15
```

## Implementasi di Dart

- `map()`: Mengaplikasikan fungsi ke setiap elemen dalam iterable.
- `where()`: Memilih elemen yang memenuhi kondisi tertentu.
- `sort()`: Mengurutkan list.
- `reduce()`: Mengakumulasi hasil dari iterable menggunakan fungsi biner.

```dart
void main() {
  List<int> numbers = [1, 2, 3, 4, 5];

  // map
  var squared = numbers.map((x) => x * x).toList();

  // filter
  var even = numbers.where((x) => x % 2 == 0).toList();

  // sort
  var sortedNumbers = List.from(numbers)..sort((a, b) => b.compareTo(a));

  // reduce
  var sumOfNumbers = numbers.reduce((x, y) => x + y);

  print(squared);         // Output: [1, 4, 9, 16, 25]
  print(even);           // Output: [2, 4]
  print(sortedNumbers); // Output: [5, 4, 3, 2, 1]
  print(sumOfNumbers);  // Output: 15
}
```
