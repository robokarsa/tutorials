---
sidebar_position: 3
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Tutorial 7 - Alarm Sensor Cahaya Lanjutan

## Selayang Pandang

Pada Tutorial 6 sebelumnya kita telah mempelajari kontrol kondisional _if else_ untuk menampilkan pesan teks pada Serial Monitor berdasarkan dua kondisi cahaya gelap atau terang.

Namun bagaimana jika kita menggunakan dua kondisi atau lebih seperti:

1.  Terang,
2.  Cukup terang,
3.  Terang sekali,
4.  Sangat terang,
5.  Terlalu terang, dan seterusnya?

Bagaimana jika kita ingin lampu merah menyala jika nilai sensor cahaya berada pada rentang angka 0-400, dan lampu kuning menyala jika nilai sensor cahaya berada pada rentang angka 450-800, dan lampu merah menyala jika nilai sensor cahaya berada pada rentang angka 950-1000?

Kita akan menggunakan perintah rentang nilai yang dimiliki Arduino IDE untuk mengatur penggolongan nilai intensitas cahaya sehingga dapat memiliki lebih dari dua kondisi yang berbeda untuk kontrol kondisional _if else_.

Pada Tutorial 7 ini kita akan mempelajari penggunaan fungsi rentang nilai dan logika AND. Logika AND merupakan logika yang yang hanya mengeluarkan pernyataan TRUE (Benar) apabila dua buah kondisi memiliki nilai yang sama dan mengeluarkan pernyataan FALSE (Salah) jika kedua kondisi tidak memiliki nilai yang sama.

Logikanya seperti ini, jika kondisi pertama, motor memiliki bensin (kondisi positif) dan kondisi kedua, motor memiliki roda (kondisi positif), maka motor akan dapat berjalan (pernyataan TRUE).

Sedangkan jika kondisi pertama negatif, yakni motor tidak memiliki bensin (kondisi negatif) dan kondisi kedua positif, yaitu motor memiliki roda (kondisi positif), maka motor tidak akan dapat berjalan (pernyataan FALSE).

Untuk mempermudah mengingatnya, kita gunakan tabel kebenaran logika AND berikut:

| No  | Kondisi 1 | Kondisi 2 | Pernyataan |
| :-: | :-------: | :-------: | :--------: |
|  1  |     +     |     +     |    TRUE    |
|  2  |     +     |     -     |   FALSE    |
|  3  |     -     |     +     |   FALSE    |
|  4  |     -     |     -     |    TRUE    |

Bingung yah cara membacanya? Tenang ada penjelasannya kok.

Penjelasan:

- Pada baris no 1, apabila Kondisi 1 bernilai + (Positif) dan Kondisi 2 bernilai + (Positif), maka pernyataan akan bernilai TRUE.
- Pada baris no 2, apabila Kondisi 2 bernilai + (Positif) dan Kondisi 2 bernilai - (Negatif), maka pernyataan akan bernilai FALSE.
- Pada baris no 3, apabila Kondisi 3 bernilai - (Negatif) dan Kondisi 2 bernilai + (Positif), maka pernyataan akan bernilai FALSE.
- Pada baris no 4, apabila Kondisi 1 bernilai - (Negatif) dan Kondisi 2 bernilai - (Negatif), maka pernyataan akan bernilai TRUE.

Masih bingung dengan penjelasan secara bahasa? Bagaimana kalau kita gunakan pendekatan matematika?

Pada dasarnya logika AND sama seperti perkalian.

| No  | Kondisi 1 | Kondisi 2 | Pernyataan | Kalimat Matematika |
| :-: | :-------: | :-------: | :--------: | :----------------: |
|  1  |     +     |     +     |    TRUE    |     1 x 1 = 1      |
|  2  |     +     |     -     |   FALSE    |     1 x 0 = 0      |
|  3  |     -     |     +     |   FALSE    |     0 x 1 = 0      |
|  4  |     -     |     -     |    TRUE    |     0 x 0 = 0      |

Singkatnya, logika AND hanya akan bernilai TRUE apabila ada dua kondisi yang bernilai sama. Dan akan bernilai FALSE jika ada dua kondisi yang memiliki nilai yang berbeda.

Pada bahasa pemrograman Arduino/Simplified C++, logika AND disimbolkan dengan simbol && (Double Ampersand).

Contoh syntaks penulisannya seperti ditunjukkan pada baris 10 oleh potongan kode di bawah ini. Kita akan mempelajari lebih lanjut bagaimana penjelasan dari syntaks tersebut.

```arduino showLineNumbers
if(nilaiSensor>100 && nilaiSensor200)
```

Untuk memberikan kondisi bahwa nilai sensor lebih besar atau lebih kecil, kita menggunakan simbol `<` atau simbol `>`. Contoh penggunaannya sebagai berikut:

| No  |    Kondisi yang diinginkan     | Apabila menggunakan simbol simbol `>` | Apabila menggunakan simbol < |
| :-: | :----------------------------: | :-----------------------------------: | :--------------------------: |
|  1  | nilaiSensor lebih besar dari 0 |             nilaiSensor>0             |        0<nilaiSensor         |
|  2  | nilaiSensor lebih kecil dari 0 |             0>nilaiSensor             |        nilaiSensor<0         |

Penjelasan singkat dari tabel di atas adalah sebagai berikut, pada baris no 1, apabila kita ingin membuat kondisi yang berbunyi “nilaiSensor lebih besar dari 0” maka kita bisa menggunakan salah satu simbol > atau <.

Apabila kita menggunakan simbol `>`, maka kita bisa menggunakan syntaks “nilaiSensor>0” yang jika diterjemahkan dalam bahasa manusia akan berbunyi, `nilaiSensor` lebih besar dari 0.

Sedangkan jika kita menggunakan simbol `<`, maka kita bisa menggunakan syntaks “0<nilaiSensor” yang juga akan berbunyi, `nilaiSensor` lebih besar dari 0.

## Mulai Beraksi 🚀

Baik, sebelum mulai beraksi, pastikan teman-teman sudah membaca Prasyarat, Target Pelajaran, dan Komponen Yang Dibutuhkan ya.

Klik pada salah satu dari ketiga tombol di bawah ini untuk membuka Prasyarat, Target Pelajaran dan Komponen Yang Dibutuhkan.

<Tabs className="unique-tabs">
<TabItem value="Prasyarat 🔑">

- Sudah lolos Tutorial 6 - Alarm Sensor Cahaya
- Sudah mempelajari Arduino Nano Expansion Board pada materi **[Arduino Nano Expansion Board](/docs/tutorial-arduino/arduino-hardware.md#arduino-nano-expansion-board)**

Kalau teman-teman merasa belum memenuhi prasyarat yang dibutuhkan, diharapkan untuk membaca dan memenuhinya terlebih dahulu.

</TabItem>

<TabItem value="Target Pelajaran 🎯">

- Memahami kontrol kondisional `if else` menggunakan lebih dari dua kondisi.
- Memahami bagaimana menampilkan pesan berdasarkan kondisi yang berbeda-beda.
- Memahami perintah rentang nilai.
- Memahami penggunaan logika AND dengan simbol &&.
- Memahami penggunaan simbol `<` dan `>` untuk membedakan angka besar dan angka kecil.

</TabItem>

<TabItem value="Komponen Yang Dibutuhkan 🛠">

- 1 x Arduino Nano
- 1 x Kabel USB Arduino Nano
- 1 x Komputer/Laptop
- 1 x Sensor Cahaya
- 3 x Kabel Jumper Female-Female
- 1 x Senter
- 1 X Modul LED Lampu Lalu Lintas Mini

</TabItem>
</Tabs>

:::caution Perhatian

Penting untuk memperhatikan setiap langkah-langkah yang diberikan dan tidak melakukan apapun diluar perintah langkah yang diberikan.

Kenapa? Hal ini untuk mencegah kerusakan yang tidak diinginkan pada komponen apabila bertindak di luar langkah pelajaran yang diberikan dan tidak mengetahui dengan pasti apa yang teman-teman lakukan.

:::

### Menghubungkan Pin-Pin

Mari kita ikuti langkah-langkah yang disediakan.

1. Kita akan menghubungkan pin-pin Modul Sensor Cahaya dan Modul LED ke Arduino Nano dengan menggunakan kabel jumper seperti pada gambar Wiring Diagram di bawah ini.

   <p align="center" width="100%">

   <img width="80%" src={require('../beginner-level/img/img7/tutorial-7-0-wiring-diagram.png').default} alt="Arduino Light Sensor Pins"/>

   </p>

Jika gambar Wiring Diagram di atas kurang jelas, teman-teman bisa gunakan tabel Wiring Diagram di bawah ini.

<table>
<tr><th>Sensor Cahaya </th><th>Modul LED</th></tr>
<tr><td>

| Sensor Cahaya | Arduino Nano Expansion Board |
| :-----------: | :--------------------------: |
|    Pin AO     |            Pin A0            |
|    Pin GND    |            Pin G             |
|    Pin VCC    |            Pin V             |

</td><td>

| Modul LED | Arduino Nano Expansion Board |
| :-------: | :--------------------------: |
|    GND    |             GND              |
|     R     |              6               |
|     Y     |              5               |
|     G     |              4               |

</td></tr> </table>

:::danger Peringatan
Sebelum menyalakan Arduino Nano, harap periksa kembali rangkaiannya. Apakah sudah sama dengan Wiring Diagram?

Periksa kembali posisi pemasangan kaki-kaki. Diharapkan agar tidak terbalik dan sesuai dengan keterangan pin agar tidak merusak komponen.
:::

Setelah Sensor Cahaya dan Arduino Nano saling terhubung, maka hasilnya akan seperti pada gambar di bawah ini.

<p align="center" width="100%">

<img width="100%" src={require('../beginner-level/img/img7/tutorial-7-1-wiring-picture.png').default} alt="Arduino Light Sensor Wiring Diagram"/>

</p>

Warna kabel yang digunakan bebas dan tak harus sama dengan gambar di atas. Namun yang harus diperhatikan, pastikan kaki Potensiometer terhubung ke posisi pin yang sama seperti pada gambar di atas. Gunakan Tabel Wiring Diagram untuk memastikannya.

### Mengetik Program

2. Bukalah Arduino IDE, kemudian buatlah sketch baru. Beri sketch baru tersebut dengan nama TUTORIAL_7_ALARM_SENSOR_CAHAYA_LANJUTAN dan simpan dalam folder **Program Tutorials** yang telah kita buat pada Tutorial 1 sebelumnya. Jika terlupa bagaimana membuat nama sketch, silahkan buka kembali Tutorial 1 sebelumnya.

   <p align="center" width="100%">

   <img width="80%" src={require('../beginner-level/img/img7/tutorial-7-2-new-sketch.png').default} alt="Arduino IDE Sketch Program"/>

   </p>

3. Kemudian ketik program berikut pada sketch tersebut.

```arduino title="TUTORIAL_7_ALARM_SENSOR_CAHAYA_LANJUTAN.ino" showLineNumbers
void setup() {
pinMode(4, OUTPUT);
pinMode(5, OUTPUT);
pinMode(6, OUTPUT);
}

void loop() {
int nilaiSensor=analogRead(A0);

 if(nilaiSensor>100 && nilaiSensor<200){
    digitalWrite(4, LOW);
    digitalWrite(5, LOW);
    digitalWrite(6, HIGH);
 }

 if(nilaiSensor>250 && nilaiSensor<550){
    digitalWrite(4, LOW);
    digitalWrite(5, HIGH);
    digitalWrite(6, LOW);
 }

 if(nilaiSensor>600 && nilaiSensor<850){
    digitalWrite(4, HIGH);
    digitalWrite(5, LOW);
    digitalWrite(6, LOW);
 }

 else if(nilaiSensor>850){
    digitalWrite(4, LOW);
    digitalWrite(5, LOW);
    digitalWrite(6, LOW);
 }

 delay(1);
}
```

4. Periksa kembali ketikan sketch program. Pastikan agar ketikan sketch program sama persis seperti diminta agar tidak mengalami error saat compiling. Jika sudah selesai mengetik program, cobalah memeriksa apakah ketikan Anda sudah benar atau belum dengan cara menekan tombol verify atau ikon di samping 👉 <img src={require('../newbies-level/img/arduino-ide-tool-bar-verify.png').default} alt="Ultrasonic Sensors"/>.

5. Jika proses verify selesai dan information bar menunjukkan “Done compiling”, berarti program yang teman-teman ketik sudah benar dan lanjutkan pada langkah berikutnya.
   <p align="center" width="100%">

   <img width="80%" src={require('../beginner-level/img/img7/tutorial-7-3-compiled.png').default} alt="Arduino IDE Sketch Program"/>

   </p>

Selanjutnya upload program tersebut ke Arduino Nano. Namun sebelum upload, pastikan teman-teman sudah mengkonfigurasi Arduino IDE dengan memilih jenis board, memilih jenis processor, dan memilih nomor port yang tepat seperti pada Level sebelumnya.

Kita tidak akan menunjukkan langkah-langkah tersebut lagi pada level Beginner karena dirasa teman-teman pasti sudah menghafal dan mengingat bagaimana mengkonfigurasi Arduino IDE pada level sebelumnya.

Apabila telah teman-teman upload, cobalah buka Serial Monitor dan amati apa yang terjadi pada Modul LED jika kita menyorot cahaya senter ke Sensor Cahaya.

## Penjelasan Program

```arduino title="TUTORIAL_7_ALARM_SENSOR_CAHAYA_LANJUTAN.ino" showLineNumbers
void setup() {
pinMode(4, OUTPUT);
pinMode(5, OUTPUT);
pinMode(6, OUTPUT);
}

void loop() {
int nilaiSensor=analogRead(A0);

 if(nilaiSensor>100 && nilaiSensor<200){
    digitalWrite(4, LOW);
    digitalWrite(5, LOW);
    digitalWrite(6, HIGH);
 }

 if(nilaiSensor>250 && nilaiSensor<550){
    digitalWrite(4, LOW);
    digitalWrite(5, HIGH);
    digitalWrite(6, LOW);
 }

 if(nilaiSensor>600 && nilaiSensor<850){
    digitalWrite(4, HIGH);
    digitalWrite(5, LOW);
    digitalWrite(6, LOW);
 }

 else if(nilaiSensor>850){
    digitalWrite(4, LOW);
    digitalWrite(5, LOW);
    digitalWrite(6, LOW);
 }

 delay(1);
}
```

Pada blok fungsi `setup()` terdapat perintah `pinMode()` pada baris 2, 3, dan 4. Perintah `pinMode()` ini akan memerintahkan Arduino Nano untuk menugaskan pin digital Arduino Nano nomor 4, 5, dan 6 sebagai pin OUTPUT atau pin keluaran untuk memberikan sinyal tegangan 5V (Logika HIGH) ataupun tegangan 0V (Logika LOW) pada pin nomor 4, 5, dan 6.

Logika HIGH dan LOW ini akan menentukan kondisi nyala dan padam nya lampu. Jika diberi logika HIGH, maka lampu akan menyala karena mendapat tegangan 5V, sedangkan jika diberi logika LOW, maka lampu akan padam karena mendapat tegangan 0V.

Kemudian terdapat fungsi `loop()` sebagaimana biasanya yang dimulai pada baris 8 dan diakhiri pada baris ke 35. Pada baris 8 terdapat perintah `analogRead()` untuk membaca nilai analog dari sinyal sensor cahaya yang masuk melalui pin `A0`.

Nilai hasil pembacaan tersebut akan disimpan dalam variabel yang bernama `nilaiSensor` dengan tipe data `int` (singkatan dari integer), yakni tipe data yang hanya hanya bisa menampung nilai yang berupa bilangan bulat seperti 1, 2, 3, 200, 125, 325, 621 dan seterusnya, dan bukan bilangan desimal seperti 0.32, 0.42 dst nya.

Perlu diingat, dalam pemrograman, menggunakan simbol titik untuk menggantikan peran tanda koma dalam bilangan desimal.

<p align="center" width="100%">

<img width="80%" src={require('../beginner-level/img/img7/tutorial-7-4-exp.png').default} alt="Arduino IDE Sketch Program"/>

</p>

Berdasarkan ilustrasi di atas, apabila misalnya hasil pembacaan pada pin `A0` dengan perintah `analogRead()` bernilai `967`, maka akan disimpan pada variable `nilaiSensor` sehingga variable `nilaiSensor` sekarang menyimpan angka `967`.

Kemudian dalam fungsi `loop()` terdapat 3 buah blok fungsi `if()` dan satu buah fungsi `else()` dimana masing-masing blok fungsi tersebut memiliki parameter kondisi yang berbeda-beda.

Dalam hal ini, parameter kondisi tersebut adalah rentang nilai sensor yang berbeda-beda untuk menyalakan masing-masing ketiga led pada Modul LED secara terpisah.

<p align="center" width="100%">

<img width="100%" src={require('../beginner-level/img/img7/tutorial-7-5-exp.png').default} alt="Arduino IDE Sketch Program"/>

</p>

Blok fungsi `if()` ke-1 menempati baris 10 hingga 14. Pada baris 10 Fungsi `if()` terdapat parameter kondisi yang berupa rentang nilai dari 100-200. Penulisan parameter kondisi untuk menentukan rentang nilai dari 100-200 adalah sebagai berikut:

<p align="center" width="100%">

<img width="100%" src={require('../beginner-level/img/img7/tutorial-7-6-exp.png').default} alt="Arduino IDE Sketch Program"/>

</p>

Blok fungsi `if()` ke-1 menempati baris 10 hingga 14. Pada baris 10 Fungsi `if()` terdapat parameter kondisi yang berupa rentang nilai dari 100-200. Penulisan parameter kondisi untuk menentukan rentang nilai dari 100-200 adalah sebagai berikut:

```arduino
nilaiSensor>100 && nilaiSensor<200
```

Cara membaca parameter kondisi tersebut adalah sebagai berikut: “`nilaiSensor` lebih besar dari 100 DAN `nilaiSensor` kurang dari 200”. Ingat kembali bahwa logika AND menggunakan simbol && (Double Ampersand). Secara keseluruhan, baris 10 ini,

```arduino
if(nilaiSensor>100 && nilaiSensor<200)
```

Akan bermakna, "jika `nilaiSensor` lebih besar dari 100 dan kurang dari 200", dengan kata lain, "jika `nilaiSensor` berada pada rentang antara 100 dan 200".

Jika parameter kondisi fungsi `if()` tersebut terpenuhi atau dengan kata lain, angka yang disimpan dalam variabel `nilaiSensor` berada pada rentang angka 100-200, maka blok perintah di dalam fungsi tersebut akan dijalankan, yakni menyalakan lampu merah dan memadamkan lampu hijau dan lampu kuning.

Blok perintah fungsi `if()` ke-1 ditandai dalam kotak biru. Blok perintah ini akan dijalankan apabila parameter kondisi fungsi `if()` ke-1 terpenuhi (jika angka yang disimpan dalam variabel `nilaiSensor` berada pada rentang angka 100-200).

<p align="center" width="100%">

<img width="100%" src={require('../beginner-level/img/img7/tutorial-7-7-exp.png').default} alt="Arduino IDE Sketch Program"/>

</p>

Terdapat tiga buah perintah `digitalWrite()` dalam blok perintah tersebut. Masing-masing digunakan untuk memadamkan dan menyalakan lampu G, Y, R pada Modul LED yang terhubung pada pin 4, 5, dan 6 Arduino Nano Expansion Board.

| Modul LED | Arduino Nano Expansion Board |
| :-------: | :--------------------------: |
|    GND    |             GND              |
|     R     |              6               |
|     Y     |              5               |
|     G     |              4               |

Ingat kembali tabel Wiring Diagram yang teman-teman gunakan sebelumnya. Pin nomor 4 Arduino Nano terhubung pada Pin G yang merupakan lampu hijau pada modul LED. Pin nomor 5 Arduino Nano terhubung pada pin Y yang merupakan lampu kuning pada modul LED. Dan pin nomor 6 Arduino Nano terhubung pada pin R yang merupakan lampu merah pada modul LED.

Jika parameter kondisi pada fungsi `if()` ke-1 terpenuhi, maka blok perintah dalam fungsi `if()` ke-1 akan dijalankan dan akan menyalakan lampu merah dan memadamkan lampu hijau serta lampu kuning.

Setelah blok perintah fungsi `if()` ke-1 dijalankan, maka berikutnya Arduino Nano akan melanjutkan membaca `nilaiSensor` dan memeriksa fungsi `if()` nomor keberapa berikutnya yang terpenuhi parameter kondisinya.

Namun jika parameter kondisi pada fungsi `if()` ke-1 tidak terpenuhi, maka blok perintah fungsi `if()` ke-1 tidak akan dijalankan dan Arduino Nano akan melanjutkan memeriksa parameter kondisi pada fungsi `if()` ke-2, namun jika parameter kondisi pada fungsi `if()` ke-2 tidak terpenuhi, maka Arduino Nano akan melanjutkan memeriksa parameter kondisi fungsi `if()` ke-3.

Namun jika Arduino Nano telah memeriksa parameter kondisi dalam fungsi `if()` ke-1, ke-2, dan ke-3 tidak ada yang terpenuhi, maka akan menjalankan blok perintah milik fungsi `else if()`. Yakni mematikan semua lampu pada Modul LED.

<p align="center" width="100%">

<img width="100%" src={require('../beginner-level/img/img7/tutorial-7-8-exp.png').default} alt="Arduino IDE Sketch Program"/>

</p>

Fungsi `else if()` perlu ditambahkan pada bagian paling akhir seluruh fungsi `if()` yang ada untuk menentukan apa yang harus dilakukan oleh Arduino Nano jika seluruh fungsi `if()` yang ada tidak terpenuhi parameter kondisinya.

Sementara perintah `delay()` pada baris 34 digunakan agar Arduino Nano memperbarui `nilaiSensor` setiap 1 milidetik sehingga Arduino Nano lebih cepat dalam memperbarui hasil pembacaan nilaiSensor berikut nya.

Ilustrasi urutan kerja program tersebut akan digambarkan secara singkat pada bagan flowchart berikut:

<p align="center" width="100%">

<img width="100%" src={require('../beginner-level/img/img7/tutorial-7-9-exp.png').default} alt="Arduino IDE Sketch Program"/>

</p>

1. Mulanya, Arduino Nano akan menjalankan perintah membaca sinyal analog pada pin A0 menggunakan perintah `analogRead()`.
2. Hasil pembacaan sinyalnya akan disimpan dalam variabel bernama `nilaiSensor`.
3. Kemudian angka yang tersimpan dalam variabel `nilaiSensor` akan diperiksa apakah memenuhi salah satu dari keempat kondisi berikut:
   1. Berada di antara angka 100-200
   2. Berada di antara angka 250-550,
   3. Berada di antara angka 600-850, atau
   4. Di atas angka 850.
4. Apabila angka dalam variabel `nilaiSensor` setelah diperiksa ternyata memenuhi salah satu dari keempat kondisi di atas, maka akan menyalakan atau mematikan lampu sesuai dengan yang ada dalam kondisi yang terpenuhi tersebut.
5. Setelah menyalakan dan memadamkan lampu sesuai dengan kondisi yang terpenuhi, program akan memeriksa apakah Arduino Nano masih menyala atau sudah padam.
6. Jika masih menyala, maka akan kembali lagi pada langkah 1.
7. Jika sudah padam, maka program akan berhenti alias selesai.

<br/>

## Tantangan Tutorial 7

Selanjutnya kita akan masuk pada topik Tantangan 7.

### Tantangan 1

Tantangan pertama, teman-teman ditantang untuk menggantikan lampu LED dengan pesan teks pada Serial Monitor.

Kita akan memberikan petunjuk untuk tantangan pertama dengan gambar di bawah.

<p align="center" width="100%">

<img width="100%" src={require('../beginner-level/img/img7/tutorial-7-10-challenge-1.png').default} alt="Arduino IDE Sketch Program"/>

</p>

Teks dalam kotak hijau tersebut harus diterjemahkan menjadi perintah yang dapat dimengerti oleh Arduino. Kalau teman-teman terlupa bagaimana perintah dasar mencetak pesan pada Serial Monitor, disarankan membuka kembali Tutorial 3.

Kemudian, hasil program pada Serial Monitor haruslah seperti pada gambar di bawah ini.

Apabila misalnya nilai hasil pembacaaan sensor cahaya yang tersimpan dalam variabel `nilaiSensor` memiliki nilai yang berada di antara angka 600-850, maka akan mencetak pesan "Agak Terang".

<p align="center" width="100%">

<img width="100%" src={require('../beginner-level/img/img7/tutorial-7-11-challenge-1.png').default} alt="Arduino IDE Sketch Program"/>

</p>

### Tantangan 2

Pada tantangan pertama sebelumnya kita sudah bisa menampilkan pesan teks sesuai dengan 3 kondisi cahaya yang berbeda-beda. Namun ada kalanya kita penasaran berapa sebenarnya nilai sensor yang terbaca ketika pesan tersebut tampil pada Serial Monitor.

Pada tantangan kedua teman-teman ditantang untuk menampilkan pesan teks beserta nilai sensor yang terbaca seperti pada gambar di bawah ini

<p align="center" width="100%">

<img width="100%" src={require('../beginner-level/img/img7/tutorial-7-12-challenge-2.png').default} alt="Arduino IDE Sketch Program"/>

</p>

Dimana pada sisi kiri menunjukkan pesan teks dan sisi kanan menunjukkan nilai sensor yang dipisah dengan satu buah spasi diantara keduanya.

Petunjuk tantangan kedua ini adalah Tutorial 4 dan “sedikit” bocoran kode di bawah ini.

<p align="center" width="100%">

<img width="100%" src={require('../beginner-level/img/img7/tutorial-7-13-challenge-2.png').default} alt="Arduino IDE Sketch Program"/>

</p>

### Tantangan 3

Setelah berhasil melewati dua tantangan sebelumnya, sekarang tantangan terakhir adalah, teman-teman harus menampilkan nilai sensor pada serial monitor seperti pada Tantangan Kedua dan menampilkan pesan teks seperti pada Tantangan Pertama dan menyalakan warna lampu sesuai pada Pelajaran #7 ini.

Ada petunjuknya nih. Ditutup dikit ya supaya teman-teman makin jago.

<p align="center" width="100%">

<img width="100%" src={require('../beginner-level/img/img7/tutorial-7-14-challenge-3.png').default} alt="Arduino IDE Sketch Program"/>

</p>
