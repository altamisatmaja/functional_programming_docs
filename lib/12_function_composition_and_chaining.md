# Function Composition dan Function Chaining

Function composition adalah teknik di mana beberapa fungsi digabungkan sehingga output dari satu fungsi menjadi input untuk fungsi berikutnya

Function chaining adalah teknik serupa di mana hasil dari fungsi sebelumnya digunakan sebagai input untuk fungsi berikutnya, sering diterapkan pada objek yang mendukung method chaining.

## Implementasi di Python

```python
def compose(*functions):
    def composed_function(x):
        for function in reversed(functions):
            x = function(x)
        return x
    return composed_function

def add_one(x):
    return x + 1

def square(x):
    return x * x

# Komposisi fungsi: add_one kemudian square
composed = compose(square, add_one)
print(composed(3))  # Output: 16 (add_one(3) = 4, square(4) = 16)
```

## Implementasi di Dart

```dart
Function compose(List<Function> functions) {
  return (dynamic x) {
    for (var function in functions.reversed) {
      x = Function.apply(function, [x]);
    }
    return x;
  };
}

int addOne(int x) => x + 1;
int square(int x) => x * x;

// Komposisi fungsi: addOne kemudian square
void main() {
  var composed = compose([square, addOne]);
  print(composed(3));  // Output: 16 (addOne(3) = 4, square(4) = 16)
}
```
