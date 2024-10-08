# Javascript Basic

Javascript adalah bahasa pemrograman yang awalnya dirancang untuk berjalan di atas browser. Namun, seiring perkembangan zaman, javascript tidak hanya berjalan di atas browser saja namun juga dapat digunakan pada sisi Server, Game, IoT, Desktop, dsb.

#### 1. Tipe variabel

Didalam javascript terdapat beberapa tipe mendeklarasikan variabel. Antara lain :

- Menggunakan huruf/sebuah nama secara langsung
- Menggunakan var
- Menggunakan let
- Menggunakan const

Sebuah deklarasi juga dapat dilakukan dalam 1 statement menggunakan koma.

```js
let orang = "John Doe",
  kucing = "Jihn Die",
  umur = 20;
```

Variabel sendiri merupakan sebuah wadah yang digunakan untuk menampung sebuah nilai. Terdapat aturan dalam menuliskan sebuah variabel antara lain :

- Variabel bisa mengandung huruf, angka, underscore, dan tanda dollar
- Variabel bisa diawali dengan huruf, underscore, dan dollar
- Case Sensitive
- Reserved words

#### 2. Tipe data

Terdapat 2 macam tipe data pada javascript

1. Tipe data primitif :
   Tipe data primitif hanya dapat menyimpan satu nilai pada satu waktu dan tidak dapat diubah menggunakan cara yang sama seperti tipe data non-primitif. Tipe data Primitif akan dianggap sama jika nilainya sama.

2. Tipe data non primitif :
   Tipe data non-primitif dapat menyimpan lebih dari satu nilai pada satu waktu dan dapat diubah. Tipe data non-primitif akan dianggap berbeda meskipun nilainya sama dan dalam urutan yang sama.

<details>
<summary>Macam tipe data primitif :</summary>

- String

```js
let nama = "altamis";
console.log(nama[0]); // a
nama[0] = "A";
console.log(nama); // altamis
```

- Number

```js
let a = 10;
let b = -10;
let c = 4.5;
let d = -4.5;
let infinityPostif = 5 / 0; // Infinity
let infinityNegatif = -5 / 0; // -Infinity
let angkaKaliString = 5 * "hello"; // NaN
```

- BigInt

```js
let b = 9007199254740992n;
console.log(b + 1n); // 9007199254740993n
let a = 1.5n; // Uncaught SyntaxError: Invalid or unexpected token

const a = 1n + 1; // Uncaught TypeError: Cannot mix BigInt and other types, use explicit conversions
const b = 1n + 1n; // 2n
```

- Boolean

```js
const akuGanteng = true;
const akuJelek = false;
```

- undefined

```js
var nama;
console.log(nama); // undefined
```

- null

```js
let mahasiswa = null;
console.log(mahasiswa); // null

mahasiswa = {
  nama: "Altamis",
  umur: 28,
  jurusan: "Informatika",
};
console.log(mahasiswa); //{nama: "Altamis", umur: 28, jurusan: "Informatika"}
```

- Symbol

```js
const a = Symbol();
const b = Symbol();
console.log(a === b); // false
console.log(a); // Symbol()
console.log(b); // Symbol()

const mahasiswa = {
  nama: "altamis",
  umur: 19,
};

const nama = Symbol();
mahasiswa[nama] = "atmaja";
console.log(mahasiswa); // {nama: "altamis", umur: 19, Symbol(): "atmaja"}
console.log(mahasiswa[nama]); // atmaja
```

</details>

<details>
<summary>Macam tipe data non primitif :</summary>

- Array

```js
const arr = [
  "altamis",
  19,
  19n,
  true,
  undefined,
  null,
  { nama: "atmaja" },
  [1, 2, 3, 4],
];
```

- Object

```js
const obj = {
  nama: "altamis",
  umur: 28,
};
```

</details>

#### 3. Operator

Operator digunakan untuk melakukan berbagai jenis perhitungan matematis dan logis. Terdapat beberapa operator dalam javascript, antara lain:

1. Assignment Operators

```js
let x = 10;
x += 5;
```

2. Arithmetic Operators

```js
let a = 3;
let x = (11 + 11) * a;
```

3. Comparison Operators

```js
let text1 = "A";
let text2 = "B";
let result = text1 > text2;
```

4. String Operators

```js
let text1 = "bashroi, raak, afif";
let text2 = "gantEng";
let text3 = text1 + " " + text2;
```

5. Logical Operators

```js
let x = 6;
let y = 3;
console.log(x < 10 && y > 1);
```

6. Ternary Operators

```js
let age = 20;
let kedewasaan = age < 18 ? "dibawah umur" : "cukup umur";
```

7. Type Operators

```js
console.log(typeof ""); // string
console.log(typeof 1); // number
console.log(typeof 2n); // bigint
console.log(typeof null); // object
console.log(typeof undefined); // undefined
console.log(typeof {}); // object
```

#### 4. Function

Function atau fungsi adalah "subprogram" yang dapat dipanggil di bagian lain kode atau di dalam fungsi itu sendiri (rekursi). Fungsi dapat memiliki serangkaian pernyataan atau statement di badan atau blok fungsi. Terdapat beberapa macam function diantaranya :

1. Function Declaration

```js
function name(param) {
  statements;
}
```

2. Function Expression

```js
let nama = function name(param) {
  statements;
};
```

3. Arrow Function

```js
(param) => {
  statements;
};
```

<details>
<summary>sintaks penulisan function secara umum</summary>
  
```js
function genap(num) {
  // num adalah parameter
  return num % 2 === 0; // statement baris code yang akan dieksekusi
}
genap(2); // 2 adalah argumen
```
</details>

<details>
<summary>Function Scope</summary>
  
Pada javascript kita tidak bisa asal mendeklarasikan variabel untuk digunakan bersama function, terdapat `function scope`. Sebagai contoh :
```js
// contoh 1
let nama = 'altamis';
function sapa() {
  console.log(nama); // altamis
}
sapa();

// contoh 2
function sapa() {
const nama = 'reza'; // function scope
}
console.log(nama); // Uncaught ReferenceError: nama is not defined.

````
Dari contoh diatas dapat disimpulkan sesuatu yang dideklarasikan didalam function tidak dapat digunakan diluar function namun sesuatu yang dideklarasikan diluar function dapat digunakan didalam function.
</details>

#### 5. Looping
Pada javascript looping sedikit lebih banyak macamnya daripada bahasa lain seperti python dsb. Diantaranya :
1. for

   For loop adalah looping yang membaca data dari suatu array atau himpunan data.

syntax :
```js
for (nilaiAwal; kondisiTerminasi; ekspresiAkhir) {
  statement;
}
````

<details>
<summary>Penjelasan :</summary>

- nilaiAwal: dapat berupa ekspresi atau deklarasi variabel yang akan dievaluasi sekali sebelum loop dimulai, biasanya deklarasi nilai awal.
- kondisiTerminasi: ekspresi atau kondisi yang menghentikan perulangan. Ekspresi ini harus mengembalikan nilai false agar perulangan berhenti, jika true perulangan terus dilakukan.
- ekspresiAkhir: dievaluasi pada akhir setiap iterasi setelah blok statement deksekusi. Biasanya digunakan untuk memperbarui atau menambah nilaiAwal.
- statement: kode atau statement yang akan dieksekusi pada setiap iterasi selama kondisiTerminasi bernilai true.
</details>

contoh :

```js
for (let nilaiAwal = 0; nilaiAwal < 5; nilaiAwal++) {
  console.log("hello world");
}
```

2. for...of

   Perulangan for..of di JavaScript bisa menjadi alternatif for ketika kita ingin mengulang sebuah array atau objek iterable.

syntax :

```js
for (variable of iterable) {
  statement;
}
```

<details>
<summary>Penjelasan :</summary>

- variable: pada setiap iterasi elemen diinisialisasi ke variabel ini. Dapat dideklarasikan menggunakan const, let, atau var.
- iterable: objek iterable yang ingin diulang, misalnya array.
- statement: statement yang dieksekusi pada setiap iterasi.
</details>

contoh :

```js
const buah = ["pisang", "mangga", "apel"];

for (const elemen of buah) {
  console.log(elemen);
}
```

3. for...in

   Untuk for in hampir sama fungsinya dengan for of namun looping ini digunakan untuk perulangan dalam objek

syntax :

```js
for (variabel in objek) {
  statement;
}
```

<details>
<summary>Penjelasan :</summary>

- variabel: variabel yang akan diinisialisasi dengan properti objek pada setiap iterasi.
- objek: objek target yang ingin dilakukan perulangan.
- statement: statement atau kode yang akan dieksekusi pada setiap iterasi.
</details>


contoh :

```js
const mahasiswa = {
  nama: "altamis",
  umur: 28,
  jurusan: "informatika",
};

for (const key in mahasiswa) {
  console.log(`${key} = ${mahasiswa[key]}`);
}
```

4. while

   While loop dapat digunakan sebagai alternatif dari for loop apabila pada perulangan tersebut kita tidak mengetahui berapa kali perulangannya, selama kondisi masih terpenuhi maka perulangan tidak akan berhenti

syntax :

```js
while (kondisi) {
  statement;
}
```

<details>
<summary>Penjelasan :</summary>

- kondisi: ekspresi yang dievaluasi disetiap iterasi. Jika true, statement dieksekusi, jika false maka keluar dari perulangan. Jika ekspresi tidak menghasilkan nilai boolean, dikonversi ke boolean secara otomatis sesuai truthy dan falsy.
- statement: statement atau kode yang dieksekusi selama kondisi bernilai true.
</details>

contoh :

```js
let n = 1;

while (n <= 5) {
  console.log(`${n}. hello world`);
  n++;
}
```

5. do...while

   Do While merupakan perulangan dimana setidaknya suatu statement akan diekseskusi sekali dalam suatu perulangan

syntax :

```js
do {
  statement;
} while (kondisi);
```

<details>
<summary>Penjelasan :</summary>

- statement: statement yang dieksekusi setidaknya sekali dan dieksekusi kembali jika kondisi bernilai true.
- kondisi: kondisi terminasi yang dievaluasi setelah statement dieksekusi. Jika kondisi true maka statement akan dieksekusi kembali, jika false maka keluar dari perulangan.
</details>

contoh :

```js
let i = 1;

do {
  console.log(`${i}. hello world`);
  i++;
} while (i <= 5);
```

#### 6. Percabangan

Pada javascript terdapat 2 percabangan yang dapat digunakan, yaitu if else dan juga switch.

- if else
  pada if else terdapat beberapa macam percabangan lagi, yaitu `if`, `else`, dan `else if`. Terdapat juga `nested if`
- switch
  untuk switch sendiri hampir sama fungsinya dengan if else, dan dapat menjadi alternatif percabangan selain if else, yang berbeda dari switch adalah syntax penulisannya

```js
// switch
switch (ekspresi) {
  case value1:
    statement1;
    break;
  case value2:
    statement2;
    break;
  case valueN:
    statementN;
    break;
  default:
    statementDefault;
    break;
}

// if else
if (kondisi) {
  statement1;
} else {
  statement2;
}
```
