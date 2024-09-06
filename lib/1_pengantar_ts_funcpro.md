# Typecript Basic

TypeScript adalah bahasa pemrograman yang merupakan superset dari JavaScript. Ini berarti semua kode JavaScript yang valid juga merupakan kode TypeScript yang valid. TypeScript menambahkan fitur typing statis pada JavaScript, yang membantu mendeteksi kesalahan pada saat pengembangan.

#### 1. Instalasi TypeScript

Untuk mulai menggunakan TypeScript, pertama-tama instal TypeScript secara global:

```ts
npm install -g typescript
```

Setelah itu, kita bisa membuat file .ts dan mengompilasinya menjadi JavaScript menggunakan perintah berikut:

```ts
tsc namaFile.ts
```

#### 2. Deklarasi Tipe

#### Tipe Dasar

```ts
let nama: string = "Raka";
let umur: number = 30;
let aktif: boolean = true;
```

#### Array

```ts
let angka: number[] = [1, 2, 3];
let nama: string[] = ["Bas", "Ho", "Rie"];
```

#### Tuple

Tuple memungkinkan array dengan tipe data yang berbeda:

```ts
let data: [string, number];
data = ["Alice", 25];
```

#### Enum

Enum digunakan untuk mendefinisikan kumpulan nilai konstan:

```ts
enum Negara {
  English,
  Spanish,
}

let englishOrSpanish: Negara = Negara.English;
```

#### Any

Tipe `any` digunakan ketika tipe variabel tidak diketahui atau bisa berubah:

```ts
let sesuatu: any = "Fasilkom";
sesuatu = 123; // valid
```

#### 3. Fungsi dalam TypeScript

Fungsi di TypeScript bisa memiliki tipe pada parameter dan nilai kembaliannya:

1. Fungsi Dasar

```ts
function penjumlahan(a: number, b: number): number {
  return a + b;
}
```

2. Arithmetic Operators

```js
let a = 3;
let x = (11 + 11) * a;
```

3. Parameter Opsional

#### Parameter opsional bisa ditandai dengan tanda `?`:

```ts
function salam(nama: string, pesan?: string): string {
  return pesan ? `${pesan}, ${nama}` : `Halo, ${nama}`;
}
```

4. Default Parameter

#### Cara mendefinisikan parameter default:

```ts
function sambutan(nama: string = "Tamu"): string {
  return `Selamat datang, ${nama}`;
}
```

#### 4. Functional Programming

Functional Programming (Funcpro) adalah paradigma pemrograman yang memfokuskan pada penggunaan fungsi murni (pure functions), komposisi fungsi, dan tidak adanya efek samping (side effects) dalam pengelolaan data.

##### Konsep Utama Functional Programming

##### a. Pure Functions (Fungsi Murni)

Fungsi murni adalah fungsi yang:

- untuk input yang sama, selalu mengembalikan output yang sama.
- Tidak memiliki efek samping seperti mengubah variabel di luar lingkupnya atau melakukan operasi I/O.

ex:

- Fungsi murni :
  ```ts
  function tambah(a, b) {
    return a + b;
  }
  ```
- Fungsi tidak murni :

```ts
let c = 10;
function tambah(a, b) {
  return a + b + c;
}
```

##### b. Immutability (Tidak Berubah)

Dalam Funcpro, data sebaiknya bersifat immutable, artinya tidak boleh diubah setelah dibuat. Di dalam Funcpro memodifikasi data, kita menghasilkan versi baru dari data tersebut

ex:

```ts
const angka = [1, 2, 3];
const angkaBaru = angka.map((n) => n * 2);
```
