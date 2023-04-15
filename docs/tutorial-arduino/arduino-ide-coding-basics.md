---
sidebar_position: 4
---

# Arduino IDE Code Basics

Topik ini akan menjelaskan secara singkat mengenai kode-kode dasar pemrograman Arduino pada Arduino IDE. Karena bahasa pemrograman yang akan digunakan dalam Arduino IDE menggunakan bahasa C dan C++, maka kode-kode pemrograman Arduino akan sama atau lebih tepatnya mirip seperti bahasa C dan C++.

Walaupun nantinya ada beberapa dari kode-kode dasar pemrograman yang disebut dalam topik ini akan dijelaskan kembali secara rinci pada topik **Penjelasan Program** yang akan disediakan pada tiap tutorial, namun tidak ada salahnya untuk memulai terlebih dahulu secara singkat.

Agar proses belajar menjadi lebih fun dan tidak terlalu membuat stress, teman-teman bisa cukup membacanya saja tanpa harus menghafal keseluruhan topik ini. Karena nantinya akan dirincikan ulang pada topik **Penjelasan Program** dalam tiap tutorial.

Jika ada istilah-istilah yang belum teman-teman ketahui ketika membaca topik ini, jangan cemas, karena nantinya istilah-istilah tersebut akan dijelaskan lagi lebih rinci selama perjalanan teman-teman melalui tutorial yang disediakan.

## Tanda Kurung

Ada dua jenis tanda kurung yang digunakan dalam pemrograman Arduino, yaitu tanda kurung biasa () dan tanda kurung kurawal {}.

### Tanda Kurung Biasa ()

Tanda kurung biasa yang menggunakan simbol () umumnya digunakan untuk mendefinisikan parameter, argumen, metode, membuat fungsi ataupun kode perintah.

Simbol `(` disebut sebagai tanda kurung buka, dan simbol `)` disebut sebagai tanda kurung tutup. Misalnya pada potongan kode di bawah ini:

```Arduino showLineNumbers
(
Namaku adalah RoboKarsa
)
```

Berdasarkan potongan kode di atas, pernyataan "Namaku adalah RoboKarsa" diapit oleh tanda kurung, dimana tanda kurung buka `(` berada baris nomor 1, dan tanda kurung tutup `)` berada pada baris 3.

Umumnya, kita akan menulisnya sebagai `(Namaku adalah RoboKarsa)` sehingga kita akan mendapatkan satu baris seperti pada potongan kode di bawah ini:

```Arduino showLineNumbers
(Namaku adalah RoboKarsa)
```

Namun, karena itu adalah bagaimana kita menulis dalam kalimat biasa bahasa Indonesia, sehingga cara seperti itu tidak disarankan, karena kita tidak bisa mengetahui dimana letak tanda kurung buka dan tanda kurung tutup jika sudah memiliki banyak kode.

Selain itu, tanda kurung biasa juga digunakan dalam proses persamaan matematika. Misalnya seperti pada potongan kode di bawah ini:

```Arduino showLineNumbers
x=21+(23-3)x2
```

Tanda kurung pada potongan kode di atas digunakan untuk menentukan prioritas pengerjaan dalam suatu persamaan matematika. Karena operasi pengurangan antara 23 dengan 3 berada dalam tanda kurung, maka operasi tersebut harus diselesaikan terlebih dahulu sebelum operasi lainnya.

Ingat selalu, dimana ada tanda kurung buka `(`, akan selalu ada tanda kurung tutup `)`.

### Tanda Kurung Kurawal {}

Tanda kurung kurawal menggunakan tanda kurung kurawal {} yang sisinya bergelombang. Sama seperti tanda kurung biasa, terdapat tanda kurawal buka `{` dan tanda kurawal tutup `}`.

Tanda kurung kurawal utamanya akan digunakan untuk membungkus statement atau perintah dalam kode. Misalnya seperti pada potongan kode di bawah ini:

```Arduino showLineNumbers
void lampuON(){
    digitalWrite(13, HIGH);
}
```

Diatas adalah sepotong kode fungsi bernama lampuON yang akan digunakan untuk menyalakan lampu. Perintah yang digunakan untuk menyalakan lampu ditulis dalam kode yang berada pada baris nomor 2, yakni `digitalWrite(13,HIGH)`.

Perhatikan bahwa kode perintah `digitalWrite(13,HIGH)` dibungkus oleh tanda kurawal, dimana tanda kurawal buka berada pada baris nomor 1 dan tanda kurawal tutup berada pada baris 3.

## Baris Komentar

Biasanya, kita akan meninggalkan catatan dalam kode program kita, sebagai pengingat untuk apa program tersebut dibuat atau ditulis. Kita bisa menulis catatan dengan menggunakan komentar. Terdapat dua jenis komentar yang dapat kita buat, yaitu komentar baris tunggal dan komentar baris ganda.

### Komentar Baris Tunggal

Komentar baris tunggal merupakan komentar yang hanya bisa dibuat dalam satu baris saja. Untuk membuat komentar baris tunggal, kita menggunakan simbol `//`, yaitu dua buah simbol garis miring /.

Misalnya, jika kita ingin menulis catatan "Program ini merupakan program pertama yang saya buat berdasarkan Tutorial 1 dari situs robokarsa.github.io/tutorials". Jika kita ingin menulisnya dalam kode program, maka akan menjadi seperti ini:

```Arduino showLineNumbers
//Program ini merupakan program pertama yang saya buat berdasarkan Tutorial 1 dari situs robokarsa.github.io/tutorials
void lampuON(){
    digitalWrite(13, HIGH);
}
```

Kini teman-teman memiliki komentar pada baris pertama. Perlu diingat, semua baris yang dimulai dengan simbol // akan diabaikan oleh Arduino. Sehingga hanya kita saja yang bisa melihatnya, sedangkan Arduino tidak bisa.

### Komentar Baris Ganda

Bagaimana jika misalnya catatan yang kita buat sangat panjang dan tidak cukup dalam satu baris saja? Kita bisa menggunakan fitur komentar baris ganda. Perhatikan contoh kode di bawah:

```Arduino showLineNumbers
//Tutorial 1 akan belajar bagaimana cara menyalakan lampu secara otomatis
//Sumber Tutorial nya dari situs robokarsa.github.io/tutorials
//Peralatan dan perlengkapan yang dibutuhkan adalah Arduino Nano, Kabel USB, dan Laptop

void lampuON(){
    digitalWrite(13, HIGH);
}
```

Pada potongan kode di atas, kita bisa lihat bahwa terdapat 3 baris komentar yang berturut-turut dimulai dari baris 1, 2, hingga 3.

Kita bisa menggunakan fitur komentar baris ganda untuk menghemat waktu kita dengan menggunakan simbol `/*` sebagai pembuka komentar dan simbol `*/` sebagai penutup komentar. Contoh penggunaannya akan seperti pada potongan kode di bawah ini:

```Arduino showLineNumbers
/*
Tutorial 1 akan belajar bagaimana cara menyalakan lampu secara otomatis
Sumber Tutorial nya dari situs robokarsa.github.io/tutorials
Peralatan dan perlengkapan yang dibutuhkan adalah Arduino Nano, Kabel USB, dan Laptop
*/

void lampuON(){
    digitalWrite(13, HIGH);
}
```

Kini catatan yang kita buat pada baris 1, 2, dan 3 sebelumnya dibungkus oleh simbol `/*` dan `*/` sehingga kita bisa membuat catatan sebanyak apapun yang kita mau tanpa harus berulang-ulang menggunakan simbol komentar baris tunggal `//`.

## Timing Arduino

Sebagai manusia yang mengenal waktu, kita membutuhkan agar bisa menentukan waktu dalam pemrograman Arduino. Kita menggunakan kode perintah `delay()` untuk menentukan waktu.

Jika misalnya kita ingin menyalakan lampu selama 5 detik, kita bisa menggunakan perintah `delay(5000)`. Lho, kok 5000? Bukankah nantinya menjadi 5000 alias lima ribu detik? sementara kita hanya butuh 5 detik saja?

Satuan waktu utama yang digunakan dalam pemrograman Arduino adalah mili sekon atau dalam bahasa Inggrisnya mili second.

Jika kita ingin 5 detik, maka kita memasukkan 5000 pada `delay()` menjadi `delay(5000)`. Karena 1 detik sama dengan 1000 mili sekon. 2 detik sama dengan 2000 mili sekon. 1,5 detik sama dengan 1500 mili sekon.

## Tanda Koma dan Tanda Titik

Umumnya, simbol tanda koma yang biasa digunakan oleh manusia adalah `,` bukan? Jika kita ingin menulis angka satu koma lima, maka kita menulisnya dengan 1,5 bukan?

Namun, dalam pemrograman Arduino, penulisan seperti itu akan menghasilkan error dan tidak terbaca oleh Arduino. Arduino hanya akan menerima tanda titik `.` sebagai simbol untuk tanda koma. Jadi, kita akan menulis 1.5 jika kita ingin menulis 1,5 pada program Arduino.
