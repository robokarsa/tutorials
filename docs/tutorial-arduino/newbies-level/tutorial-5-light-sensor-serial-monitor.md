---
sidebar_position: 6
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Tutorial 5 - Light Sensor and Serial Monitor

Pada Tutorial 4 sebelumnya kita telah mempelajari bagaimana Serial Monitor bekerja untuk menampilkan data berupa nilai resistansi pada potensiometer menggunakan fungsi `analogRead()`. Dengan Serial Monitor kita dapat melihat berapa nilai resistansi potensiometer jika kita memutarnya ke arah tertentu.

Sekarang kita akan mempelajari lebih dalam lagi fungsi pemrograman baru yakni `digitalRead()` dengan Serial Monitor. Komponen tambahan yang kita gunakan pada Tutorial 5 kali ini adalah Sensor Cahaya. Bentuk fisik sensor cahaya yang akan kita gunakan pada Pelajaran #4 ini ditunjukkan oleh gambar di bawah.

## Apa itu Sensor Cahaya?

Sensor cahaya merupakan sensor yang dapat mendeteksi keberadaan cahaya atau mengukur gelap terangnya cahaya pada suatu tempat.

<p align="center" width="100%">

<img width="50%" src={require('./img/img5/tutorial-5-1-light-sensor.png').default} alt="Arduino Light Sensor"/>

</p>

Pada dasarnya sensor cahaya menggunakan komponen utama yang disebut sebagai LDR (Light Dependent Resistor) atau dalam bahasa Indonesia, Resistor Berdasarkan Cahaya. Komponen LDR ini sama seperti potensiometer yang telah kita pelajari sebelumnya pada Tutorial. Bisakah teman-teman menebak yang mana komponen LDR pada gambar di bawah ini? Di kiri atau di kanan?

<p align="center" width="100%">

<img width="50%" src={require('./img/img5/tutorial-5-2-ldr-sensor.png').default} alt="Arduino Light Sensor"/>

</p>

LDR dan potensiometer sama-sama merupakan komponen resistor yang nilai resistansinya dapat berubah-ubah. Namun perbedaannya terletak pada pemicu atau penyebab yang membuat nilai resistansi nya berubah.

Pada potensiometer yang kita gunakan pada Tutorial 4 sebelumnya, nilai resistansi akan berubah jika kita memutar topi potensiometer. Sedangkan pada LDR, nilai resistansi berubah jika terkena cahaya terang atau cahaya gelap.

Teman-teman bisa melihat komponen LDR terpasang pada Modul Sensor Cahaya seperti yang ditunjuk oleh tanda panah di bawah ini.

<p align="center" width="100%">

<img width="50%" src={require('./img/img5/tutorial-5-3-ldr-sensor-parts.png').default} alt="Arduino Light Sensor Parts"/>

</p>

Semakin terang cahaya yang mengenai komponen LDR, maka resistansinya akan semakin kecil. Semakin gelap cahaya yang mengenai komponen LDR, maka resistansinya akan semakin besar.

<p align="center" width="100%">

<img width="80%" src={require('./img/img5/tutorial-5-4-ldr-pins.png').default} alt="Arduino Light Sensor Pins"/>

</p>

Seperti yang ditunjukkan pada gambar di atas, Modul Sensor Cahaya memiliki 4 buah kaki yakni GND dan VCC sebagai masukan untuk daya listrik. Pin AO (Analog Output) untuk membaca nilai keluaran sinyal analog dan pin DO (Digital Output) untuk membaca nilai keluaran sinyal digital. Kita akan mempelajari perbedaan keluaran analog dan keluaran digital pada Tutorial 5 ini.

## Mulai Beraksi 🚀

Baik, sebelum mulai beraksi, pastikan teman-teman sudah membaca Prasyarat, Target Pelajaran, dan Komponen Yang Dibutuhkan ya.

Klik pada salah satu dari ketiga tombol di bawah ini untuk membuka Prasyarat, Target Pelajaran dan Komponen Yang Dibutuhkan.

<Tabs className="unique-tabs">
<TabItem value="Prasyarat 🔑">

- Sudah lolos Tutorial 4 - Serial Monitor dan Potensiometer
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

1. Baik, langkah pertama kita akan menyiapkan perangkat utama kita dahulu, yaitu Arduino Nano. Kemudian siapkan Modul Sensor Cahaya dan 3 buah kabel jumper.

   <p align="center" width="100%">

   <img width="80%" src={require('./img/img5/tutorial-5-4-ldr-pins.png').default} alt="Arduino Light Sensor Pins"/>

   </p>

2. Lihat gambar di atas sebagai petunjuk untuk membaca pin-pin yang ada pada Modul Sensor Cahaya. Kita akan menghubungkan pin-pin Modul Sensor Cahaya tersebut ke Arduino Nano dengan menggunakan kabel jumper seperti pada gambar Wiring Diagram di bawah ini.

   <p align="center" width="100%">

   <img width="100%" src={require('./img/img5/tutorial-5-5-wiring-diagram.png').default} alt="Arduino Light Sensor Wiring Diagram"/>

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

    <img width="100%" src={require('./img/img5/tutorial-5-6-wiring-diagram.jpg').default} alt="Arduino Light Sensor Wiring Diagram"/>

    </p>

Warna kabel yang digunakan bebas dan tak harus sama dengan gambar di atas. Namun yang harus diperhatikan, pastikan kaki Potensiometer terhubung ke posisi pin yang sama seperti pada gambar di atas. Gunakan Tabel Wiring Diagram untuk memastikannya. Pastikan pin VCC Sensor Cahaya terhubung ke pin V Arduino Nano dan pin GND Sensor Cahaya terhubung ke pin G Arduino Nano.

### Mengetik Program

3. Bukalah Arduino IDE, kemudian buatlah sketch baru. Beri sketch baru tersebut dengan nama TUTORIAL_5_SENSOR_CAHAYA_SERIAL_MONITOR dan simpan dalam folder TUTORIAL PROGRAMS yang telah kita buat pada Tutorial 1 sebelumnya. Jika terlupa bagaimana membuat nama sketch, silahkan buka kembali Tutorial 1 sebelumnya.

   <p align="center" width="100%">

   <img
   width="80%"
   src={require('./img/img5/tutorial-5-7-sketch.png').default}
   alt="Arduino IDE Sketch Program"
   />

   </p>

4. Karena kita memang akan mempelajari fungsi baru, yakni `digitalWrite()`, namun sebelumnya mari kita perdalam dahulu fungsi `analogWrite()` dengan menggunakan Sensor Cahaya. Karenanya kita akan menggunakan sketch program Tutorial 4 sebelumnya. Ketik program berikut pada sketch tersebut.

```arduino title="TUTORIAL_5_POTENTIOMETER_SERIAL_MONITOR.ino" showLineNumbers
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

### Mengkonfigurasi Arduino IDE

Sebelum mengupload program, sama seperti pada Tutorial 1, mari kita melakukan konfigurasi terlebih dahulu pada Arduino IDE.

7. Memilih Jenis Board

Pastikan jenis board yang digunakan sudah sesuai dengan settingan pada Arduino IDE dengan cara memilih opsi berikut secara berurutan Tools ➜ Board ➜ Arduino Nano atau perhatikan urutan tanda panah pada gambar di bawah ini. Disini kita memilih Arduino Nano karena kita menggunakan Arduino Nano.

    <p align="center" width="100%">

    <img width="100%" src={require('./img/img5/tutorial-5-8-select-board.png').default} alt="Arduino Light Sensor Wiring Diagram"/>

    </p>

8. Memilih Jenis Processor

Processor dalam bahasa Indonesia berarti Prosessor, atau Pemroses sebuah perintah, singkatnya seperti otak dari robot. Disini kita akan menentukan jenis Processor yang digunakan oleh Arduiino Nano, yaitu ATMega328P (Old Bootloader), dengan cara memilih opsi berikut secara berurutan Tools ➜ Processor ➜ ATmega328P (Old Bootloader). Atau ikuti urutan tanda panah pada gambar di bawah ini

    <p align="center" width="100%">

    <img width="80%" src={require('./img/img5/tutorial-5-9-select-processor.png').default} alt="Ultrasonic Sensors"/>

    </p>

9. Memilih Nomor Port

Nomor port untuk Arduino Nano pada tiap laptop/komputer dapat berbeda-beda. Pilihlah nomor port yang muncul pada pilihan yang tersedia di Arduino IDE. Lebih jelasnya, perhatikan gambar di bawah.

    <p align="center" width="100%">

    <img width="80%" src={require('./img/img5/tutorial-5-10-select-port.png').default} alt="Ultrasonic Sensors"/>

    </p>

### Mengupload Program

10. Setelah proses konfigurasi selesai seperti yang diperintahkan, lanjutkan dengan mengklik tombol upload <img src={require('./img/arduino-ide-tool-bar-upload.png').default} alt="Ultrasonic Sensors"/> pada Arduino IDE.

:::note Catatan
jika proses upload gagal, cobalah mengganti nomor PORT COMXX yang tersedia pada daftar pilihan nomor port pada langkah 3 di atas sampai proses upload berhasil.
:::

12. Jika proses upload berhasil, klik ikon “Serial Monitor” IDE seperti ditunjukkan oleh gambar disamping, <img src={require('./img/img3/arduino-ide-tool-bar-sermon.png').default} alt="Ultrasonic Sensors"/>, yang terletak pada pojok atas kanan Arduino.

Maka akan muncul window “Serial Monitor” seperti pada gambar di bawah ini.

Jika belum muncul teks tersebut, cobalah nyalakan centang pada “Autoscroll”, atur setinggan pada “Newline”, dan “9600 baud”.

    <p align="center" width="100%">

    <img width="20%" src={require('./img/img5/tutorial-5-11-sermon.png').default} alt="Ultrasonic Sensors"/>

    </p>

Pada window tersebut akan menampilkan angka yang merupakan nilai hasil pembacaa resistansi LDR.

Nilai resistansi yang terbaca akan berubah-ubah sesuai dengan kondisi pencahayaan pada ruangan tempat sensor cahaya berada.

Cobalah sorot bagian LDR dengan menggunakan cahaya senter dan amati perubahannya pada serial monitor.

Nilai resistansi yang muncul akan semakin kecil apabila semakin banyak cahaya yang diterimanya. Dan semakin besar jika cahaya semakin gelap.

<br/>

## Penjelasan Program

Sebenarnya, program yang kita gunakan untuk Tutorial 5 ini sama dengan program yang kita gunakan pada Tutorial 4 sebelumnya, sehingga penjelasan programnya akan sama persis. Namun, meskipun demikian, kita akan memberikan penjelasannya lagi secara singkat terlebih dahulu.

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

Pada baris 3 fungsi `setup()` terdapat fungsi `Serial.begin(9600)` yang memerintahkan Arduino Nano untuk memulai komunikasi untuk Serial Monitor.

Kemudian pada baris 8 terdapat variabel `nilaiSensor` bertipe integer dan perintah `analogRead()`. Perintah `analogRead()` akan digunakan untuk membaca nilai sinyal analog Sensor Cahaya yang terhubung pada pin A0. Nilai hasil pembacaan tersebut kemudian akan disimpan pada variabel `nilaiSensor`.

Nilai hasil pembacaan sinyal analog yang tersimpan pada variabel `nilaiSensor` tersebut kemudian ditampilkan pada Serial Monitor dengan perintah `Serial.println` yang terdapat pada baris 9.

Pada dasarnya, keseluruhan program yang digunakan sama persis seperti yang digunakan pada Tutorial 4 sebelumnya.

Oleh karenanya penjelasan program nya juga akan sama persis sehingga tidak akan dijelaskan kembali pada Tutorial 4 ini. Jika ingin mengingat kembali penjelasan program ini, teman-teman bisa menjumpainya lagi pada **[Penjelasan Program Tutorial 4 ](/docs/tutorial-arduino/newbies-level/tutorial-4-potensio-serial-monitor.md#penjelasan-program)**.

Seperti yang telah dikatakan sebelumnya, bahwa program di atas menggunakan progam yang sama dengan Tutorial 4 ketika membaca nilai resistansi Potensiometer. Yang membuatnya berbeda hanyalah komponen yang digunakan. Jika pada Tutorial 4 sebelumnya kita menggunakan Potensiometer, maka pada program ini menggunakan Sensor Cahaya.

Kali ini kita akan memodifikasi program di atas tadi dengan mengubah `analogRead()` pada baris 8 menjadi `digitalRead()` seperti yang diterangi pada kode program di bawah ini.

```arduino title="TUTORIAL_4_POTENTIOMETER_SERIAL_MONITOR.ino" showLineNumbers
void setup() {
  // put your setup code here, to run once:
Serial.begin(9600);
}

void loop() {
 // put your main code here, to run repeatedly:
 //highlight-start
 int nilaiSensor = digitalRead(A0);
 //highlight-end
 Serial.println(nilaiSensor);
 delay(1);
}
```

Kemudian cobalah teman-teman upload ke Arduino Nano dan lihat hasilnya pada Serial Monitor.

:::note Catatan
Sebelum mengupload sketch program baru ke Arduino Nano, pastikan teman-teman menutup window Serial Monitor terlebih dahulu jika masih terbuka.
:::

Hasil pada sketch tersebut akan menampilkan angka 0 ketika LDR disorot oleh cahaya senter dan akan menampilkan angka 1 ketika LDR tidak disorot oleh cahaya senter.

|                                                                                                                     Ketika LDR disorot cahaya senter                                                                                                                      |                                                                                                                    Ketika LDR tidak disorot cahaya senter                                                                                                                     |
| :-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| <img width="100%" src={require('./img/img5/tutorial-5-12-lighted.png').default} alt="Ultrasonic Sensors"/> akan menampilkan angka 0 pada Serial Monitor <img width="100%" src={require('./img/img5/tutorial-5-13-lighted-sermon.png').default} alt="Ultrasonic Sensors"/> | <img width="100%" src={require('./img/img5/tutorial-5-14-unlighted.png').default} alt="Ultrasonic Sensors"/> akan menampilkan angka 1 pada Serial Monitor <img width="100%" src={require('./img/img5/tutorial-5-15-unlighted-sermon.png').default} alt="Ultrasonic Sensors"/> |

Disinilah letak perbedaan perintah `digitalRead()` dan `analogRead()`. Perintah `analogRead()` akan membaca secara pasti perubahan variabel nilaisensor seperti 872, 921, 1023, 400, 12 dan seterusnya. Sedangkan perintah `digitalRead()` hanya akan membaca apabila nilai sensor `HIGH` (ditandai dengan angka 1) atau `LOW` (ditandai dengan angka 0).

Dengan kata lain, apabila bagian LDR pada Sensor Cahaya disorot oleh cahaya, maka nilai sensor akan menjadi `LOW` dan menampilkan angka 0 pada Serial Monitor. Sedangkan apabila bagian LDR tidak disorot oleh cahaya, maka nilai sensor akan menjadi `HIGH` dan menampilkan angka 1 pada Serial Monitor.

Perintah `digitalRead()` hanya akan menampilkan hasil berupa angka 1 atau angka 0 saja pada Serial Monitor. Sedangkan perintah `analogRead()` bisa menampilkan berapapun angka yang akan diberikan oleh Sensor Cahaya.

<br/>

## Tantangan Tutorial 5

Selanjutnya kita akan masuk pada topik Tantangan 5.

### Tantangan 1

Pada Tantangan 1 Tutorial 5 ini, kita akan belajar bagaimana mengatur sensitivitas sensor. Seperti telah disebutkan sebelumnya pada Pendahuluan, Sensor Cahaya memiliki komponen yang bernama Trimpot. Trimpot ini memiliki bentuk seperti tanda plus yang dapat diputar dengan menggunakan obeng plus.

<p align="center" width="100%">

<img width="50%" src={require('./img/img5/tutorial-5-3-ldr-sensor-parts.png').default} alt="Arduino Light Sensor Parts"/>

</p>

Trimpot akan berguna untuk mengatur ambang batas cahaya normal sekitar. Ambang batas cahaya normal adalah tingkat kecerahan cahaya yang bersifat tetap dan tidak berubah-ubah di sekitar Sensor Cahaya.

Kita bisa mengatur ambang batas cahaya normal. Apabila kita memutar Trimpot searah dengan jarum jam, maka sensitivitas/kepekaan sensor akan meningkat. Sedangkan apabila kita memutar Trimpot berlawanan dengan jarum jam, maka sensitivitas/kepekaan sensor akan menurun.

<p align="center" width="100%">

<img width="80%" src={require('./img/img5/tutorial-5-4-ldr-pins.png').default} alt="Arduino Light Sensor Pins"/>

</p>

Sebelum kita memulai Tantangan 2, perhatikan kembali bahwa terdapat 2 pin output pada Sensor LDR, yakni pin **AO** dan **DO**. Pin **AO** merupakan singkatan dari pin Analog Output, sedangkan pin **DO** merupakan singkatan dari Digital Output.

Untuk mengetahui secara pasti intensitas atau tingkat kecerahan cahaya dalam suatu ruangan, kita akan menggunakan pin AO atau Analog Output sehingga kita bisa menampilkan angka yang bervariasi dari 0-1023 pada Serial Monitor. Dimana nilai 0 merupakan nilai terendah dan nilai 1023 merupakan nilai tertinggi yang bisa ditampilkan pada Serial Monitor.

Sedangkan kalau kita akan menggunakannya hanya untuk mengetahui apakah ada keberadaan cahaya atau tidak, kita akan menggunakan pin Digital Output yang akan berlogika `LOW` atau menampilkan angka 0 pada Serial Monitor ketika mendeteksi keberadaan cahaya, dan akan berlogika `HIGH` atau menampilkan angka 1 pada Serial Monitor ketika tidak mendeteksi keberadaan cahaya.

Pada Tantangan 1 ini, pertama kali kita akan menggunakan rangkaian komponen yang digunakan pada awal Tutorial #5 ini. Agar teman-teman tidak repot mencarinya kembali ke atas, kita akan menunjukkannya di bawah.

<p align="center" width="100%">

<img width="100%" src={require('./img/img5/tutorial-5-5-wiring-diagram.png').default} alt="Arduino Light Sensor Wiring Diagram"/>

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

Sketch Program di bawah ini pada dasarnya sama seperti yang telah dijelaskan pada penjelasan di atas. Hanya saja, kali ini kita akan menggunakan perintah `analogRead()` pada baris 8 untuk membaca nilai sinyal pada pin A0. Ketik dan upload lah program di bawah ini. Lihat hasilnya pada Serial Monitor.

```arduino title="TUTORIAL_4_POTENTIOMETER_SERIAL_MONITOR.ino" showLineNumbers
void setup() {
  // put your setup code here, to run once:
Serial.begin(9600);
}

void loop() {
 // put your main code here, to run repeatedly:
 //highlight-start
 int nilaiSensor = analogRead(A0);
 //highlight-end
 Serial.println(nilaiSensor);
 delay(1);
}
```

Nilai yang muncul pada Serial Monitor adalah nilai resistansi sensor ketika terkena lampu ruangan yang sedang menyala seperti ditunjukkan oleh gambar di bawah berada pada nilai 700-an. Kondisi cahaya ruangan saat ini akan kita anggap sebagai kondisi cahaya normal dan memiliki nilai 700-an pada kondisi normal sesuai yang tampil pada Serial Monitor.

:::note Catatan
Perlu diingat, nilai yang muncul pada Tantangan 1 ini bisa berbeda dengan yang teman-teman dapatkan karena kondisi cahaya ruangan kita yang berbeda-beda. Jadi tidak perlu khawatir jika mendapatkan nilai yang berbeda dengan gambar di bawah ini.
:::

<p align="center" width="100%">

<img width="80%" src={require('./img/img5/tutorial-5-16-challenge-1.png').default} alt="Arduino Light Sensor Wiring Diagram"/>

</p>

Kemudian, dengan kondisi cahaya ruangan yang sama dan tetap, putarlah Trimpot pada Sensor LDR menggunakan obeng plus secara perlahan agar tidak merusak komponen. Amati apakah ada perubahan nilai yang muncul pada Serial Monitor.

Setelah teman-teman putar baik searah jarum jam maupun berlawanan jarum jam, nilai yang muncul pada Serial Monitor tidak berubah, bukan? Alias tetap pada nilai yang sama dengan yang sebelumnya teman-teman dapatkan, bukan?

Hal ini karena putaran Trimpot tidak mempengaruhi hasil nilai pembacaan sensor. Melainkan hanya mempengaruhi batas ambang normal cahaya. Batas ambang normal cahaya adalah batas yang menentukan kapan lampu indikator pada Sensor LDR menyala dan kapan lampu indikator pada Sensor LDR padam berdasarkan tingkat kecerahan cahaya yang mengenai Sensor Cahaya.

Lampu indikator Sensor LDR ditunjukkan oleh panah nomor 2 pada gambar di bawah yang bertuliskan DO-LED. Lampu indikator ini akan membantu kita kapan kita harus berhenti memutar Trimpot pada Sensor LDR.

<p align="center" width="100%">

<img width="80%" src={require('./img/img5/tutorial-5-17-challenge-1.png').default} alt="Arduino Light Sensor Wiring Diagram"/>

</p>

Sebagai contoh, apabila kita mendapatkan nilai yang tetap dan tidak berubah sebesar 700-an pada Serial Monitor. Maka nilai tersebut akan dianggap sebagai batas ambang normal. Yakni kondisi dimana tingkat kecerahan ruangan di sekitar sensor dianggap normal.

Sedangkan jika kita melihat lampu indikator DO-LED menyala, meskipun nilai yang muncul pada Serial Monitor sudah berada pada ambang batas normal sebesar 700-an, maka kita harus memutar Trimpot pada Sensor LED berlawanan arah jarum jam secara perlahan-lahan dan berhenti memutarnya tepat ketika lampu indikator DO-LED telah padam.

Kemudian apabila kita menyorot Sensor LDR dengan senter, atau dengan mengarahkan pada cahaya yang lebih terang dari ruangan sekitar, lampu indikator DO-LED akan menyala. Apabila hal ini telah berhasil, maka dapat dikatakan kita telah mengatur ambang batas normal cahaya.

Kita akan belajar bagaimana melakukan hal tersebut di Tantangan 1 ini.

Berikut petunjuk bagaimana kita akan mengatur ambang batas normal Sensor Cahaya disertai disertai foto.

1. Posisikan Sensor Cahaya seperti pada gambar di bawah. Kita akan menganggap tingkat kecerahan cahaya pada ruangan sekitar sensor saat ini berada pada kondisi normal. Perhatikan juga bahwa lampu DO-LED sedang menyala.

   <p align="center" width="100%">

   <img width="80%" src={require('./img/img5/tutorial-5-18-challenge-1.png').default} alt="Arduino Light Sensor Wiring Diagram"/>

   </p>

2. Kemudian dengan menggunakan obeng plus, putarlah Trimpot berlawanan jarum jam ke kiri. Memutar trimpot berlawanan arah jarum jam akan menurunkan ambang batas sensor, sedangkan memutar trimpot searah jarum jam akan menaikkan ambang batas sensor.

   <p align="center" width="100%">

   <img width="80%" src={require('./img/img5/tutorial-5-19-challenge-1.png').default} alt="Arduino Light Sensor Wiring Diagram"/>

   </p>

   Semakin tinggi ambang batas sensor, maka akan semakin mudah lampu DO-LED menyala dengan cahaya sekecil apapun. Sedangkan semakin rendah ambang batas sensor, maka akan semakin sulit lampu DO-LED menyala sehingga dibutuhkan cahaya yang sangat terang untuk menyalakan lampu DO-LED.

3. Putarlah Trimpot secara perlahan berlawanan arah jarum jam ke kiri sedikit demi sedikit sampai lampu indikator DO-LED padam.

   <p align="center" width="100%">

   <img width="80%" src={require('./img/img5/tutorial-5-20-challenge-1.png').default} alt="Arduino Light Sensor Wiring Diagram"/>

   </p>

4. Setelah lampu indikator DO-LED padam, kini ambang batas normal Sensor Cahaya telah diatur. Lampu indikator DO-LED sekarang hanya akan menyala apabila mendapat cahaya yang lebih terang dari cahaya ruangan sekitar Sensor Cahaya saat ini.

   <p align="center" width="100%">

   <img width="80%" src={require('./img/img5/tutorial-5-21-challenge-1.png').default} alt="Arduino Light Sensor Wiring Diagram"/>

   </p>

<br/>

### Tantangan 2

Setelah mengetahui bagaimana mengatur ambang batas cahaya normal, kita akan mencoba menyorot Sensor Cahaya dengan cahaya yang lebih terang dari cahaya ruangan sekitar Sensor Cahaya. Sebelumnya pada Tantangan 1 kita telah mengatur ambang batas cahaya normal. Yakni lampu indikator DO-LED tidak akan menyala apabila tidak terkena cahaya yang lebih terang dari cahaya ruangan sekitar Sensor Cahaya saat ini.

Sekarang kita akan menguji apakah ambang batas normal tersebut sudah sesuai dengan yang kita inginkan atau tidak. Pertama siapkanlah dahulu sumber cahaya seperti senter atau flashlight dari smartphone teman-teman dan ikuti langkah-langkah berikut:

1. Sorot cahaya senter/flashlight smartphone teman-teman mendekati kepala Sensor Cahaya, tidak harus tepat di atas kepala Sensor Cahaya, namun cukup di dekatnya saja seperti pada gambar di bawah.

   <p align="center" width="100%">

   <img width="50%" src={require('./img/img5/tutorial-5-22-challenge-2.png').default} alt="Arduino Light Sensor Wiring Diagram"/>

   </p>

   Pada gambar di atas, menunjukkan bahwa lingkaran cahaya senter, meskipun belum mengenai kepala Sensor Cahaya, lampu indikator DO-LED sudah menyala. Hal ini terjadi karena ambang batas sensor cahaya masih tinggi. Kita tidak menginginkan hal ini.

2. Untuk mengatasinya, kita akan tetap memposisikan lingkaran cahaya senter tetap berada pada tempat sebelumnya seperti pada gambar di bawah ini. Sambil memutar Trimpot pada Sensor Cahaya dengan menggunakan obeng plus berlawanan arah jarum jam ke kiri. Putarlah Trimpot tersebut secara perlahan-lahan sampai lampu indikator DO-LED padam.
   <p align="center" width="100%">

   <img width="50%" src={require('./img/img5/tutorial-5-23-challenge-2.png').default} alt="Arduino Light Sensor Wiring Diagram"/>

   </p>

3. Apabila lampu indikator DO-LED telah padam meskipun lingkaran cahaya masih tetap berada di tempat yang sama seperti sebelumnya, hentikan memutar Trimpot pada Sensor Cahaya. Hal ini menandakan bahwa kita telah berhasil mengatur ambang batas normal Sensor Cahaya dengan lebih baik.
   <p align="center" width="100%">

   <img width="50%" src={require('./img/img5/tutorial-5-24-challenge-2.png').default} alt="Arduino Light Sensor Wiring Diagram"/>

   </p>

4. Sekarang kita akan mendapati lampu indikator DO-LED pada Sensor Cahaya tidak akan menyala meskipun lingkaran cahaya senter belum berada berada di atas LDR dan belum tepat berada di atas LDR.
   <p align="center" width="100%">

   <img width="50%" src={require('./img/img5/tutorial-5-25-challenge-2.png').default} alt="Arduino Light Sensor Wiring Diagram"/>

   </p>

5. Kemudian cobalah pindahkan lingkaran cahaya tepat di atas kepala Sensor Cahaya dengan menyorot LDR langsung seperti ditunjukkan oleh gambar di bawah.
   <p align="center" width="100%">

   <img width="50%" src={require('./img/img5/tutorial-5-26-challenge-2.png').default} alt="Arduino Light Sensor Wiring Diagram"/>

   </p>

Apabila teman-teman berhasil menyalakan lampu indikator dan memadamkan lampu indikator dengan posisi lampu senter seperti pada gambar langkah 4 dan 5 di atas, maka teman-teman telah berhasil melewati semua tantangan.

<!--
<br/>

### Tantangan 3

Kita dapat menggunakan barisan pin analog pada Arduino Nano dari A0-A7 untuk membaca sinyal dengan menggunakan perintah `analogread()` maupun `digitalRead()`. Namun pada barisan pin digital Arduino Nano, kita hanya bisa membaca sinyal dengan menggunakan perintah `digitalRead()` saja.

Untuk menyegarkan ingatan teman-teman, gambar dibawah ini menunjukkan mana pin digital Arduino Nano dan mana pin analog Arduino Nano. Panah merah menunjukkan barisan pin digital Arduino Nano dan panah biru menunjukkan barisan pin analog Arduino Nano.

<p align="center" width="100%">

<img width="50%" src={require('./img/img5/tutorial-5-27-challenge-3.png').default} alt="Arduino Light Sensor Wiring Diagram"/>

</p>

Untuk membuktikan bahwa pin digital hanya bisa membaca sinyal dengan perintah `digitalRead()`, cobalah hubungkan pin AO (Analog Output) Sensor Cahaya pada pin digital 4 Arduino Nano Expansion Board.

<p align="center" width="100%">

<img width="100%" src={require('./img/img5/tutorial-5-28-challenge-3.png').default} alt="Arduino Light Sensor Wiring Diagram"/>

</p>

Jika gambar Wiring Diagram di atas kurang jelas, teman-teman bisa gunakan tabel Wiring Diagram di bawah ini.

| Sensor Cahaya | Arduino Nano Expansion Board |
| :-----------: | :--------------------------: |
|    Pin AO     |            Pin 4             |
|    Pin GND    |            Pin G             |
|    Pin VCC    |            Pin V             |

:::danger Peringatan
Sebelum menyalakan Arduino Nano, harap periksa kembali rangkaiannya. Apakah sudah sama dengan Wiring Diagram?

Periksa kembali posisi pemasangan kaki-kaki. Diharapkan agar tidak terbalik dan sesuai dengan keterangan pin agar tidak merusak komponen.
:::

Kemudian ketik dan upload program sketch berikut. Kemudian perhatikan hasilnya pada Serial Monitor.

```arduino title="TUTORIAL_4_POTENTIOMETER_SERIAL_MONITOR.ino" showLineNumbers
void setup() {
  // put your setup code here, to run once:
Serial.begin(9600);
}

void loop() {
 // put your main code here, to run repeatedly:
 int nilaiSensor = analogRead(4);
 Serial.println(nilaiSensor);
 delay(1);
}
```

Teman-teman akan memperhatikan bahwa nilai hasil pembacaan pada pin digital 4 tidak akan berubah dan tetap berkisar pada angka 200 hingga 300 meskipun kita telah menyorot sensor cahaya menggunakan senter seperti ditunjukkan pada gambar Serial Monitor di bawah. Hal ini karena pin digital pada Arduino Nano tidak dapat membaca sinyal analog dari pin AO Sensor Cahaya.

<p align="center" width="100%">

<img width="100%" src={require('./img/img5/tutorial-5-29-challenge-3.png').default} alt="Arduino Light Sensor Wiring Diagram"/>

</p>

Kemudian cobalah mengganti perintah `analogRead()` pada baris 8 sketch di atas menjadi `digitalRead()` seperti pada gambar di bawah ini yang telah diubah pada baris 8.

```arduino title="TUTORIAL_4_POTENTIOMETER_SERIAL_MONITOR.ino" showLineNumbers
void setup() {
  // put your setup code here, to run once:
Serial.begin(9600);
}

void loop() {
 // put your main code here, to run repeatedly:
 //highlight-start
 int nilaiSensor = digitalRead(4);
 //highlight-end
 Serial.println(nilaiSensor);
 delay(1);
}
```

Upload dan perhatikan hasilnya pada Serial Monitor dengan sorotan cahaya senter.

Sekarang pada Serial Monitor akan menampilkan angka 0 ketika disorot oleh cahaya senter sehingga resistansinya dianggap rendah dan dapat menyalakan lampu indikator pada sensor. Dan akan menampilkan angka 1 ketika tidak disorot oleh cahaya senter sehingga resistansinya dianggap tinggi dan menyebabkan lampu indikator pada sensor menjadi padam.

Dengan kata lain, apabila kita ingin membaca sinyal digital dari pin DO Sensor Cahaya menggunakan pin digital pada Arduino Nano, kita harus menggunakan perintah `digitalRead()`. -->
