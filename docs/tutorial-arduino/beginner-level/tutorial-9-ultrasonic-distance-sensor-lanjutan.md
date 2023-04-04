---
sidebar_position: 5
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Tutorial 9 - Sensor Jarak Ultrasonik Lanjutan

## Selayang Pandang

Pada Tutorial 8 sebelumnya, banyak hal yang telah kita pelajari. Seperti bagaimana menghitung jarak jika diketahui kecepatan suara ultrasonik dan waktu rambat suara ultrasonik, aturan urutan prioritas menggunakan tanda kurung, dan sebagainya.

Namun, tahukah teman-teman? Kita sebenarnya belum memenuhi seluruh materi yang ada dalam bahasa pemrograman. Kali ini kita akan belajar mengenai fungsi.

Benar, fungsi yang sering kita temui seperti fungsi `setup()`, fungsi `loop()`, fungsi `analogWrite()`, fungsi `digitalWrite()`, fungsi `analogRead()`, fungsi `digitalRead()`, dan terakhir, kita mempelajari fungsi `pulseIn()` untuk menghitung waktu rambat suara ultrasonik pada Tutorial 8 sebelumnya.

Tahukah teman-teman, semua fungsi yang disebutkan di atas adalah fungsi yang dibuat dan disediakan oleh Arduino IDE. Dan tahukah lagi teman-teman, bahwa kita bisa membuat fungsi kita sendiri.

Keuntungan dari membuat fungsi sendiri ini ada beragam. Seperti program kita menjadi lebih ringkas, lebih mudah memanggil fungsi untuk menjalankan perintah yang kita inginkan, dan lain sebagainya yang akan disebutkan ke depannya nanti.

Penasaran bagaimana caranya? Mari kita simak bersama.

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
- 1 x Sensor Jarak
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

2. Bukalah Arduino IDE, kemudian buatlah sketch baru. Beri sketch baru tersebut dengan nama TUTORIAL_9_SENSOR_JARAK_LANJUTAN dan simpan dalam folder **Program Tutorials** yang telah kita buat pada Tutorial 1 sebelumnya. Jika terlupa bagaimana membuat nama sketch, silahkan buka kembali Tutorial 1 sebelumnya.

3. Kemudian ketik program berikut pada sketch tersebut.

```arduino title="TUTORIAL_9_SENSOR_JARAK_LANJUTAN.ino" showLineNumbers
const int trigPin = 8;
const int echoPin = 9;

float jarak;

void setup() {
Serial.begin(9600);
pinMode(trigPin, OUTPUT);
pinMode(echoPin, INPUT);
}

void loop() {
jarak=ukurJarak();

Serial.print("Jarak: ");
Serial.println(jarak);

delay(100);
}

float ukurJarak(){
float distance = 0;

digitalWrite(trigPin, LOW);
delayMicroseconds(2);

digitalWrite(trigPin, HIGH);
delayMicroseconds(10);
digitalWrite(trigPin, LOW);

distance = ((pulseIn(echoPin, HIGH)) * 0.034) / 2;

return distance;
}
```

4. Setelah selesai mengetik program, jalankan proses verify. Dan apabila proses verify sudah berhasil, upload lah program tersebut ke Arduino Nano.

5. Setelah proses upload berhasil, bukalah Serial Monitor, dan amati perubahan nilai jaraknya apabila kita mendekatkan atau menjauhkan tangan kita dari Sensor Jarak.

<br/>

## Penjelasan Program

Sekarang kita akan menjelaskan bagaimana programnya berjalan.

```arduino title="TUTORIAL_9_SENSOR_JARAK_LANJUTAN.ino" showLineNumbers
const int trigPin = 8;
const int echoPin = 9;

float jarak;

void setup() {
Serial.begin(9600);
pinMode(trigPin, OUTPUT);
pinMode(echoPin, INPUT);
}

void loop() {
jarak=ukurJarak();

Serial.print("Jarak: ");
Serial.println(jarak);

delay(100);
}

float ukurJarak(){
float distance = 0;

digitalWrite(trigPin, LOW);
delayMicroseconds(2);

digitalWrite(trigPin, HIGH);
delayMicroseconds(10);
digitalWrite(trigPin, LOW);

distance = ((pulseIn(echoPin, HIGH)) * 0.034) / 2;

return distance;
}
```

Pada baris 1 dan 2, kita memiliki perintah untuk membuat variable `trigPin` dan variabel `echoPin`.

```arduino
const int trigPin = 8;
const int echoPin = 9;
```

Variabel `trigPin` akan menyimpan angka 8 karena pin Trigger pada Sensor Jarak terhubung pada pin digital nomor 8 pada Arduino Nano.

Kemudian variabel `echoPin` akan menyimpan angka 9 karena pin Echo pada Sensor Jarak terhubung pada pin digital nomor 9 pada Arduino Nano.

Kemudian pada baris 4, kita membuat variabel baru bernama `jarak` yang akan kita gunakan untuk menyimpan angka jarak benda/tangan kita dari depan sensor jarak. Kita bebas menamainya dengan nama apapun.

```arduino
float jarak;
```

Tipe data variabel `jarak` tersebut adalah `float`, karena kita ingin menyimpan bilangan angka desimal yang akan kita dapatkan nantinya. Karena bisa saja jarak yang kita dapatkan akan bernilai 10.21 Cm atau 12.32 Cm dan sebagainya.

Jika kita ingin menampilkan jarak yang berupa bilangan bulat saja seperti 10 cm atau 12 cm, maka kita harus mengganti `float` menjadi `int`, sehingga bilangan desimal dibelakang 10 atau 12 akan diabaikan.

Kemudian pada fungsi `setup()` terdapat perintah `Serial.begin()` untuk memulai komunikasi serial antara Arduino Nano dengan laptop/komputer kita serta perintah `pinMode()` untuk menugaskan pin `trigPin` sebagai pin `OUTPUT` dan menugaskan pin `echoPin` sebagai pin `INPUT`.

```arduino
void setup() {
Serial.begin(9600);
pinMode(trigPin, OUTPUT);
pinMode(echoPin, INPUT);
}
```

Selanjutnya, kita akan masuk ke dalam fungsi `loop()`.

Jika teman-teman perhatikan, hasil program di atas sama seperti pada program yang kita gunakan pada Tutorial 8 sebelumnya.

Namun, mengapa fungsi `loop()` yang kita gunakan pada Tutorial 9 ini lebih sedikit jika dibandingkan dengan fungsi `loop()` yang kita gunakan pada Tutorial 8 sebelumnya?

<Tabs className="unique-tabs">
<TabItem value="fungsi loop() Tutorial 9">

```arduino showLineNumbers
void loop() {
jarak=ukurJarak();

Serial.print("Jarak: ");
Serial.println(jarak);

delay(100);
}
```

</TabItem>

<TabItem value="fungsi loop() Tutorial 8">

```arduino showLineNumbers
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

</TabItem>
</Tabs>

Kita akan mengetahui jawabannya sebentar lagi. Namun kita ulas terlebih dahulu fungsi `loop()` milik Tutorial 9 ini. Fungsi `loop()` milik Tutorial 9 dimulai dari baris 12 karena tanda kurawal buka `{` berada pada baris 12 dan diakhiri pada baris 20 karena tanda kurawal tutup `}` berada pada baris 19.

```arduino title="TUTORIAL_9_SENSOR_JARAK_LANJUTAN.ino" showLineNumbers
const int trigPin = 8;
const int echoPin = 9;

float jarak;

void setup() {
Serial.begin(9600);
pinMode(trigPin, OUTPUT);
pinMode(echoPin, INPUT);
}

//highlight-start
void loop() {
jarak=ukurJarak();

Serial.print("Jarak: ");
Serial.println(jarak);

delay(100);
}
//highlight-end

float ukurJarak(){
float distance = 0;

digitalWrite(trigPin, LOW);
delayMicroseconds(2);

digitalWrite(trigPin, HIGH);
delayMicroseconds(10);
digitalWrite(trigPin, LOW);

distance = ((pulseIn(echoPin, HIGH)) * 0.034) / 2;

return distance;
}
```

Dan di dalam fungsi `loop()` tersebut terdapat beberapa perintah dari baris 13 hingga baris 18.

Perintah pertama berada pada baris 13. Pada baris 13 tersebut, kita memanggil fungsi yang bernama `ukurJarak()`. Fungsi tersebut merupakan fungsi yang dibuat sendiri dimana di dalam fungsi tersebut terdapat beberapa baris kode program untuk menghitung jarak antara sensor jarak dengan benda/tangan kita.

Hasil perhitungan jarak antara sensor jarak dengan benda/tangan kita yang telah selesai dihitung oleh fungsi `ukurJarak()` tersebut kemudian akan disimpan dalam variabel bernama `jarak`.

Ingat kembali bahwa pada baris 4, kita telah membuat variabel bernama `jarak` dengan tipe data `float` yang digunakan untuk menyimpan bilangan desimal. Oleh karenanya, sebagai permisalan, jika hasil perhitungan `ukurJarak()` yang dihasilkan berupa bilangan desimal seperti 10.21, maka akan disimpan ke dalam variabel `jarak` tersebut.

Selanjutnya pada baris 15 terdapat perintah untuk mencetak teks "Jarak: " ke Serial Monitor menggunakan perintah `Serial.print`.

Setelah itu, pada baris 16, terdapat perintah untuk mencetak nilai yang disimpan dalam variabel `jarak` ke Serial Monitor menggunakan perintah `Serial.println`.

Perintah terakhir yang ada dalam fungsi `loop()` berada pada baris 18, yakni perintah untuk menunda program selama 100 mili sekon dengan menggunakan perintah `delay(100)`.

Itulah semua perintah yang ada di dalam fungsi `loop()`. Singkat sekali bukan?

Apakah dengan demikian, penjelasan programnya selesai sampai sini? karena selama ini, topik Penjelasan Program selalu selesai jika sudah mencapai bagian terakhir dari fungsi `loop()`.

Tentu saja tidak. Karena pada Tutorial 9 kali ini, setelah fungsi `loop()` selesai, masih ada fungsi lagi, yakni fungsi yang dibuat sendiri. Apa itu fungsi yang dibuat sendiri?

Jika kita lihat pada fungsi `analogWrite()`, `analogRead()`, `digitalRead()` dan sebagainya, semua itu adalah fungsi yang dibuat oleh Arduino IDE, dan bukan dibuat oleh kita sehingga kita tinggal memakainya saja.

Sedangkan, fungsi yang dibuat sendiri, atau bahasa Inggris nya yang sering disebut oleh programmer luar negeri, "self-built function", adalah fungsi yang dibuat oleh pengguna itu sendiri.

Fungsi yang kita buat sendiri pada Tutorial ini bernama `ukurJarak()` dan berada pada baris 21 hingga baris 33. Sama seperti fungsi `setup()` dan fungsi `loop()`, perintah dalam suatu fungsi selalu diapit oleh tanda kurawal buka `{` dan tanda kurawal tutup `}`.

```arduino title="TUTORIAL_9_SENSOR_JARAK_LANJUTAN.ino" showLineNumbers
const int trigPin = 8;
const int echoPin = 9;

float jarak;

void setup() {
Serial.begin(9600);
pinMode(trigPin, OUTPUT);
pinMode(echoPin, INPUT);
}

void loop() {
jarak=ukurJarak();

Serial.print("Jarak: ");
Serial.println(jarak);

delay(100);
}

//highlight-start
float ukurJarak(){
float distance = 0;

digitalWrite(trigPin, LOW);
delayMicroseconds(2);

digitalWrite(trigPin, HIGH);
delayMicroseconds(10);
digitalWrite(trigPin, LOW);

distance = ((pulseIn(echoPin, HIGH)) * 0.034) / 2;

return distance;
}
//highlight-end
```

Mari kita bedah, perintah apa saja yang terdapat dalam fungsi `ukurJarak()`.

Pada baris 22 program di atas, kita membuat variabel baru bernama `distance` dengan tipe data `float` sehingga variabel tersebut bisa menyimpan bilangan desimal.

Perhatikan pula terdapat angka 0 pada baris 22 tersebut yang berarti variabel `distance` akan menyimpan angka awal sebesar 0 tiap kali fungsi `ukurJarak()` dipanggil.

Jadi variabel `distance` akan selalu menyimpan angka awal 0 tiap kali fungsi `ukurJarak()` dipanggil dan apabila perhitungan untuk mengukur jarak di dalam fungsi `ukurJarak()` selesai dihitung, angka 0 tadi akan digantikan oleh hasil perhitungan baru tersebut.

Kemudian pada baris 24 dan 25, terdapat perintah untuk memastikan komponen T sensor jarak tidak memancarkan suara ultrasonik apapun selama 2 mili sekon.

Hal ini dilakukan dengan cara memberikan logika `LOW` pada pin trigPin menggunakan perintah `digitalWrite()`, kemudian perintah `delayMicroseconds(2)` membuat baris 24 tertunda selama 2 mikro detik sehingga membuat pin `trigPin` menerima logika `LOW` selama 2 detik.

Selanjutnya pada baris 27, karena pin `trigPin` diberi logika `HIGH` menggunakan perintah `digitalWrite()`, menyebabkan komponen T sensor jarak akan memancarkan suara ultrasonik selama 10 mikro detik karena kita memerintahkan untuk menunda program selama 10 mili detik melalui perintah `delayMicroseconds(10)` yang terdapat pada baris 28.

Setelah selesai memancarkan suara ultrasonik selama 10 mikro detik, kita memberi logika `LOW` pada pin `trigPin` dengan perintah `digitalWrite()` pada baris 29 sehingga komponen T sensor jarak akan berhenti memancarkan suara ultrasonik.

Setelahnya, barulah kita masuk ke dalam persamaan untuk menghitung jarak yang terdapat pada baris 31. Persamaan yang kita masukkan pada baris 31 ini sama seperti dengan persamaan yang kita gunakan pada Tantangan 2 Tutorial 8 sebelumnya.

```arduino
((pulseIn(echoPin, HIGH)) * 0.034) / 2;
```

Dimana kita mengukur lama waktu yang ditempuh oleh suara ultrasonik untuk merambat dengan menggunakan fungsi `pulseIn()`. Karena berada dalam tanda kurung, maka fungsi `pulseIn()` ini akan dijalankan terlebih dahulu sebelum dilakukan perkalian dengan 0.034.

Setelah diketahui waktu yang ditempuh oleh suara ultrasonik untuk merambat, maka selanjutnya dikali dengan angka 0.034. Hasil perkalian antara waktu tempuh dengan angka 0.034 kemudian dibagi dengan angka 2.

Hasil persamaan tersebut kemudian disimpan dalam variabel `distance`. Ingat kembali bahwa awalnya variabel `distance` adalah berisi nilai 0. Sekarang variabel `distance` akan berisi berapapun hasil perhitungan persamaan pada baris 31 tersebut.

Kode perintah terakhir yang dimiliki oleh fungsi `ukurJarak()` adalah perintah `return` yang berada pada baris 33. Kata `return` dalam bahasa Indonesia berarti "Mengembalikan". Sehingga perintah tersebut adalah perintah untuk mengembalikan nilai yang tersimpan dalam variabel `distance` ke fungsi `ukurJarak()`.

Kini, sama seperti variabel `distance`, fungsi `ukurJarak()` menyimpan nilai hasil perhitungan persamaan pada baris 31 tadi dan menunggu untuk dipanggil lagi pada baris 13 dalam fungsi `loop()`.

Ingat kembali, semua perintah yang berada dalam fungsi `loop()` akan berjalan terus menerus. Sementara fungsi `ukurJarak()` yang kita buat sendiri berada di luar fungsi `loop()` sehingga akan berjalan jika kita memanggil fungsi `ukurJarak()` tersebut ke dalam fungsi `loop()` sebagaimana yang kita lakukan pada baris 13 dalam fungsi `loop()`.

<br/>

## Tantangan Tutorial 9

Sebelum masuk ke Tantangan Tutorial 9, kita sarankan teman-teman membuat sketch baru dan menyimpan sketch tersebut dengan nama TUTORIAL_9_SENSOR_JARAK_CHALLENGE dan simpanlah dalam folder **Program Tutorials**. Agar sketch awal yang telah teman-teman buat pada langkah sebelumnya tidak terhapus. Sehingga teman-teman memiliki dua buah sketch untuk tiap tutorial.

### Tantangan 1

Baik, selanjutnya kita akan masuk ke topik tantangan pertama yang fokus utamanya adalah untuk membantu teman-teman lebih paham dan terbiasa lagi dengan konsep fungsi yang dibuat sendiri atau _self-built function_. Mengapa? karena ke depannya, konsep _self-built function_ atau fungsi yang dibuat sendiri akan sering kita gunakan untuk mempermudah atau mempersingkat kode program agar lebih rapi.

Selain itu, kita tidak perlu melakukan berulang kali menulis perintah yang sama. Dengan fungsi yang dibuat sendiri, kita cukup membuat perintah tertentu sekali saja, kemudian jika kita ingin mengunakannya, kita cukup memanggilnya berkali-berkali sebanyak yang kita inginkan.

Sebagai contoh, apabila kita ingin membuat garis unik yang berbeda-beda untuk menghias Serial Monitor kita ketika kita menampilkan pesan teks atau informasi seperti pada gambar di bawah ini,

<p align="center" width="100%">

<img width="80%" src={require('../beginner-level/img/img9/tutorial-9-challenge-1.png').default} alt="Arduino Light Sensor Pins"/>

</p>

Di bawah ini adalah program yang digunakan untuk membuat pesan teks pada gambar di atas.

```arduino title="TUTORIAL_9_SENSOR_JARAK_CHALLENGE.ino" showLineNumbers
void setup() {
Serial.begin(9600);
Serial.println("~~~~~~~~~~~~~~~~~~~~~~");
Serial.println("| Menu Makanan |");
Serial.println("~~~~~~~~~~~~~~~~~~~~~~");
Serial.println("| Nasi Goreng |");
Serial.println("| Mi Ayam |");
Serial.println("| Bakso |");
Serial.println("| Sate |");
Serial.println("~~~~~~~~~~~~~~~~~~~~~~");
Serial.println("----------------------");
Serial.println("| Menu Minuman |");
Serial.println("----------------------");
Serial.println("| Es Teh |");
Serial.println("| Jus Jeruk |");
Serial.println("| Bakso |");
Serial.println("| Sate |");
Serial.println("----------------------");
}

void loop() {
}

```

Perhatikan bahwa kita memasukkan semua pesan teks dalam fungsi `setup()` dan kita membiarkan fungsi `loop()` kosong. Karena kita ingin pesan teks tersebut hanya dicetak sekali saja. Bayangkan jika teman-teman memasukkan semua pesan teks tersebut ke dalam fungsi `loop()`, maaka teman-teman akan melihat Serial Monitor mencetak pesan teks tersebut berulang-ulang secara terus menerus.

Namun, kita bukan ingin kembali mengajarkan tentang perbedaan fungsi `setup()` dan fungsi `loop()` kali ini. Perhatikan pada baris 3, 5, dan 10, kita memasukkan garis bergelombang `~~~~~~` . Serta kita memasukkan garis putus-putus `--------` pada baris 11, 13, dan 18.

Jika kita menggunakan copy paste saja untuk membuat garis-garis tersebut berulang-ulang, mungkin memang dirasa mudah. Namun, bagaimana jika membuat fungsi sendiri dan jika kita ingin memasukkan garis bergelombang dan garis putus-putus, kita tinggal memanggil garis tersebut dengan fungsi yang telah kita buat sesuai namanya?

Mari simak bagaimana caranya dalam program berikut. Sebelum mulai mengetik, tutuplah dahulu Serial Monitor jika masih terbuka. Kemudian cobalah ketik dan upload program berikut ke Arduino Nano teman-teman dan lihat bagaimana hasilnya pada Serial Monitor.

```arduino title="TUTORIAL_9_SENSOR_JARAK_CHALLENGE.ino" showLineNumbers
void setup() {
Serial.begin(9600);
garisGelombang();
Serial.println("| Menu Makanan |");
garisGelombang();
Serial.println("| Nasi Goreng |");
Serial.println("| Mi Ayam |");
Serial.println("| Bakso |");
Serial.println("| Sate |");
garisGelombang();
garisPutusPutus();
Serial.println("| Menu Minuman |");
garisPutusPutus();
Serial.println("| Es Teh |");
Serial.println("| Jus Jeruk |");
Serial.println("| Bakso |");
Serial.println("| Sate |");
garisPutusPutus();
}

void loop() {
}

void garisGelombang(){
    Serial.println("~~~~~~~~~~~~~~~~~~~~~~");
}

void garisPutusPutus(){
    Serial.println("----------------------");
}

```

Hasilnya akan seperti pada gambar di bawah ini bukan?

<p align="center" width="100%">

<img width="80%" src={require('../beginner-level/img/img9/tutorial-9-challenge-1.png').default} alt="Arduino Light Sensor Pins"/>

</p>

Mengapa demikian?

Hal ini bisa terjadi karena kita telah membuat dua buah fungsi yang dibuat sendiri. Bisakah teman-teman menebak apa nama kedua fungsi yang dibuat sendiri dalam program tersebut?

Jika tebakan teman-teman adalah `garisGelombang()` dan `garisPutusPutus()`, maka tebakan teman-teman benar. Kita bisa dengan bebas menentukan nama fungsi yang dibuat sendiri sesuai dengan keinginan kita.

Misalnya seperti `garisBergelombang()` atau `garisPutus()`. Nama apapun tak masalah selama nama fungsi tersebut mudah diingat oleh teman-teman ketika kita ingin memanggilnya untuk menggunakan fungsi tersebut.

Bisakah teman-teman menebak, dalam fungsi `setup()`, pada baris nomor berapa fungsi `garisGelombang()` dipanggil? Jika teman-teman menjawab pada baris 3, 5, dan 10, maka jawaban teman-teman benar. Teman-teman juga pasti tahu fungsi `garisPutusPutus()` dipanggil pada baris nomor berapa.

Mari kita bedah anatomi fungsi `garisGelombang()` melalui gambar di bawah ini

<p align="center" width="100%">

<img width="100%" src={require('../beginner-level/img/img9/tutorial-9-challenge-1-1.png').default} alt="Arduino Light Sensor Pins"/>

</p>

Dan anatomi fungsi `garisPutus()` melalui gambar di bawah ini

<p align="center" width="100%">

<img width="100%" src={require('../beginner-level/img/img9/tutorial-9-challenge-1-2.png').default} alt="Arduino Light Sensor Pins"/>

</p>

Itulah serunya jika kita bisa membuat fungsi sendiri. Kita tinggal memanggil nama fungsi dengan kemampuan yang kita butuhkan pada baris berapapun. Dengan demikian, kita tidak perlu melakukan copy paste berulang-ulang untuk membuat baris kode program yang sama.

### Tantangan 2

Kali ini kita akan mencoba meningkatkan tantangannya. Kita akan mencoba untuk membuat fungsi penjumlahan, pengurangan, perkalian, dan pembagian.

Sebagai contoh awal, cobalah ketik dan upload program di bawah ini.

```arduino title="TUTORIAL_9_SENSOR_JARAK_CHALLENGE.ino" showLineNumbers
int jumlah;

void setup() {
Serial.begin(9600);
jumlah=2+3+3;
Serial.print("Hasil penjumlahan: ");
Serial.println(jumlah);
}

void loop() {

}

```

Hasil yang teman-teman dapatkan pasti seperti ini

<p align="center" width="100%">

<img width="80%" src={require('../beginner-level/img/img9/tutorial-9-challenge-2.png').default} alt="Arduino Light Sensor Pins"/>

</p>

Untuk penjelasan programnya, pada baris 1, kita membuat sebuah variabel bernama `jumlah` yang bertipe `int`. Variabel ini akan kita gunakan untuk menyimpan nilai hasil penjumlahan yang kita buat.

Kemudian dalam fungsi `setup()` pada baris 5, terdapat persamaan matematika `2+3+3`, setelah operasi persamaan matematika tersebut dihitung, akan menghasilkan angka 8. Angka 8 tersebut akan disimpan dalam variabel `jumlah`.

Kemudian angka dalam variabel `jumlah` tersebut akan dicetak pada Serial Monitor dengan menggunakan perintah `Serial.println` pada baris 7.

Jika kita ingin menjumlahkan suatu angka, kita harus mengetik angka-angka yang ingin kita jumlahkan. Kemudian menyimpannya ke dalam suatu variabel. Tentunya variabel tersebut harus kita buat terlebih dahulu sebelumnya di atas fungsi `setup()`.

Namun, jika kita membuat fungsi sendiri dengan nama `jumlah()` dan kita tinggal memasukkan angka-angka yang ingin kita jumlahkan ke dalam parameter fungsi `jumlah()` tadi sehingga akan menjadi seperti `jumlah(2,3,4)`, maka hasilnya juga pasti akan bernilai 8. Bagaimana caranya? Mari simak program berikut

```arduino title="TUTORIAL_9_SENSOR_JARAK_CHALLENGE.ino" showLineNumbers
void setup() {
Serial.begin(9600);
Serial.print("Hasil penjumlahan: ");
Serial.println(jumlah(2,3,3));
}

void loop() {

}

int jumlah(int x, int y, int z){
    int hasil;
    hasil=x + y + z;
    return hasil;
}
```

Jika teman-teman mengupload programnya, maka hasil yang teman-teman dapatkan pasti sama juga seperti pada program sebelumnya bukan? Dan fungsi `setup()` menjadi lebih ringkas bukan?

Mari kita bedah anatomi fungsi yang kita buat sendiri melalui ilustrasi berikut:

<p align="center" width="100%">

<img width="100%" src={require('../beginner-level/img/img9/tutorial-9-challenge-2-1.png').default} alt="Arduino Light Sensor Pins"/>

</p>

Kalau teman-teman perhatikan kembali fungsi `garisGelombang()` pada fungsi sebelumnya, kita tinggal memanggilnya saja tanpa harus menulis parameter apapun dalam tanda kurung fungsi tersebut. Namun berbeda dengan fungsi `jumlah()` yang mengharuskan kita untuk memasukkan angka ke dalam tanda kurungnya seperti `jumlah(3,2,1)`. Mengapa demikian?

Perhatikan bahwa fungsi `jumlah()` memiliki tiga buah parameter yakni, parameter bernama `x`, `y`, dan `z`. Ketiga parameter tersebut bertipe data `int`. Ketiga parameter ini akan berfungsi untuk menyimpan nilai yang ingin kita hitung hasil penjumlahannya dengan menggunakan fungsi `jumlah()`.

Misalnya jika kita ketik seperti pada di bawah ini

```arduino showLineNumbers
jumlah(3, 2, 1);
```

Maka, angka 3 akan disimpan dalam parameter `x` dan angka 2 disimpan dalam parameter `y` dan terakhir, angka 1 disimpan dalam parameter `z`. Sehingga, pada operasi penjumlahannya

```arduino
hasil=x + y + z;
```

sama dengan

```arduino
hasil=3 + 2 + 1;
```

Jika dimisalkan kita memasukkan angka desimal ke dalam parameter tersebut, seperti

```arduino
jumlah(23.31, 27.5, 112.2);
```

:::note Catatan
Ingat kembali, bahwa dalam bahasa pemrograman, tanda koma untuk bilangan desimal disimbolkan sebagai titik. Jadi, jika kita ingin menulis 3 koma 9 dalam program, maka kita akan menulisnya `3.9`
:::

Maka program hanya akan mengambil dan menyimpan angka di depan tanda koma saja dan mengabaikan angka setelah tanda koma sehingga akan menjadi seperti di bawah ini

```arduino
hasil=23 + 27 + 112;
```

Fungsi `jumlah()` tersebut hanya akan bisa menjumlahkan bilangan bulat saja. Mengapa demikian? karena parameter `x`, `y`, dan `z` sudah kita buat dengan menggunakan tipe data `int`.

Apabila kita ingin supaya fungsi `jumlah()` bisa menjumlahkan bilangan desimal juga, kita harus mengganti tipe data pada parameter `x`, `y`, dan `z` dengan tipe data `float` sehingga ketiga parameter tersebut bisa menyimpan angka setelah tanda koma.

Sekarang tantangannya, cobalah teman-teman modifikasi agar fungsi `jumlah()` bisa menyimpan dan menjumlahkan bilangan desimal.
