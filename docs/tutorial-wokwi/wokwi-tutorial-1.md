---
sidebar_position: 3
---

import wokwiBlinkDemo from '/DOCUSAURUS VIDEO ASSETS - WOKWI_BLINK_DEMO.mp4';

# Wokwi Tutorial 1

Mari kita memulai untuk membuat project pertama kita di Wokwi. Project pertama ini cukup sederhana, yakni hanya menyalakan
sebuah lampu LED yang terdapat pada Arduino Nano.

## Intro

Pada Arduino, terdapat sebuah lampu LED dengan label huruf L tercetak pada Arduino Nano seperti ditunjuk pada gambar di bawah ini.

<p align="center" width="100%">

<img
width="80%"
src={require('./img/img1/wokwi_tutorial_1_00.png').default}
alt="Ultrasonic Sensors"
/>

</p>

Bisakah teman-teman menemukan yang mana komponen dengan label huruf L yang dimaksud?

Pada gambar di atas, lampu indikator power yang berwarna hijau dengan label "ON" sedang menyala, sedangkan lampu LED dengan label huruf L sedang padam. Jika lampu LED dengan label huruf L sedang menyala, maka rupanya akan seperti pada gambar di bawah ini.

<p align="center" width="100%">

<img
width="80%"
src={require('./img/img1/wokwi_tutorial_1_01.png').default}
alt="Ultrasonic Sensors"
/>

</p>

Warna lampu LED dengan label huruf L yang menyala akan tampak kekuningan pada simulator Wokwi. Itulah yang akan kita lakukan pada tutorial pertama kita dengan Wokwi. Kita akan mengedipkan lampu LED kuning tersebut dengan jeda 1 detik seperti ditunjukkan oleh video singkat di bawah ini:

<div style={{textAlign: 'center'}}>

<video width="70%" controls>
  <source src={wokwiBlinkDemo}/>
</video>

</div>

## Mulai Beraksi

Baik, setelah diberi tahu mengenai apa yang akan kita lakukan pada Tutorial pertama kita pada Intro di atas, selanjutnya kita akan langsung praktik. Ikutilah langkah-langkah berikut di bawah ini:

1. Bukalah situs simulator Wokwi pada browser favorit teman-teman. Situs simulator Wokwi dapat diakses melalui tautan berikut: <a target="_blank" rel="noopener noreferrer" href="https://wokwi.com">**wokwi.com**</a>

   Oh iya, pastikan teman-teman sudah membuat akun Wokwi terlebih dahulu sebelumnya ya. Petunjuk untuk membuat akun Wokwi bisa teman-teman temukan pada topik **[Membuat akun Wokwi ](/docs/tutorial-wokwi/anatomi-wokwi.md#membuat-akun-wokwi)**.

   Setelah terbuka, tampilannya akan seperti pada gambar di bawah ini:

   <p align="center" width="100%">

   <img
   width="80%"
   src={require('./img/img1/wokwi_tutorial_1_1.png').default}
   alt="Ultrasonic Sensors"
   />

   </p>

2. Kemudian gulir ke bawah hingga sampai pada bagian **Start from Scratch**. Kemudian klik pada Arduino Nano seperti ditunjukkan oleh panah besar pada gambar di bawah ini.

   <p align="center" width="100%">

   <img
   width="80%"
   src={require('./img/img1/wokwi_tutorial_1_2.png').default}
   alt="Ultrasonic Sensors"
   />

   </p>

3. Nantinya teman-teman akan di arahkan pada area kerja (Working Area) seperti pada gambar di bawah ini:

   Jika teman-teman ingin mengetahui apa saja fungsi dari area kerja tersebut, teman-teman bisa membuka topik **[Membuat akun Wokwi ](/docs/tutorial-wokwi/anatomi-wokwi.md#anatomi-wokwi-1)**.

   <p align="center" width="100%">

   <img
   width="80%"
   src={require('./img/img1/wokwi_tutorial_1_3.png').default}
   alt="Ultrasonic Sensors"
   />

   </p>

4. Kita akan mengganti nama sketch program yang akan kita tulis sesuai dengan keinginan kita. Caranya adalah mengklik tanda panah bawah 🔽 seperti ditunjukkan pada gambar di bawah.

   <p align="center" width="100%">

   <img
   width="80%"
   src={require('./img/img1/wokwi_tutorial_1_4.png').default}
   alt="Ultrasonic Sensors"
   />

   </p>

   Kemudian pilih opsi "rename".

   <p align="center" width="100%">

   <img
   width="80%"
   src={require('./img/img1/wokwi_tutorial_1_5.png').default}
   alt="Ultrasonic Sensors"
   />

   </p>

   Selanjutnya, gantilah nama file dari **sketch.ino** menjadi **robokarsa_wokwi_tutorial_1.ino**

   <p align="center" width="100%">
   <img
   width="80%"
   src={require('./img/img1/wokwi_tutorial_1_6.png').default}
   alt="Ultrasonic Sensors"
   />

   </p>

   Setelah mengganti namanya, klik tombol **Rename** seperti ditunjuk oleh panah pada gambar di bawah.

   <p align="center" width="100%">
      <img
      width="80%"
      src={require('./img/img1/wokwi_tutorial_1_7.png').default}
      alt="Ultrasonic Sensors"
      />

      </p>

5. Setelah berhasil mengganti nama file sketch program kita, kita akan menyimpan perubahan namanya. Klik ikon 💾 SAVE seperti ditunjuk oleh tanda panah pada gambar di bawah.

    <p align="center" width="100%">
   <img
   width="80%"
   src={require('./img/img1/wokwi_tutorial_1_8.png').default}
   alt="Ultrasonic Sensors"
   />

   </p>

   Nantinya akan muncul pop up seperti di bawah ini. Isilah dengan nama yang sama dengan nama file sketch yang kita gunakan sebelumnya, yakni **robokarsa_wokwi_tutorial_1**.

    <p align="center" width="100%">
   <img
   width="80%"
   src={require('./img/img1/wokwi_tutorial_1_9.png').default}
   alt="Ultrasonic Sensors"
   />

   </p>

   Setelah selesai mengubah namanya, kemudian klik tombol **SAVE**. Nantinya, teman-teman akan melihat nama project telah berubah seperti yang ditunjuk oleh tanda panah pada gambar di bawah ini

    <p align="center" width="100%">
   <img
   width="80%"
   src={require('./img/img1/wokwi_tutorial_1_10.png').default}
   alt="Ultrasonic Sensors"
   />

   </p>

6. Kini kita masuk pada langkah mengetik kode program. Ketiklah kode program seperti yang tertulis pada sketch di bawah ini

    <p align="center" width="100%">
   <img
   width="80%"
   src={require('./img/img1/wokwi_tutorial_1_11.png').default}
   alt="Ultrasonic Sensors"
   />

   </p>

   Oops, jika terlalu kecil, teman-teman bisa melihatnya disini saja

   ```arduino title="robokarsa_wokwi_tutorial_1.ino" showLineNumbers
   void setup() {
   // put your setup code here, to run once:
   pinMode(13, OUTPUT);
   }

   void loop() {
   // put your main code here, to run repeatedly:
   digitalWrite(13, HIGH);
   delay(1000);
   digitalWrite(13, LOW);
   delay(1000);
   }
   ```

   Setelah teman-teman selesai mengetik program nya, teman-teman akan melihat tanda bulat hitam seperti yang ditunjuk oleh tanda panah pada gambar di bawah. Jika teman-teman menemukan tanda bulat hitam tersebut, itu berarti perubahan pada sketch program yang telah teman-teman buat sebelumnya belum disimpan.

   <p align="center" width="100%">
   <img
   width="80%"
   src={require('./img/img1/wokwi_tutorial_1_12.png').default}
   alt="Ultrasonic Sensors"
   />

   </p>

   Untuk menyimpannya, teman-teman tinggal tinggal meng-klik tombol **SAVE**. Seperti yang ditunjuk oleh tanda panah pada gambar di bawah. Begitu teman-teman meng-klik tombol **SAVE** tersebut, tanda bulat hitam akan hilang dan menandakan perubahan sketch yang telah teman-teman buat sebelumnya telah disimpan.

   <p align="center" width="100%">
   <img
   width="80%"
   src={require('./img/img1/wokwi_tutorial_1_13.png').default}
   alt="Ultrasonic Sensors"
   />

   </p>

7. Kini teman-teman tinggal meng-klik tombol Start Simulation, yaitu meng-klik tombol bulat hijau seperti yang ditunjukkan oleh tanda panah pada gambar di bawah. Perhatikan bagaimana lampu led Kuning nya akan berkedip seperti pada video yang telah ditunjukkan sebelumnya pada **Intro**.

   <p align="center" width="100%">
   <img
   width="80%"
   src={require('./img/img1/wokwi_tutorial_1_14.png').default}
   alt="Ultrasonic Sensors"
   />

   </p>

## Penjelasan Program

Apabila teman-teman berhasil menjalankan simulasi dan lampu LED pada Arduino Nano berkedip setiap satu detik, sekarang saat nya masuk ke topik **Penjelasan Program**.

Pastinya teman-teman penasaran bagaimaana program yang kita tulis bisa membuat lampu LED pada Arduino Nano berkedip setiap satu detik. Di bawah ini adalah potongan program yang kita gunakan pada tutorial pertama kita.

```arduino title="robokarsa_wokwi_tutorial_1.ino" showLineNumbers
void setup() {
// put your setup code here, to run once:
pinMode(13, OUTPUT);
}

void loop() {
// put your main code here, to run repeatedly:
digitalWrite(13, HIGH);
delay(1000);
digitalWrite(13, LOW);
delay(1000);
}
```

Sketch program kosong Arduino akan selalu berisi dua buah fungsi utama, yakni fungsi `setup()` dan fungsi `loop()` berikut ini:

```arduino title="sketch kosong" showLineNumbers
void setup() {
// put your setup code here, to run once:

}

void loop() {
// put your main code here, to run repeatedly:

}
```

Fungsi setup() dimulai dari baris 1 yang ditandai dengan simbol kurawal buka **{** dan diakhiri pada baris 4 yang ditandai dengan tanda kurawal tutup **}**.

Tanda kurawal buka **{** dan tanda kurawal tutup berfungsi untuk membungkus **}** semua kode program milik fungsi `setup()`. Pada sketch program kosong di atas, dalam fungsi `setup()` hanya terdapat komentar `// put your setup code here, to run once:` yang dibungkus oleh tanda kurawal buka dan tanda kurawal tutup.

Begitu pula, pada fungsi `loop()` dalam sketch kosong di atas, juga memiliki tanda kurawal buka dan tanda kurawal tutup yang membungkus komentar `// put your main code here, to run repeatedly:`.

Sebagai catatan awal, semua baris yang dimulai dengan simbol // merupakan baris komentar. Dan semua komentar yang kita buat hanya bisa dilihat oleh manusia saja, sedangkan Arduino tidak bisa melihat ataupun membaca komentar tersebut, sehingga seolah-olah baris komentar tidak dianggap oleh Arduino. Nantinya kita akan membuktikan tentang ini pada Tantangan Tutorial 1.

Balik ke program utama yang kita gunakan yang ditunjukkan pada potongan di bawah ini:

```arduino title="robokarsa_wokwi_tutorial_1.ino" showLineNumbers
void setup() {
// put your setup code here, to run once:
pinMode(13, OUTPUT);
}

void loop() {
// put your main code here, to run repeatedly:
digitalWrite(13, HIGH);
delay(1000);
digitalWrite(13, LOW);
delay(1000);
}
```

Fungsi `setup()` memiliki perintah `pinMode(13, OUTPUT)` pada baris 3. Perintah `pinMode()` tersusun dari dua buah argumen, yakni nomor pin, dan mode pin dengan cara penulisan argumennya seperti berikut: `pinMode(nomor pin, mode pin)`.

Jika kita menggunakan contoh perintah pada baris 3 program di atas, bisakah teman-teman menebak argumennya apa saja?

Jika teman-teman menebak argumennya sebagai berikut: `13` adalah argumen nomor pin, dan `OUTPUT` adalah argumen mode pin. Maka tebakan teman-teman benar.

Kita menggunakan angka 13 karena lampu LED yang program agar berkedip setiap 1 detik terhubung secara langsung dengan pin Arduino Nano nomor 13. Kemudian mode pin yang kita gunakan adalah `OUTPUT`, yakni kita memberika keluaran berupa sinyal tegangan 5 Volt untuk menyalakan lampu LED pada Arduino Nano.

Perlu diingat, beberapa perintah dalam pemrograman Arduino menggunakan bahasa Inggris. Misalnya, OUTPUT, jika diartikan ke bahasa Indonesia akan berarti `KELUARAN`. Jika sebuah pin diatur agar memiliki mode `KELUARAN`, anggaplah seperti keran yang mengeluarkan air yang sangat deras. Namun dalam Arduino Nano, pin dengan mode `KELUARAN` akan mengeluarkan tegangan 5 Volt.

Selain itu ada juga mode pin INPUT, yang jika diartikan sebagai ke bahasa Indonesia akan berarti `MASUKAN`. Jika sebuah pin diatur agar memiliki mode `MASUKAN`, anggaplah pin tersebut seperti lubang tempat masuknya air ke dalam botol. Nantinya, kita akan mempelajari lebih lanjut tentang mode pin `INPUT` pada tutorial berikutnya.

Selanjutnya, kita akan membahas fungsi `loop()`.

```arduino title="robokarsa_wokwi_tutorial_1.ino" showLineNumbers
void setup() {
// put your setup code here, to run once:
pinMode(13, OUTPUT);
}

void loop() {
// put your main code here, to run repeatedly:
digitalWrite(13, HIGH);
delay(1000);
digitalWrite(13, LOW);
delay(1000);
}
```

fungsi `loop()` dimulai dari baris 6 karena tanda kurawal buka **{** milik fungsi `loop()` berada pada baris 6. Dan diakhiri pada baris 12 karena tanda kurawal tutup **}** milik fungsi `loop()` berada pada baris 12. Ingat kembali, tanda kurawal buka dan tanda kurawal tutup ini berguna untuk membungkus perintah milik suatu fungsi, dalam hal ini membungkus perintah milik fungsi `loop()`.

Nah, kira-kira bisakah teman-teman menebak yang mana saja perintah milik fungsi `loop()` yang dibungkus oleh tanda kurawal tersebut?

Benar, perintah milik fungsi `loop()` yang dibungkus oleh tanda kurawal tersebut berada pada baris 7 hingga baris 11.

Pada baris 7 terdapat sebuah komentar. Komentar tersebut digunakan hanya sebagai catatan saja.

Selanjutnya, pada baris 8, terdapat perintah `digitalWrite(13, HIGH)`. Perintah `digitalWrite()` memiliki dua buah argumen, yakni nomor pin dan logika.

Jika kita menggunakan contoh pada perintah yang terletak pada baris 8, yakni perintah `digitalWrite(13, HIGH)`, perintah tersebut memiliki dua buah argumen, yakni nomor pin dan logika. Bisakah teman-teman menebak argumen nomor pin dan logikanya apa saja? Benar, nomor pin nya adalah `13` dan logika nya adalah `HIGH`.

Disini kita menggunakan nomor pin 13 karena kita akan menyalakan lampu LED pada Arduino Nano yang terhubung dengan pin nomor 13 Arduino Nano. Kemudian kita menggunakan logika `HIGH` karena dalam bahasa mesin, logika HIGH itu berarti menyala dan logika LOW itu berarti mati. Mengapa demikian? Karena pada logika HIGH dalam Arduino Nano, logika HIGH berarti memberikan tegangan 5 Volt sehingga lampu LED bisa menyala, sedangkan jika kita memberikan logika LOW, maka Arduino Nano akan memberikan tegangan 0 Volt sehingga lampu LED padam.

Kita juga bisa menggunakan angka 1 dan 0 untuk menggantikan logika HIGH dan LOW. Kita akan mempelajari hal ini lebih lanjut pada Tantangan Tutorial 1 nantinya.

Singkatnya, perintah `digitalWrite(13, HIGH)` pada baris 8 akan memberikan tegangan 5 Volt ke pin 13, sehingga menyebabkan lampu LED pada Arduino Nano akan menyala.

Kemudian pada baris 9 terdapat perintah `delay(1000)` untuk menunda waktu selama 1 detik. perintah `delay()` hanya memiliki satu buah argumen, yakni waktu dalam mili sekon. Jika mengambil contoh pada baris 9, perintah `delay(1000)`, memiliki argumen sebesar 1000 mili sekon yang setara dengan 1 detik.

Jadi, apabila kita ingin menunda waktunya selama 1 detik, maka kita bisa memasukkan 1000 mili sekon. Jika kita ingin menunda selama 2 detik, kita bisa memasukkan 2000 mili sekon. Jika kita ingin menunda selama 1.5 detik, kita bisa memasukkan 1500 detik.

Perintah `delay()` ini akan menunda eksekusi program selama waktu yang telah ditentukan dalam argumennya. Jika misalnya pada baris 8 sebelumnya, kita telah menyalakan lampu LED dengan perintah `digitalWrite()`, kemudian bertemu dengan perintah `delay(1000)` pada baris berikutnya, maka lampu LED akan menyala selama 1 detik.

Singkatnya, anggaplah perintah `delay(1000)` menjalankan proses hitung mundur dari 1000 sampai habis. Begitu proses hitung mundurnya selesai, maka Arduino Nano akan menjalankan perintah berikutnya, yakni mematikan lampu LED.

Perintah berikutnya adalah perintah `digitalWrite(13, LOW)` yang berada pada baris 10. Perintah pada baris 10 sama seperti perintah pada baris 8, namun memiliki argumen yang berbeda. Bisakah teman-teman menemukan letak perbedaannya?

Jika pada baris 8, argumen logika yang digunakan adalah `HIGH` karena kita ingin menyalakan lampu LED, maka pada baris 10, argumen logika yang digunakan adalah `LOW` karena kita ingin mematikan lampu LED.

Sederhananya, perintah `digitalWrite(13, LOW)` dengan logika LOW akan memberikan tegangan 0 Volt ke pin 13 yang terhubung ke lampu LED pada Arduino Nano sehingga lampu LED akan menjadi padam.

Begitu perintah `digitalWrite(13, LOW)` selesai dijalankan, yang ditandai dengan padamnya lampu LED kuning pada Arduino Nano, maka Arduino Nano akan lanjut mengeksekusi program pada baris berikutnya, yakni pada baris 11.

Benar, pada baris 11 terdapat perintah `delay(1000)` untuk menunda waktu dengan cara memerintahkan Arduino Nano untuk menghitung mundur dari angka 1000 sampai 0.

Karena pada baris sebelumnya, kita memberikan logika `LOW` pada pin 13 sehingga membuat lampu LED pada Arduino Nano padam, kemudian diikuti perintah `delay(1000)` pada baris berikutnya, sehingga akan membuat lampu LED padam selama 1 detik. Ingat kembali bahwa 1000 mili sekon setara dengan 1 detik.

Begitu perintah `delay(1000)` pada baris 11 selesai menghitung mundur dari 1000 sampai 0, akan dilanjutkan mengeksekusi baris kode berikutnya. Namun, karena baris kode berikutnya yang ditemui adalah tanda kurawal tutup pada baris 12 milik fungsi `loop()`, maka Arduino Nano akan kembali menjalankan perintah berikutnya dari awal fungsi `loop()` lagi, yakni pada baris 6.

Begitu seterusnya secara berulang-ulang selama simulasi masih dijalankan.

## Tantangan Tutorial 1

Karena ini adalah tantangan untuk tutorial Wokwi pertama, kami ingin menyampaikan beberapa pengantar terlebih dahulu. Tantangan yang muncul pada tiap Tutorial dimaksudkan untuk membantu teman-teman memahami lebih dalam lagi tutorial yang sedang dikerjakan. Selain itu juga untuk membuktikan beberapa penjelasan program yang telah diulas pada topik **Penjelasan Program** sebelumnya.

Tantangan yang diberikan nantinya akan berupa tugas atau perintah untuk memodifikasi program asli yang digunakan pada Tutorial yang sedang dikerjakan.

### Tantangan 1

Tantangan pertama ini ditujukan untuk membuktikan bahwa simbol `//` akan membuat sebuah baris kode menjadi tidak terlihat oleh Arduino Nano atau singkatnya, diabaikan oleh Arduino Nano.

Mari kita lihat kembali sketch program yang kita gunakan pada snippet code di bawah ini

```arduino title="robokarsa_wokwi_tutorial_1.ino" showLineNumbers
void setup() {
// put your setup code here, to run once:
pinMode(13, OUTPUT);
}

void loop() {
// put your main code here, to run repeatedly:
digitalWrite(13, HIGH);
delay(1000);
digitalWrite(13, LOW);
delay(1000);
}
```

Jika teman-teman menjalankan program di atas pada simulasi Wokwi, tentunya lampu LED pada Arduino nano akan berkedip persis seperti yang telah kita lakukan sebelum Tantangan ini, bukan?

Nah, sekarang, bagaimana jika kita menaruh simbol komentar atau simbol `//` pada baris 10 dan 11. Sehingga program nya akan menjadi seperti pada snippet code di bawah ini:

```arduino title="robokarsa_wokwi_tutorial_1.ino" showLineNumbers
void setup() {
// put your setup code here, to run once:
pinMode(13, OUTPUT);
}

void loop() {
// put your main code here, to run repeatedly:
digitalWrite(13, HIGH);
delay(1000);
//digitalWrite(13, LOW);
//delay(1000);
}
```

Setelah memodifikasinya sesuai dengan snippet code di atas, cobalah SAVE kemudian klik tombol **Start the simulation**. Lihat apa yang akan terjadi pada lampu LED Arduino Nano.

Pastinya lampu LED tersebut akan menyala terus menerus dan tidak padam. Mengapa?

Karena, meskipun perintah untuk mematikan lampu LED setelah 1 detik dengan menggunakan perintah `digitalWrite(13, LOW)` pada baris 10 masih ada dan masih bisa kita lihat pada program, namun karena kita menambahkan simbol `//` di depan baris perintah tersebut membuat baris 10 dan baris 11 tersebut menjadi tidak terlihat oleh Arduino Nano sehingga kedua baris tersebut akan diabaikan oleh Arduino dan hanya mengeksekusi program pada baris 8 dan 9 saja.

Tindakan menambah simbol `//` di awal baris suatu program disebut "Commenting", atau dalam bahasa Indonesia kita bisa menyebutnya sebagai "Mengomentari".

Selanjutnya, mari kita kembalikan kode program di atas yang telah kita beri komentar sebelumnya.

Sebelumnya kita melakukan Commenting pada baris 10 dan 11 dengan cara meletakkan simbol `//` di awal baris 10 dan 11. Sekarang simbol `//` tersebut kita hapus dan menjadi seperti pada snippet code di bawah ini:

```arduino title="robokarsa_wokwi_tutorial_1.ino" showLineNumbers
void setup() {
// put your setup code here, to run once:
pinMode(13, OUTPUT);
}

void loop() {
// put your main code here, to run repeatedly:
digitalWrite(13, HIGH);
delay(1000);
digitalWrite(13, LOW);
delay(1000);
}
```

Tindakan menghapus simbol `//` yang kita lakukan tadi disebut `Uncomment`, atau jika kita menyebutnya dalam bahasa Indonesia, "Menghapus Komentar".

Nah, selanjutnya, bagaimana kalau kita meng-Comment program di atas pada baris 8 dan 9? Kira-kira apa yang akan terjadi?

Tentunya lampu LED akan pada Arduino Nano akan selalu padam karena satu-satunya perintah yang bisa dilihat dan dieksekusi oleh Arduino Nano adalah perintah untuk mematikan lampu LED dengan kode `digitalWrite(13, LOW)`.

### Tantangan 2

Tantangan Tutorial 1 berikutnya akan membantu teman-teman lebih paham mengenai perintah `delay()` yang kita gunakan untuk menunda atau memberi jeda waktu pada baris program tertentu. Perintah `delay()` ini akan sering kita gunakan pada tutorial berikutnya, sehingga penting untuk dipahami lebih lanjut.

Perlu diingat, perintah `delay()` hanya akan menunda eksekusi program yang berada di atasnya.

Misalnya pada baris 8, terdapat kode perintah `digitalWrite(13, HIGH)` untuk menyalakan lampu, kemudian tepat di bawah perintah untuk menyalakan lampu tersebut, yakni pada baris 9 terdapat kode perintah `delay(1000)` yang akan memberi jeda waktu kode perintah di atasnya.

Sehingga kode pada baris 8 akan dieksekusi selama 1 detik (1000 mili sekon = 1 detik). Setelah kode perintah `delay(1000)` pada baris 9 selesai menjeda waktu selama 1 detik, maka akan melanjutkan untuk mengeksekusi program pada baris berikutnya.

```arduino title="robokarsa_wokwi_tutorial_1.ino" showLineNumbers
void setup() {
// put your setup code here, to run once:
pinMode(13, OUTPUT);
}

void loop() {
// put your main code here, to run repeatedly:
digitalWrite(13, HIGH);
delay(1000);
digitalWrite(13, LOW);
delay(1000);
}
```

Nah, pada Tantangan 2 ini, kita akan mencoba memodifikasi nilai yang dimasukkan pada perintah `delay()`. Ingat kembali bahwa satuan yang digunakan dalam perintah `delay()` adalah mili sekon. Jika kita memasukkan 1000, maka itu berarti kita memasukkan 1 detik. Cobalah memasukkan nilai `delay()` yang digunakan seperti pada snippet program di bawah ini:

```arduino title="robokarsa_wokwi_tutorial_1.ino" showLineNumbers
void setup() {
// put your setup code here, to run once:
pinMode(13, OUTPUT);
}

void loop() {
// put your main code here, to run repeatedly:
digitalWrite(13, HIGH); //nyalakan lampu
delay(5000);            //tunda 5 detik
digitalWrite(13, LOW);  //matikan lampu
delay(5000);            //tunda 5 detik
}
```

Kemudian tekan tombol hijau "Start the simulation" pada area diagram editor untuk menjalankan program tersebut. Cobalah amati berapa lama lampu LED pada Arduino menyala dan mati.

Tentu saja lampu LED pada Arduino akan menyala selama 5 detik dan padam selama 5 detik juga karena kita memasukkan nilai 5000 pada kode perintah `delay()`.

Selanjutnya, untuk memahami urutan perintah program Arduino, kita akan mencoba untuk menyalakan lampu selama 5 detik, kemudian padam selama 1 detik. Setelah padam selama 1 detik, akan menyala kembali selama 5 detik. Ikutilah terlebih dahulu program yang ditunjukkan oleh snippet program di bawah ini:

```arduino title="robokarsa_wokwi_tutorial_1.ino" showLineNumbers
void setup() {
// put your setup code here, to run once:
pinMode(13, OUTPUT);
}

void loop() {
// put your main code here, to run repeatedly:
digitalWrite(13, HIGH); //nyalakan lampu
delay(5000);            //tunda 5 detik
digitalWrite(13, LOW);  //matikan lampu
delay(1000);            //tunda 1 detik
}
```

Cobalah jalankan simulasi dan amati dengan menghitung berapa lama lampu LED padam dan menyala untuk mengetahui apakah hasilnya sesuai dengan program yang teman-teman buat.

Cobalah untuk bermain dengan nilai delay yang berbeda.
