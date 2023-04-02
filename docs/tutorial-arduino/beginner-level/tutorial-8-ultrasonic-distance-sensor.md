---
sidebar_position: 4
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Tutorial 8 - Ultrasonic Distance Sensor

## Apa itu Ultrasonic Distance Sensor?

Pada tutorial kali ini, kita akan mempelajari komponen baru, yakni Ultrasonic Distance Sensor. Nama tersebut terdiri dari tiga kata dalam bahasa Inggris, yakni "Ultrasonic", "Distance", "Sensor". Kata "Ultrasonic" berarti Ultrasonik, kata "Distance" berarti Jarak, dan kata "Sensor" juga kita terjemahkan sebagai "Sensor".

Secara keseluruhan akan memiliki arti sebagai Sensor Jarak Ultrasonik. Komponen ini, sesuai namanya, digunakan untuk mengukur jarak dengan menggunakan prinsip kerja pantulan suara Ultrasonik.

Ultrasonik merupakan istilah yang digunakan untuk suara yang memiliki frekuensi di atas 20.000 Hz. Yang mana suara dengan frekuensi tinggi tersebut tidak bisa didengar oleh telinga manusia.

Ilustrasi pantulan suara ultrasonik yang dimaksud diilustrasikan seperti pada gambar di bawah ini.

<p align="center" width="100%">

<img width="80%" src={require('../beginner-level/img/img8/tutorial-8-0-bouncing-sound.png').default} alt="Arduino Light Sensor Pins"/>

</p>

Komponen T merupakan singkatan dari "Transmitter" yang merupakan sebuah speaker mini untuk mentransmisikan atau mengeluarkan suara ultrasonik. Komponen R merupakan singkatan dari "Receiver" yang merupakan sebuah mikrofon mini untuk menangkap suara ultrasonik yang dipantulkan.

Apabila ada halangan atau objek di depan sensor, suara ultrasonik yang dihasilkan oleh komponen T akan dipantulkan oleh halangan atau objek.

<p align="center" width="100%">

<img width="80%" src={require('../beginner-level/img/img8/tutorial-8-1-bouncing-sound.png').default} alt="Arduino Light Sensor Pins"/>

</p>

Suara ultrasonik yang dipantulkan oleh objek atau halangan tadi kemudian ditangkap oleh komponen R.

<p align="center" width="100%">

<img width="80%" src={require('../beginner-level/img/img8/tutorial-8-2-bouncing-sound.png').default} alt="Arduino Light Sensor Pins"/>

</p>

Waktu yang ditempuh oleh suara ultrasonik untuk berjalan bolak balik dari komponen T sampai ke komponen R direkam. Dan digunakan untuk menghitung jarak benda atau halangan yang memantulkan suara ultrasonik tadi dari sensor.

## Menghitung Jarak

Sebagai contoh pada ilustrasi di atas, ketika suara ultrasonik pertama kali dikeluarkan dari komponen T kemudian sampai pada objek atau halangan, memakan waktu sekitar 250µs.

<p align="center" width="100%">

<img width="80%" src={require('../beginner-level/img/img8/tutorial-8-3-bouncing-sound.png').default} alt="Arduino Light Sensor Pins"/>

</p>

Kemudian suara ultrasonik dipantulkan dari objek/halangan dan sampai pada komponen R, membutuhkan waktu sekitar 250µs.

<p align="center" width="100%">

<img width="80%" src={require('../beginner-level/img/img8/tutorial-8-4-bouncing-sound.png').default} alt="Arduino Light Sensor Pins"/>

</p>

Maka total waktu yang ditempuh oleh suara ultrasonik untuk bolak balik dari komponen T ke objek/halangan kemudian dipantulkan ke komponen R, memakan waktu selama 500µs.

Setelah diketahui total waktu yang ditempuh suara ultrasonik, kita kemudian menggunakan rumus di bawah ini

<p align="center" width="100%">

Jarak = Kecepatan x Waktu

</p>

Kita sudah mengetahui Waktunya, yakni 500µs. Sekarang kita harus mencari kecepatan suara ultrasonik yang merambat, yakni 340 m/s. Suara ultrasonik merambat di udara pada kecepatan 340 m/s. Kemudian kita ubah satuannya menjadi ke cm/µs sehingga menjadi 0.034 cm/µs.

Sekarang ktia sudah mengetahui Waktu dan Kecepatannya dan kita masukkan ke dalam persamaan.

<p align="center" width="100%">

Jarak = 0.034 cm/µs x 500µs

</p>

Disini kita hampir selesai menghitung jaraknya. Namun, karena kita tahu suara ultrasonik nya merambat dua kali, pertama dari komponen T ke objek/halangan. Kemudian dari objek/halangan ke komponen R, sehingga bisa dikatakan suara ultrasoniknya merambat dua kali. Dengan demikian, kita harus membagi persamaan di atas tadi dengan dua dan hasil finalnya akan menjadi:

<p align="center" width="100%">

Jarak = (0.034 cm/µs x 500µs) / 2

</p>

<p align="center" width="100%">

Jarak = 8.5 cm

</p>

Dengan demikian, kita tahu jarak objek/halangan berada pada jarak sejauh 8.5 cm dari sensor.

Sensor Ultrasonik akan berguna untuk project yang membutuhkan pengukuran jarak ataupun untuk mendeteksi keberadaan benda/objek.

Mari kita belajar bagaimana memprogram sensor tersebut.

## Mulai Beraksi 🚀

Baik, sebelum mulai beraksi, pastikan teman-teman sudah membaca Prasyarat, Target Pelajaran, dan Komponen Yang Dibutuhkan ya.

Klik pada salah satu dari ketiga tombol di bawah ini untuk membuka Prasyarat, Target Pelajaran dan Komponen Yang Dibutuhkan.

<Tabs className="unique-tabs">
<TabItem value="Prasyarat 🔑">

- Sudah lolos Tutorial 7 - Alarm Sensor Cahaya Lanjutan
- Sudah mempelajari Arduino Nano Expansion Board pada materi **[Arduino Nano Expansion Board](/docs/tutorial-arduino/arduino-hardware.md#arduino-nano-expansion-board)**

Kalau teman-teman merasa belum memenuhi prasyarat yang dibutuhkan, diharapkan untuk membaca dan memenuhinya terlebih dahulu.

</TabItem>

<TabItem value="Target Pelajaran 🎯">

- Memahami bagaimana memprogram Sensor Jarak Ultrasonik
- Memahami bagaimana memasukkan rumus matematika ke dalam program
-

</TabItem>

<TabItem value="Komponen Yang Dibutuhkan 🛠">

- 1 x Arduino Nano
- 1 x Kabel USB Arduino Nano
- 1 x Komputer/Laptop
- 1 x Jarak
- 4 x Kabel Jumper Female-Female

</TabItem>
</Tabs>

:::caution Perhatian

Penting untuk memperhatikan setiap langkah-langkah yang diberikan dan tidak melakukan apapun diluar perintah langkah yang diberikan.

Kenapa? Hal ini untuk mencegah kerusakan yang tidak diinginkan pada komponen apabila bertindak di luar langkah pelajaran yang diberikan dan tidak mengetahui dengan pasti apa yang teman-teman lakukan.

:::

### Menghubungkan Pin-Pin

Mari kita ikuti langkah-langkah yang disediakan.

1. Kita akan menghubungkan pin-pin Modul Sensor Jarak ke Arduino Nano dengan menggunakan kabel jumper seperti pada gambar Wiring Diagram di bawah ini.

<p align="center" width="100%">

<img width="80%" src={require('../beginner-level/img/img8/tutorial-8-5-wiring-diagram.png').default} alt="Arduino Light Sensor Pins"/>

</p>

Jika gambar Wiring Diagram di atas kurang jelas, teman-teman bisa gunakan tabel Wiring Diagram di bawah ini.

| Sensor Jarak | Arduino Nano Expansion Board |
| :----------: | :--------------------------: |
|     VCC      |              V               |
|     Trig     |              8               |
|     Echo     |              9               |
|     GND      |              G               |

:::danger Peringatan
Sebelum menyalakan Arduino Nano, harap periksa kembali rangkaiannya. Apakah sudah sama dengan Wiring Diagram?

Periksa kembali posisi pemasangan kaki-kaki. Diharapkan agar tidak terbalik dan sesuai dengan keterangan pin agar tidak merusak komponen.
:::

### Mengetik Program

2. Bukalah Arduino IDE, kemudian buatlah sketch baru. Beri sketch baru tersebut dengan nama TUTORIAL_8_SENSOR_JARAK dan simpan dalam folder **Program Tutorials** yang telah kita buat pada Tutorial 1 sebelumnya. Jika terlupa bagaimana membuat nama sketch, silahkan buka kembali Tutorial 1 sebelumnya.

   <p align="center" width="100%">

   <img width="80%" src={require('../beginner-level/img/img8/tutorial-8-6-new-sketch.png').default} alt="Arduino IDE Sketch Program"/>

   </p>

3. Kemudian ketik program berikut pada sketch tersebut.

```arduino title="TUTORIAL_8_SENSOR_JARAK.ino" showLineNumbers
const int trigPin = 8;
const int echoPin = 9;

float duration;
float distance;

void setup() {
Serial.begin(9600);
pinMode(trigPin, OUTPUT);
pinMode(echoPin, INPUT);
}

// repeat infinitely
void loop() {
digitalWrite(trigPin, LOW);
delayMicroseconds(2);

digitalWrite(trigPin, HIGH);
delayMicroseconds(10);
digitalWrite(trigPin, LOW);

duration = pulseIn(echoPin, HIGH);
distance = (duration * 0.0343) / 2;

Serial.print("Jarak: ");
Serial.println(distance);

delay(100);
}
```

4. Setelah selesai mengetik program, jalankan proses verify. Dan apabila proses verify sudah berhasil, upload lah program tersebut ke Arduino Nano.

5. Setelah proses upload berhasil, bukalah Serial Monitor, dan amati perubahan nilai jaraknya apabila kita mendekatkan atau menjauhkan tangan kita dari Sensor Jarak.

<br/>

## Penjelasan Program

Sekarang kita akan menjelaskan bagaimana programnya berjalan.

```arduino title="TUTORIAL_8_SENSOR_JARAK.ino" showLineNumbers
const int trigPin = 8;
const int echoPin = 9;

float duration;
float distance;

void setup() {
   // put your setup code here, to run once:
Serial.begin(9600);
pinMode(trigPin, OUTPUT);
pinMode(echoPin, INPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
digitalWrite(trigPin, LOW);
delayMicroseconds(2);

digitalWrite(trigPin, HIGH);
delayMicroseconds(10);
digitalWrite(trigPin, LOW);

duration = pulseIn(echoPin, HIGH);

distance = (duration * 0.034  ) / 2;

Serial.print("Afstand: ");
Serial.println(distance);

delay(100);
}
```

Pada baris ke 1 dan baris ke 2, kita membuat dua buah variabel bernama `trigPin` dan `echoPin`.

```arduino
const int trigPin = 8;
const int echoPin = 9;
```

Variabel `trigPin` menyimpan angka 8 karena pin Trigger Sensor Jarak terhubung pada pin 8 Arduino Nano. Begitupula variabel `echoPin` menyimpan angka 9 karena pin Echo Sensor Jarak terhubung pada pin 9 Arduino Nano. Jika kita ingin menghubungkan ke pin yang berbeda, kita cukup mengganti angka-angkanya saja.

Misalnya apabila kita ingin menghubungkan pin Trigger Sensor Jarak pada pin 12 Arduino Nano, kita cukup mengganti angka 8 pada variabel trigPin menjadi angka 12.

Kemudian pada variabel trigPin dan echoPin terdapat tipe data `const` dan `int`. Tipe data `const` merupakan singkatan dari "constant" yang berarti konstan dalam bahasa Indonesia. Apabila kita membuat sebuah variabel dengan tipe `const`, maka isi dari variabel tersebut akan tetap dan tidak bisa berubah-ubah.

Misalnya variabel `trigPin` dan variabel `echoPin` yang bertipe `const`, maka angka 8 yang disimpan dalam variabel `trigPin` dan angka 9 yang disimpan dalam variabel `echoPin` akan selalu tetap dan tidak akan bisa berubah selama program berjalan sampai kita mengubahnya sendiri.

Kemudian untuk tipe data `int` merupakan singkatan dari "integer" yang berarti bilangan bulat dalam bahasa Indonesia. Kita menggunakan tipe data ini jika ingin menyimpan bilangan bulat ke dalam suatu variabel. Bilangan bulat yang dimaksud seperti 1, 2, 4, atau 10. Jika kita ingin menyimpan bilangan desimal seperti 3.14, maka kita menggunakan tipe data `float`.

Kemudian pada baris 4 dan baris 5, kita membuat dua buah variabel baru bernama `duration` dan `distance`. "Duration" berarti Durasi dan Distance berarti Jarak dalam bahasa Indonesia. Kita bebas memberi nama untuk variabelnya asalkan mudah diingat dan mudah dimengerti peruntukkannya.

```arduino
float duration;
float distance;
```

Perhatikan bahwa tipe data kedua variabel tersebut adalah `float`. Hal ini karena kita akan membuat supaya variabel `duration` dan variabel `distance` bisa menyimpan bilangan desimal.

Dimana angkanya yang akan disimpan dalam variabel `duration` dan variabel `distance` tersebut? Kita akan menemukannya nanti dalam fungsi `loop()`.

Kemudian kita masuk dalam fungsi `setup()` pada baris 7 hingga baris 12.

```arduino
void setup() {
Serial.begin(9600);
pinMode(trigPin, OUTPUT);
pinMode(echoPin, INPUT);
}
```

Dalam fungsi `setup()` terdapat perintah `Serial.begin(9600)` untuk memerintahkan Arduino Nano agar memulai komunikasi serial dengan laptop pada kecepatan baudrate sebesar 9600.

Kemudian terdapat perintah `pinMode()` untuk menjadikan pin nomor 8 Arduino Nano sebagai OUTPUT untuk memberikan sinyal ke luar dan pin nomor 9 Arduino Nano sebagai INPUT untuk menerima sinyal yang masuk.

Mengapa kita tidak melihat angka 8 dan angka 9 pada fungsi `setup()` tersebut?

Perhatikan kembali pada baris 1 dan baris 2 bahwa kita sudah membuat variabel bernama `trigPin` yang menyimpan angka 8 yang merupakan angka dari pin nomor 8 milik Arduino Nano yang terhubung dengan pin Echo Sensor Jarak.

Begitu pula variabel `echoPin` yang menyimpan angka 9 yang merupakan angka dari pin nomor 9 milik Arduino Nano yang terhubung dengan pin Echo Sensor Jarak.

Selanjutnya kita masuk ke fungsi `loop()`. Fungsi loop() dimulai dari baris 14 sampai pada baris 30 dalam program.

```arduino
void loop() {
  // put your main code here, to run repeatedly:
digitalWrite(trigPin, LOW);
delayMicroseconds(2);

digitalWrite(trigPin, HIGH);
delayMicroseconds(10);
digitalWrite(trigPin, LOW);

duration = pulseIn(echoPin, HIGH);

distance = (duration * 0.0343) / 2;

Serial.print("Afstand: ");
Serial.println(distance);

delay(100);
}
```

Pada baris 16 terdapat perintah `digitalWrite()` yang memerintahkan Arduino Nano untuk memberikan sinyal `LOW` ke pin `trigPin`. Ingat kembali bahwa `trigPin` merupakan pin nomor 8 miilik Arduino Nano dan bisa diperintahkan untuk memberikan sinyal LOW ataupun sinyal HIGH karena kita sudah mengatur pin nomor 8 sebagai OUTPUT pada fungsi `setup()`.

```arduino
digitalWrite(trigPin, LOW);
delayMicroseconds(2);
```

Selanjutnya pada baris 17 terdapat perintah `delayMicroseconds()`. Biasanya pada tutorial-tutorial sebelumnya kita menggunakan perintah `delay()`, dimana 1000 mili sekon sama dengan 1 detik.

Kali ini kita menggunakan perintah `delayMicroseconds(2)` yang membuat Arduino Nano menjalankan perintah pada baris 16 sebelumnya berjalan selama 2 mikro detik.

Karena pin Trigger sensor jarak diberi logika `LOW` selama 2 mikro detik, maka komponen T (Transmitter) pada Sensor Jarak tidak akan bisa memancarkan suara ultrasonik.

Barulah pada baris 19 dan baris 20, komponen Transmitter pada Sensor Jarak memancarkan suara ultrasonik selama 10 detik.

```arduino
digitalWrite(trigPin, HIGH);
delayMicroseconds(10);
digitalWrite(trigPin, LOW);
```

Pada baris 19 terdapat perintah `digitalWrite()` yang memerintahkan Arduino Nano untuk memberikan logika `HIGH` ke pin Trigger Sensor Jarak sehingga komponen T bisa memancarkan suara ultrasonik.

Dan pada baris 20 terdapat perintah `delayMicroseconds(10)` untuk menunda selama 10 mikro detik. Dengan kata lain, komponen T memancarkan suara ultraasonik selama 10 mikro detik.

Komponen T kemudian berhenti memancarkan suara ultrasonik tepat setelah 10 mikro detik dengan memberi logika LOW ke pin Trigger Sensor Jarak menggunakan perintah `digitalWrite()` pada baris 21.

Karena suara ultrasonik tadi telah dipancarkan selama 10 detik, komponen R (Receiver) pada sensor jarak kemudian menunggu suara ultrasoniknya dipantulkan kembali oleh objek/halangan di depan sensor jarak.

Untuk mengukur jarak antara sensor jarak dengan objek/halangan, kita perlu mengetahui berapa lama waktu yang dibutuhkan suara ultrasonik dari sejak dipancarkan oleh komponen T sampai komponen R menerima pantulan suara ultrasoniknya dari objek/halangan di depan sensor jarak.

Untuk mengukur waktunya, kita menggunakan fungsi spesial yang disediakan oleh Arduino IDE, yakni `pulseIn()`. Fungsi ini ditemui pada baris 23. Pada dasarnya, fungsi ini tidak benar-benar mengukur waktu, melainkan mengukur panjang pulsa.

```arduino
duration = pulseIn(echoPin, HIGH);
```

Fungsi `pulseIn()` memiliki tiga buah parameter, yakni:

- Nomor pin yang akan dibaca panjang pulsanya.
- Tipe pulsa yang akan dibaca. Ada dua tipe pulsa yang dapat digunakan, yakni:
  - Pulsa dari LOW ke HIGH, atau
  - Pulsa dari HIGH ke LOW.
- Waktu tunggu sebelum mulai mengukur.

Parameter ketiga merupakan parameter opsional, artinya bisa digunakan, dan bisa juga tidak digunakan. Jika kita lihat kembali kode program kita pada baris 23, kita bisa lihat bahwa kita hanya menggunakan dua buah parameter.

```arduino
duration = pulseIn(echoPin, HIGH);
```

Parameter pertama itu adalah nomor pin yang akan dibaca panjang pulsanya, yakni pin nomor 9 Arduino Nano (diwakili oleh variabel `echoPin` karena variabel `echoPin` menyimpan angka 9).

Dan parameter kedua adalah tipe pulsa yang kita gunakan, karena kita menggunakan `HIGH`, maka tipe pulsa yang kita gunakan yakni tipe pulsa dari `LOW` ke `HIGH`. Untuk lebih jelasnya, mari perhatikan ilustrasi berikut.

<p align="center" width="100%">

<img width="80%" src={require('../beginner-level/img/img8/tutorial-8-7-LOW-HIGH.png').default} alt="Arduino Light Sensor Pins"/>

</p>

Begitu sinyal naik dari LOW ke HIGH, maka akan mulai mengukur berapa lama sinyalnya pada posisi HIGH. Jika kita mengambil contoh pada ilustrasi di atas, waktu sinyal HIGH yang terukur selama 8 mikro sekon.

Jika kita menggunakan parameter `LOW` dalam perintah `pulseIn(echoPin, LOW)`, maka tipe pulsa yang kita gunakan adalah tipe pulsa dari `HIGH` ke `LOW`.

<p align="center" width="100%">

<img width="80%" src={require('../beginner-level/img/img8/tutorial-8-8-HIGH-LOW.png').default} alt="Arduino Light Sensor Pins"/>

</p>

Begitu sinyal turun dari LOW ke HIGH, maka akan mulai mengukur berapa lama sinyalnya pada posisi LOW. Jika kita mengambil contoh pada ilustrasi di atas, waktu sinyal LOW yang terukur selama 8 mikro sekon.

Mari kita perhatikan sekali lagi kode pada baris 23 di bawah

```arduino
duration = pulseIn(echoPin, HIGH);
```

Jika misalnya setelah menjalankan perintah `pulseIn(echoPin, HIGH)` untuk mengukur berapa lama sinyalnya berada pada posisi HIGH dan waktu terukur yang didapat adalah 500 µs (µ=smikro, s=sekon), maka angka 500 ini akan disimpan dalam variabel `duration`.

Setelah waktu yang dibutuhkan suara ultrasonik untuk memancar dan memantul pada objek diketahui, selanjutnya kita akan menghitung jaraknya dengan menggunakan persamaan:

<p align="center" width="100%">

Jarak = (Waktu x Kecepatan) / 2

</p>

Anggaplah sebagai permisalan, waktu yang dibutuhkan suara ultrasonik merambat dan memantul sudah diketahui yakni sebesar 500 µs, dan kecepatan suara ultrasonik adalah 0.0343 cm/µs, maka kita masukkan data-data tersebut ke dalam persamaan sehingga menjadi:

<p align="center" width="100%">

Jarak = (500 x 0.034) / 2

</p>

<p align="center" width="100%">

Jarak = 8.5

</p>

Namun, bagaimana kita menuliskannya dalam program? Mari kita perhatikan kode pada baris 25:

```arduino
distance = (duration * 0.0343) / 2;
```

Ingat kembali, bahwa variabel `duration` sudah menyimpan angka 500 dari kode pada baris 23 sebelumnya. Sehingga secara langsung, kode nya akan menjadi seperti di bawah ini.

```arduino
distance = (500 * 0.034) / 2;
```

Hasil operaasi matematika `(500 * 0.0343) / 2` jika kita hitung dengan menggunakan kalkulator, maka akan menghasilkan angka 8.5. Angka 8.5 yang merupakan hasil operasi matematika tersebut kemudian disimpan dalam variabel bernama `distance`.

Selanjutnya pada baris 27, akan memerintahkan Arduino Nano untuk mencetak "Jarak: " pada Serial Monitor.

```arduino
Serial.print("Jarak: ");
Serial.println(distance);
```

Setelah mencetak "Jarak: " pada Serial Monitor, kemudian dilanjutkan menjalankan perintah pada baris 28, yakni mencetak data yang tersimpan dalam variabel bernama `distance`. Masih ingatkah teman-teman data yang disimpan dalam variabel distance setelah menjalankan kode pada baris 25?

Karena variabel `distance` sudah menyimpan angka 8.5, maka pada Serial Monitor akan dicetak angka 8.5 pula. Sehingga tampilan yang dicetak pada Serial Monitor teman-teman mungkin akan tertulis seperti ini:

```arduino
Jarak: 8.5
```

Kemudian pada baris terakhir, yakni pada baris 30, terdapat perintah `delay(100)` untuk menunda selama 100 mili sekon sebelum kembali lagi ke awal fungsi `loop()` yang berada pada baris 16.

Perhatikan pada baris 28, perintah yang digunakan adalah `println`, jadi begitu angka 8.5 atau angka yang ada di dalam variabel `distance` sebelumnya sudah dicetak, maka setelah Arduino Nano menjalankan programnya lagi dari awal fungsi `loop()`, dan mendapati jarak baru yang terukur sebesar 7.5, maka akan membuat baris baru di bawah nya seperti ini:

```arduino
Jarak: 8.5
Jarak: 7.5
```
