---
sidebar_position: 2
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Tutorial 6 - Alarm Sensor Cahaya

## Selayang Pandang

Kali ini kita akan menerapkan kembali apa yang telah kita pelajari pada level sebelumnya. Pada Tutorial 5 sebelumnya kita telah mempelajari perbedaan perintah `analogRead()` dan `digitalRead()` untuk keperluan membaca data atau sinyal pada sensor cahaya. Kini saatnya menyelam lebih jauh dalam kontrol kondisional _if else_.

Kontrol kondisional _if else_ adalah suatu perintah yang memungkinkan pengguna nya memerintahkan suatu pekerjaan dijalankan apabila penyebab pekerjaan tersebut dijalankan telah terpenuhi dan tidak akan memerintahkan suatu pekerjaan untuk dijalankan apabila penyebabnya belum terpenuhi.

Dalam bahasa Indonesia, kata “If” berarti “Jika” dan kata “Else” berarti “Selain itu”. Contoh umum struktur kontrol kondisi _if else_ seperti pada program di bawah.

```arduino title="Contoh Penggunaan if else" showLineNumbers
if(kondisi){
    perintah A
}
else{
    perintah B
}
```

Parameter “kondisi” merupakan suatu pemicu yang menjadi penyebab dijalankannya “Perintah A” dalam fungsi if.

Perhatikan bahwa blok “Perintah A” milik fungsi `if` pada baris 2 diapit oleh tanda kurawal buka `{` pada baris 1 dan tanda kurawal tutup `}` pada baris 3.

Begitu pula blok “Perintah B” milik fungsi `else` pada baris 6 diapit oleh kurawal buka `{` pada baris 5 dan tanda kurawal tutup `}` pada baris 7.

Hal ini menunjukkan bahwa tiap fungsi `if` dan fungsi `else` memiliki blok perintahnya sendiri yang harus dijalankan ketika suatu kondisi terpenuhi maupun ketika tidak terpenuhi.

Contoh kontrol kondisional dalam pemrograman pada dasarnya dapat dikatakan seperti ini: Jika gelap, maka nyalakan lampu. Selain itu, tidak gelap, matikan lampu.

Contoh programnya seperti di bawah.

```arduino title="Contoh Penggunaan if else" showLineNumbers
if(gelap){
    nyalakan lampu
}
else{
    matikan lampu
}
```

Kita akan mencoba menggunakan _if else_ ini untuk menyalakan dan mematikan lampu LED yang ada pada Arduino Nano ketika sensor cahaya disorot cahaya senter ataupun tidak disorot oleh cahaya senter.

Komponen tambahan yang kita gunakan pada Tutorial 6 ini sama seperti Tutorial 5 sebelumnya adalah Sensor Cahaya dan Arduino Nano Expansion Board.

## Mulai Beraksi 🚀

Baik, sebelum mulai beraksi, pastikan teman-teman sudah membaca Prasyarat, Target Pelajaran, dan Komponen Yang Dibutuhkan ya.

Klik pada salah satu dari ketiga tombol di bawah ini untuk membuka Prasyarat, Target Pelajaran dan Komponen Yang Dibutuhkan.

<Tabs className="unique-tabs">
<TabItem value="Prasyarat 🔑">

- Sudah lolos Tutorial 5 - Sensor Cahaya dan Serial Monitor
- Sudah mempelajari Arduino Nano Expansion Board pada materi **[Arduino Nano Expansion Board](/docs/tutorial-arduino/arduino-hardware.md#arduino-nano-expansion-board)**

Kalau teman-teman merasa belum memenuhi prasyarat yang dibutuhkan, diharapkan untuk membaca dan memenuhinya terlebih dahulu.

</TabItem>

<TabItem value="Target Pelajaran 🎯">

- Memahami perintah pembacaan input
- Memahami lebih dalam perintah `analogRead()` dan `digitalRead()`
- Memahami bagaimana menampilkan data langsung ke Serial Monitor
- Memahami fisik sensor cahaya

</TabItem>

<TabItem value="Komponen Yang Dibutuhkan 🛠">

- 1 x Arduino Nano
- 1 x Kabel USB Arduino Nano
- 1 x Komputer/Laptop
- 1 x Sensor Cahaya
- 3 x Kabel Jumper Female-Female
- 1 x Senter

</TabItem>
</Tabs>

:::caution Perhatian

Penting untuk memperhatikan setiap langkah-langkah yang diberikan dan tidak melakukan apapun diluar perintah langkah yang diberikan.

Kenapa? Hal ini untuk mencegah kerusakan yang tidak diinginkan pada komponen apabila bertindak di luar langkah pelajaran yang diberikan dan tidak mengetahui dengan pasti apa yang teman-teman lakukan.

:::

### Menghubungkan Pin-Pin

Sebenarnya, langkah yang akan teman-teman jumpai pada Tutorial 6 ini mungkin akan sama persis dengan Tutorial 5 sebelumnya. Namun kita tuliskan kembali disini.

Bagaimanapun, mari kita ikuti langkah-langkah yang disediakan.

1. Baik, langkah pertama kita akan menyiapkan perangkat utama kita dahulu, yaitu Arduino Nano. Kemudian siapkan Modul Sensor Cahaya dan 3 buah kabel jumper.

   <p align="center" width="100%">

   <img width="80%" src={require('../newbies-level/img/img5/tutorial-5-4-ldr-pins.png').default} alt="Arduino Light Sensor Pins"/>

   </p>

2. Lihat gambar di atas sebagai petunjuk untuk membaca pin-pin yang ada pada Modul Sensor Cahaya. Kita akan menghubungkan pin-pin Modul Sensor Cahaya tersebut ke Arduino Nano dengan menggunakan kabel jumper seperti pada gambar Wiring Diagram di bawah ini.

   <p align="center" width="100%">

   <img width="100%" src={require('../newbies-level/img/img5/tutorial-5-5-wiring-diagram.png').default} alt="Arduino Light Sensor Wiring Diagram"/>

   </p>

Jika gambar Wiring Diagram di atas kurang jelas, teman-teman bisa gunakan tabel Wiring Diagram di bawah ini.

| Sensor Cahaya | Arduino Nano Expansion Board |
| :-----------: | :--------------------------: |
|    Pin AO     |            Pin A0            |
|    Pin GND    |            Pin G             |
|    Pin VCC    |            Pin V             |

:::danger Peringatan
Sebelum menyalakan Arduino Nano, harap periksa kembali rangkaiannya. Apakah sudah sama dengan Wiring Diagram?

Periksa kembali posisi pemasangan kaki-kaki. Diharapkan agar tidak terbalik dan sesuai dengan keterangan pin agar tidak merusak komponen.
:::

Setelah Sensor Cahaya dan Arduino Nano saling terhubung, maka hasilnya akan seperti pada gambar di bawah ini.

<p align="center" width="100%">

<img width="100%" src={require('../newbies-level/img/img5/tutorial-5-6-wiring-diagram.jpg').default} alt="Arduino Light Sensor Wiring Diagram"/>

</p>

Warna kabel yang digunakan bebas dan tak harus sama dengan gambar di atas. Namun yang harus diperhatikan, pastikan kaki Potensiometer terhubung ke posisi pin yang sama seperti pada gambar di atas. Gunakan Tabel Wiring Diagram untuk memastikannya. Pastikan pin VCC Sensor Cahaya terhubung ke pin V Arduino Nano dan pin GND Sensor Cahaya terhubung ke pin G Arduino Nano.

### Mengetik Program

3. Bukalah Arduino IDE, kemudian buatlah sketch baru. Beri sketch baru tersebut dengan nama TUTORIAL_6_ALARM_SENSOR_CAHAYA dan simpan dalam folder **Program Tutorials** yang telah kita buat pada Tutorial 1 sebelumnya. Jika terlupa bagaimana membuat nama sketch, silahkan buka kembali Tutorial 1 sebelumnya.

   <p align="center" width="100%">

   <img width="80%" src={require('./img/img6/tutorial-6-0-sketch.png').default} alt="Arduino IDE Sketch Program"/>

   </p>

4. Kemudian ketik program berikut pada sketch tersebut.

```arduino title="TUTORIAL_6_ALARM_SENSOR_CAHAYA.ino" showLineNumbers
void setup() {
Serial.begin(9600);
}

void loop() {
 int nilaiSensor=digitalRead(A0);

 if(nilaiSensor == 1){
  Serial.println("Sudah Malam");
 }

 else{
  Serial.println("Sudah Pagi");
 }

 delay(1);
}
```

5. Periksa kembali ketikan sketch program. Pastikan agar ketikan sketch program sama persis seperti diminta agar tidak mengalami error saat compiling. Jika sudah selesai mengetik program, cobalah memeriksa apakah ketikan Anda sudah benar atau belum dengan cara menekan tombol verify atau ikon di samping 👉 <img src={require('../newbies-level/img/arduino-ide-tool-bar-verify.png').default} alt="Ultrasonic Sensors"/>.

6. Jika proses verify selesai dan information bar menunjukkan “Done compiling”, berarti program yang teman-teman ketik sudah benar dan lanjutkan pada langkah berikutnya.
   <p align="center" width="100%">

   <img width="80%" src={require('./img/img6/tutorial-6-1-sketch.png').default} alt="Arduino IDE Sketch Program"/>

   </p>

### Mengkonfigurasi Arduino IDE

Sebelum mengupload program, sama seperti pada Tutorial 1, mari kita melakukan konfigurasi terlebih dahulu pada Arduino IDE.

7. Memilih Jenis Board

   Pastikan jenis board yang digunakan sudah sesuai dengan settingan pada Arduino IDE dengan cara memilih opsi berikut secara berurutan Tools ➜ Board ➜ Arduino Nano atau perhatikan urutan tanda panah pada gambar di bawah ini. Disini kita memilih Arduino Nano karena kita menggunakan Arduino Nano.

      <p align="center" width="100%">

   <img width="100%" src={require('./img/img6/tutorial-6-2-select-board.png').default} alt="Arduino Light Sensor Wiring Diagram"/>

      </p>

8. Memilih Jenis Processor

   Processor dalam bahasa Indonesia berarti Prosessor, atau Pemroses sebuah perintah, singkatnya seperti otak dari robot. Disini kita akan menentukan jenis Processor yang digunakan oleh Arduiino Nano, yaitu ATMega328P (Old Bootloader), dengan cara memilih opsi berikut secara berurutan Tools ➜ Processor ➜ ATmega328P (Old Bootloader). Atau ikuti urutan tanda panah pada gambar di bawah ini

      <p align="center" width="100%">

   <img width="80%" src={require('./img/img6/tutorial-6-3-select-processor.png').default} alt="Ultrasonic Sensors"/>

      </p>

9. Memilih Nomor Port

   Nomor port untuk Arduino Nano pada tiap laptop/komputer dapat berbeda-beda. Pilihlah nomor port yang muncul pada pilihan yang tersedia di Arduino IDE. Lebih jelasnya, perhatikan gambar di bawah.

      <p align="center" width="100%">

   <img width="80%" src={require('./img/img6/tutorial-6-4-select-port.png').default} alt="Ultrasonic Sensors"/>

      </p>

### Mengupload Program

10. Setelah proses konfigurasi selesai seperti yang diperintahkan, lanjutkan dengan mengklik tombol upload <img src={require('../newbies-level/img/arduino-ide-tool-bar-upload.png').default} alt="Ultrasonic Sensors"/> pada Arduino IDE.

:::note Catatan
jika proses upload gagal, cobalah mengganti nomor PORT COMXX yang tersedia pada daftar pilihan nomor port pada langkah 3 di atas sampai proses upload berhasil.
:::

12. Jika proses upload berhasil, klik ikon “Serial Monitor” IDE seperti ditunjukkan oleh gambar disamping, <img src={require('../newbies-level/img/img3/arduino-ide-tool-bar-sermon.png').default} alt="Ultrasonic Sensors"/>, yang terletak pada pojok atas kanan Arduino.

Maka akan muncul window “Serial Monitor” seperti pada gambar di bawah ini.

Jika belum muncul teks tersebut, cobalah nyalakan centang pada “Autoscroll”, atur setinggan pada “Newline”, dan “9600 baud”.

<p align="center" width="100%">

<img width="100%" src={require('./img/img6/tutorial-6-5-sermon.png').default} alt="Ultrasonic Sensors"/>

</p>

Pada Serial Monitor tersebut akan menampilkan pesan yang menyatakan kondisi cahaya di sekitar ruangan sensor cahaya.

Cobalah sorot bagian LDR dengan menggunakan cahaya senter. Pesan yang berbeda akan muncul pada Serial Monitor sesuai dengan kondisi cahaya yang berbeda.

<br/>

## Penjelasan Program

```arduino title="TUTORIAL_6_ALARM_SENSOR_CAHAYA.ino" showLineNumbers
void setup() {
Serial.begin(9600);
}

void loop() {
 int nilaiSensor=digitalRead(A0);

 if(nilaiSensor == 1){
  Serial.println("Sudah Malam");
 }

 else{
  Serial.println("Sudah Pagi");
 }

 delay(1);
}
```

Pada baris 2 dalam fungsi `setup()` terdapat fungsi `Serial.begin(9600)` yang memerintahkan Arduino Nano untuk memulai komunikasi dengan laptop agar bisa menampilkan data pada Serial Monitor.

Kemudian pada baris 6 dalam fungsi `loop()` terdapat perintah `digitalRead()` untuk membaca nilai sinyal digital dari pin AO milik Sensor Cahaya yang masuk melalui pin A0 milik Arduino Nano.

Nilai sinyal digital hasil pembacaan tersebut akan disimpan dalam variabel `nilaiSensor` yang bertipe integer alias menyimpan bilangan bulat. Untuk lebih jelasnya, perhatikan ilustrasi berikut:

<p align="center" width="100%">

<img width="100%" src={require('./img/img6/tutorial-6-6-exp.png').default} alt="Ultrasonic Sensors"/>

</p>

Berdasarkan ilustrasi di atas, apabila misalnya hasil pembacaan pada pin A0 dengan perintah `digitalRead()` bernilai 1, maka akan disimpan pada variable `nilaiSensor`.

Karena nilai 1 tadi disimpan pada variable `nilaiSensor`, kini `variable` nilaiSensor sekarang menyimpan angka 1.

Kemudian pada baris 8 hingga baris 10 yang diterangi di bawah ini terdapat blok fungsi `if()` dengan parameter `nilaiSensor==1` yang diapit dalam dua tanda kurung biasa.

Parameter yang diapit dalam dua tanda kurung tersebut disebut sebagai parameter kondisi. Dimana parameter kondisi milik fungsi `if()` adalah `nilaiSensor==1`.

Mengapa kita menggunakan angka 1 untuk parameter kondisi?

Kalau kita ingat kembali Tutorial 5, jika Sensor Cahaya tidak disorot oleh cahaya senter atau ketika ruangan dalam kondisi gelap, maka pada Serial Monitor akan menampilkan angka 1.

```arduino title="TUTORIAL_6_ALARM_SENSOR_CAHAYA.ino" showLineNumbers
void setup() {
Serial.begin(9600);
}

void loop() {
 int nilaiSensor=digitalRead(A0);

//highlight-start
 if(nilaiSensor == 1){
  Serial.println("Sudah Malam");
 }
//highlight-end

 else{
  Serial.println("Sudah Pagi");
 }

 delay(1);
}
```

Perhatikan terdapat dua buah tanda sama dengan ( = ) pada baris 8. Pada bahasa pemrograman, tanda = tidak sama dengan makna “Sama Dengan” seperti dalam bahasa manusia umumnya.

Pada bahasa pemrograman, satu buah tanda = berfungsi sebagai perintah untuk memerintahkan menyimpan/memindahkan data dari ruas kanan ke data ke ruas kiri.

<p align="center" width="100%">

<img width="100%" src={require('./img/img6/tutorial-6-7-exp.png').default} alt="Ultrasonic Sensors"/>

</p>

Seperti contoh pada baris 6, satu buah tanda `=` akan memerintahkan nilai hasil perintah pembacaan pada ruas kanan disimpan atau dapat disebut juga, dipindahkan, ke variabel `nilaiSensor` yang berada pada ruas sebelah kiri.

Sedangkan untuk membuat frasa “Sama Dengan” dalam bahasa pemrograman seperti pada bahasa manusia umumnya, kita dapat menggunakan dua buah tanda = seperti pada baris 8.

<p align="center" width="100%">

<img width="60%" src={require('./img/img6/tutorial-6-8-exp.png').default} alt="Ultrasonic Sensors"/>

</p>

Secara keseluruhan baris 8 akan berbunyi, “jika variable `nilaiSensor` sama dengan 1” (ingat kembali, "if" artinya "jika"). Dengan kata lain, baris 8 di atas akan memeriksa atau lebih tepatnya menanyakan apakah variabel `nilaiSensor` menyimpan angka 1 atau tidak.

Kemudian pada baris 9 merupakan blok perintah milik fungsi `if()` karena terletak diantara tanda kurawal buka `{` pada baris 8 dan kurawal tutup `}` pada baris 10 milik fungsi `if()`.

```arduino title="TUTORIAL_6_ALARM_SENSOR_CAHAYA.ino" showLineNumbers
void setup() {
Serial.begin(9600);
}

void loop() {
 int nilaiSensor=digitalRead(A0);

 if(nilaiSensor == 1){
  //highlight-start
  Serial.println("Sudah Malam");
  //highlight-end
 }

 else{
  Serial.println("Sudah Pagi");
 }

 delay(1);
}
```

Blok perintah pada fungsi `if()` tersebut terdapat perintah `println` yang memerintahkan Arduino Nano mencetak pesan "Sudah Malam" pada Serial Monitor.

Maka secara keseluruhan, blok fungsi `if()` pada baris 8 hingga 10 akan berbunyi, jika nilai yang disimpan dalam variabel `nilaiSensor` sama dengan `1`, maka akan mencetak cetak teks “Sudah Malam” pada Serial Monitor.

<p align="center" width="100%">

<img width="100%" src={require('./img/img6/tutorial-6-9-exp.png').default} alt="Ultrasonic Sensors"/>

</p>

Selanjutnya, terdapat blok fungsi `else()` pada baris 12 hingga baris 14.

```arduino title="TUTORIAL_6_ALARM_SENSOR_CAHAYA.ino" showLineNumbers
void setup() {
Serial.begin(9600);
}

void loop() {
 int nilaiSensor=digitalRead(A0);

 if(nilaiSensor == 1){
  Serial.println("Sudah Malam");
 }

  //highlight-start
 else{
  Serial.println("Sudah Pagi");
 }
  //highlight-end

 delay(1);
}
```

Pada baris 8, fungsi `if()` memiliki parameter kondisi `nilaiSensor==1`, sedangkan fungsi `else()` tidak memiliki parameter kondisi yang diapit dalam dua tanda kurung sebagaimana fungsi if pada baris 8.

Hal ini karena fungsi else itu sendiri dalam bahasa manusia memiliki arti “selain itu".

Blok perintah milik fungsi `else()` itu sendiri berada pada baris 13 dan diapit oleh tanda kurawal buka `{` pada baris 12 dan tanda kurawal tutup `}` pada baris 14.

Blok perintah tersebut berisi perintah `println` untuk mencetak teks “Sudah Pagi” pada Serial Monitor.

<p align="center" width="100%">

<img width="100%" src={require('./img/img6/tutorial-6-10-exp.png').default} alt="Ultrasonic Sensors"/>

</p>

Maka secara keseluruhan blok fungsi kondisional _if else_ terangkum pada ilustrasi berikut:

<p align="center" width="100%">

<img width="100%" src={require('./img/img6/tutorial-6-11-exp.png').default} alt="Ultrasonic Sensors"/>

</p>

Atau juga bisa dipahami melalui bagan flowchart berikut ini:

<p align="center" width="100%">

<img width="60%" src={require('./img/img6/tutorial-6-12-exp.png').default} alt="Ultrasonic Sensors"/>

</p>

Dan memiliki makna yang jika diterjemahkan dalam bahasa manusia akan berbunyi:
Jika `nilaiSensor `sama dengan `1`, maka cetak teks "Sudah Malam".
Jika tidak, cetak teks "Sudah Pagi".

## Tantangan Tutorial 6

Selanjutnya kita akan masuk pada topik Tantangan 6.

### Tantangan 1

Tahukah teman-teman? Teman-teman bisa memodifikasi teks pesan yang ingin ditampilkan pada Serial Monitor sesuai dengan keinginan teman-teman jika suatu kondisi terpenuhi. Misalnya pada gambar berikut:

<p align="center" width="100%">

<img width="60%" src={require('./img/img6/tutorial-6-13-challenge-1.png').default} alt="Ultrasonic Sensors"/>

</p>

Kita harus menampilkan pesan persis seperti di atas apabila Sensor Cahaya berada pada kondisi minim cahaya. Tantangan pertama ini sangat sederhana cobalah belajar menantang diri mengganti teks pesan sesuai keinginan teman-teman.

Kita beri petunjuk yah, kita gunakan sketch program yang telah dijelaskan sebelumnya, hanya saja kita akan mengganti pesan dalam fungsi `if` dan `else` nya menjadi sesuai yang tampil pada gambar Serial Monitor di atas.

Setelah itu, cobalah ganti pesannya sesuai dengan keinginan teman-teman sendiri.

### Tantangan 2

Cobalah memodifikasi isi dalam fungsi `if` dan `else` seperti pada potongan sketch program yang di-higlight di bawah. Lihatlah hasilnya pada Serial Monitor.

```arduino title="TUTORIAL_6_ALARM_SENSOR_CAHAYA.ino" showLineNumbers
void setup() {
Serial.begin(9600);
}

void loop() {
 int nilaiSensor=digitalRead(A0);

 if(nilaiSensor == 1){
  //highlight-start
  Serial.print("Sudah Malam ");
  Serial.println(nilaiSensor);
  //highlight-end
 }


 else{
  //highlight-start
  Serial.print("Sudah Pagi ");
  Serial.println(nilaiSensor);
  //highlight-end
 }

 delay(1);
}
```

Sketch program di atas tersebut merupakan contoh bagaimana kita memeriksa hasil pembacaan sensor yang disimpan dalam variabel `nilaiSensor` dengan menampilkannya pada Serial Monitor sekaligus menampilkan pesan teks secara bersamaan pada Serial Monitor juga.

Perhatikan bahwa terdapat perbedaan dalam menulis parameter data untuk perintah `print`, apabila kita ingin mencetak parameter berupa teks atau huruf, kita harus mengapitnya dalam dua tanda kutip.

Sedangkan untuk parameter yang berupa data milik suatu variabel, misalnya variabel `nilaiSensor` yang menyimpan angka 1 atau angka 0, kita tidak perlu mengapitnya dalam dua tanda kutip.

### Tantangan 3

Pada Tantangan 3 ini, kita akan menyalakan lampu indikator L (panah putih) pada Arduino Nano apabila kondisi cahaya sedang gelap (gambar kiri), dan mematikan lampu ketika kondisi cahaya sedang terang (gambar kanan).

|                                           Lampu Menyala Ketika Gelap                                           |                                           Lampu Padam ketika Terang                                            |
| :------------------------------------------------------------------------------------------------------------: | :------------------------------------------------------------------------------------------------------------: |
| <img width="100%" src={require('./img/img6/tutorial-6-14-challenge-3.png').default} alt="Ultrasonic Sensors"/> | <img width="100%" src={require('./img/img6/tutorial-6-15-challenge-3.png').default} alt="Ultrasonic Sensors"/> |

Sebagai permulaan, kita akan menggunakan lampu indikator L bawaan milik Arduino Nano yang terhubung pada pin 13.

Ada petunjuk? Ada nih, Bestie,, kuncinya adalah Tutorial 1 dan sepotong sketch program berikut:

<p align="center" width="100%">

<img width="100%" src={require('./img/img6/tutorial-6-16-challenge-3.png').default} alt="Ultrasonic Sensors"/>

</p>

Petunjuk singkat, pada kotak hijau itu adalah satu baris perintah untuk menyalakan atau mematikan lampu pada pin 13. Masih ingat kan fungsi untuk menyalakan dan mematikan lampu pada pin 13 seperti yang telah dipelajari pada Tutorial 1 sebelumnya?
