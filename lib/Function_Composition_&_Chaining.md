# Functional Programming di JavaScript - Function Composition & Chaining

## 1. Function Composition

### Pengertian
**Function composition** adalah teknik di mana beberapa fungsi digabungkan menjadi satu fungsi besar. Artinya, output dari satu fungsi menjadi input untuk fungsi berikutnya. Ini memungkinkan kita untuk membuat fungsi yang lebih kompleks dengan menggabungkan fungsi yang lebih kecil.

Komposisi fungsi mengikuti aturan **f(g(x))**, di mana fungsi `g` dieksekusi terlebih dahulu, lalu hasilnya digunakan sebagai input untuk fungsi `f`.

### Keuntungan Function Composition
- **Reusability**: Fungsi kecil dapat digunakan kembali di banyak tempat.
- **Readability**: Kode menjadi lebih bersih dan mudah dibaca.
- **Maintainability**: Mudah dikelola karena setiap fungsi kecil hanya memiliki satu tanggung jawab.

### Contoh Kasus Sederhana
Misalkan kita memiliki beberapa fungsi berikut:

- `multiplyBy2(x)`: Mengalikan nilai dengan 2.
- `add3(x)`: Menambahkan 3 ke nilai.
- `subtract1(x)`: Mengurangi 1 dari nilai.

```javascript
const multiplyBy2 = x => x * 2;
const add3 = x => x + 3;
const subtract1 = x => x - 1;

// Komposisi fungsi manual
const composedFunction = x => subtract1(add3(multiplyBy2(x)));

console.log(composedFunction(5)); // Output: 12
```

Pada contoh di atas, `multiplyBy2(5)` dieksekusi pertama kali, menghasilkan 10, kemudian `add3(10)` menghasilkan 13, dan terakhir `subtract1(13)` menghasilkan 12.

### Membuat Helper Function untuk Komposisi
Anda bisa membuat helper function compose untuk mempermudah komposisi:

```javascript
const compose = (...fns) => x => fns.reduceRight((acc, fn) => fn(acc), x);

const composed = compose(subtract1, add3, multiplyBy2);
const composed2 = compose(add3, multiplyBy2, subtract1);
const composed3 = compose(multiplyBy2, subtract1);

console.log(composed(5)); // Output: 12
console.log(composed2(5)); // Output: 11
console.log(composed3(5)); // Output: 8
```

Fungsi `compose` memungkinkan kita menggabungkan beberapa fungsi secara dinamis dan digunakan berkali-kali.

---

## 2. Function Chaining
### Pengertian
**Function chaining** adalah teknik di mana beberapa metode dipanggil berurutan pada objek yang sama dalam satu pernyataan, sehingga hasil dari satu metode menjadi input untuk metode berikutnya. Hal ini memungkinkan gaya penulisan kode yang lebih rapi dan efisien.

Dalam function chaining, setiap metode harus mengembalikan objek `this` atau objek yang relevan sehingga fungsi berikutnya dapat terus dipanggil.

### Keuntungan Function Chaining
- **Kode lebih ringkas**: Mengurangi jumlah variabel dan operasi antara fungsi.
- **Modularitas**: Setiap fungsi atau metode mudah dipecah menjadi fungsi yang lebih kecil.
- **Lebih mudah dibaca**: Setiap operasi berantai lebih jelas karena ditulis dalam satu baris aliran logika.

### Contoh Kasus
Misalkan kita memiliki sebuah objek `Calculator` dengan metode seperti `add`, `subtract`, `multiply`, dan `divide`.

```javascript
class Calculator {
  constructor(value = 0) {
    this.value = value;
  }

  add(num) {
    this.value += num;
    return this; // Mengembalikan objek untuk chaining
  }

  subtract(num) {
    this.value -= num;
    return this; 
  }

  multiply(num) {
    this.value *= num;
    return this;
  }

  divide(num) {
    this.value /= num;
    return this;
  }

  getResult() {
    return this.value;
  }
}

const calc = new Calculator();
const result = calc.add(10).subtract(5).multiply(3).divide(2).getResult();

console.log(result); // Output: 7.5
```

Pada contoh di atas, kita menggunakan chaining untuk melakukan operasi perhitungan berurutan tanpa perlu mendeklarasikan variabel perantara. Setiap metode mengembalikan objek `this`, sehingga metode berikutnya bisa langsung dipanggil pada objek yang sama.

### Chaining di Array Methods
Method chaining sering digunakan dengan method array seperti `map`, `filter`, dan `reduce`.

```javascript
const numbers = [1, 2, 3, 4, 5];

const result = numbers
  .filter(num => num > 2)   // Memfilter angka yang lebih besar dari 2
  .map(num => num * 2)      // Mengalikan setiap angka dengan 2
  .reduce((acc, num) => acc + num, 0); // Menjumlahkan semua angka

console.log(result); // Output: 18
```

Pada contoh ini, kita pertama-tama memfilter array, lalu menerapkan `map` untuk memodifikasi nilai, dan akhirnya menggunakan `reduce` untuk menjumlahkan semua hasil. Kode ini ditulis dalam satu baris alur logika, menjadikannya lebih mudah dipahami dan lebih ringkas.

---

## 3. Perbedaan Function Composition vs Function Chaining
- **Function Composition** digunakan untuk menggabungkan beberapa fungsi berbeda menjadi satu fungsi baru yang lebih kompleks, di mana fungsi pertama menerima input dan fungsi terakhir memberikan output.
- **Function Chaining** digunakan ketika kita ingin menjalankan serangkaian operasi berurutan pada objek yang sama, di mana setiap metode mengembalikan objek atau nilai baru yang digunakan oleh metode berikutnya.

---

## 4. Praktik Terbaik dalam Menggunakan Composition & Chaining
1. **Gunakan untuk Membuat Kode Modular**: Pastikan setiap fungsi atau metode memiliki satu tanggung jawab spesifik.
2. **Hindari Kode Berantakan**: Jangan membuat terlalu banyak fungsi kecil jika tidak diperlukan; tetap fokus pada keterbacaan.
3. **Pastikan Kode Teruji**: Karena function composition dan chaining sering digunakan dalam banyak alur, penting untuk menguji fungsi individual secara menyeluruh.
4. **Gunakan Higher-Order Functions (HOF)**: Kombinasikan dengan fungsi-fungsi seperti `map`, `filter`, dan `reduce` yang banyak digunakan dalam FP untuk mendapatkan manfaat maksimal.
