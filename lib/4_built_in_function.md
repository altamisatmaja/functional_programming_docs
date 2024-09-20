# 1. Imperative Programming dan Functional Programming
## Imperative Programming
Adalah paradigma pemrograman di mana instruksi diberikan kepada komputer untuk melakukan tindakan tertentu dalam urutan yang telah ditentukan. Dalam pendekatan ini, kode ditulis sebagai serangkaian perintah yang mengubah keadaan program melalui perubahan variabel, penggunaan struktur kontrol seperti loop dan kondisi, serta pemanggilan fungsi atau prosedur.

#### Contoh Imperative Programming
```js
var arr = [[1,2],[3,4],[5,6],[7,8]];
var hasil = [];

function luasPersegiPanjang(a,b) {
    return a*b;
}
for (let idx = 0; idx < arr.length; idx++) {
    const luas = luasPersegiPanjang(arr[idx][0],arr[idx][1]);
    hasil.push(luas);
}

console.log(hasil); // output = [ 2, 12, 30, 56 ]
```

## Functional Programming
Adalah paradigma pemrograman yang berfokus pada penggunaan fungsi murni untuk membangun program. Alih-alih mengubah keadaan atau data, fungsional programming menekankan evaluasi ekspresi dan komposisi fungsi. Ini berarti bahwa program ditulis sebagai serangkaian fungsi yang mengubah input menjadi output tanpa mengubah keadaan global atau menyebabkan efek samping.

#### Contoh Functional Programming
```js
var arr = [[1,2],[3,4],[5,6],[7,8]];
const hasil = arr.map(a => a[0] * a[1])
console.log(hasil); // output = [ 2, 12, 30, 56 ]
console.log(arr); // output = [ [ 1, 2 ], [ 3, 4 ], [ 5, 6 ], [ 7, 8 ] ]
```

# 2. Built in function (map, filter, reduce), Rekursi, dan Copy (spread operator)
Built in function adalah fungsi yang sudah disediakan oleh sebuah bahasa pemrograman atau lingkungan runtime tertentu. Fungsi ini sudah ada secara default dan siap digunakan tanpa perlu didefinisikan oleh programmer. Built-in functions dirancang untuk membantu dalam melakukan tugas-tugas umum dan sering digunakan, seperti manipulasi data, perhitungan matematis, operasi string, dan pengelolaan koleksi data.

## Map
Digunakan untuk membuat array baru dari array yang sudah ada, dan menerapkan fungsi ke masing-masing elemen pada array.

#### Contoh Penggunaan Map
```js
const products = [
    { name: 'Barang 1', qty: 2, price: 1000 },
    { name: 'Barang 2', qty: 5, price: 2000 },
    { name: 'Barang 3', qty: 4, price: 3000 },
];

const hasil = products.map(barang => ({
    name: barang.name,
    subTotal: barang.qty * barang.price
}));

console.log(hasil);
```

## Filter
Mengambil setiap elemen dalam array dan menerapkan pernyataan kondisional terhadapnya. Jika kondisi ini mengembalikan nilai true, elemen akan ditambahkan ke array baru. Jika kondisinya bernilai false, elemen tidak akan ditambahkan ke array baru.

#### Contoh Penggunaan Filter
```js
const negara = ['katak', 'bola', 'level', 'radar', 'mobil'];
const hasil = negara.filter(kata => kata[0] === kata.slice(-1));

console.log(hasil); // output = [ 'katak', 'level', 'radar' ]
```

## Reduce
Mengakumulasi semua elemen array menjadi satu nilai dengan menerapkan fungsi pada setiap elemen array.

#### Contoh Penggunaan Reduce
```js
const fruits = ['apple', 'banana', 'apple', 'orange', 'banana', 'banana'];

const hasil = fruits.reduce((temp, buah) => {
    if (temp[buah]) {
        temp[buah]++;
    } else {
        temp[buah] = 1;
    }
    return temp;
}, {});

console.log(hasil); // output = { apple: 2, banana: 3, orange: 1 }
```

## Rekursi
Rekursi adalah teknik di mana sebuah fungsi memanggil dirinya sendiri untuk menyelesaikan masalah yang lebih besar dengan membaginya menjadi sub-masalah yang lebih kecil. Recursion menggantikan perulangan (loops) yang umum dalam pemrograman imperatif, karena FP sering kali menghindari penggunaan pernyataan iteratif seperti for atau while.

Rekursi dibagi menjadi 2 bagian:
##### 1. Base Case: kondisi yang menghentikan rekursi.
##### 2. Recursive Case: memanggil fungsi itu sendiri dengan masalah yang lebih kecil.

```js
function factorial(n) {
    if (n === 0) return 1; // Base Case
    return n * factorial(n - 1); // Recursive Case
}

console.log(factorial(5)); // output = 120
```
#### Contoh Lain Penggunaan Rekursi
```js
function printCombinations(str, prefix = '') {
    // Base Case
    if (str.length === 0) {
        console.log(prefix);
        return;
    }

    // Recursive Case: mencetak kombinasi dengan dan tanpa karakter pertama dari string
    printCombinations(str.slice(1), prefix + str[0]);
    printCombinations(str.slice(1), prefix);
}

printCombinations('123');
```

![image](https://github.com/user-attachments/assets/3603ce68-41d8-4404-8575-3ebcceb6e0fa)

## Spread Operator "..."
Sintaks yang memungkinkan Anda untuk "menyebarkan" elemen-elemen dari sebuah array atau objek ke dalam array atau objek lainnya. Ini sangat berguna dalam berbagai situasi, seperti menggabungkan array, membuat salinan, atau mengubah elemen dalam struktur data.

#### Contoh Penggunaan Spread Operator
##### Menggabungkan
###### Array
```js
const array1 = [1, 2, 3];
const array2 = [4, 5, 6];

const combinedArray = [...array1, ...array2];
console.log(combinedArray); // Output: [1, 2, 3, 4, 5, 6]
```
###### Object
```js
const obj1 = { a: 1, b: 2 };
const obj2 = { c: 3, d: 4 };

const combinedObject = { ...obj1, ...obj2 };
console.log(combinedObject); // Output: { a: 1, b: 2, c: 3, d: 4 }
```

##### Menyalin
###### Array
```js
const originalArray = [1, 2, 3];
const copiedArray = [...originalArray];

console.log(copiedArray); // Output: [1, 2, 3]
```
###### Object
```js
const originalObject = { a: 1, b: 2 };
const copiedObject = { ...originalObject };

console.log(copiedObject); // Output: { a: 1, b: 2 }
```

## Rest Parameter
Adalah fitur di JavaScript yang memungkinkan fungsi untuk menerima jumlah argumen yang tidak ditentukan dengan cara mengumpulkan semua argumen tersebut menjadi sebuah array.

#### Contoh Rest Parameter
```js
function sum(...numbers) {
    return numbers.reduce((acc, num) => acc + num, 0);
}

console.log(sum(1, 2, 3, 4)); // Output: 10
```
