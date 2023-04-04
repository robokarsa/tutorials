---
sidebar_position: 6
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Tutorial 10 - Triple Distance Sensor

## Selayang Pandang

Karena teman-teman sudah berhasil melewati Tutorial 8 dan 9, maka dikatakan teman-teman sekarang sudah memiliki pengetahuan mengenai Sensor Ultrasonik dan bagaimana memprogramnya baik dengan menggunakan perintah dan persamaan yang kita tulis secara manual dalam fungsi `loop()` maupun menggunakan fungsi yang dibuat sendiri.

Namun, pada kedua tutorial tersebut, teman-teman masih belajar memprogram satu buah sensor jarak saja. Bagaimana jika ada kondisi atau project yang mengharuskan teman-teman untuk menggunakan lebih dari satu buah sensor jarak?

Pada Tutorial 10 kali ini, kita akan belajar bagaimana melakukannya. Kita akan belajar bagaimana membaca jarak yang terukur dari tiga buah sensor jarak dan bagaimana memprogram ketiganya.

Selain itu, kita juga akan mengenalkan teman-teman dengan yang namanya "library" atau bahasa Indonesianya adalah "Pustaka". Library yang akan kita gunakan pada dasarnya mirip seperti fungsi yang dibuat sendiri yang telah kita pelajari sebelumnya.

Hanya saja, library memiliki lebih besar dan lebih banyak baris kode program yang tersembunyi dan tidak berada di bawah fungsi `loop()`. Dan penggunaan library ini sama seperti fungsi yang dibuat sendiri, yakni kita hanya perlu memanggilnya saja dalam baris program yang kita inginkan. Sehingga kode program kita menjadi lebih rapi dan lebih ringkas lagi.

Library yang akan kita gunakan ini bernama libary **NewPing**, yakni library yang digunakan untuk memprogram sensor jarak dengan satu baris kode saja. Contoh singkatnya seperti pada program di bawah ini:

```arduino title="CONTOH" showLineNumbers
#include <NewPing.h>

#define TRIGGER_PIN 8
#define ECHO_PIN 9
#define MAX_DISTANCE 400

NewPing sonar(TRIGGER_PIN, ECHO_PIN, MAX_DISTANCE);

void setup() {
Serial.begin(9600);
}

void loop() {
delay(50);
int distance = sonar.ping_cm();
Serial.print("Distance: ");
Serial.print(distance);
Serial.println(" cm");
}
```

Program di atas adalah program untuk membaca jarak yang diukur oleh satu buah sensor jarak. Terlihat cukup ringkas dan singkat bukan?

Kira-kira bagaimana hasil dan penjelasan programnya? Mari kita simak langkah berikutnya.

## Mulai Beraksi 🚀

Kita akan menggunakan bahan dan peralatan yang sama seperti pada Tutorial 8 sebelumnya. Sebelum mulai beraksi, pastikan teman-teman sudah membaca Prasyarat, Target Pelajaran, dan Komponen Yang Dibutuhkan ya.

Klik pada salah satu dari ketiga tombol di bawah ini untuk membuka Prasyarat, Target Pelajaran dan Komponen Yang Dibutuhkan.

<Tabs className="unique-tabs">
<TabItem value="Prasyarat 🔑">

- Sudah lolos Tutorial 7 - Alarm Sensor Cahaya Lanjutan
- Sudah mempelajari Arduino Nano Expansion Board pada materi **[Arduino Nano Expansion Board](/docs/tutorial-arduino/arduino-hardware.md#arduino-nano-expansion-board)**

Kalau teman-teman merasa belum memenuhi prasyarat yang dibutuhkan, diharapkan untuk membaca dan memenuhinya terlebih dahulu.

</TabItem>

<TabItem value="Target Pelajaran 🎯">

- Memahami bagaimana memprogram Sensor Jarak Ultrasonik menggunakan fungsi yang kita buat sendiri
- Memahami bagaimana memprogram Sensor Jarak Ultrasonik menggunakan library
- Memahami bagaimana membuat fungsi sendiri.

</TabItem>

<TabItem value="Komponen Yang Dibutuhkan 🛠">

- 1 x Arduino Nano
- 1 x Kabel USB Arduino Nano
- 1 x Komputer/Laptop
- 3 x Sensor Jarak
- 4 x Kabel Jumper Female-Female

</TabItem>
</Tabs>

:::caution Perhatian

Penting untuk memperhatikan setiap langkah-langkah yang diberikan dan tidak melakukan apapun diluar perintah langkah yang diberikan.

Kenapa? Hal ini untuk mencegah kerusakan yang tidak diinginkan pada komponen apabila bertindak di luar langkah pelajaran yang diberikan dan tidak mengetahui dengan pasti apa yang teman-teman lakukan.

:::

### Menghubungkan Pin-Pin

Sesuai judul Tutorial 10 ini, kita akan belajar bagaimana memprogram dan mengukur jarak menggunakan tiga buah sensor jarak. Namun sebelumnya, mari kita gunakan satu buah sensor jarak terlebih dahulu dan belajar bagaimana menggunakan library **NewPing** untuk satu buah sensor terlebih dahulu.

1. Kita akan meminjam wiring diagram milik Tutorial 8 dan 9 untuk menghubungkan pin-pin Modul Sensor Jarak ke Arduino Nano dengan menggunakan kabel jumper seperti pada gambar Wiring Diagram di bawah ini.

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

2. Bukalah Arduino IDE, kemudian buatlah sketch baru. Beri sketch baru tersebut dengan nama TUTORIAL_10_TRIPLE_DISTANCE_SENSOR dan simpan dalam folder **Program Tutorials** yang telah kita buat pada Tutorial 1 sebelumnya. Jika terlupa bagaimana membuat nama sketch, silahkan buka kembali Tutorial 1 sebelumnya.

3. Kemudian ketik program berikut pada sketch tersebut. Namun, setelah mengetik programnya, jangan diupload dahulu ya, teman-teman. Lanjutkan ke langkah 4 berikutnya terlebih dahulu.

```arduino title="TUTORIAL_10_TRIPLE_DISTANCE_SENSOR.ino" showLineNumbers
#include <NewPing.h>

#define TRIGGER_PIN 8
#define ECHO_PIN 9
#define MAX_DISTANCE 400

NewPing sonar(TRIGGER_PIN, ECHO_PIN, MAX_DISTANCE);

void setup() {
Serial.begin(9600);
}

void loop() {
delay(50);
int distance = sonar.ping_cm();
Serial.print("Distance: ");
Serial.print(distance);
Serial.println(" cm");
}
```

4. Setelah selesai mengetik program, sekarang kita harus menginstall library NewPing. Teman-teman terlebih dahulu harus mengunduh file library NewPing dengan menekan [link ini](../beginner-level/img/img10/NewPing_v1.9.1). Teman-teman akan mendapatkan file .zip dengan nama file seperti pada gambar di bawah ini.

   <p align="center" width="100%">
   <img width="40%" src={require('../beginner-level/img/img10/tutorial-10-install-newping-0.png').default} alt="Arduino Light Sensor Pins"/>
   </p>

5. Setelah selesai mengunduh file library NewPing, selanjutnya kita akan menambahkan file .zip tersebut ke dalam Arduino IDE. Caranya adalah menekan tab `Sketch` > `Include Library` > `Add .ZIP Library` secara berurutan seperti pada gambar di bawah ini:

   <p align="center" width="100%">
   <img width="80%" src={require('../beginner-level/img/img10/tutorial-10-install-newping-1.png').default} alt="Arduino Light Sensor Pins"/>
   </p>

6. Begitu teman-teman menekan `Add .ZIP Library`, maka akan muncul jendela baru seperti pada gambar di bawah ini

   <p align="center" width="100%">
   <img width="80%" src={require('../beginner-level/img/img10/tutorial-10-install-newping-2.png').default} alt="Arduino Light Sensor Pins"/>
   </p>

   Tekan dua kali pada file **Download** seperti yang ditunjukkan pada gambar di atas.

7. Kemudian teman-teman akan masuk ke dalam file Download dan menemukan file .zip dengan nama NewPing seperti yang ditunjukkan pada gambar di bawah

   <p align="center" width="100%">
   <img width="80%" src={require('../beginner-level/img/img10/tutorial-10-install-newping-3.png').default} alt="Arduino Light Sensor Pins"/>
   </p>

   Tekan sekali saja pada file tersebut, kemudian tekan tombol **Open** yang berada pada pojok kanan bawah.

8. Apabila pada Notification Bar Arduino IDE berwarna orange dan menunjukkan pesan "A library named NewPing already exists", berarti library NewPing sudah berhasil diinstal.

   <p align="center" width="100%">
   <img width="80%" src={require('../beginner-level/img/img10/tutorial-10-install-newping-4.png').default} alt="Arduino Light Sensor Pins"/>
   </p>

9. Setelah selesai mengetik program, menginstall library, kemudian jalankan proses verify. Dan apabila proses verify sudah berhasil, upload lah program tersebut ke Arduino Nano.

10. Setelah proses upload berhasil, bukalah Serial Monitor, dan amati perubahan nilai jaraknya apabila kita mendekatkan atau menjauhkan tangan kita dari Sensor Jarak.

   <p align="center" width="100%">
   <img width="80%" src={require('../beginner-level/img/img10/tutorial-11-sermon.png').default} alt="Arduino Light Sensor Pins"/>
   </p>

<br/>

## Penjelasan Program

Mari kita mencari tahu bagaimana program yang kita upload tadi berjalan.

```arduino title="TUTORIAL_10_TRIPLE_DISTANCE_SENSOR.ino" showLineNumbers
#include <NewPing.h>

#define TRIGGER_PIN 8
#define ECHO_PIN 9
#define MAX_DISTANCE 400

NewPing sonar(TRIGGER_PIN, ECHO_PIN, MAX_DISTANCE);

void setup() {
Serial.begin(9600);
}

void loop() {
delay(50);
int distance = sonar.ping_cm();
Serial.print("Distance: ");
Serial.print(distance);
Serial.println(" cm");
}
```

Perhatikan bahwa pada baris 1, terdapat perintah `#include <NewPing.h>` yang memerintahkan Arduino IDE untuk memasukkan library NewPing ke dalam program. Kata "include" yang digunakan dalam perintah tersebut aslinya merupakan kata dari bahasa Inggris yang berarti "sertakan".

Maka secara tidak langsung, arti program pada baris 1 di atas adalah, "sertakan library NewPing". Perhatikan bahwa terdapat akhiran .h di belakang nama NewPing. Semua library yang akan digunakan dalam Arduino IDE memiliki akhiran .h di belakangnya. Selain itu, untuk memasukkan library, kita harus meletakkan nama library yang ingin dipanggil dalam tanda kurung panah `<` `>`.

Jadi, jika teman-teman menemukan baris program yang memiliki akhiran .h di dalam tanda kurung panah `<` `>`, maka bisa dikatakan itu adalah library.

Kemudian pada baris 3 sampai pada baris 5, terdapat perintah `#define`, yakni perintah yang digunakan untuk mendefinisikan suatu variabel dengan data yang berupa angka-angka tertentu.

```arduino
#define TRIGGER_PIN 8
#define ECHO_PIN 9
#define MAX_DISTANCE 400
```

Misalnya pada baris 3, terdapat perintah `#define TRIGGER_PIN 8`, kita membuat variabel bernama `TRIGGER_PIN` yang kemudian didefinisikan menyimpan angka 8. Sebenarnya, secara tepatnya, perintah `#define` tidak benar-benar memerintahkan untuk menyimpan angka 8 ke variabel `TRIGGER_PIN` melainkan membuat Arduino IDE berpikir bahwa variabel `TRIGGER_PIN` juga adalah angka 8.

Mengapa angka 8? Hal ini karena kita menghubungkan pin Trigger Sensor Jarak ke pin nomor 8 Arduino Nano. Sama halnya pada baris 4, yang mendefinisikan bahwa pin Echo Sensor Jarak terhubung ke pin nomor 9 Arduino Nano.

Kemudian pada baris 5, terdapat perintah untuk mendefinisikan variabel `MAX_DISTANCE` yang akan menyimpan jarak maksimal yang dapat diukur oleh Sensor Jarak adalah sejauh 400 Cm. Jadi, jika misalnya sensor jarak mengukur jarak yang melebihi jarak maksimal yang sudah didefinisikan, maka pada Serial Monitor akan mengeluarkan angka 0 Cm.

Kemudian pada baris 7, kita memiliki kode berikut

```arduino
NewPing sonar(TRIGGER_PIN, ECHO_PIN, MAX_DISTANCE);
```

`NewPing` merupakan kelas dari library yang kita gunakan. Kita akan belajar tentang kelas pada bahasa pemrograman nantinya pada level yang lebih tinggi lagi. Namun, untuk sekarang, anggaplah kelas `NewPing` pada dasarnya sama seperti perintah `#define` yang mendefisinikan suatu variabel.

Jika `#define` digunakan untuk mendefinisikan suatu variabel, sedangkan kelas `NewPing` digunakan untuk mendefinisikan objek. Objek disini maksudnya adalah sensor yang akan kita gunakan.

Sama seperti mendefinisikan variabel dengan nama bebas, kita juga dengan bebas bisa menamai sensor yang ingin kita gunakan. Nama sensor yang kita buat ini nantinya akan kita gunakan ketika kita ingin memanggilnya dalam fungsi `loop()` nantinya ketika kita ingin mengukur jarak menggunakan sensor tersebut.

Ketika membuat objek sensor, kita juga akan mendefinisikan nomor Arduino Nano yang akan terhubung dengan pin Trigger dan pin Echo sensor jarak yang kita gunakan serta mendefinisikan berapa jarak maksimum sensor jarak yang akan kita tetapkan.

Karena `TRIGGER_PIN` sudah didefinisikan sebagai angka `8` pada baris 3 sebelumnya, begitupula `ECHO_PIN` sudah didefinisikan sebagai angka `9` pada baris 4 sebelumnya, dan terakhir, `MAX_DISTANCE` telah didefinisikan sejauh `400` cm pada baris 5 sebelumnya, maka kode pada baris 7 akan seperti ini

```arduino
NewPing sonar(8, 9, 400);
```

Mirip seperti fungsi bukan? Dan fungsi tersebut memiliki tiga buah parameter, yakni 8, 9, dan 400. Kemudian `sonar` merupakan nama objek sensor jarak kita yang terhubung ke pin 8 dan pin 9 pada Arduino Nano.

Selanjutnya kita masuk ke fungsi `setup()`. Dalam fungsi setup, hanya terdapat perintah `Serial.begin(9600)` untuk memulai komunikasi serial antara Arduino Nano dengan Laptop/Komputer kita pada kecepatan baud rate 9600.

```arduino
void setup() {
Serial.begin(9600);
}
```

Kini kita masuk ke fungsi `loop()`. Perintah pertama pada fungsi `loop()` adalah perintah `delay(50)` karena kita ingin menunda selama 50 mili detik terlebih dahulu untuk membersihkan suara ultrasonik bekas pancaran sebelumnya.

```arduino
int distance = sonar.ping_cm();
```

Pada baris 15, kita membuat variabel bernama `distance` bertipe `int`, yakni tipe data untuk menyimpan bilangan bulat. Kemudian terdapat perintah `sonar.ping_cm()`. Disinilah semua proses pembacaan dan perhitungan sensor jarak dilakukan.

Masih ingat kah pada baris 7 sebelumnya, dimana kita menamai objek sensor yang kita gunakan dengan nama `sonar`? Benar, perintah pada baris 15 tersebut memerintahkan untuk membaca jarak sensor ultrasonik dengan tangan kita. Kemudian hasil pembacaannya akan disimpan dalam variabel `distance` tadi.

Dengan menggunakan library NewPing, kita cukup menggunakan perintah `namaSensorKita.ping_cm()` untuk membaca jarak dan menyimpan hasil pembacaan jaraknya ke dalam variabel yang kita buat.

Kalau misalnya nama sensor yang kita buat adalah `sensorKanan`, maka jika kita ingin membaca jaraknya, kita cukup menggunakan perintah `sensorKanan.ping_cm()`.

Hasil pembacaan sensor jarak yang tersimpan dalam variabel `distance` tadi kemudian akan dicetak pada Serial Monitor seperti yang terlihat pada baris 17 dalam program.

```arduino
Serial.print("Distance: ");
Serial.print(distance);
Serial.println(" cm");
```

Cukup ringkas bukan? Itulah kelebihannya jika kita menggunakan library NewPing untuk membaca/mengukur jarak suatu benda.

Setelah mengetahui bagaimana cara library NewPing bekerja. Mari kita menambah jumlah sensornya menjadi 2 buah sensor lagi sehingga secara keseluruhan kita akan memprogram tiga buah sensor.

## Memprogram Tiga Sensor Jarak

### Menghubungkan Pin-Pin

Mari kita ikuti langkah-langkah yang disediakan.

1. Kita akan menghubungkan pin-pin Modul Sensor Jarak ke Arduino Nano dengan menggunakan kabel jumper seperti pada gambar Wiring Diagram di bawah ini.

<p align="center" width="100%">

<img width="100%" src={require('../beginner-level/img/img10/tutorial-11-triple-sensor.png').default} alt="Arduino Light Sensor Pins"/>

</p>

Jika gambar Wiring Diagram di atas kurang jelas, teman-teman bisa gunakan tabel Wiring Diagram di bawah ini.

<table>
<tr><th>Sensor Jarak Kiri</th><th>Sensor Jarak Tengah</th><th>Sensor Jarak Kanan</th></tr>
<tr>
<td>

| Sensor Jarak | Arduino Nano Expansion Board |
| :----------: | :--------------------------: |
|     GND      |            Pin G             |
|     TRIG     |            Pin 8             |
|     ECHO     |            Pin 9             |
|     VCC      |            Pin V             |

</td>

<td>

| Sensor Jarak | Arduino Nano Expansion Board |
| :----------: | :--------------------------: |
|     GND      |            Pin G             |
|     TRIG     |            Pin 6             |
|     ECHO     |            Pin 5             |
|     VCC      |            Pin V             |

</td>

<td>

| Sensor Jarak | Arduino Nano Expansion Board |
| :----------: | :--------------------------: |
|     GND      |            Pin G             |
|     TRIG     |            Pin 2             |
|     ECHO     |            Pin 3             |
|     VCC      |            Pin V             |

</td>

</tr>

</table>

:::danger Peringatan
Sebelum menyalakan Arduino Nano, harap periksa kembali rangkaiannya. Apakah sudah sama dengan Wiring Diagram?

Periksa kembali posisi pemasangan kaki-kaki. Diharapkan agar tidak terbalik dan sesuai dengan keterangan pin agar tidak merusak komponen.
:::

### Mengetik Program

Setelah memastikan semua rangkaian sudah benar, ketiklah program di bawah ini.

```arduino title="TUTORIAL_10_TRIPLE_DISTANCE_SENSOR.ino" showLineNumbers
#include <NewPing.h>

//Sensor Kiri
#define LEFT_TRIGGER_PIN 8
#define LEFT_ECHO_PIN 9

//Sensor Tengah
#define CENTER_TRIGGER_PIN 6
#define CENTER_ECHO_PIN 5

//Sensor Kanan
#define RIGHT_TRIGGER_PIN 2
#define RIGHT_ECHO_PIN 3

#define MAX_DISTANCE 400

NewPing SensorKiri(LEFT_TRIGGER_PIN, LEFT_ECHO_PIN, MAX_DISTANCE);
NewPing SensorTengah(CENTER_TRIGGER_PIN, CENTER_ECHO_PIN, MAX_DISTANCE);
NewPing SensorKanan(RIGHT_TRIGGER_PIN, RIGHT_ECHO_PIN, MAX_DISTANCE);

void setup() {
Serial.begin(9600);
}

void loop() {
delay(50);
int dataKiri = SensorKiri.ping_cm();
int dataTengah = SensorTengah.ping_cm();
int dataKanan = SensorKanan.ping_cm();
Serial.print("Sensor Kiri: ");
Serial.print(dataKiri);
Serial.print(" cm");
Serial.print(" | ");
Serial.print("Sensor Tengah: ");
Serial.print(dataTengah);
Serial.print(" cm");
Serial.print(" | ");
Serial.print("Sensor Kanan: ");
Serial.print(dataKanan);
Serial.println(" cm");
}
```

Setelah mengupload program tersebut, nantinya teman-teman akan mendapati informasi pada Serial Monitor seperti pada gambar di bawah ini

<p align="center" width="100%">

<img width="80%" src={require('../beginner-level/img/img10/tutorial-11-triple-sensor-sermon.png').default} alt="Arduino Light Sensor Pins"/>

</p>

Nantinya, angka 0 pada gambar di atas akan terganti dengan angka sesuai dengan hasil pengukuran yang didapatkan oleh sensor jarak milik teman-teman.

### Penjelasan Program

Secara singkat, penjelasan program untuk tiga buah sensor jarak ini pada dasarnya sama seperti penjelasan program untuk satu buah sensor sebelumnya.

Seperti mendefinisikan nomor pin-pin Arduino Nano yang akan digunakan untuk menghubungkan pin-pin Trigger dan Echo Sensor Jarak. Mendefinisikan jarak maksimum yang harus dibaca oleh Sensor jarak. Kemudian memanggil kelas NewPing untuk membuat nama sensor yang akan digunakan. Kemudian, memanggil nama sensor yang telah dibuat tadi untuk dilakukan pengukuran menggunakan perintah namaSensor.ping_cm() dan menyimpan hasil pengukurannya ke dalam suatu variabel.

Hanya saja, karena kita menggunakan tiga buah sensor, kita melakukan semua itu sebanyak tiga kali.

Sebagai contoh, baris 4 sampai 5 yang diterangi di bawah ini akan mendefinisikan bahwa pin Trigger Sensor Kiri akan terhubung pada pin Arduino Nano nomor 8. Begitupula pin Echo Sensor Kiri akan terhubung pada pin Arduino Nano nomor 9.

Sementara untuk sensor tengah dan kanan bisa teman-teman lihat pada baris berikutnya. Penomoran pin-pin nya akan sesuai dengan Wiring Diagram atau Tabel Diagram yang teman-teman gunakan.

```arduino title="TUTORIAL_10_TRIPLE_DISTANCE_SENSOR.ino" showLineNumbers
#include <NewPing.h>

//highlight-start
//Sensor Kiri
#define LEFT_TRIGGER_PIN 8
#define LEFT_ECHO_PIN 9
//highlight-end

//Sensor Tengah
#define CENTER_TRIGGER_PIN 6
#define CENTER_ECHO_PIN 5

//Sensor Kanan
#define RIGHT_TRIGGER_PIN 2
#define RIGHT_ECHO_PIN 3

#define MAX_DISTANCE 400

NewPing SensorKiri(LEFT_TRIGGER_PIN, LEFT_ECHO_PIN, MAX_DISTANCE);
NewPing SensorTengah(CENTER_TRIGGER_PIN, CENTER_ECHO_PIN, MAX_DISTANCE);
NewPing SensorKanan(RIGHT_TRIGGER_PIN, RIGHT_ECHO_PIN, MAX_DISTANCE);

void setup() {
Serial.begin(9600);
}

void loop() {
delay(50);
int dataKiri = SensorKiri.ping_cm();
int dataTengah = SensorTengah.ping_cm();
int dataKanan = SensorKanan.ping_cm();
Serial.print("Sensor Kiri: ");
Serial.print(dataKiri);
Serial.print(" cm");
Serial.print(" | ");
Serial.print("Sensor Tengah: ");
Serial.print(dataTengah);
Serial.print(" cm");
Serial.print(" | ");
Serial.print("Sensor Kanan: ");
Serial.print(dataKanan);
Serial.println(" cm");
}
```

Kemudian pada baris 15, kita mendefinisikan MAX_DISTANCE untuk menetapkan jarak maksimal yang dapat diukur oleh Sensor Jarak sejauh 400 cm. Kita mendefinisikannya sekali karena kita akan menggunakannya untuk ketiga sensor.

Selanjutnya, pada baris 17, 18, dan 19 berturut-turut, kita membuat tiga buah objek sensor menggunakan kelas `NewPing`. Bisakah teman-teman lihat nama ketiga objek sensor yang kita buat pada program di bawah ini?

```arduino title="TUTORIAL_10_TRIPLE_DISTANCE_SENSOR.ino"
NewPing SensorKiri(LEFT_TRIGGER_PIN, LEFT_ECHO_PIN, MAX_DISTANCE);
NewPing SensorTengah(CENTER_TRIGGER_PIN, CENTER_ECHO_PIN, MAX_DISTANCE);
NewPing SensorKanan(RIGHT_TRIGGER_PIN, RIGHT_ECHO_PIN, MAX_DISTANCE);
```

Benar, ketiga objek sensor tersebut memiliki nama yang unik dan saling berbeda, yaitu `SensorKiri`, `SensorTengah`, dan `SensorKanan`. Masing-masing objek tersebut juga telah didefinisikan nomor pin-pin Arduino Nano yang terhubung pada pin Trigger dan pin Echo sensor jarak.

Misalnya untuk objek `SensorKiri`, pin Triggernya terhubung pada pin nomor `LEFT_TRIGGER_PIN`. Tahukah teman-teman `LEFT_TRIGGER_PIN` itu maksudnya pin nomor berapa? Jawabannya bisa teman-teman lihat pada baris 4 program, yaitu pin nomor 4 karena kita telah mendefinisikan `LEFT_TRIGGER_PIN` sebagai angka 8. Begitu pula untuk pin Echo milik `SensorKiri` terhubung pada pin 9.

```arduino title="TUTORIAL_10_TRIPLE_DISTANCE_SENSOR.ino"
int dataKiri = SensorKiri.ping_cm();
int dataTengah = SensorTengah.ping_cm();
int dataKanan = SensorKanan.ping_cm();
```

Selanjutnya kita masuk pada fungsi `loop()`. Kita membuat tiga buah variabel baru bertipe `int` untuk menyimpan nilai hasil pengukuran sensor jarak dalam bilangan bulat. Ketiga variabel tersebut memiliki nama yang unik dan berbeda satu sama lainnya.

Untuk mengukur atau membaca jarak pada setiap sensor yang kita inginkan, kita cukup menggunakan perintah `namaSensor.ping_cm()` dimana `namaSensor` diganti dengan nama sensor yang telah kita buat pada baris 17, 18, dan 19 sebelumnya, yakni `SensorKiri`, `SensorTengah`, dan `SensorKanan`.

Begitu variabel dataKiri, dataTengah, dataKanan telah menyimpan hasil pengukuran ketiga sensor, kita akan menampilkan data nya pada Serial Monitor dengan perintah `serial.print()`

```arduino title="TUTORIAL_10_TRIPLE_DISTANCE_SENSOR.ino"
Serial.print("Sensor Kiri: ");
Serial.print(dataKiri);
Serial.print(" cm");
Serial.print(" | ");
Serial.print("Sensor Tengah: ");
Serial.print(dataTengah);
Serial.print(" cm");
Serial.print(" | ");
Serial.print("Sensor Kanan: ");
Serial.print(dataKanan);
Serial.println(" cm");
```
