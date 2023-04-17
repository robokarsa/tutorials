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

   ```arduino showLineNumbers
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
