---
sidebar_position: 5
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Tutorial 4 - Serial Monitor dan Potensiometer

Pada Tutorial 3 sebelumnya kita telah mempelajari bagaimana Serial Monitor bekerja. Dengan Serial Monitor kita dapat menampilkan teks ataupun data yang kita inginkan ke layar laptop/komputer untuk diketahui bagaimana perubahan nilai atau perubahan aktivitas suatu komponen.

Sekarang kita akan mempelajari lebih dalam lagi fungsi Serial Monitor sembari mempelajari fungsi-fungsi pemrograman baru, yakni fungsi perintah untuk membaca input/membaca sinyal yang diberikan suatu komponen kemudian menampilkannya ke layar laptop/komputer dengan fungsi Serial Monitor.

## Apa itu Potensiometer?

Komponen tambahan yang kita gunakan pada Tutorial 4 kali ini adalah Potensiometer. Bentuk fisik potensiometer yang akan kita gunakan pada Tutorial ini ditunjukkan oleh gambar di bawah.

<p align="center" width="100%">

<img width="80%" src={require('./img/img4/tutorial-4-1.png').default} alt="Ultrasonic Sensors"/>

</p>

Kita bisa melepas bagian yang disebut sebagai "Topi" pada Potensiometer.

<p align="center" width="100%">

<img width="80%" src={require('./img/img4/tutorial-4-2.png').default} alt="Ultrasonic Sensors"/>

</p>

Topi pada potensiometer yang dimaksud seperti pada gambar di bawah ini. Topi ini pada dasarnya berfungsi agar kita mudah menggenggam Potensiometer ketika kita akan memutarnya.

<p align="center" width="100%">

<img width="40%" src={require('./img/img4/tutorial-4-3.png').default} alt="Ultrasonic Sensors"/>

</p>

Kita bisa memilih untuk menggunakan Topi atau tanpa menggunakan Topi pada potensiometer.

Potensiometer merupakan komponen elektronika yang digunakan untuk memberikan nilai resistansi yang dapat berubah-ubah sesuai kebutuhan penggunanya dengan cara memutar topi potensiometer searah jarum jam ataupun berlawanan jarum jam.

Potensiometer memiliki tiga buah kaki yakni kaki GND, kaki VCC, dan kaki OUT. Kaki GND harus dihubungkan dengan kutub negatif sumber tegangan. Sedangkan kaki VCC harus dihubungkan dengan kutub positif sumber tegangan.

<p align="center" width="100%">

<img width="80%" src={require('./img/img4/tutorial-4-4.png').default} alt="Ultrasonic Sensors"/>

</p>

Kaki OUT merupakan tempat keluarnya nilai resistansi yang dibutuhkan oleh pengguna. Pemasangan kaki-kaki harus benar-benar tepat dan tidak boleh terbalik karena dapat menyebabkan kerusakan potensiometer.

Untuk lebih memahami apa itu Potensiometer, mari kita langsung mulai beraksi.

## Mulai Beraksi 🚀

Baik, sebelum mulai beraksi, pastikan teman-teman sudah membaca Prasyarat, Target Pelajaran, dan Komponen Yang Dibutuhkan ya.

Klik pada salah satu dari ketiga tombol di bawah ini untuk membuka Prasyarat, Target Pelajaran dan Komponen Yang Dibutuhkan.

<Tabs className="unique-tabs">
<TabItem value="Prasyarat 🔑">

- Sudah lolos Tutorial 3 - Serial Monitor
- Sudah mempelajari Arduino Nano Expansion Board pada materi **[Arduino Nano Expansion Board](/docs/tutorial-arduino/arduino-hardware.md#arduino-nano-expansion-board)**

Kalau teman-teman merasa belum memenuhi prasyarat yang dibutuhkan, diharapkan untuk membaca dan memenuhinya terlebih dahulu.

</TabItem>

<TabItem value="Target Pelajaran 🎯">

- Memahami perintah pembacaan input
- Memahami fungsi `analogRead()`
- Memahami bagaimana menampilkan data langsung pada layar laptop/komputer dengan Serial Monitor
- Memahami fisik potensiometer

</TabItem>

<TabItem value="Komponen Yang Dibutuhkan 🛠">

- 1 x Arduino Nano
- 1 x Kabel USB Arduino Nano
- 1 x Komputer/Laptop
- 1 x Potensiometer
- Kabel jumper secukupnya

</TabItem>
</Tabs>

:::caution Perhatian

Penting untuk memperhatikan setiap langkah-langkah yang diberikan dan tidak melakukan apapun diluar perintah langkah yang diberikan.

Kenapa? Hal ini untuk mencegah kerusakan yang tidak diinginkan pada komponen apabila bertindak di luar langkah pelajaran yang diberikan dan tidak mengetahui dengan pasti apa yang teman-teman lakukan.

:::

### Menghubungkan Pin-Pin

1. Baik, langkah pertama kita akan menyiapkan perangkat utama kita dahulu, yaitu Arduino Nano. Kemudian siapkan Potensiometer dan 3 buah kabel jumper.

<p align="center" width="100%">

<img width="50%" src={require('./img/img4/tutorial-4-4.png').default} alt="Ultrasonic Sensors"/>

</p>

2. Lihat kembali kaki-kaki Potensiometer pada gambar di atas. Kita akan menghubungkan kaki-kaki Potensiometer tersebut ke Arduino Nano dengan menggunakan kabel jumper seperti pada gambar Wiring Diagram di bawah ini.

<p align="center" width="100%">

<img
width="80%"
src={require('./img/img4/tutorial-4-5.png').default}
alt="Ultrasonic Sensors"
/>

</p>

Jika gambar Wiring Diagram di atas kurang jelas, teman-teman bisa gunakan tabel Wiring Diagram di bawah ini.

| Potensiometer | Arduino Nano Expansion Board |
| :-----------: | :--------------------------: |
|    Pin OUT    |            Pin G             |
|    Pin GND    |            Pin 4             |
|    Pin VCC    |            Pin 5             |

:::danger Peringatan
Sebelum menyalakan Arduino Nano, harap periksa kembali rangkaiannya. Apakah sudah sama dengan Wiring Diagram?

Periksa kembali kabel-kabel jumper agar tidak ada kesalahan yang dapat berpotensi merusak komponen ataupun mengganggu pelajaran.
:::

Setelah Potensiometer dan Arduino Nano saling terhubung, maka hasilnya akan seperti pada gambar di bawah ini.

<p align="center" width="100%">

<img
width="80%"
src={require('./img/img4/tutorial-4-6.png').default}
alt="Ultrasonic Sensors"
/>

</p>

Warna kabel yang digunakan bebas dan tak harus sama dengan gambar di atas. Namun yang harus diperhatikan, pastikan kaki Potensiometer terhubung ke posisi pin yang sama seperti pada gambar di atas.

### Mengetik Program

3. Bukalah Arduino IDE, kemudian buatlah sketch baru. Beri sketch baru tersebut dengan nama TUTORIAL_4_POTENTIOMETER_SERIAL_MONITOR dan simpan dalam folder TUTORIAL PROGRAMS yang telah kita buat pada Tutorial 1 sebelumnya. Jika terlupa bagaimana membuat nama sketch, silahkan buka kembali Tutorial 1 sebelumnya.

<p align="center" width="100%">

<img
width="80%"
src={require('./img/img4/tutorial-4-7.png').default}
alt="Ultrasonic Sensors"
/>

</p>

4. Kemudian ketik program berikut pada sketch tersebut.

```arduino title="TUTORIAL_4_POTENTIOMETER_SERIAL_MONITOR.ino" showLineNumbers
void setup() {
  // put your setup code here, to run once:
Serial.begin(9600);
}

void loop() {
  // put your main code here, to run repeatedly:
 int nilaiSensor = analogRead(A0);
 Serial.println(nilaiSensor);
 delay(1);
}
```

5. Periksa kembali ketikan sketch program. Pastikan agar ketikan sketch program sama persis seperti diminta agar tidak mengalami error saat compiling. Jika sudah selesai mengetik program, cobalah memeriksa apakah ketikan Anda sudah benar atau belum dengan cara menekan tombol verify atau ikon di samping 👉 <img src={require('./img/arduino-ide-tool-bar-verify.png').default} alt="Ultrasonic Sensors"/>.

6. Jika proses verify selesai dan information bar menunjukkan “Done compiling”, berarti program yang teman-teman ketik sudah benar dan lanjutkan pada langkah berikutnya.

<p align="center" width="100%">

<img
width="80%"
src={require('./img/img4/tutorial-4-8.png').default}
alt="Ultrasonic Sensors"
/>

</p>

### Mengkonfigurasi Arduino IDE

Sebelum mengupload program, sama seperti pada Tutorial 1, mari kita melakukan konfigurasi terlebih dahulu pada Arduino IDE.

7. Memilih Jenis Board

Pastikan jenis board yang digunakan sudah sesuai dengan settingan pada Arduino IDE dengan cara memilih opsi berikut secara berurutan Tools ➜ Board ➜ Arduino Nano atau perhatikan urutan tanda panah pada gambar di bawah ini. Disini kita memilih Arduino Nano karena kita menggunakan Arduino Nano.

<p align="center" width="100%">

<img width="80%" src={require('./img/img4/tutorial-4-9.png').default} alt="Ultrasonic Sensors"/>

</p>

8. Memilih Jenis Processor

Processor dalam bahasa Indonesia berarti Prosessor, atau Pemroses sebuah perintah, singkatnya seperti otak dari robot. Disini kita akan menentukan jenis Processor yang digunakan oleh Arduiino Nano, yaitu ATMega328P (Old Bootloader), dengan cara memilih opsi berikut secara berurutan Tools ➜ Processor ➜ ATmega328P (Old Bootloader). Atau ikuti urutan tanda panah pada gambar di bawah ini

<p align="center" width="100%">

<img width="80%" src={require('./img/img4/tutorial-4-10.png').default} alt="Ultrasonic Sensors"/>

</p>

9. Memilih Nomor Port

Nomor port untuk Arduino Nano pada tiap laptop/komputer dapat berbeda-beda. Pilihlah nomor port yang muncul pada pilihan yang tersedia di Arduino IDE. Lebih jelasnya, perhatikan gambar di bawah.

<p align="center" width="100%">

<img width="80%" src={require('./img/img4/tutorial-4-11.png').default} alt="Ultrasonic Sensors"/>

</p>

### Mengupload Program

10. Setelah proses konfigurasi selesai seperti yang diperintahkan, lanjutkan dengan mengklik tombol upload <img src={require('./img/arduino-ide-tool-bar-upload.png').default} alt="Ultrasonic Sensors"/> pada Arduino IDE.

11. Setelah proses upload selesai, information bar akan menunjukkan pesan “Done uploading” yang berarti proses upload telah selesai.

<p align="center" width="100%">

<img width="80%" src={require('./img/img4/tutorial-4-12.png').default} alt="Ultrasonic Sensors"/>

</p>

:::note Catatan
jika proses upload gagal, cobalah mengganti nomor PORT COMXX yang tersedia pada daftar pilihan nomor port pada langkah 3 di atas sampai proses upload berhasil.
:::

12. Jika proses upload berhasil, klik ikon “Serial Monitor” IDE seperti ditunjukkan oleh gambar disamping, <img src={require('./img/img3/arduino-ide-tool-bar-sermon.png').default} alt="Ultrasonic Sensors"/>, yang terletak pada pojok atas kanan Arduino.

Maka akan muncul window “Serial Monitor” seperti pada gambar di bawah ini.

<p align="center" width="100%">

<img width="80%" src={require('./img/img4/tutorial-4-14.png').default} alt="Ultrasonic Sensors"/>

</p>

Pada window tersebut akan menampilkan angka yang merupakan data dari nilai resistansi potensiometer.

Jika belum muncul teks tersebut, cobalah nyalakan centang pada “Autoscroll”, atur setinggan pada “Newline”, dan “9600 baud”.

Nilai resistansi terbesar pada potensiometer adalah 1023 dan nilai resistansi terkecil adalah 0.

Cobalah memutar topi potensiometer searah jarum jam maupun berlawanan jarum jam untuk mengetahui posisi putaran maksimum dan putaran minimum potensiometer.

Sambungan kabel pada kaki-kaki potensiometer rentan kendor. Oleh karenanya cobalah memutarnya dengan berhati-hati agar tidak membuat kabel terlepas dari kaki-kaki potensiometer.

<br/>

## Penjelasan Program

Pada Tutorial 3 sebelumnya, kita sudah mempelajari bahwa Serial Monitor dapat berfungsi untuk menampilkan data yang berupa pesan atau kalimat ke layar monitor.

Serial Monitor juga bisa menampilkan data yang berupa angka atau nilai resistansi komponen Potensiomter yang diproses oleh Arduino Nano ke layar laptop/komputer sehingga kita bisa mengetahui nilai-nilai data atau kejadian suatu proses yang sedang dikerjakan oleh Arduino Nano.

<p align="center" width="100%">

<img width="80%" src={require('./img/img4/tutorial-4-15.png').default} alt="Ultrasonic Sensors"/>

</p>

Pada dasarnya, kurang lebih, penjelasan untuk program kali ini mirip dengan penjelasan pada Tutorial 3 sebelumnya.

Namun, karena kita menggunakan komponen tambahan berupa Potensiometer, bagaimana cara kerja programnya kali ini?

```arduino title="TUTORIAL_4_POTENTIOMETER_SERIAL_MONITOR.ino" showLineNumbers
void setup() {
  // put your setup code here, to run once:
Serial.begin(9600);
}

void loop() {
  // put your main code here, to run repeatedly:
 int nilaiSensor = analogRead(A0);
 Serial.println(nilaiSensor);
 delay(1);
}
```

Pada sketch program di atas terdapat fungsi `setup()` dan `loop()` sebagaimana biasanya.

Fungsi `setup()` hanya memiliki satu buah perintah di dalamnya yang terletak pada baris nomor 3. Sementara sisanya hanya komentar yang terletak pada baris nomor 2 yang mana komentar tersebut diabaikan atau tidak dianggap oleh Arduino IDE.

```arduino title="TUTORIAL_4_POTENTIOMETER_SERIAL_MONITOR.ino" showLineNumbers
void setup() {
  // put your setup code here, to run once:
// highlight-start
Serial.begin(9600);
// highlight-end
}

void loop() {
  // put your main code here, to run repeatedly:
 int nilaiSensor = analogRead(A0);
 Serial.println(nilaiSensor);
 delay(1);
}
```

Pada baris 3 fungsi `setup()` terdapat fungsi `Serial.begin(9600)` . Perintah tersebut memiliki 3 parameter yakni `Serial` , `begin` , dan `9600` . Fungsi `Serial.begin(9600)` harus dijalankan terlebih dahulu dalam fungsi `setup()`.

Baris 3 tersebut akan memerintahkan Arduino Nano untuk memulai proses pertukaran data dari Arduino Nano ke laptop/komputer agar laptop/komputer dapat menerima data dari Arduino Nano untuk ditampilkan pada layar laptop/komputer.

Selanjutnya pada fungsi `loop()`, pada baris 8 terdapat variabel bertipe `int` (singkatan dari integer atau bilangan bulat) dengan nama variabel `nilaiSensor`. Nama variabel ini dapat teman-teman tentukan dengan bebas sesuai nama yang mudah diingat oleh teman-teman. Misalnya `nilaiPotensiometer` ataupun `nilaiData` pun tak masalah.

```arduino title="TUTORIAL_4_POTENTIOMETER_SERIAL_MONITOR.ino" showLineNumbers
void setup() {
  // put your setup code here, to run once:
Serial.begin(9600);
}

void loop() {
  // put your main code here, to run repeatedly:
 // highlight-start
 int nilaiSensor = analogRead(A0);
  // highlight-end
 Serial.println(nilaiSensor);
 delay(1);

}
```

Masih pada baris 8, terdapat perintah `analogRead(A0)`. Perintah ini merupakan perintah untuk membaca (`Read`) sinyal `analog` dari `nomor pin` yang diperintahkan. Perintah ini hanya memiliki satu parameter yakni nomor pin.

Parameter nomor pin yang digunakan pada perintah ini adalah pin nomor A0. Hal ini karena kita menghubungkan kaki OUT potensiometer ke pin A0 Arduino Nano Expansion Board.

Jika kita memperhatikan tanda penugasan, yakni yang disimbolkan dengan tanda `=` (tanda sama dengan), yang terdapat pada baris 8, maka jika dibaca dari kiri ke kanan, baris 8 tersebut kurang lebih akan seperti ini: “variabel `nilaiSensor` bertipe integer menyimpan hasil pembacaan sinyal analog dari pin A0 Arduino Nano”.

Untuk lebih jelasnya, perhatikan gambar berikut:

<p align="center" width="100%">

<img width="80%" src={require('./img/img4/tutorial-4-16.png').default} alt="Ultrasonic Sensors"/>

</p>

Dengan kata lain, sekarang variabel nilaiSensor berisi angka 483

Kemudian pada baris 9, terdapat perintah Serial.println untuk mencetak nilai yang disimpan dalam variabel nilaiSensor pada Serial Monitor. Nilai yang disimpan dalam variabel `nilaiSensor` merupakan nilai hasil pembacaan sinyal analog pada pin A0.

```arduino title="TUTORIAL_4_POTENTIOMETER_SERIAL_MONITOR.ino" showLineNumbers
void setup() {
  // put your setup code here, to run once:
Serial.begin(9600);
}

void loop() {
  // put your main code here, to run repeatedly:
 int nilaiSensor = analogRead(A0);
 // highlight-start
 Serial.println(nilaiSensor);
 // highlight-end
 delay(1);

}
```

Untuk lebih jelasnya lagi, perhatikan gambar berikut:

<p align="center" width="100%">

<img width="80%" src={require('./img/img4/tutorial-4-17.png').default} alt="Ultrasonic Sensors"/>

Karena variabel `nilaiSensor` menyimpan angka 483,

<img width="80%" src={require('./img/img4/tutorial-4-18.png').default} alt="Ultrasonic Sensors"/>

</p>

Maka pada window Serial Monitor akan menampilkan angka 483

<p align="center" width="100%">

<img width="80%" src={require('./img/img4/tutorial-4-19.png').default} alt="Ultrasonic Sensors"/>

</p>

Perhatikan bahwa baris 9 tersebut menggunakan perintah `println` yang memiliki kepanjangan “print line” dimana `ln` merupakan singkatan dari _line_ (_line_ merupakan kata dalam bahasa Inggris yang artinya "baris"). Perintah `println` digunakan untuk mencetak baris baru sehingga setelah mencetak nilai yang disimpan dalam variabel `nilaiSensor`, akan membuat baris baru di bawahnya dan mencetak nilai yang disimpan dalam variabel `nilaiSensor` berikutnya.

Pada baris 10 terdapat fungsi `delay()` dengan nilai parameter 1 milisecond. Sehingga nilai yang tampil pada Serial Monitor merupakan hasil pembacaan nilai resistansi yang selalu baru.
<br/>

## Tantangan Tutorial 4

### Tantangan 1

Masih ingat fungsi `delay()` pada baris 10 di atas? Semakin kecil nilai delay, maka akan semakin cepat Arduino Nano mengupdate nilai hasil pembacaan potensiometer ke Serial Monitor sembari membaca data putaran potensiometer secara bersamaan.

```arduino title="TUTORIAL_4_POTENTIOMETER_SERIAL_MONITOR.ino" showLineNumbers
void setup() {
  // put your setup code here, to run once:
Serial.begin(9600);
}

void loop() {
  // put your main code here, to run repeatedly:
 int nilaiSensor = analogRead(A0);
 Serial.println(nilaiSensor);
 // highlight-start
 delay(1);
 // highlight-end
}
```

Apa yang terjadi jika kita memperbesar nilai pada delay tersebut dengan cara mengubah angka 1 menjadi 1000. Cobalah kepoin gimana hasilnya.

:::note Catatan
Sebelum mengupload sketch program baru ke Arduino Nano, pastikan teman-teman menutup window Serial Monitor terlebih dahulu jika masih terbuka.
:::

Nilai delay pada proses pembacaan sensor tersebut sebenarnya bisa diatur berapapun kita inginkan. Namun terkadang membuat hasil pembacaan yang tampil pada Serial Monitor menjadi kurang presisi.

### Tantangan 2

```arduino title="TUTORIAL_4_POTENTIOMETER_SERIAL_MONITOR.ino" showLineNumbers
void setup() {
  // put your setup code here, to run once:
Serial.begin(9600);
}

void loop() {
  // put your main code here, to run repeatedly:
  // highlight-start
 int nilaiSensor = analogRead(A0);
  // highlight-end
 Serial.println(nilaiSensor);
 delay(1);
}
```

Sketch di atas masih menggunakan pin A0 sebagai input untuk membaca sinyal keluaran dari kaki OUT potensiometer.

Cobalah teman-teman menggunakan pin Analog lain yang tersedia seperti pin A1, A2, hingga A6 dengan mengganti nomor pin pada parameter fungsi `analogRead()`.

Hal ini agar teman-teman bisa lebih paham bagaimana menggunakan nomor pin analog yang lain.
Oh iya, teman-teman juga bisa mengganti nama variabel sesuai dengan nama yang teman-teman inginkan.
