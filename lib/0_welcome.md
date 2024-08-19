# Apa itu Functional Programming

<img src="https://media.licdn.com/dms/image/D5612AQGz0SZ37l3wgg/article-cover_image-shrink_720_1280/0/1676517964517?e=2147483647&v=beta&t=1X59FiqONO9DGZgcMGhEyLEv5H5iSyF7LRv1MSdxEKU" width="550">

Functional Programming (FP) adalah paradigma pemrograman yang berfokus pada penggunaan fungsi sebagai unit utama untuk melakukan komputasi.

Dalam FP, fungsi-fungsi dianggap sebagai objek-objek utama yang dapat diperlakukan sebagai nilai, yang memungkinkan mereka untuk disimpan dalam variabel, diteruskan sebagai argumen ke fungsi lain, dan dikembalikan sebagai hasil dari fungsi lain.

## Prinsip Utama Functional Programming

1. Immutability (Ketidakberubahan)
   - Data yang digunakan dalam FP bersifat tidak berubah setelah diciptakan. Alih-alih memodifikasi data, FP membuat salinan data dengan perubahan yang diterapkan. Ini membantu menghindari efek samping dan membuat program lebih mudah dipahami dan dikelola.
2. Pure Functions (Fungsi Murni)
   - Fungsi murni adalah fungsi yang menghasilkan output yang sama setiap kali diberikan input yang sama dan tidak menyebabkan efek samping (seperti mengubah variabel global atau menulis ke file).
3. First-Class and Higher-Order Functions (Fungsi Kelas Satu dan Fungsi Orde Tinggi)

   - Fungsi dalam FP adalah objek kelas satu, yang berarti mereka dapat disimpan dalam variabel, diteruskan sebagai argumen ke fungsi lain, dan dikembalikan sebagai hasil. Fungsi orde tinggi adalah fungsi yang dapat menerima fungsi lain sebagai argumen atau mengembalikan fungsi sebagai hasil.

4. Function Composition (Komposisi Fungsi)

   - FP mendukung komposisi fungsi, yaitu menggabungkan beberapa fungsi untuk membuat fungsi baru. Fungsi baru ini adalah hasil dari menerapkan satu fungsi setelah fungsi lainnya.

5. Declarative Approach (Pendekatan Deklaratif)

   - FP lebih fokus pada apa yang harus dilakukan daripada bagaimana melakukannya. Ini berarti Anda mendeklarasikan apa yang Anda inginkan sebagai hasil akhir tanpa harus merinci langkah-langkah detail bagaimana mencapainya.

6. Recursion (Rekursi)
   - Dalam FP, rekursi digunakan sebagai pengganti iterasi atau loop. Fungsi dapat memanggil dirinya sendiri untuk memecahkan masalah dengan cara yang lebih deklaratif.

## Mengapa Harus Functional Programming?

1. Keterbacaan dan Pemeliharaan Kode

   - Karena fungsi-fungsi murni tidak memiliki efek samping, kode menjadi lebih mudah dibaca dan dipahami. Ketika Anda memodifikasi kode, Anda hanya perlu memeriksa bagian yang relevan tanpa khawatir mempengaruhi bagian lain dari program.

2. Concurrency dan Paralelisme

   - Immutability memudahkan pengembangan aplikasi yang berjalan secara paralel atau bersamaan, karena data yang tidak berubah mengurangi risiko konflik antara thread atau proses.

3. Debugging dan Testing

   - Fungsi murni yang tidak memiliki efek samping lebih mudah untuk diuji dan debug. Karena mereka selalu menghasilkan output yang sama untuk input yang sama, Anda dapat dengan mudah memvalidasi perilaku mereka.

4. Reusability and Modularity
   - Fungsi yang dapat digunakan kembali dan dikomposisikan memfasilitasi pengembangan perangkat lunak yang modular. Ini membuat kode lebih terstruktur dan memudahkan integrasi komponen.

## Perbedaan dengan Paradigma Lain

1. Imperative Programming (Pemrograman Imperatif)

   - Paradigma imperatif, seperti yang digunakan dalam bahasa pemrograman seperti C atau Java, berfokus pada bagaimana tugas dilakukan. Anda mengatur langkah-langkah spesifik dan perubahan status program secara eksplisit. Ini sering melibatkan penggunaan variabel yang dapat berubah dan loop untuk iterasi.

2. Object-Oriented Programming (Pemrograman Berorientasi Objek)

   - Paradigma berorientasi objek, seperti yang ditemukan dalam bahasa seperti Java atau C++, berfokus pada objek dan interaksi mereka. Ini mengorganisir kode dalam bentuk objek yang memiliki status dan perilaku. Meskipun OOP mendukung beberapa prinsip FP, seperti enkapsulasi dan polimorfisme, FP lebih menekankan pada penggunaan fungsi dan ketidakberubahan.

3. Procedural Programming (Pemrograman Prosedural)
   - Paradigma prosedural, yang merupakan bentuk dari pemrograman imperatif, berfokus pada urutan prosedur atau fungsi yang dijalankan untuk memecahkan masalah. Sementara FP dan prosedural dapat berbagi beberapa kesamaan, FP lebih menekankan pada penggunaan fungsi murni dan ketidakberubahan.

## Kesimpulan

Functional Programming adalah paradigma yang kuat dan fleksibel yang menawarkan pendekatan deklaratif untuk memecahkan masalah dengan fungsi murni, immutability, dan komposisi fungsi.

Ini berbeda dari paradigma lain dalam hal fokus pada fungsi sebagai unit utama dan penghindaran efek samping, yang dapat meningkatkan keterbacaan, pemeliharaan, dan kemampuan paralelisme aplikasi Anda.

Meskipun mungkin memerlukan perubahan cara berpikir bagi banyak pengembang, manfaat jangka panjang dari FP dapat membuatnya menjadi pilihan yang berharga dalam pengembangan perangkat lunak modern.
