---
sidebar_position: 3
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Tutorial 2 - Mengedipkan Mini Traffic Light Module 🚦

Pada Tutorial 1, kita sudah belajar bagaimana mengedipkan satu buah lampu LED, yaitu lampu LED bawaan yang tertanam pada Arduino Nano.

<p align="center" width="100%">

<img width="80%" src={require('./img/img2/tutorial-2-led-traffic-light-module-arduino-nano.png').default} alt="Ultrasonic Sensors"/>

</p>

Namun bagaimana jika kita ingin mengedipkan 3 buah lampu LED seperti pada gambar di atas, baik secara bersamaan maupun secara bergiliran? Nah, pada Tutorial 2 ini akan mengajarkan teman-teman bagaimana melakukan semua itu.

Namun, sebelum kita mulai merangkai kabel-kabel, mari kita pelajari terlebih dahulu tentang Mini Traffic Light Module.

:::caution Perhatian
Penting untuk memperhatikan setiap langkah-langkah yang diberikan dan tidak melakukan apapun diluar perintah langkah yang diberikan. Kenapa? Hal ini untuk mencegah kerusakan yang tidak diinginkan pada komponen apabila bertindak di luar langkah tutorial yang diberikan dan tidak mengetahui dengan pasti apa yang teman-teman lakukan.
:::

## Apa itu Mini Traffic Light Module 🚦 ?

Kelas bahasa Inggris singkat RoboKarsa kembali. Mari kita belajar bahasa Inggris dan mencari tahu arti dari nama **Mini Traffic Light Module**

1. Mini = Mini. Dalam bahasa Indonesia juga artinya mini lho. Kata mini digunakan untuk menandakan ukurannya yang kecil.
2. Traffic = Lalu Lintas.
3. Light = Lampu.
4. Module = Modul.

Kalau kita gabungkan kata-kata tersebut, akan menjadi **Modul Lampu Lalu Lintas Mini**. Yang merupakan nama dari komponen di bawah ini.

<p align="center" width="100%">

<img width="80%" src={require('./img/img2/tutorial-2-led-traffic-light-module.png').default} alt="Ultrasonic Sensors"/>

</p>

Kata "Modul" biasanya digunakan untuk menggambarkan suatu komponen yang tersusun dari banyak komponen dalam satu-kesatuan. Misalnya Modul Lampu Lalu Lintas Mini yang akan kita gunakan, terdiri dari tiga buah lampu LED, tiga buah resistor, dan empat buah pin.

Terdapat tiga buah lampu LED berwarna merah, kuning, dan hijau untuk mensimulasikan lampu lalu lintas pada umumnya. Serta terdapat tiga buah resistor untuk masing-masing lampu LED seperti ditunjukkan oleh tanda panah merah pada gambar di bawah.

<p align="center" width="100%">

<img width="80%" src={require('./img/img2/tutorial-2-led-traffic-light-module-parts.png').default} alt="Ultrasonic Sensors"/>

</p>

Dan tanda panah kuning menunjukkan salah satu dari empat pin yang ada pada modul tersebut. Pin tersebut digunakan untuk menghubungkan ketiga lampu dengan sumber tegangan dan salah satu pin merupakan pin GND yang digunakan untuk menghubungkan ketiga lampu dengan kutub negatif baterai atau tegangan negatif Arduino Nano.

Resistor tersebut memiliki fungsi sebagai pembatas arus listrik agar tidak melebihi yang bisa diterima oleh lampu LED. Apabila lampu LED menerima arus listrik yang lebih besar dari yang mampu diterimanya, maka lampu LED dapat berpotensi mengalami kerusakan.

<p align="center" width="100%">

<img width="30%" src={require('./img/img2/tutorial-2-led-traffic-light-module-parts-resistor.png').default} alt="Ultrasonic Sensors"/>

</p>

Jika dilihat dengan lebih jelas, bentuk komponen resistor tersebut akan tampak seperti pada gambar di bawah ini. Resistor tersebut disebut resistor jenis SMD (_Surface Mounting Device_/Perangkat Yang Ditanam Pada Permukaan) karena ukurannya yang sangat kecil.

Nilai yang tertera pada badan resistor tersebut adalah sebesar 331 dimana dua angka pertama menginformasikan nilai hambatan yang dimiliki oleh resistor dan angka terakhir menunjukkan nilai persentase toleransi angka hambatan pada resistor.

Pada contoh resistor pada gambar di atas, resistor tersebut memiliki nilai hambatan sebesar 330 Ohm dan toleransi 1%. Maka dengan toleransi resistor sebesar 1%, resistor tersebut dalam praktiknya bisa saja memiliki nilai real sebesar (330 x 1%)-330 = 326,7 Ohm lebih rendah ataupun (330 x 1%)+330 =333,3 Ohm lebih tinggi dari nilai asli yang tertera pada badan resistor.

Hal ini dikarenakan dalam praktiknya, jarang terdapat komponen dalam kondisi yang ideal 100% sehingga nilai komponen resistor sulit mencapai nilai yang sebenarnya.

Rangkaian resistor dengan lampu akan tampak seperti Wiring Diagram di bawah.

<p align="center" width="100%">

<img width="10%" src={require('./img/img2/tutorial-2-led-traffic-light-module-leds-wiring-diagram-1.png').default} alt="Ultrasonic Sensors"/>

</p>

Pada Wiring Diagram di atas, terdapat ilustrasi resistor 331 yang terhubung dengan kaki positif lampu LED. Resistor harus dihubungkan dengan kaki positif lampu LED dan ujung resistor satunya menjadi kutub positif (tanda +) lampu LED. Kemudian pada kaki LED sebelah kanan, akan menjadi kutub negatif (tanda -) lampu LED.

Tanda-tanda positif dan negatif tersebut disebut sebagai polaritas dalam dunia elektronika. Polaritas suatu komponen harus sesuai dengan tanda-tandanya dan tidak boleh terbalik karena dapat berpotensi merusak komponen jika terbalik.

Seperti pada contoh Wiring Diagram di bawah ini, kutub positif (tanda +) baterai terhubung dengan kutub positif (tanda +) lampu LED. Dan kutub negatif (tanda -) baterai terhubung dengan kutub negatif (tanda -) lampu LED.

<p align="center" width="100%">

<img width="50%" src={require('./img/img2/tutorial-2-led-traffic-light-module-leds-wiring-diagram-2.png').default} alt="Ultrasonic Sensors"/>

</p>

:::info Sekadar Informasi

Wiring Diagram artinya Diagram Pengabelan, yaitu suatu diagram atau gambar yang digunakan untuk memberikan informasi jalur-jalur kabel pada suatu rangkaian elektronik.

:::

Dengan polaritas yang benar, lampu LED akan dapat menyala. Namun apabila polaritas lampu LED terbalik dalam waktu yang lama, akan membuat lampu LED berpotensi mengalami kerusakan.

Wiring Diagram dalam Modul LED akan tampak seperti pada gambar di bawah. Dimana kaki-kaki negatif lampu LED terhubung dengan satu titik yang sama dengan label GND (singkatan dari GROUND).

GROUND umumnya digunakan untuk menyatakan kutub negatif dalam dunia elektronika. Semua kutub negatif komponen elektronika yang digunakan harus terhubung dengan pin GROUND.

Sedangkan kaki positif masing-masing LED terhubung dengan titik yang terpisah dengan label G (GREEN), Y (Yellow), dan R (Red). Ketiga titik tersebut akan berperan sebagai kutub positif masing-masing LED.

<p align="center" width="100%">

<img width="50%" src={require('./img/img2/tutorial-2-led-traffic-light-module-leds-wiring-diagram-3.png').default} alt="Ultrasonic Sensors"/>

</p>

Sebagaimana contoh pada Wiring Diagram sebelumnya, kutub positif lampu LED harus dihubungkan dengan kutub positif baterai.
Apa yang akan terjadi apabila kutub positif ketiga lampu LED terhubung dalam satu titik yang sama seperti pada Wiring Diagram di bawah ini?

<p align="center" width="100%">

<img width="50%" src={require('./img/img2/tutorial-2-led-traffic-light-module-leds-wiring-diagram-4.png').default} alt="Ultrasonic Sensors"/>

</p>

Maka akan menyebabkan ketiga lampu LED menyala bersamaan. Sementara pada lalu lintas umumnya, tiap lampu tidak menyala secara bersamaan, namun menyala bergantian dengan durasi yang berbeda. Oleh karenanya kaki positif tiap lampu LED diberi titik yang terpisah seperti pada Wiring Diagram sebelumnya.

Titik-titik kutub positif ketiga lampu LED dengan label G, Y, dan R pada Wiring Diagram tersebut akan diwakili oleh komponen pada Modul yang disebut Pin seperti ditandai oleh gambar di bawah. Pin terbuat dari bahan logam konduktif sehingga dapat menghantarkan arus listrik ke lampu LED.

<p align="center" width="100%">

<img width="50%" src={require('./img/img2/tutorial-2-led-traffic-light-module-parts-pins.png').default} alt="Ultrasonic Sensors"/>

</p>

Apabila kita hanya menghubungkan kutub positif baterai pada kaki positif lampu LED hijau yang berlabel G, maka akan menyebabkan hanya lampu LED hijau saja yang menyala.

<p align="center" width="100%">

<img width="50%" src={require('./img/img2/tutorial-2-led-traffic-light-module-leds-wiring-diagram-5.png').default} alt="Ultrasonic Sensors"/>

</p>

Dua lampu lainnya akan tetap padam meskipun ketiga kaki negatif lampu LED sama-sama terhubung dengan kutub negatif baterai. Hal ini karena Pin Y dan Pin G tidak terhubung dengan kutub positif baterai sehingga arus listrik tidak mengalir ke pin Y dan pin G dan lampu tidak dapat menyala.

<p align="center" width="100%">

<img width="50%" src={require('./img/img2/tutorial-2-led-traffic-light-module-leds-wiring-diagram-6.png').default} alt="Ultrasonic Sensors"/>

<img width="50%" src={require('./img/img2/tutorial-2-led-traffic-light-module-leds-wiring-diagram-7.png').default} alt="Ultrasonic Sensors"/>

</p>

Jika ingin menyalakan lampu LED kuning, maka kita perlu memindahkan kabel yang menghubungkan kutub positif baterai dengan titik G ke titik Y. Begitu pula jika kita ingin menyalakan lampu LED merah, maka kita perlu memindahkan kabel yang menghubungkan kutub positif baterai dengan titik R ke titik R.

## Simulasi Virtual

Untuk membantu teman-teman memahami bagaimana maksudnya, kita berikan contoh simulasi virtual melalui video singkat dibawah ini.

<div style={{textAlign: 'center'}}>

<video width="70%" controls>
  <source src="/tinkercad-sims-manual-blink-led-modules.mp4"/>
</video>

</div>

Pada video singkat di atas, kalau kita ingin menyalakan lampu kuning, kita harus memindahkan kabelnya ke kaki resistor milik lampu kuning, begitu pula jika kita ingin menyalakan lampu hijau, kita harus memindahkan kabelnya ke kaki resistor milik lampu hijau.

Namun memindahkan kabel tersebut secara manual dan satu persatu akan dianggap merepotkan. Terutama jika ingin menyala dan mati secara bergantian dalam waktu singkat.

Pada Tutorial #2 ini akan mengajarkan bagaimana melakukan hal tersebut secara digital dengan Arduino Nano sehingga tidak perlu melakukan penggantian kabel secara manual.

Bagaimana caranya?

Mari kita simak bersama ya, teman-teman.

## Mulai Beraksi 🚀

Baik, sebelum mulai beraksi, pastikan teman-teman sudah membaca Prasyarat, Target Pelajaran, dan Komponen Yang Dibutuhkan ya.

Klik pada salah satu dari ketiga tombol di bawah ini untuk membuka Prasyarat, Target Pelajaran dan Komponen Yang Dibutuhkan.

<Tabs className="unique-tabs">
<TabItem value="Prasyarat 🔑">

- Sudah lolos Tutorial 1 - Blink
- Sudah mempelajari Arduino Nano Expansion Board pada materi **[Arduino Nano Expansion Board](/docs/tutorial-arduino/arduino-hardware#arduino-nano-expansion-board)**

Kalau teman-teman merasa belum memenuhi prasyarat yang dibutuhkan, diharapkan untuk membaca dan memenuhinya terlebih dahulu.

</TabItem>

<TabItem value="Target Pelajaran 🎯">

- Memahami konsep kelistrikan dasar
- Memahami bagaimana menggunakan pin digital Arduino Nano
- Mengenali fisik lampu LED
- Mengenali deklarasi variabel

</TabItem>

<TabItem value="Komponen Yang Dibutuhkan 🛠">

- 1 x Arduino Nano
- 1 x Kabel USB Arduino Nano
- 1 x Komputer/Laptop
- 4 x Kabel Jumper Male-Male
- 1 X Modul LED Lampu Lalu Lintas Mini

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

Setelah Arduino Nano terhubung dengan laptop, seharusnya Arduino Nano teman-teman akan menyala. Kemudian lanjut ke langkah berikutnya untuk memeriksa konduktivitas kabel.

### Memeriksa Konduktivitas Kabel

Sebelum memulai pelajaran elektronika dasar hingga mengetik program, penting untuk memeriksa konduktivitas kabel jumper terlebih dahulu untuk membantu proses mengeliminasi kabel jumper yang rusak dan tidak dapat menghantarkan listrik. Kita berikan gambar kabel jumper di bawah ini ya.

<p align="center" width="100%">

<img
width="45%"
src={require('./img/img2/tutorial-2-cable-jumpers.png').default}
alt="Ultrasonic Sensors"
/>

</p>

Konduktivitas Kabel adalah kemampuan suatu kabel untuk dapat menghantarkan arus listrik. Apabila konduktivitas suatu kabel buruk, maka kabel tersebut dianggap rusak dan tidak dapat menghantarkan arus listrik. Peluang kabel jumper yang rusak biasanya kita akan menemukan 1 kabel rusak dari 100 kabel yang bagus, namun tetap saja kita perlu memeriksa konduktivitas kabel tersebut terlebih dahulu.

Ikuti langkah-langkah berikut untuk memeriksa konduktivitas kabel jumper satu persatu. Ambil salah satu kabel jumper yang akan diperiksa konduktivitasnya.

Selagi Arduino Nano menyala dan terhubung dengan laptop, hubungkan Modul Lampu Lalu Lintas Mini (selanjutnya kita akan menyebutnya sebagai Modul LED) sesuai dengan rangkaian pada Wiring Diagram berikut.

<p align="center" width="100%">

<img
width="100%"
src={require('./img/img2/tutorial-2-cable-jumpers-check.png').default}
alt="Ultrasonic Sensors"
/>

</p>

Perhatikan dengan baik label-label pin ketika memasang kabel agar tidak salah ataupun terbalik. Anggaplah garis hitam pada rangkaian di atas sebagai kabel jumper. Pemasangan kabel pada label pin yang tidak sesuai dengan Wiring Diagram dapat berpotensi memicu kerusaskan pada salah satu komponen.

Hasil Wiring Diagram di atas akan tampak seperti pada gambar di bawah ini. Perhatikan bahwa pin berlabel GND pada Arduino Nano Expansion Board terhubung ke pin berlabel GND pada Modul LED.

<p align="center" width="100%">

<img
width="100%"
src={require('./img/img2/tutorial-2-cable-jumpers-check-2.jpg').default}
alt="Ultrasonic Sensors"
/>

</p>

:::info Sekadar Informasi

Warna kabel jumper pada gambar di atas dengan warna kabel jumper yang teman-teman miliki mungkin berbeda. Dan itu tidak masalah. Teman-teman hanya perlu memperhatikan kemana kabel nya ditancapkan. Pastikan agar sesuai dengan perintah pada Wiring Diagram.

:::

Berikutnya hubungkan pin G Modul LED pada pin 5V Arduino Nano Expansion Board seperti pada Wiring Diagram berikut. Huruf G pada label pin G merupakan singkatan dari kata Green yang artinya warna Hijau karena terhubung ke lampu warna hijau.

<p align="center" width="100%">

<img
width="100%"
src={require('./img/img2/tutorial-2-cable-jumpers-check-3.png').default}
alt="Ultrasonic Sensors"
/>

</p>

Patut diingat, label huruf G bisa saja dianggap sebagai pin Ground seperti pada Arduino Nano Expansion Board. Namun khusus pada Modul LED, pin Ground diberi label GND.
Sedangkan pin dengan label G merupakan singkatan dari kata bahasa Inggris Green karena terhubung dengan kaki positif lampu LED warna Hijau.

Hasil rangkaian asli menurut Wiring Diagram akan tampak seperti pada gambar berikut. Perhatikan kedua ujung kabel merah di bawah. Kabel jumper merah tersebut menghubungkan pin 5V pada Arduino Nano Expansion Board dengan pin G pada Modul LED.

<p align="center" width="100%">

<img
width="100%"
src={require('./img/img2/tutorial-2-cable-jumpers-check-4.jpg').default}
alt="Ultrasonic Sensors"
/>

</p>

Apabila lampu LED hijau tampak menyala, maka dapat dikatakan kabel jumper coklat maupun kabel jumper merah memiliki konduktivitas yang baik dan tidak rusak.

Ulangi langkah-langkah sebelumnya dengan mengganti kabel yang terhubung pada pin G Modul LED ke pin 5V Arduino Nano Expansion Board dengan kabel jumper warna lainnya yang tersisa seperti pada gambar berikut.

<p align="center" width="100%">

<img
width="100%"
src={require('./img/img2/tutorial-2-cable-jumpers-check-5.jpg').default}
alt="Ultrasonic Sensors"
/>

</p>

Berdasarkan hasil pengamatan, kabel jumper warna kuning dikatakan memiliki konduktivitas yang baik dan tidak rusak karena lampu hijau tetap menyala.

<p align="center" width="100%">

<img
width="100%"
src={require('./img/img2/tutorial-2-cable-jumpers-check-6.jpg').default}
alt="Ultrasonic Sensors"
/>

</p>

Kabel jumper warna ungu dikatakan memiliki konduktivitas yang baik dan tidak rusak karena lampu hijau tetap menyala.

Sebagai catatan, warna kabel jumper yang teman-teman dapatkan mungkin berbeda dengan gambar di atas. Oleh karenanya perlu dicoba setiap warna kabel jumper yang teman-teman dapatkan dalam kotak kit.

Lakukan langkah di atas hingga semua kabel jumper telah diperiksa konduktivitasnya. Dan sisihkan kabel yang rusak agar dapat diganti/ditukarkan.
Setelah selesai memeriksa konduktivitas semua kabel, lanjutkan ke langkah berikutnya.

### Menghubungkan Pin-Pin

:::caution Peringatan
**Sebelum merangkai kabel-kabel, matikan terlebih dahulu Arduino Nano dengan cara melepaskan kabel USB dari Arduino Nano jika masih terhubung dengan laptop/komputer.**
:::

Gunakan Wiring Diagram/rangkaian di bawah ini untuk menghubungkan kabel-kabel jumper.

| Modul LED | Arduino Nano Expansion Board |
| :-------: | :--------------------------: |
|  Pin GND  |            Pin G             |
|   Pin R   |            Pin 4             |
|   Pin R   |            Pin 5             |
|   Pin R   |            Pin 6             |

<p align="center" width="100%">

<img
width="80%"
src={require('./img/img2/tutorial-2-main-wiring-diagram.png').default}
alt="Ultrasonic Sensors"
/>

</p>

:::danger Peringatan
Sebelum menyalakan kembali Arduino Nano, harap periksa kembali rangkaiannya. Apakah sudah sama dengan Wiring Diagram di atas?
Periksa kembali kabel-kabel jumper agar tidak ada kesalahan yang dapat berpotensi merusak komponen ataupun mengganggu pelajaran.
:::

### Mengetik Program

1. Bukalah Arduino IDE, kemudian buatlah sketch baru. Beri sketch baru tersebut dengan nama TUTORIAL_2_TRAFFIC_LIGHT_LED_MODULE dan simpan dalam folder TUTORIAL PROGRAMS yang telah kita buat pada Tutorial 1 sebelumnya. Jika terlupa bagaimana membuat nama sketch, silahkan buka kembali Tutorial 1 sebelumnya.

<p align="center" width="100%">

<img
width="80%"
src={require('./img/img2/tutorial-2-arduino-ide-new-sketch.png').default}
alt="Ultrasonic Sensors"
/>

</p>

2. Kemudian ketik program berikut pada sketch tersebut.

```arduino title="TUTORIAL_2_TRAFFIC_LIGHT_LED_MODULE.ino" showLineNumbers
int R=4; //deklarasikan variabel R sebagai pin 4
int Y=5; //deklarasikan variabel Y sebagai pin 5
int G=6; //deklarasikan variabel G sebagai pin 6

void setup() {
  //tugaskan variabel R, Y, dan G sebagai OUTPUT
  pinMode(R, OUTPUT);
  pinMode(Y, OUTPUT);
  pinMode(G, OUTPUT);
}

// the loop function runs over and over again forever
void loop() {
  digitalWrite(R, HIGH); //beri logika HIGH ke pin R
  digitalWrite(Y, HIGH); //beri logika HIGH ke pin Y
  digitalWrite(G, HIGH); //beri logika HIGH ke pin G
  delay(1000);
  digitalWrite(R, LOW); //beri logika HIGH ke pin R
  digitalWrite(Y, LOW); //beri logika HIGH ke pin Y
  digitalWrite(G, LOW); //beri logika HIGH ke pin G
  delay(1000);
}
```

3. Periksa kembali ketikan sketch program. Pastikan agar ketikan sketch program sama persis seperti diminta agar tidak mengalami error saat compiling. Jika sudah selesai mengetik program, cobalah memeriksa apakah ketikan Anda sudah benar atau belum dengan cara menekan tombol verify atau ikon di samping 👉 <img src={require('./img/arduino-ide-tool-bar-verify.png').default} alt="Ultrasonic Sensors"/>.

4. Jika proses verify selesai dan information bar menunjukkan “Done compiling”, berarti program yang teman-teman ketik sudah benar dan lanjutkan pada langkah berikutnya.

<p align="center" width="100%">

<img
width="80%"
src={require('./img/img2/tutorial-2-arduino-ide-sketch-done-compiling.png').default}
alt="Ultrasonic Sensors"
/>

</p>

### Mengkonfigurasi Arduino IDE

Sebelum mengupload program, sama seperti pada Tutorial 1, mari kita melakukan konfigurasi terlebih dahulu pada Arduino IDE.

5. Memilih Jenis Board

Pastikan jenis board yang digunakan sudah sesuai dengan settingan pada Arduino IDE dengan cara memilih opsi berikut secara berurutan Tools ➜ Board ➜ Arduino Nano atau perhatikan urutan tanda panah pada gambar di bawah ini. Disini kita memilih Arduino Nano karena kita menggunakan Arduino Nano.

<p align="center" width="100%">

<img width="80%" src={require('./img/img2/tutorial-2-arduino-ide-choose-board.png').default} alt="Ultrasonic Sensors"/>

</p>

6. Memilih Jenis Processor

Processor dalam bahasa Indonesia berarti Prosessor, atau Pemroses sebuah perintah, singkatnya seperti otak dari robot. Disini kita akan menentukan jenis Processor yang digunakan oleh Arduiino Nano, yaitu ATMega328P (Old Bootloader), dengan cara memilih opsi berikut secara berurutan Tools ➜ Processor ➜ ATmega328P (Old Bootloader). Atau ikuti urutan tanda panah pada gambar di bawah ini

<p align="center" width="100%">

<img width="80%" src={require('./img/img2/tutorial-2-arduino-ide-choose-processor.png').default} alt="Ultrasonic Sensors"/>

</p>

7. Memilih Nomor Port

Nomor port untuk Arduino Nano pada tiap laptop/komputer dapat berbeda-beda. Pilihlah nomor port yang muncul pada pilihan yang tersedia di Arduino IDE. Lebih jelasnya, perhatikan gambar di bawah.

<p align="center" width="100%">

<img width="80%" src={require('./img/img2/tutorial-2-arduino-ide-choose-port.png').default} alt="Ultrasonic Sensors"/>

</p>

### Mengupload Program

Setelah proses verifikasi teman-teman sudah berhasil dan konfigurasi Arduino IDE sudah selesai, saatnya kita mengupload program. Mengupload Program sama seperti kita menulis sebuah surat lalu mengantarkan surat tersebut kepada orang lain. Ketika kita sudah selesai menulis atau mengetik program, kita mengantarkan program tersebut ke Arduino Nano. Proses mengantarkan program tersebut disebut sebagai "Upload".

23. Setelah proses konfigurasi selesai seperti yang diperintahkan, lanjutkan dengan mengklik tombol upload <img src={require('./img/arduino-ide-tool-bar-upload.png').default} alt="Ultrasonic Sensors"/> pada Arduino IDE.

<p align="center" width="100%">

<img width="80%" src={require('./img/img2/tutorial-2-arduino-ide-upload.png').default} alt="Ultrasonic Sensors"/>

</p>

24. Tunggulah beberapa. Setelah proses upload selesai, information bar akan menunjukkan pesan “Done uploading” yang berarti proses upload telah selesai

<p align="center" width="100%">

<img width="80%" src={require('./img/img2/tutorial-2-arduino-ide-upload-done.png').default} alt="Ultrasonic Sensors"/>

</p>

Jika proses upload berhasil, perhatikan ketiga lampu LED pada Modul LED. Ketiga lampu LED tersebut akan berkedip setiap 1 detik sesuai yang diperintahkan oleh program yang telah ditulis.

<p align="center" width="100%">

<img width="80%" src={require('./img/img2/tutorial-2-led-module-blinking.jpg').default} alt="Ultrasonic Sensors"/>

</p>

Selanjutnya kita akan masuk ke topik Penjelasan Program

<br/>

## Penjelasan Program

Sama seperti pada Tutorial 1, pada akhir Tutorial 2 akan diberi tantangan. Namun sebelumnya mari kita pahami terlebih dahulu program yang kita gunakan pada Tutorial 2 ini.

```arduino title="TUTORIAL_2_TRAFFIC_LIGHT_LED_MODULE.ino" showLineNumbers
int R=4; //deklarasikan variabel R sebagai pin 4
int Y=5; //deklarasikan variabel Y sebagai pin 5
int G=6; //deklarasikan variabel G sebagai pin 6

void setup() {
  //tugaskan variabel R, Y, dan G sebagai OUTPUT
  pinMode(R, OUTPUT);
  pinMode(Y, OUTPUT);
  pinMode(G, OUTPUT);
}

// the loop function runs over and over again forever
void loop() {
  digitalWrite(R, HIGH); //beri logika HIGH ke pin R
  digitalWrite(Y, HIGH); //beri logika HIGH ke pin Y
  digitalWrite(G, HIGH); //beri logika HIGH ke pin G
  delay(1000);
  digitalWrite(R, LOW); //beri logika HIGH ke pin R
  digitalWrite(Y, LOW); //beri logika HIGH ke pin Y
  digitalWrite(G, LOW); //beri logika HIGH ke pin G
  delay(1000);
}
```

Pada sketch program di atas, memiliki tiga bagian utamam yakni bagian deklarasi variabel, bagian fungsi `setup()`, dan bagian fungsi `loop()`.
Kita akan membahas bagian pertama terlebih dahulu, yakni bagian deklarasi variabel yang ditunjukkan oleh potongan sketch program pada gambar di bawah.

<p align="center" width="100%">

<img width="100%" src={require('./img/img2/tutorial-2-arduino-ide-program-exp-1.png').default} alt="Ultrasonic Sensors"/>

</p>

Deklarasi variabel adalah proses untuk membuat dan mengenalkan sebuah variabel dengan nama variabel dan tipe variabel yang diinginkan kepada Arduino IDE. Analogi deklarasi variabel akan seperti Soekarno mendeklarasikan kemerdekaan negara bernama Republik Indonesia kepada dunia, kita akan mendeklarasikan variabel dengan nama yang kita inginkan kepada Arduino IDE.

Contoh lainnya, jika ada anak bernama Nina menyimpan kucing peliharaan baru dengan nama Mimi, Nina akan memberitahu orangtuanya bahwa Nina menyimpan hewan peliharaan baru yakni seekor kucing yang bernama Mimi.

Dengan analogi tersebut, kita akan mengganggap orangtua Nina sebagai Arduino IDE, Mimi adalah nama variabel, dan Nina adalah nama pemilik variabel, jenis hewan peliharaan sebagai tipe data variabel.

Tipe data variabel dapat Arduino IDE dapat bervariasi. Dengan analogi sebelumnya, jika kita menganggap tipe data adalah jenis hewan peliharaan, maka kita bisa menggunakan hewan anjing, kelinci, dan marmut. Jika tipe datanya adalah hewan ternak, kita bisa menggunakan ayam, sapi, kambing. Jika tipe datanya adalah sayuran, kita bisa menggunakan kangkung, bayam, wortel.

Tipe data dalam Arduino IDE ada beragam, yakni int, float, char, double dan sebagainya. Pada potongan kode di atas, tipe data yang digunakan adalah int.

Pada Tutorial ini akan dikhususkan membahas tipe data int terlebih dahulu. Tipe data int (singkatan dari kata Integer) merupakan tipe data yang dikhususkan untuk menampung bilangan bulat positif.

Bilangan bulat adalah bilangan yang dapat dituliskan tanpa komponen pecahan atau desimal. Sebagai contoh tipe data int hanya dapat menampung bilangan bulat positif seperti 1, 2, 29, 192, atau 1294 dan sebagainya.

Jika menggunakan bilangan terdapat tanda minus atau pecahan desimal seperti -1, -2, 2.9, 19.2, 129.4 untuk disimpan dalam variabel bertipe data int, maka variabel tersebut hanya akan menyimpan angka positif dan angka pertama dari contoh bilangan tersebut seperti 1, 2, 2, 19, 129.

Kita lihat kembali potongan kode sebelumnya.

<p align="center" width="100%">

<img width="100%" src={require('./img/img2/tutorial-2-arduino-ide-program-exp-2.png').default} alt="Ultrasonic Sensors"/>

</p>

Deklarasi variabel umumnya harus dilakukan sebelum fungsi `setup()`. Sama seperti Nina harus mendeklarasikan kucing miliknya kepada orangtua terlebih dahulu sebelum masuk rumah.

Pada baris pertama potongan kode di atas, terdapat variabel dengan nama variabel `R` dan bertipe data `int` yang menyimpan angka `4`.

Dengan menggunakan analogi kucing peliharaan Nina sebelumnya, Arduino IDE akan mengganggap bahwa `R` adalah nama orang yang menyimpan angka `4` yang merupakan seekor hewan peliharaan bertipe data `int`.

Atau dengan kata lain, Arduino IDE akan menganggap `R` merupakan nama variabel bertipe data int yang menyimpan angka `4`. Singkatnya sih, sekarang huruf R akan dianggap sebagai angka 4 oleh Arduino IDE.

Nama variabel bisa ditentukan dengan bebas sesuai keinginan kita seperti `merah`, `PinRed`, `pinred`, `PINMERAH`, `lampumerah`, `LEDmerah` dan sebagainya. Namun perlu diingat penamaan variabel tidak boleh dipisah menggunakan spasi seperti `Pin Red`, `pin red`, `PIN MERAH`, `lampu merah`, `LED merah`.

Selain itu nama variabel bersifat case sensitive alias peka terhadap perbedaan huruf kapital. Dimana jika kita mendeklarasikan `Nina` sebagai pemilik angka `4` di awal program sebelum fungsi `setup()`, kemudian kita memanggil `nina` dalam fungsi `loop()`, maka Arduino IDE tidak akan mengenalinya, karena `Nina` dan `nina` adalah nama dua variabel atau dua anak yang berbeda. Bisakah teman-teman menemukan perbedaan antara `Nina` dan `nina`? Perbedaannya terletak pada huruf N besar dan huruf n kecil pada awal nama.

Sedangkan angka `4` disini dipilih karena kita akan menghubungkan pin R Modul LED pada pin digital nomor 4 pada Arduino Nano Expansion Board.

Angka yang ingin disimpan dapat kita tentukan dengan bebas sesuai dengan nomor pin yang ingin kita gunakan pada Arduino Nano Expansion Board.

Kemudian tipe data dapat dipiilih berdasarkan jenis bilangan yang ingin disimpan. Sebagai contoh di atas, karena kita menggunakan angka `4` yang merupakan bilangan bulat, oleh karenanya kita menggunakan tipe data `int`.

<p align="center" width="100%">

<img width="100%" src={require('./img/img2/tutorial-2-arduino-ide-program-exp-1.png').default} alt="Ultrasonic Sensors"/>

</p>

Bagian deklarasi variabel sendiri menempati baris 1 hingga 3 karena kita harus mendeklarasikan 3 buah variabel berbeda untuk tiap-tiap pin digital yang ingin kita gunakan.

Selanjutnya kita akan membahas bagian fungsi `setup()`. Potongan fungsi `setup()` akan ditampilkan pada gambar berikut:

<p align="center" width="100%">

<img width="100%" src={require('./img/img2/tutorial-2-arduino-ide-program-exp-3.png').default} alt="Ultrasonic Sensors"/>

</p>

Fungsi `setup()` dimulai dengan tanda kurawal buka `{` pada baris 5. Pada baris 6 terdapat komentar yang dimulai dengan tanda `//`.

Fungsi komentar tersebut adalah pesan dari pembuat sketch program kepada pembaca untuk memberitahu bahwa fungsi `setup()` tersebut akan menugaskan nomor pin yang tersimpan dalam variabel `R`, `Y`, dan `G` sebagai pin untuk memberikan sinyal keluaran dengan cara menjadikannya `OUTPUT` dengan perintah `pinMode()`.

Arduino IDE akan menganggap angka yang tersimpan dalam variabel `R`, `Y`, dan `G` sebagai nomor pin yang akan ditugaskan sebagai pin `OUTPUT` untuk memberikan sinyal logika `HIGH` atau `LOW`.

Singkatnya, karena kita telah menyimpan angka `4` dalam variabel `R` pada bagian deklarasi variabel seperti ditunjukkan oleh potongan kode baris 1 di bawah, maka Arduino IDE akan mengganggap variabel `R` sebagai angka `4`.

<p align="center" width="100%">

<img width="100%" src={require('./img/img2/tutorial-2-arduino-ide-program-exp-2.png').default} alt="Ultrasonic Sensors"/>

</p>

Sehingga baris 7 kode di bawah juga akan mengganggap `R` sebagai angka `4` yang merupakan pin digital Arduino Nano nomor 4.

<p align="center" width="100%">

<img width="100%" src={require('./img/img2/tutorial-2-arduino-ide-program-exp-4.png').default} alt="Ultrasonic Sensors"/>

</p>

Terdapat tiga buah perintah `pinMode()` yang digunakan. Hal ini karena terdapat tiga buah variabel yang harus ditugaskan sebagai pin keluaran dengan parameter `OUTPUT`.

Fungsi `setup()` diakhiri dengan tanda kurawal tutup `]` pada baris 10.

Selanjutnya kita akan membahas bagian fungsi `loop()`. Potongan kode `loop()` ditunjukkan pada gambar di bawah. Fungsi `loop()` dimulai dengan tanda kurawal buka `{` pada baris 13.

<p align="center" width="100%">

<img width="100%" src={require('./img/img2/tutorial-2-arduino-ide-program-exp-5.png').default} alt="Ultrasonic Sensors"/>

</p>

Pada baris 14 terdapat perintah `digitalWrite()` yang memerintahkan untuk memberikan sinyal logika `HIGH` kepada pin `R`. Ingat kembali bahwa variabel `R` menyimpan angka `4` yang merupakan pin digital Arduino Nano nomor `4`.

Pin digital Arduino Nano nomor 4 terhubung dengan pin R Modul LED. Sehingga apabila sinyal logika `HIGH` diberikan dari pin Arduino Nano nomor 4 kepada pin R Modul LED, maka lampu merah pada Modul LED akan menyala.

Pin digital Arduino Nomor 4 ini telah ditugaskan sebagai pin OUTPUT sebelumnya dalam fungsi `setup()`. Apabila pin digital memberikan sinyal logika `HIGH`, dengan kata lain pin digital tersebut mengeluarkan tegangan 5 Volt sehingga lampu merah pada Modul LED dapat menyala karena mendapat tegangan listrik sebesar 5 Volt.

Hal ini berlaku juga untuk variabel `Y` dan `G`. Dimana variabel `Y` menyimpan angka 5 yang merupakan pin digital Arduino Nano nomor 5 dan terhubung dengan pin `Y` Modul LED. Dan variabel `G` menyimpan angka 6 yang merupakan pin digital Arduino Nano nomor 6 dan terhubung dengan pin G Modul LED.

<p align="center" width="100%">

<img width="100%" src={require('./img/img2/tutorial-2-arduino-ide-program-exp-6.png').default} alt="Ultrasonic Sensors"/>

</p>

Kemudian pada baris 17 terdapat perintah `delay()` dengan nilai parameter 1000 milisecond (1 detik). Baris 17 tersebut akan membuat baris 14, 15, dan 16 di atasnya akan tertahan/tertunda selama 1 detik.

Dengan kata lain, lampu merah, lampu kuning, dan lampu hijau pada Modul LED akan menyala selama 1 detik.

Begitu delay 1 detik telah selesai, akan dilanjutkan mengeksekusi program pada baris 18 seperti ditunjukkan oleh potongan kode di bawah.

<p align="center" width="100%">

<img width="100%" src={require('./img/img2/tutorial-2-arduino-ide-program-exp-7.png').default} alt="Ultrasonic Sensors"/>

</p>

Terdapat perintah `digitalWrite()` yang memerintahkan untuk memberikan sinyal logika `LOW` kepada pin R. Ingat kembali bahwa pin R merupakan pin digital Arduino Nano nomor 4 yang terhubung dengan pin R Modul LED.

Apabila pin digital Arduino Nano nomor 4 tersebut memberikan sinyal logika `LOW`, dengan kata lain pin digital tersebut mengeluarkan tegangan 0 Volt sehingga lampu merah pada Modul LED padam karena tegangan listrik yang diberikan terlalu kecil untuk dapat menyalakan lampu merah.

Baris 19 dan baris 20 memiliki fungsi yang sama dengan baris 18, yakni memberikan sinyal logika `LOW` pada pin `Y` dan pin `G`. Sinyal `LOW` ini akan menyebabkan lampu kuning dan hijau ikut padam.

Kemudian pada baris 21 terdapat perintah `delay()` untuk menunda selama 1 detik hasil eksekusi baris di atasnya, yakni baris 18, 19, dan 20. Sehingga menyebabkan ketiga lampu akan padam selama 1 detik.

Kemudian setelah perintah `delay()` pada baris 21 telah selesai dijalankan selama 1 detik, akan dilanjutkan kembali ke atas pada awal mula fungsi `loop()` yang terdapat pada baris 14.

Hal ini karena setelah perintah `delay()` pada baris 21, akan bertemu dengan tanda kurawal tutup `}` yang terletak pada baris 22 yang merupakan akhir dari fungsi `loop()`. Apabila telah mencapai akhir fungsi `loop()` pada baris 22, maka fungsi loop() akan kembali lagi ke baris 13. Dan berulang-ulang secara terus menerus selama Arduino Nano menyala.

Sampai sini Penjelasan Program. Mari kita masuk ke topik Tantangan agar lebih paham dengan programnya.

<br/>

## Tantangan Tutorial 2 🕹

### Tantangan 1

Tantangan pertama ini akan membuat teman-teman sedikit lebih paham dengan urutan program yang berulang-ulang pada fungsi `loop()`. Ubahlah kode program yang teman-teman gunakan pada awal Tutorial 2 tadi menjadi seperti di bawah ini.

```arduino title="TUTORIAL_BLINK_2.ino" showLineNumbers
int R=4; //deklarasikan variabel R sebagai pin 4

void setup() {
  //tugaskan variabel R, Y, dan G sebagai OUTPUT
  pinMode(R, OUTPUT);
}

// the loop function runs over and over again forever
void loop() {
  digitalWrite(R, HIGH); //beri logika HIGH ke pin R
  delay(1000);
}
```

Kemudian upload sketch tersebut ke Arduino Nano. Perhatikan apa yang terjadi. Pada Modul LED seharusnya hanya lampu merah saja yang akan menyala tanpa berkedip dan lampu kuning dan lampu hijau sisanya akan mati.

Mengapa? karena dalam perulangan fungsi `loop()`, fungsi loop() hanya mengulangi perintah `digitalWrite()` untuk memberi logika `HIGH` pada pin `R` sehingga lampu merah akan menyala secara terus menerus tanpa padam.

Bagaimana kalau teman-teman mengganti logika `HIGH` tersebut menjadi `LOW`? Tentunya lampu merah akan padam selamanya.

Sekarang Tantangan untuk teman-teman, cobalah menyalakan lampu merah dan lampu hijau secara bersamaan terus menerus sementara lampu kuning tetap padam.

Petunjuk: tambahkan deklarasi variabel pin lampu hijau.

### Tantangan 2

Setelah melewati Tantangan 1, saatnya melanjutkan ke Tantangan 2. Ketiklah sketch berikut ini.

```arduino title="TUTORIAL_BLINK_2.ino" showLineNumbers
int R=2; //deklarasikan variabel R sebagai pin 4
int Y=3; //deklarasikan variabel Y sebagai pin 5
int G=4; //deklarasikan variabel G sebagai pin 6

void setup() {
  //tugaskan variabel R, Y, dan G sebagai OUTPUT
  pinMode(R, OUTPUT);
  pinMode(Y, OUTPUT);
  pinMode(G, OUTPUT);
}

// the loop function runs over and over again forever
void loop() {
  digitalWrite(R, HIGH); //beri logika HIGH ke pin R
  digitalWrite(Y, LOW); //beri logika HIGH ke pin Y
  digitalWrite(G, HIGH); //beri logika HIGH ke pin G
  delay(1000);
  digitalWrite(R, LOW); //beri logika HIGH ke pin R
  digitalWrite(Y, HIGH); //beri logika HIGH ke pin Y
  digitalWrite(G, LOW); //beri logika HIGH ke pin G
  delay(1000);
  digitalWrite(R, LOW); //beri logika HIGH ke pin R
  digitalWrite(Y, LOW); //beri logika HIGH ke pin Y
  digitalWrite(G, HIGH); //beri logika HIGH ke pin G
  delay(1000);
}
```

Hasil dari sketch di atas akan membuat lampu pada Modul LED berjalan dengan pola berikut:

- Detik pertama: lampu merah dan lampu hijau menyala, lampu kuning mati.
- Detik kedua: lampu merah dan lampu hijau mati, lampu kuning menyala.
- Detik ketiga: lampu merah dan lampu kuning mati, lampu hijau menyala.

Secara singkat dapat digambarkan dalam kotak merah yang kita sebut blok penyalaan pada gambar berikut:

<p align="center" width="100%">

<img width="100%" src={require('./img/img2/tutorial-2-arduino-ide-program-exp-8.png').default} alt="Ultrasonic Sensors"/>

</p>

Dalam blok penyalaan tersebut terdapat 1 buah baris perintah delay dan 3 buah baris yang menggunakan perintah `digitalWrite()` karena terdapat 3 buah lampu yang ingin dinyalakan dalam satu waktu.

<p align="center" width="100%">

<img width="100%" src={require('./img/img2/tutorial-2-arduino-ide-program-exp-9.png').default} alt="Ultrasonic Sensors"/>

</p>

<p align="center" width="100%">

<img width="50%" src={require('./img/img2/tutorial-2-led-module-blinking-red-yellow.jpg').default} alt="Ultrasonic Sensors"/>

</p>

<p align="center" width="100%">

<img width="100%" src={require('./img/img2/tutorial-2-arduino-ide-program-exp-10.png').default} alt="Ultrasonic Sensors"/>

</p>

<p align="center" width="100%">

<img width="50%" src={require('./img/img2/tutorial-2-led-module-blinking-yellow.jpg').default} alt="Ultrasonic Sensors"/>

</p>

<p align="center" width="100%">

<img width="100%" src={require('./img/img2/tutorial-2-arduino-ide-program-exp-11.png').default} alt="Ultrasonic Sensors"/>

</p>

<p align="center" width="100%">

<img width="50%" src={require('./img/img2/tutorial-2-led-module-blinking-green.jpg').default} alt="Ultrasonic Sensors"/>

</p>

Pola yang dihasilkan oleh sketch program di atas bukanlah pola yang sama persis dengan pola lampu lalu lintas pada umumnya. Sehingga teman-teman harus memperbaiki urutan pola tersebut agar sesuai dengan pola pada lalu lintas umumnya.

Disinilah Tantangan 2, teman-teman harus mengatur sketch tersebut agar sesuai dengan pola berikut:

Lampu merah menyala 3 detik. Lampu kuning dan lampu hijau mati.

<p align="center" width="100%">

<img width="50%" src={require('./img/img2/tutorial-2-led-module-blinking-challenge-2-1.jpg').default} alt="Ultrasonic Sensors"/>

</p>

Lampu kuning menyala 1 detik. Lampu merah dan lampu hijau mati.

<p align="center" width="100%">

<img width="50%" src={require('./img/img2/tutorial-2-led-module-blinking-challenge-2-2.jpg').default} alt="Ultrasonic Sensors"/>

</p>

Lampu hijau menyala 2 detik. Lampu merah dan lampu kuning mati.

<p align="center" width="100%">

<img width="50%" src={require('./img/img2/tutorial-2-led-module-blinking-challenge-2-3.jpg').default} alt="Ultrasonic Sensors"/>

</p>

Petunjuk Tantangan 2:

- Mainkan angka delay pada program.
- Mainkan urutan logika parameter `HIGH` dan `LOW` pada perintah `digitalWrite()`
