---
sidebar_position: 2
---

# Anatomi Wokwi

Mari kita pelajari terlebih dahulu antarmuka simulator Wokwi dan apa saja fitur-fitur yang tersedia di dalamnya. Namun sebelumnya, mari kita membuat akun Wokwi terlebih dahulu.

## Membuat Akun Wokwi

1. Bukalah simulator Wokwi terlebih dahulu pada browser teman-teman melalui link berikut: <a target="_blank" rel="noopener noreferrer" href="https://wokwi.com">**wokwi.com**</a>. Nantinya halaman awal Wokwi akan terbuka seperti di bawah ini

<p align="center" width="100%">

<img
width="80%"
src={require('./img/wokwi-landing-page.png').default}
alt="Ultrasonic Sensors"
/>

</p>

2. Selanjutnya klik tombol **Sign In** yang terletak pada pojok kanan atas. Nantinya sebuah pop-up akan muncul seperti pada gambar di bawah ini. Akan diberikan tiga pilihan cara untuk membuat akun Wokwi, yakni Google Email, Github Account, dan Email (jika memiliki email selain Google Mail).

<p align="center" width="100%">

<img
width="80%"
src={require('./img/wokwi-sign-up.png').default}
alt="Ultrasonic Sensors"
/>

</p>

Pada tutorial ini, kita menggunakan akun Gmail, jadi, jika teman-teman memiliki akun Gmail, klik pilihan Google. Nantinya akan terbuka tab baru dimana teman-teman menginput email teman-teman.

3. Jika teman-teman telah login, nantinya tombol **Sign In** yang sebelumnya berada pada pojok kanan atas akan berubah menjadi ikon bulat sesuai dengan inisial awal email teman-teman.

<p align="center" width="100%">

<img
width="80%"
src={require('./img/wokwi-signed-in.png').default}
alt="Ultrasonic Sensors"
/>

</p>

4. Selanjutnya, gulir halaman tersebut ke bawah hingga sampai pada bagian Start from Stratch seperti pada gambar di bawah ini, kemudian pilih Arduino Nano dengan cara meng-klik pada gambar Arduino Nano tersebut.

<p align="center" width="100%">

<img
width="80%"
src={require('./img/wokwi-start.png').default}
alt="Ultrasonic Sensors"
/>

</p>

5. Nantinya, akan terbuka area baru seperti pada gambar di bawah ini

<p align="center" width="100%">

<img
width="80%"
src={require('./img/wokwi-start-1.png').default}
alt="Ultrasonic Sensors"
/>

</p>

Disinilah area utama tempat kita akan bereksperimen dan belajar. Dan sebelum itu, mari kita pelajari terlebih dahulu apa saja fitur-fitur dan fungsi-fungsi yang tersedia pada area tersebut.

## Anatomi Wokwi

### Code Editor

Merupakan area utama tempat kita mengetik dan mengedit semua program dan kode seperti library, konfigurasi diagram.json.
Pada code Editor terdapat tiga buah tab utama, yakni tab sketch.ino, tab diagram.json, dan tab Libary Manager.

<p align="center" width="100%">

<img
width="100%"
src={require('./img/wokwi-start-2.png').default}
alt="Ultrasonic Sensors"
/>

</p>

#### Sketch Editor Tab

Tampilan ketika kita memulai sketch baru akan sama seperti tampilan pada Arduino IDE. Dimana .ino adalah ekstensi file yang dikhuskan untuk Arduino IDE.

Nama file awalnya adalah "Sketch.ino" ketika kita pertama kali membuka sketch baru. Kita bisa mengedit nama file tersebut dengan meng-klik tombol segitiga hitam pada ujung kanan barisan tab lalu memilih opsi "rename".

<p align="center" width="100%">

<img
width="100%"
src={require('./img/wokwi-start-4.png').default}
alt="Ultrasonic Sensors"
/>

</p>

#### Diagram.json Editor Tab

Secara umum, file diagram.json digunakan untuk mendefinisikan setiap komponen yang akan disimulasikan, properti setiap komponen, dan rangkaian yang digunakan antar komponen.

<p align="center" width="100%">

<img
width="100%"
src={require('./img/wokwi-start-5.png').default}
alt="Ultrasonic Sensors"
/>

</p>

Keterangan:
`"version"` selalu diisi dengan 1, `"author"` adalah nama orang yang membuat file saat ini, `"editor"` diisi dengan aplikasi/program yang digunakan untuk mengedit file tersebut (dalam hal ini diisi dengan Wokwi karena diedit pada Wokwi).

Untuk informasi lebih lanjut, teman-teman bisa lihat pada dokumentasi Wokwi pada tautan <a target="_blank" rel="noopener noreferrer" href="https://docs.wokwi.com/diagram-format">**ini**</a>.

#### Library Manager Tab

Sama seperti Arduino IDE, kita membutuhkan library untuk membantu kita memprogram suatu komponen, Wokwi juga menyediakan fitur agar kita bisa memasukkan libary melalui tab Library Manager. Seperti yang bisa terlihat pada gambar di bawah ini, saat ini tertera informasi No libraries installed, yang berarti belum ada libary yang terinstall saat ini.

<p align="center" width="100%">

<img
width="100%"
src={require('./img/wokwi-start-6.png').default}
alt="Ultrasonic Sensors"
/>

</p>

#### Editor Area Settings

Memuat beberapa pilihan seperti format code (merapikan kode), rename (mengganti nama file), delete (menghapus file), new file (membuat file baru), Upload file(s) (memuat file dari komputer ke Editor Area Wokwi).

<p align="center" width="100%">

<img
width="100%"
src={require('./img/wokwi-start-7.png').default}
alt="Ultrasonic Sensors"
/>

</p>

Jika teman-teman meng-klik ikon panah bawah tersebut, akan muncul beberapa pilihan seperti pada gambar di bawah ini.

<p align="center" width="100%">

<img
width="50%"
src={require('./img/wokwi-start-8.png').default}
alt="Ultrasonic Sensors"
/>

</p>

### Diagram Editor

Merupakan area utama tempat kita merangkai dan menghubungkan komponen-komponen elektronika yang disediakan oleh Wokwi. Pada gambar di bawah ini, simulasi virtual dari Arduino Nano sudah disediakan oleh Wokwi karena sebelumnya kita meng-klik Arduino Nano pada langkah 4 sebelumnya.

<p align="center" width="100%">

<img
width="100%"
src={require('./img/wokwi-start-3.png').default}
alt="Ultrasonic Sensors"
/>

</p>

Terdapat tiga buah tombol utama pada Diagram Editor yakni, tombol `Start the simulation`, tombol `Add a new part`, dan tombol `Zoom, grid and more`.

#### Tombol **Start the simulation**

Jika semua rangkaian teman-teman sudah siap dan akan diuji coba, teman-teman bisa menekan tombol ini untuk menjalankan program yang telah teman-teman buat pada Editor Area.

<p align="center" width="100%">

<img
width="10%"
src={require('./img/wokwi-start-9.png').default}
alt="Ultrasonic Sensors"
/>

</p>

#### Tombol **Add a new part**

Jika teman-teman ingin menambah komponen yang akan dimasukkan ke dalam Diagram Area, teman-teman bisa menekan tombol ini dan akan muncul beragam pilihan komponen yang disediakan oleh Wokwi.

<p align="center" width="100%">

<img
width="10%"
src={require('./img/wokwi-start-10.png').default}
alt="Ultrasonic Sensors"
/>

</p>

#### Tombol **Zoom, grid and more**

Singkatnya, tombol ini memuat beberapa opsi seperti memperbesar, atau memperkecil Diagram Area, Full screen, ataupun menyalakan garis bantu kotak-kotak agar penempatan tiap kompnen bisa lebih rapi.

<p align="center" width="100%">

<img
width="10%"
src={require('./img/wokwi-start-11.png').default}
alt="Ultrasonic Sensors"
/>

</p>

Jika teman-teman meng-klik tombol titik tiga tersebut, teman-teman akan mendapati beberapa pilihan seperti pada gambar di bawah ini

<p align="center" width="100%">

<img
width="50%"
src={require('./img/wokwi-start-12.png').default}
alt="Ultrasonic Sensors"
/>

</p>
