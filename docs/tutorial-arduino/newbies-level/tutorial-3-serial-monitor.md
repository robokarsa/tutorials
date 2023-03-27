---
sidebar_position: 4
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Tutorial 3 - Serial Monitor Arduino IDE 💻

## Apa itu Serial Monitor?

Tahukah teman-teman, kalau Arduino IDE memiliki fitur yang bisa kita gunakan agar Arduino IDE menampilkan informasi program yang sedang dieksekusi atau dijalankan oleh Arduino Nano.

Nama fitur tersebut adalah Serial Monitor.

<p align="center" width="100%">

<img width="80%" src={require('./img/img3/tutorial-3-arduino-ide-serial-monitor.png').default} alt="Ultrasonic Sensors"/>

</p>

Apa itu Serial Monitor? Bayangkan smartphone/laptop/komputer yang teman-teman gunakan sekarang. Kesamaan Arduino Nano dengan smartphone/laptop/komputer adalah sama-sama memiliki komponen yang disebut chip. Chip ini berguna seperti otak untuk memproses semua informasi, perintah, dan data yang diberikan pengguna.

<p align="center" width="100%">

<img width="80%" src={require('./img/img3/tutorial-3-arduino-nano-and-xiaomi-chips.png').default} alt="Ultrasonic Sensors"/>

</p>

Namun perbedaannya adalah smartphone/laptop/komputer memiliki layar untuk menampilkan informasi yang sedang diproses oleh otak nya. Sedangkan Arduino Nano tidak memiliki layar tersebut.

Oleh karenanya, dibutuhkan fitur agar laptop/komputer dapat membaca dan menampilkan informasi yang sedang diproses oleh Arduino Nano sehingga teman-teman bisa mengetahui informasi apa yang sedang diproses oleh Arduino Nano. Fitur tersebut disebut sebagai Serial Monitor.

Singkatnya, Serial Monitor adalah fitur yang memungkinkan Arduino Nano mengirimkan data berupa angka, teks, grafik kepada laptop/komputer agar dapat dibaca oleh pengguna melalui Arduino IDE.

Serial Monitor ini akan berguna bagi teman-teman nantinya untuk mengetahui informasi seperti nilai suhu ruangan, nilai resistansi potensiometer, jarak suatu benda, dan lainnya.

Namun sebelumnya, kita harus mempelajari dasar-dasar nya terlebih dahulu. Pada Tutorial #3 ini kita hanya menggunakan Arduino Nano Expansion Board, kabel, dan laptop/komputer.

## Mulai Beraksi 🚀

Baik, sebelum mulai beraksi, pastikan teman-teman sudah membaca Prasyarat, Target Pelajaran, dan Komponen Yang Dibutuhkan ya.

Klik pada salah satu dari ketiga tombol di bawah ini untuk membuka Prasyarat, Target Pelajaran dan Komponen Yang Dibutuhkan.

<Tabs className="unique-tabs">
<TabItem value="Prasyarat 🔑">

- Sudah lolos Tutorial 2 - Mengedipkan Mini Traffic Light Module 🚦
- Sudah mempelajari Arduino Nano Expansion Board pada materi **[Arduino Nano Expansion Board](/docs/tutorial-arduino/arduino-hardware.md#arduino-nano-expansion-board)**

Kalau teman-teman merasa belum memenuhi prasyarat yang dibutuhkan, diharapkan untuk membaca dan memenuhinya terlebih dahulu.

</TabItem>

<TabItem value="Target Pelajaran 🎯">

- Memahami alur eksekusi program
- Memahami komunikasi serial
- Mengenali perintah mencetak data dan menampilkan data pada Serial Monitor

</TabItem>

<TabItem value="Komponen Yang Dibutuhkan 🛠">

- 1 x Arduino Nano
- 1 x Kabel USB Arduino Nano
- 1 x Komputer/Laptop

</TabItem>
</Tabs>

:::caution Perhatian

Penting untuk memperhatikan setiap langkah-langkah yang diberikan dan tidak melakukan apapun diluar perintah langkah yang diberikan.

Kenapa? Hal ini untuk mencegah kerusakan yang tidak diinginkan pada komponen apabila bertindak di luar langkah pelajaran yang diberikan dan tidak mengetahui dengan pasti apa yang teman-teman lakukan.

:::

### Menyiapkan Arduino Nano

Baik, langkah pertama kita akan menyiapkan perangkat utama kita dahulu, yaitu Arduino Nano. Ikuti langkah-langkahnya.

1. Siapkan Arduino Nano dan kabel USB Arduino Nano seperti pada gambar di bawah.

<p align="center" width="100%">

<img width="40%" src={require('./img/img2/tutorial-2-arduino-nano-board.png').default} alt="Ultrasonic Sensors"/>
&nbsp; &nbsp; &nbsp;
<img width="40%" src={require('./img/img2/tutorial-2-arduino-nano-usb-cables.png').default} alt="Ultrasonic Sensors"/>

</p>

2. Hubungkan Kabel USB Arduino Nano pada port USB Arduino Nano seperti ditunjukkan oleh gambar di bawah.

<p align="center" width="100%">
<img width="45%" src={require('./img/arduino-nano-usb-connected.png').default} alt="Jumper Cables"/>
</p>

3. Hubungkan ujung kabel lainnya pada Port USB Laptop/Komputer seperti pada gambar di bawah.

<p align="center" width="100%">

<img
width="45%"
src={require('./img/arduino-nano-usb-laptop-connected.png').default}
alt="Ultrasonic Sensors"
/>

</p>

Setelah Arduino Nano terhubung dengan laptop, seharusnya Arduino Nano teman-teman akan menyala. Kemudian lanjut ke langkah, yaitu mengetik program.

### Mengetik Program

1. Bukalah Arduino IDE, kemudian buatlah sketch baru. Simpan sketch baru tersebut dengan nama TUTORIAL_3_SERIAL_MONITOR dan simpan dalam folder TUTORIAL PROGRAMS yang telah kita buat pada Tutorial 1 sebelumnya.

<p align="center" width="100%">

<img
width="50%"
src={require('./img/img3/tutorial-3-arduino-ide-new-sketch.png').default}
alt="Ultrasonic Sensors"
/>

</p>

2. Kemudian ketik program berikut pada sketch tersebut.

```arduino title="TUTORIAL_2_TRAFFIC_LIGHT_LED_MODULE.ino" showLineNumbers
void setup() {
  // put your setup code here, to run once:
Serial.begin(9600);

}

void loop() {
  // put your main code here, to run repeatedly:
Serial.println("Hello World");
delay(1000);
}
```

3. Periksa kembali ketikan sketch program. Pastikan agar ketikan sketch program sama persis seperti diminta agar tidak mengalami error saat compiling.

4. Jika sudah selesai mengetik program, cobalah memeriksa apakah ketikan Anda sudah benar atau belum dengan cara menekan tombol verify atau ikon di samping 👉 <img src={require('./img/arduino-ide-tool-bar-verify.png').default} alt="Ultrasonic Sensors"/>. Jika proses verify selesai dan tidak ada error, information bar akan menunjukkan “Done compiling” pada information bar Arduino IDE.

<p align="center" width="100%">

<img
width="80%"
src={require('./img/img3/tutorial-3-arduino-ide-sketch-done-compiling.png').default}
alt="Ultrasonic Sensors"
/>

</p>

### Mengkonfigurasi Arduino IDE

Sebelum mengupload program, sama seperti pada Tutorial 1, mari kita melakukan konfigurasi terlebih dahulu pada Arduino IDE.

5. Memilih Jenis Board

Pastikan jenis board yang digunakan sudah sesuai dengan settingan pada Arduino IDE dengan cara memilih opsi berikut secara berurutan Tools ➜ Board ➜ Arduino Nano atau perhatikan urutan tanda panah pada gambar di bawah ini. Disini kita memilih Arduino Nano karena kita menggunakan Arduino Nano.

<p align="center" width="100%">

<img width="80%" src={require('./img/img3/tutorial-3-arduino-ide-choose-board.png').default} alt="Ultrasonic Sensors"/>

</p>

6. Memilih Jenis Processor

Processor dalam bahasa Indonesia berarti Prosessor, atau Pemroses sebuah perintah, singkatnya seperti otak dari robot. Disini kita akan menentukan jenis Processor yang digunakan oleh Arduiino Nano, yaitu ATMega328P (Old Bootloader), dengan cara memilih opsi berikut secara berurutan Tools ➜ Processor ➜ ATmega328P (Old Bootloader). Atau ikuti urutan tanda panah pada gambar di bawah ini

<p align="center" width="100%">

<img width="80%" src={require('./img/img3/tutorial-3-arduino-ide-choose-processor.png').default} alt="Ultrasonic Sensors"/>

</p>

7. Memilih Nomor Port

Nomor port untuk Arduino Nano pada tiap laptop/komputer dapat berbeda-beda. Pilihlah nomor port yang muncul pada pilihan yang tersedia di Arduino IDE. Lebih jelasnya, perhatikan gambar di bawah.

<p align="center" width="100%">

<img width="80%" src={require('./img/img3/tutorial-3-arduino-ide-choose-port.png').default} alt="Ultrasonic Sensors"/>

</p>

### Mengupload Program

Setelah proses verifikasi teman-teman sudah berhasil dan konfigurasi Arduino IDE sudah selesai, saatnya kita mengupload program. Mengupload Program sama seperti kita menulis sebuah surat lalu mengantarkan surat tersebut kepada orang lain. Ketika kita sudah selesai menulis atau mengetik program, kita mengantarkan program tersebut ke Arduino Nano. Proses mengantarkan program tersebut disebut sebagai "Upload".

23. Setelah proses konfigurasi selesai seperti yang diperintahkan, lanjutkan dengan mengklik tombol upload <img src={require('./img/arduino-ide-tool-bar-upload.png').default} alt="Ultrasonic Sensors"/> pada Arduino IDE.

<p align="center" width="100%">

<img width="80%" src={require('./img/img3/tutorial-3-arduino-ide-upload.png').default} alt="Ultrasonic Sensors"/>

</p>

24. Tunggulah beberapa. Setelah proses upload selesai, information bar akan menunjukkan pesan “Done uploading” yang berarti proses upload telah selesai

<p align="center" width="100%">

<img width="80%" src={require('./img/img3/tutorial-3-arduino-ide-upload-done.png').default} alt="Ultrasonic Sensors"/>

</p>

Jika proses upload berhasil, klik ikon “Serial Monitor” IDE seperti ditunjukkan oleh gambar disamping, <img src={require('./img/img3/arduino-ide-tool-bar-sermon.png').default} alt="Ultrasonic Sensors"/>, yang terletak pada pojok atas kanan Arduino.

Maka akan muncul window baru yang disebut sebagai “Serial Monitor” seperti pada gambar di bawah ini.

<p align="center" width="100%">

<img width="80%" src={require('./img/img3/tutorial-3-arduino-ide-serial-monitor.png').default} alt="Ultrasonic Sensors"/>

</p>

Pada window tersebut akan menampilkan teks “Hello World” seperti yang telah dimasukkan pada sketch program sebelumnya.

Jika belum muncul teks tersebut, cobalah nyalakan centang pada “Autoscroll”, atur setinggan pada “Newline”, dan “9600 baud” seperti yang ditunjukkan pada gambar di bawah ini.

<p align="center" width="100%">

<img width="80%" src={require('./img/img3/tutorial-3-arduino-ide-serial-monitor-config.png').default} alt="Ultrasonic Sensors"/>

</p>

Jika sudah berhasil, saatnya kita masuk ke topik Penjelasan Program.

<br/>

## Penjelasan Program

Persiapkan diri nya ya, teman-teman. Karena seperti biasa, teman-teman akan diberi Tantangan di akhir penjelasan.

Sebagaimana telah dijelaskan sebelumnya, Serial Monitor berfungsi untuk menyampaikan apa yang diproses oleh Arduino Nano kepada pengguna melalui layar laptop/komputer.

<p align="center" width="100%">

<img width="80%" src={require('./img/img3/tutorial-3-arduino-ide-serial-monitor.png').default} alt="Ultrasonic Sensors"/>

</p>

```arduino title="TUTORIAL_2_TRAFFIC_LIGHT_LED_MODULE.ino" showLineNumbers
void setup() {
  // put your setup code here, to run once:
//highlight-start
Serial.begin(9600);
//highlight-end
}

void loop() {
  // put your main code here, to run repeatedly:
Serial.println("Hello World");
delay(1000);
}
```

Sketch program di atas memang tampak sederhana. Terdapat fungsi `setup()` dan `setup()` sebagaimana biasanya.

Namun pada baris 3 fungsi `setup()` terdapat fungsi `Serial.begin(9600)`. Perintah tersebut memiliki 3 parameter yakni `Serial` , `begin` , dan `9600` . Fungsi `Serial.begin(9600)` harus dijalankan dalam fungsi `setup()`.

Parameter pertama yakni, `Serial`, merupakan nama jalur komunikasi yang digunakan untuk membedakan jalur komunikasi yang kita gunakan. Pada Arduino Nano, ada dua jenis jalur komunikasi yang bisa kita gunakan, yaitu `Serial` yang menggunakan pin TX dan RX serta `I2C` yang menggunakan pin SCL dan SDA Arduino Nano. Di level Advanced kita akan menemukan penggunaan `I2C` ini. Namun untuk saat ini, mari kita fokus ke `Serial` dahulu.

Pada Arduino Mega terdapat parameter `Serial`, `Serial1`, `Serial2`, hingga `Serial3` karena memiliki banyak jalur komunikasi. Sedangkan pada Arduino Nano hanya memiliki satu buah jalur komunikasi saja dengan nama `Serial`.

Apabila menggunakan nama `Serial1`, `Serial2`, dan `Serial3` pada Arduino Nano, maka data tidak akan terbaca pada window Serial Monitor.

Parameter angka `9600` merupakan kecepatan pertukaran data antara Arduino Nano dengan laptop/komputer dalam satuan bps (bit per second). Kita akan membahas lebih lanjut mengenai bps ini pada pelajaran lain.

Parameter `begin` , yang menggunakan kata dari bahasa Inggris dengan arti dalam bahasa Indonesia yang berarti “mulai” merupakan perintah agar kita memberitahu kepada Arduino Nano bahwa kita akan memulai pertukaran data/komunikasi serial dari Arduino Nano ke laptop/komputer.

Maka, dapat diringkas fungsi `Serial.begin(9600)` adalah untuk memerintahkan Arduino Nano agar memulai pertukaran data/komunikasi serial dengan laptop/komputer pada kecepatan 9600 bps.

Apabila kita menggunakan kecepatan `9600` bps dalam program, maka kita harus mengatur settingan baud dengan 9600 juga pada Serial Monitor. Meskipun terdapat beragam kecepatan baud yang diberikan oleh window Serial Monitor, namun pada Arduino Nano menggunakan kecepatan baud 9600. Selain itu, data tidak akan terbaca pada Serial Monitor.

Selanjutnya kita akan masuk ke fungsi `loop()`.

```arduino title="TUTORIAL_2_TRAFFIC_LIGHT_LED_MODULE.ino" showLineNumbers
void setup() {
  // put your setup code here, to run once:
Serial.begin(9600);
}

void loop() {
  // put your main code here, to run repeatedly:
//highlight-start
Serial.println("Hello World");
//highlight-end
delay(1000);
}
```

Pada fungsi `loop()`, pada baris 8 yang diterangi di atas, terdapat perintah `Serial.println("Hello World")`. Perintah ini memiliki tiga parameter, yakni `Serial` , `println` , `Hello World`.

Parameter `Serial` merupakan nama jalur komunikasi yang digunakan untuk mengidentifikasi jalur komunikasi mana yang sedang digunakan.

Jika pada fungsi `setup()` sebelumnya telah menggunakan nama `Serial1`, maka dalam fungsi `loop()` harus menggunakan nama `Serial1` pula. Hal ini biasanya hanya berlaku pada board Arduino yang memiliki lebih dari 1 jalur komunikasi seperti Arduino Mega.

Namun karena kita menggunakan Arduino Nano dan kita sudah mendekelarasikan nama `Serial` dalam fungsi `setup()`, maka kita harus menggunakan nama `Serial` juga dalam fungsi `loop()`.

Pada parameter `Hello World` merupakan isi dari parameter data. Artinya parameter data diisi dengan data yang ingin ditampilkan pada Serial Monitor. Dalam hal ini, teks `Hello World` adalah data yang ingin ditampilkan pada Serial Monitor. Kita bisa mengganti teks "Hello World" tersebut sesuai dengan teks yang kita inginkan.

Ingatlah kedepannya, bahwa untuk mencetak data berbentuk teks, kita harus menggunakan dua tanda kutip dan meletakkan teks yang ingin dicetak diletakkan diantara dua tanda kutip tersebut.

Kemudian pada parameter `println` merupakan perintah untuk mencetak data yang disimpan dalam parameter data ke Serial Monitor, dalam hal ini adalah teks "Hello World" yang akan dicetak.

Pada parameter mencetak terdapat dua versi, yakni println dan print . Perbedaan keduanya adalah, println akan mencetak data kemudian membuat baris baru di bawahnya. Sedangkan print akan mencetak data tanpa membuat baris baru di bawahnya.

Contoh:

|                                                           Dengan `println`                                                           |                                                           Dengan `print`                                                           |
| :----------------------------------------------------------------------------------------------------------------------------------: | :--------------------------------------------------------------------------------------------------------------------------------: |
| <img width="100%" src={require('./img/img3/tutorial-3-arduino-ide-hello-world-with-println.png').default} alt="Ultrasonic Sensors"/> | <img width="100%" src={require('./img/img3/tutorial-3-arduino-ide-hello-world-with-print.png').default} alt="Ultrasonic Sensors"/> |

Kemudian pada baris 9 seperti yang diterangi di bawah, terdapat fungsi `delay` untuk menjeda selama 1000 milisekon (setara dengan 1 detik). Nilai pada delay dapat diatur sesuai kebutuhan baik cepat maupun lambat.

```arduino title="TUTORIAL_2_TRAFFIC_LIGHT_LED_MODULE.ino" showLineNumbers
void setup() {
  // put your setup code here, to run once:
Serial.begin(9600);
}

void loop() {
  // put your main code here, to run repeatedly:

Serial.println("Hello World");
//highlight-start
delay(1000);
//highlight-end
}
```

Setelah baris ke 9 di atas selesai dijalankan, alias Arduino Nano telah ditunda selama 1 detik, maka akan lanjut ke baris berikutnya, yakni baris 11.

Karena baris 11 di atas berisi tanda kurawal tutup `}` milik fungsi `loop()`, maka akan kembali lagi ke awal mula fungsi `loop()` pada baris 6. Begitu seterusnya sehingga akan membuat Serial Monitor mencetak teks "Hello World" secara berulang-ulang tiap 1 detik.

Itulah penjelasan program untuk Tutorial 3 kali ini. Mari kita masuk ke topik Tantangan.

## Tantangan Tutorial 3

### Tantangan 1

Seperti sebelumnya, hubungkan Arduino Nano ke Laptop/komputer menggunakan kabel USB.

Kemudian ketik dan upload sketch program di bawah.

```arduino title="TUTORIAL_2_TRAFFIC_LIGHT_LED_MODULE.ino" showLineNumbers
void setup() {
  // put your setup code here, to run once:
Serial.begin(9600);
}

void loop() {
  // put your main code here, to run repeatedly:

Serial.print("Nama Saya adalah:");
Serial.print("RoboKarsa");
delay(1000);
}
```

Jika telah selesai mengetik program, verify terlebih dahulu ketikan program teman-teman. Jika proses verify menunjukan “Done Compiling” pada information bar, maka upload program tersebut.

Jika proses upload berhasil, klik ikon “Serial Monitor” IDE seperti ditunjukkan oleh gambar disamping <img src={require('./img/img3/arduino-ide-tool-bar-sermon.png').default} alt="Ultrasonic Sensors"/> yang terletak pada pojok atas kanan Arduino .

Maka hasil running program nya akan menjadi seperti di bawah. Terlihat berantakan bukan?

<p align="center" width="100%">

<img width="80%" src={require('./img/img3/tutorial-3-challenges-1.png').default} alt="Ultrasonic Sensors"/>

</p>

Tantangan pertama untuk teman-teman adalah merapikannya agar lebih rapi menjadi seperti di bawah.

<p align="center" width="100%">

<img width="80%" src={require('./img/img3/tutorial-3-challenges-2.png').default} alt="Ultrasonic Sensors"/>

</p>

Ada petunjuk? Ada dong,, petunjuknya adalah,

Gunakan `println` pada salah satu baris programnya nya. Tebak `println` harus diletakkan pada baris 8 atau baris 9? Berhasil ga yah??

```arduino title="TUTORIAL_2_TRAFFIC_LIGHT_LED_MODULE.ino" showLineNumbers
void setup() {
  // put your setup code here, to run once:
Serial.begin(9600);
}

void loop() {
  // put your main code here, to run repeatedly:

//highlight-start
Serial.print("Nama Saya adalah:");
Serial.print("RoboKarsa");
//highlight-end
delay(1000);
}
```

Kalau berhasil, teman-teman hebat,, sudah sampai sejauh ini,,

Tapi masih belum rapi lho ya,, selanjutnya hasil Serial Monitor harus tampak seperti pada gambar di bawah ini:

<p align="center" width="100%">

<img width="80%" src={require('./img/img3/tutorial-3-challenges-3.png').default} alt="Ultrasonic Sensors"/>

</p>

Ada spasi diantara karakter titik dua dengan teks "RoboKarsa". Teman-teman harus membuat hasil Serial Monitor persis seperti itu,,

Ini nih petunjuk lagi,, beri spasi pada salah satu karakternya,, gitu aja deh,,

soalnya nanti keenakan kalau dikasi petunjuk melulu,, agar teman-teman mau mencoba brainstorming,,

### Tantangan 2

Selanjutnya, kita tantang teman-teman mencoba sketch program ini. Cobalah ketik kemudian upload upload.

```arduino title="TUTORIAL_2_TRAFFIC_LIGHT_LED_MODULE.ino" showLineNumbers
void setup() {
  // put your setup code here, to run once:
Serial.begin(9600);
}

void loop() {
  // put your main code here, to run repeatedly:
Serial.print("RoboKarsa");
delay(1000);
}
```

Kemudian buka Serial Monitor. Hasilnya akan seperti ditunjukkan oleh gambar di bawah.

<p align="center" width="100%">

<img width="80%" src={require('./img/img3/tutorial-3-challenges-4.png').default} alt="Ultrasonic Sensors"/>

</p>

Nah kalau kita semua program yang berada pada baris 8 dan 9 seperti yang diterangi di bawah dari fungsi `loop()`,

```arduino title="TUTORIAL_2_TRAFFIC_LIGHT_LED_MODULE.ino" showLineNumbers
void setup() {
  // put your setup code here, to run once:
Serial.begin(9600);
}

void loop() {
  // put your main code here, to run repeatedly:
//highlight-start
Serial.print("RoboKarsa");
delay(1000);
//highlight-end
}
```

ke fungsi `setup()` seperti sketch di bawah ini,

```arduino title="TUTORIAL_2_TRAFFIC_LIGHT_LED_MODULE.ino" showLineNumbers
void setup() {
  // put your setup code here, to run once:
Serial.begin(9600);

//highlight-start
Serial.print("RoboKarsa");
delay(1000);
//highlight-end
}

void loop() {
  // put your main code here, to run repeatedly:

}
```

Bagaimana hasilnya?

<p align="center" width="100%">

<img width="80%" src={require('./img/img3/tutorial-3-challenges-5.png').default} alt="Ultrasonic Sensors"/>

</p>

Loh, kok cuma sekali? Udah ditungguin lama, namun hanya satu teks "RoboKarsa" yang muncul??

Yap,, itu sebagai bukti bahwa semua sketch yang dijalankan dalam fungsi `setup()` itu hanya sekali saja. Sementara semua sketch yang dijalankan dalam fungsi `loop()` itu akan dijalankan terus menerus.

Agar teman-teman semakin paham saja perbedaan fungsi `setup()` dan `loop()` saja ya,,

Selanjutnya kalau kita ubah sketch program menjadi seperti di bawah ini:

```arduino title="TUTORIAL_2_TRAFFIC_LIGHT_LED_MODULE.ino" showLineNumbers
void setup() {
  // put your setup code here, to run once:
//highlight-start
Serial.print("RoboKarsa");
delay(1000);
//highlight-end

Serial.begin(9600);
}

void loop() {
  // put your main code here, to run repeatedly:

}
```

Kemudian cobalah upload dan lihat bagaimana hasilnya.

Tidak muncul apa-apa kan?

Kenapa kira-kira? Itu karena Arduino IDE menjalankan programnya secara berurutan dari atas ke bawah.

Jika kita memerintahkan untuk mencetak kata RoboKarsa pada baris 3, perintah tersebut memang berhasil dieksekusi oleh Arduino Nano.

Namun karena kita menuliskan perintah `Serial.begin(9600)` pada baris ke 5 Arduino Nano gagal menampilkan kata RoboKarsa.

Hal ini dikarenakan Arduino Nano belum memerintahkan untuk memulai pertukaran data antara Arduino Nano dengan laptop/komputer ketika baris 3 tersebut dieksekusi. Sehingga kata RoboKarsa tidak akan tampil ketika kita membuka Serial Monitor. Oleh karenanya, perintah Serial.begin(9600); harus diletakkan di awal sebelum perintah untuk mencetak kata RoboKarsa.

Jadi apa yang harus teman-teman lakukan? Cobalah perintahkan agar Arduino Nano memulai pertukaran data terlebih dahulu sebelum mulai mengeksekusi perintah untuk mencetak kata RoboKarsa. Caranya cukup dengan memindahkan perintah Serial.begin(9600); di awal fungsi `setup()`.

### Tantangan 3

Tantangan untuk Tutorial #3 apa lagi yaa,

Sepertinya itu saja Tantangan Tutorial 3 deh,,

Cobalah teman-teman berkreasi dan bermain teks ala-ala teman-teman seperti di bawah ini:

<p align="center" width="100%">

<img width="80%" src={require('./img/img3/tutorial-3-challenges-6.png').default} alt="Ultrasonic Sensors"/>

</p>

Coba upload deh salam/pesan nya teman-teman ke Instagram, jangan lupa tag RoboKarsa yaaa, biar kita repost hasil belajar teman-teman nanti.

Sekian untuk Tutorial 3 kali ini, sampai jumpa di pelajaran berikutnya, dan jangan lupa istirahat.
