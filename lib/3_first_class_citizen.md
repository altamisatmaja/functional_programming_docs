# Function as First-Class Citizen

`Function as First-Class Citizen` berarti fungsi dapat diperlakukan sebagai nilai yang dapat disimpan dalam variabel, diteruskan sebagai argumen ke fungsi lain, atau dikembalikan sebagai nilai dari fungsi lain.

## Implementasi di Python

```python
def greet(name):
    return f"Hello, {name}"

# Menyimpan fungsi dalam variabel
say_hello = greet
print(say_hello("Alice"))  # Output: Hello, Alice
```

## Implementasi di Dart

```dart
String greet(String name) {
  return "Hello, $name";
}

void main() {
  // Menyimpan fungsi dalam variabel
  var sayHello = greet;
  print(sayHello("Alice"));  // Output: Hello, Alice
}
```
