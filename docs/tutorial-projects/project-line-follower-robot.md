---
sidebar_position: 7
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Line Follower Robot 👋

## Perkenalan

<div width="100%" style={{textAlign: 'center'}}>

![Docs Version Dropdown](./img/project-line-follower-robot.png)

</div>

Pada project sebelumnya, kita sudah membuat robot yang bisa mengikuti sumber cahaya. Pada project sebelumnya kita menggunakan Sensor Cahaya atau bisa disebut juga sebagai Sensor LDR untuk mendeteksi keberadaan cahaya.

Pada project kali ini, kita akan membuat robot yang bisa bergerak mengikuti garis hitam di atas lantai putih. Untuk mendeteksi keberadaan garis hitam di atas lantai putih, kita akan menggunakan Sensor Infra Merah pada project ini.

## Alat dan Komponen yang diperlukan

<Tabs className="unique-tabs">
<TabItem value="Alat 🛠">

- Obeng Plus

</TabItem>

<TabItem value="Komponen Yang Dibutuhkan 🔑">

- 1 x Arduino Nano
- 1 x Kabel USB Arduino Nano
- 1 x Komputer/Laptop
- 1 x Sensor Jarak Ultrasonik
- 1 x Driver Motor
- 2 X Motor DC + Ban
- 1 x Kotak Baterai 2 Slot
- 2 x Baterai
- Baut seperlunya
- Kabel Jumper seperlunya

</TabItem>
</Tabs>

## Petunjuk Merakit

### ◼️ Merakit Komponen Utama

#### ▪️ Memasang Dudukan Motor ke Rangka Utama

1. Siapkan dua buah Dudukan Motor dan Rangka Utama seperti pada gambar di bawah ini.
   <p align="center" width="100%">

   <img width="50%" src={require('./img/img-project-obstacle-avoider-robot/poar-1.png').default} alt="Ultrasonic Sensors"/>

   <img width="50%" src={require('./img/img-project-obstacle-avoider-robot/poar-2.png').default} alt="Ultrasonic Sensors"/>

   </p>

2. Kemudian ambil salah satu dari dudukan motor. Kita akan memasang untuk sisi kiri terlebih dahulu. Pasangkan dudukan motor pada rangka utama dengan posisi seperti pada gambar di bawah ini.
   <p align="center" width="100%">

   <img width="50%" src={require('./img/img-project-obstacle-avoider-robot/poar-3.png').default} alt="Ultrasonic Sensors"/>

   <img width="50%" src={require('./img/img-project-obstacle-avoider-robot/poar-4.png').default} alt="Ultrasonic Sensors"/>

   </p>

3. Selanjutnya kita akan memasang untuk sisi kanan. Pasangkan dudukan motor pada rangka utama dengan posisi seperti pada gambar di bawah ini.
   <p align="center" width="100%">

   <img width="50%" src={require('./img/img-project-obstacle-avoider-robot/poar-5.png').default} alt="Ultrasonic Sensors"/>

   <img width="50%" src={require('./img/img-project-obstacle-avoider-robot/poar-6.png').default} alt="Ultrasonic Sensors"/>

   </p>

#### ▪️ Memasang Motor Kiri

4. Setelah kedua dudukan motor terpasang, selanjutnya kita akan memasang motor kiri. Siapkan terlebih dahulu motor DC seperti ditunjukkan pada gambar di bawah ini.
   <p align="center" width="100%">

   <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-7.png').default} alt="Ultrasonic Sensors"/>

   <br/>
   Sebelumnya, pastikan titik tengah pada motor DC seperti yang ditunjuk oleh tanda panah di bawah ini menghadap atas.

   <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-8.png').default} alt="Ultrasonic Sensors"/>

   </p>

5. Kemudian masukkan baut panjang pada lubang sebelah kanan pada Motor DC seperti ditunjukkan pada gambar di bawah.

   <p align="center" width="100%">

   <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-9.png').default} alt="Ultrasonic Sensors"/>

   <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-10.png').default} alt="Ultrasonic Sensors"/>

   </p>

6. Masukkan baut panjang pada lubang sebelah kiri pada Motor DC seperti ditunjukkan pada gambar di bawah.

   <p align="center" width="100%">

   <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-11.png').default} alt="Ultrasonic Sensors"/>

   <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-12.png').default} alt="Ultrasonic Sensors"/>

   </p>

7. Selanjutnya, kita akan mengencangkan Motor DC pada Dudukan Motor menggunakan baut panjang yang telah kita pasang tadi. Sejajarkan ujung baut panjang pada lubang yang tersedia pada Dudukan Motor DC seperti ditunjukkan pada gambar di bawah ini.

   <p align="center" width="100%">

   <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-13.png').default} alt="Ultrasonic Sensors"/>

   <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-14.png').default} alt="Ultrasonic Sensors"/>

   </p>

8. Selanjutnya, kita akan mengencangkan Motor DC pada Dudukan Motor menggunakan baut panjang yang telah kita pasang tadi. Sejajarkan ujung baut panjang pada lubang yang tersedia pada Dudukan Motor DC seperti ditunjukkan pada gambar di bawah ini.

   <p align="center" width="100%">

   <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-13.png').default} alt="Ultrasonic Sensors"/>

   <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-14.png').default} alt="Ultrasonic Sensors"/>

   </p>

9. Setelah ujung baut panjang sejajar dengan lubang pada Dudukan Motor DC, kencangkan kedua baut tersebut dengan obeng seperti pada gambar di bawah ini.

   <p align="center" width="100%">

   <img width="50%" src={require('./img/img-project-obstacle-avoider-robot/poar-15.png').default} alt="Ultrasonic Sensors"/>

   <img width="50%" src={require('./img/img-project-obstacle-avoider-robot/poar-16.png').default} alt="Ultrasonic Sensors"/>

   <br/>

   Setelah dikencangkan, Motor DC akan tetap diam pada Dudukan Motor seperti pada gambar di bawah ini.
   <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-17.png').default} alt="Ultrasonic Sensors"/>

   </p>

#### ▪️ Memasang Motor Kanan

10. Selanjutnya, kita akan memasang Motor DC pada dudukan kanan. Langkah-langkahnya sama seperti memasang Motor DC kiri sebelumnya. Setelah Motor DC kanan terpasang, hasil akhirnya akan seperti pada gambar di bawah ini.

   <p align="center" width="100%">

    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-18.png').default} alt="Ultrasonic Sensors"/>

    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-19.png').default} alt="Ultrasonic Sensors"/>

   </p>

#### ▪️ Memasang Roda Bebas

11. Langkah berikutnya, kita akan memasang roda bebas, yakni roda yang bebas bergerak ke arah manapun. Siapkan komponen roda bebas seperti yang ditunjukkan pada gambar di bawah.
    <p align="center" width="100%">

    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-20.png').default} alt="Ultrasonic Sensors"/>

   </p>

12. Kemudian kita akan memasang roda bebas tersebut pada sisi bawah rangka utama. Perhatikan baik-baik gambar di bawah.
    <p align="center" width="100%">

    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-21.png').default} alt="Ultrasonic Sensors"/>

    Sejajarkan lubang yang terdapat pada roda bebas dengan lubang yang terdapat pada bagian bawah rangka utama seperti yang ditunjuk oleh tanda panah di bawah.
    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-22.png').default} alt="Ultrasonic Sensors"/>

    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-23.png').default} alt="Ultrasonic Sensors"/>

    Kencangkan roda bebas dengan baut seperti ditunjuk pada gambar di bawah.
    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-24.png').default} alt="Ultrasonic Sensors"/>

   </p>

13. Maka hasil akhirnya akan seperti pada gambar di bawah. Bagian depan rangka utama akan tampak naik karena terdapat roda bebas di bawahnya.
    <p align="center" width="100%">

    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-25.png').default} alt="Ultrasonic Sensors"/>

   </p>

#### ▪️ Memasang Ban

14. Selanjutnya kita akan memasang ban pada Motor DC. Siapkan dua buah ban Motor DC seperti pada gambar di bawah.
    <p align="center" width="100%">

    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-26.png').default} alt="Ultrasonic Sensors"/>

   </p>

15. Kita akan memasang ban nya pada poros Motor DC yang berwarna putih.
     <p align="center" width="100%">

    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-27.png').default} alt="Ultrasonic Sensors"/>

     <br/>
     Namun sebelum itu, perhatikan terlebih dahulu kalau terdapat bentuk yang unik antara poros Motor DC dan poros Ban. Pastikan antara poros Motor DC dan poros Ban sudah sejajar seperti ditandai pada gambar di bawah ini. 
     <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-28.png').default} alt="Ultrasonic Sensors"/>

     <br/>
     Setelah sejajar, doronglah Ban tersebut ke poros Motor DC secara perlahan.
     <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-29.png').default} alt="Ultrasonic Sensors"/>
    </p>

16. Lakukanlah hal yang sama untuk ban sebelah kanan. Jika kedua ban sudah terpasang, maka hasilnya akan seperti pada gambar di bawah ini.

    <p align="center" width="100%">

    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-30.png').default} alt="Ultrasonic Sensors"/>

   </p>

#### ▪️ Memasang Driver Motor

17. Selanjutnya kita akan memasang Driver Motor pada rangka utama. Siapkan 4 buah spacer kertas dan Driver Motor L298N seperti pada gambar di bawah ini.

     <p align="center" width="100%">

    <img width="50%" src={require('./img/img-project-obstacle-avoider-robot/poar-31.png').default} alt="Ultrasonic Sensors"/>

    <img width="50%" src={require('./img/img-project-obstacle-avoider-robot/poar-32.png').default} alt="Ultrasonic Sensors"/>
    </p>

18. Bukalah baut yang sebelumnya masih terpasang pada spacer kertas. Kemudian pasang keempat spacer kertas tersebut pada keempat lubang yang terdapat pada Driver Motor L298N. Hasil akhirnya akan seperti pada gambar di bawah ini yang menunjukkan keempat spacer kertas telah terpasang pada Driver Motor L298N.

     <p align="center" width="100%">

    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-33.png').default} alt="Ultrasonic Sensors"/>

    </p>

19. Setelah memasang keempat spacer kertas pada Driver Motor L298N, selanjutnya kita akan memasangkannya pada rangka utama. Namun sebelum itu, perhatikan terlebih dahulu keempat posisi lubang pada rangka utama untuk memasang Driver Motor L298N di bawah ini.
     <p align="center" width="100%">

    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-34.png').default} alt="Ultrasonic Sensors"/>

    <br/>
    Tancapkan dan sejajarkan ujung tajam spacer kertas pada keempat lubang tersebut dengan posisi seperti ditunjukkan pada gambar di bawah ini.

    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-35.png').default} alt="Ultrasonic Sensors"/>

    <br/>
    Apabila sudah keempat lubang sudah sejajar dengan keempat ujung spacer kertas, tekanlah hingga ujung spacer kertas terbenam sepenuhnya.

    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-36.png').default} alt="Ultrasonic Sensors"/>

    </p>

20. Hasil akhir apabila Driver Motor L298N telah terpasang pada rangka utama akan seperti pada gambar di bawah ini.
     <p align="center" width="100%">

    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-37.png').default} alt="Ultrasonic Sensors"/>

    </p>

#### ▪️ Memasang Kotak Baterai

20. Selanjutnya kita akan memasang kotak baterai pada rangka utama. Siapkan komponen di bawah ini.
     <p align="center" width="100%">

    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-38.png').default} alt="Ultrasonic Sensors"/>

    </p>

21. Pada rangka utama terdapat dua buah lubang baut untuk memasang kotak baterai seperti ditunjukkan pada gambar di bawah ini.
     <p align="center" width="100%">

    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-39.png').default} alt="Ultrasonic Sensors"/>

    <br/>
    Sejajarkan dua buah lubang pada rangka utama tersebut dengan dua buah lubang yang terdapat pada kotak baterai.

    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-40.png').default} alt="Ultrasonic Sensors"/>

    <br/>
    Kemudian kencangkan dua buah lubang tersebut dengan dua buah baut.

    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-41.png').default} alt="Ultrasonic Sensors"/>

    </p>

22. Maka hasil akhirnya setelah kotak baterai terpasang akan seperti pada gambar di bawah ini.
     <p align="center" width="100%">

    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-42.png').default} alt="Ultrasonic Sensors"/>

    </p>

#### ▪️ Memasang Baterai

23. Selanjutnya kita akan memasang dua buah baterai pada kotak baterai tersebut. Siapkan dua buah baterai seperti pada gambar di bawah ini.
     <p align="center" width="100%">

    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-43.png').default} alt="Ultrasonic Sensors"/>

    </p>

24. Kemudian masukkan salah satu baterai ke slot pertama pada kotak baterai. Perhatikan petunjuk pada gambar di bawah. Masukkan baterai dengan kutub negatif masuk terlebih dahulu ke pegas pada kotak baterai.
     <p align="center" width="100%">

    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-44.png').default} alt="Ultrasonic Sensors"/>

    <br/>

    Kemudian tekan hingga baterai masuk sepenuhnya pada slot pertama kotak baterai.
    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-45.png').default} alt="Ultrasonic Sensors"/>

    </p>

25. Lakukan hal yang sama untuk baterai kedua. Masukkan baterai dengan kutub negatif masuk terlebih dahulu menghadap pegas pada kotak baterai seperti ditunjukkan oleh gambar di bawah ini.
     <p align="center" width="100%">

    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-46.png').default} alt="Ultrasonic Sensors"/>

    <br/>

    Kemudian tekan hingga baterai masuk sepenuhnya pada slot kotak baterai.
    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-47.png').default} alt="Ultrasonic Sensors"/>

    </p>

26. Untuk keamanan, sebelum lanjut ke langkah berikutnya, pastikan posisi saklar pada kotak baterai sudah berada pada posisi OFF seperti ditunjukkan pada gambar di bawah ini.
     <p align="center" width="100%">

    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-48.png').default} alt="Ultrasonic Sensors"/>

    </p>

27. Beginilah hasil akhirnya apabila kita telah memasang baterai pada kotak baterai.
     <p align="center" width="100%">

    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-49.png').default} alt="Ultrasonic Sensors"/>

    </p>

#### ▪️ Memasang Arduino Nano

28. Selanjutnya kita akan memasang Arduino Nano pada rangka utama. Siapkan 4 buah spacer kertas dan Arduino Nano.
     <p align="center" width="100%">

    <img width="50%" src={require('./img/img-project-obstacle-avoider-robot/poar-50.png').default} alt="Ultrasonic Sensors"/>

    <img width="50%" src={require('./img/img-project-obstacle-avoider-robot/poar-51.png').default} alt="Ultrasonic Sensors"/>

    </p>

29. Pasangkan keempat spacer kertas pada keempat lubang yang terdapat pada Arduino Nano sehingga menjadi seperti pada gambar di bawah ini.
     <p align="center" width="100%">

    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-52.png').default} alt="Ultrasonic Sensors"/>

    </p>

30. Setelah keempat spacer kertas dipasang, kita akan memasangkan pada rangka utama. Perhatikan tanda panah pada gambar di bawah ini. Lubang yang ditandai oleh tanda panah putih pada gambar di bawah ini adalah lubang tempat kita memasukkan keempat ujung spacer kertas tadi.
     <p align="center" width="100%">

    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-53.png').default} alt="Ultrasonic Sensors"/>

    <br/>
    Sejajarkan keempat ujung spacer kertas dengan keempat lubang pada rangka utama seperti ditunjukkan pada gambar di bawah ini.

    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-54.png').default} alt="Ultrasonic Sensors"/>
    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-55.png').default} alt="Ultrasonic Sensors"/>
    </p>

31. Kemudian tekan keempat spacer kertas hingga bagian putih spacer kertas menyentuh rangka utama seperti pada gambar di bawah ini.
     <p align="center" width="100%">
    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-56.png').default} alt="Ultrasonic Sensors"/>
    <img width="100%" src={require('./img/img-project-obstacle-avoider-robot/poar-57.png').default} alt="Ultrasonic Sensors"/>
    </p>

#### ▪️ Memasang Sensor Infra Merah

32. Selanjutnya, kita akan memasang Sensor Infra Merah atau bisa disingkat sebagai Sensor IR untuk mendeteksi garis hitam. Siapkan Sensor IR seperti ditunjukkan pada gambar di bawah ini.
    <p align="center" width="100%">
    <img width="100%" src={require('./img/img-project-line-follower-robot/plinefr-1.png').default} alt="Ultrasonic Sensors"/>

    <br/>
    Kita akan memasang Sensor IR pada Dudukan Sensor Jarak pada lubang yang ditunjuk oleh tanda panah hitam pada gambar di bawah. Posisikan terlebih dahulu Dudukan Sensor Jarak persis seperti pada gambar di bawah ini.
    <img width="100%" src={require('./img/img-project-line-follower-robot/plinefr-2.png').default} alt="Ultrasonic Sensors"/>
    <br/>
    Kemudian kencangkan Sensor IR pada dudukan sensor jarak dengan baut seperti ditunjukkan oleh gambar di bawah.
    <img width="100%" src={require('./img/img-project-line-follower-robot/plinefr-3.png').default} alt="Ultrasonic Sensors"/>
    <img width="100%" src={require('./img/img-project-line-follower-robot/plinefr-4.png').default} alt="Ultrasonic Sensors"/>
    </p>

33. Lakukan langkah di atas sekali lagi agar kita mendapatkan dua buah Sensor IR seperti pada gambar di bawah ini.
    <p align="center" width="100%">
    <img width="100%" src={require('./img/img-project-line-follower-robot/plinefr-5.png').default} alt="Ultrasonic Sensors"/>
    </p>

34. Setelah memiliki dua buah Sensor IR, selanjutnya kita akan memasang salah satunya pada rangka utama. Kita mulai pada sisi kiri robot terlebih dahulu. Posisikan dan pasang Sensor IR seperti ditunjukkan pada gambar di bawah ini.
    <p align="center" width="100%">
    <img width="100%" src={require('./img/img-project-line-follower-robot/plinefr-6.png').default} alt="Ultrasonic Sensors"/>
    <img width="100%" src={require('./img/img-project-line-follower-robot/plinefr-7.png').default} alt="Ultrasonic Sensors"/>    
    </p>

35. Lakukan hal yang sama untuk sensor yang tersisa di sebelah kanan robot seperti pada gambar di bawah ini.
    <p align="center" width="100%">
    <img width="100%" src={require('./img/img-project-line-follower-robot/plinefr-8.png').default} alt="Ultrasonic Sensors"/>
    <img width="100%" src={require('./img/img-project-line-follower-robot/plinefr-9.png').default} alt="Ultrasonic Sensors"/>
    </p>

36. Setelah semua komponen terpasang, beginilah hasil finalnya.
    <p align="center" width="100%">
    <img width="100%" src={require('./img/img-project-line-follower-robot/plinefr-10.png').default} alt="Ultrasonic Sensors"/>
    </p>

### ◼️ Wiring Diagram

Selanjutnya, kita akan merangkai dan menghubungkan komponen-komponen tersebut dengan kabel jumper.

#### ▪️ Diagram Gambar

Teman-teman bisa gunakan gambar Wiring Diagram di bawah ini sebagai petunjuk untuk merangkai kabel-kabelnya.

<div width="100%" style={{textAlign: 'center'}}>

![Docs Version Dropdown](./img/ARDUINO_ROBOT_LINE_FOLLOWER_bb.png)

</div>

#### ▪️ Diagram Tabel

Apabila titik ujung kabel pada gambar di atas kurang jelas, teman-teman bisa gunakan tabel di bawah ini.

<table>
<tr><th>Modul l298N </th></tr>
<tr><td>

| Modul L298N | Arduino Nano Expansion Board |
| :---------: | :--------------------------: |
|     ENA     |            Pin 10            |
|     IN1     |            Pin 9             |
|     IN2     |            Pin 8             |
|     IN3     |            Pin 6             |
|     IN4     |            Pin 5             |
|     ENB     |            Pin 4             |

</td></tr> </table>

<table>
<tr><th>Motor Kiri </th><th>Motor Kanan</th></tr>
<tr><td>

|  Motor Kiri  | Modul L298N |
| :----------: | :---------: |
| Kabel Merah  |    OUT 1    |
| Kabel Coklat |    OUT 2    |

</td><td>

| Motor Kanan  | Modul L298N |
| :----------: | :---------: |
| Kabel Merah  |    OUT 4    |
| Kabel Coklat |    OUT 3    |

</td></tr> </table>

<table>
<tr><th>LDR Sensor Kiri</th><th>LDR Sensor Kanan</th></tr>
<tr><td>

| LDR Sensor | Arduino Nano Expansion Board |
| :--------: | :--------------------------: |
|    VCC     |            Pin V             |
|    GND     |            Pin G             |
|     D0     |            Pin 3             |

</td><td>

| LDR Sensor | Arduino Nano Expansion Board |
| :--------: | :--------------------------: |
|    VCC     |            Pin V             |
|    GND     |            Pin G             |
|     D0     |            Pin 2             |

</td></tr> </table>

<br/>

## Mengetik Program

Kemudian ketik program di bawah ini. Setelah selesai mengetik, jalankan proses Verify. Setelah proses verify dan compiling selesai, upload programnya ke Arduino Nano.

```arduino title="RoboKarsa_Light_Follower_Robot.ino" showLineNumbers
const int IRSensorPin0=2;
const int IRSensorPin1=3;

// Motor A connections
//Red Cable goes to OUT1
//Brown Cable goes to OUT2
int enA = 10;
int in1 = 9;
int in2 = 8;

// Motor B connections
//Red Cable goes to OUT4
//Brown Cable goes to OUT3
int in3 = 6;
int in4 = 5;
int enB = 4;

void setup() {
  // Set all the motor control pins to outputs
  pinMode(enA, OUTPUT);
  pinMode(enB, OUTPUT);
  pinMode(in1, OUTPUT);
  pinMode(in2, OUTPUT);
  pinMode(in3, OUTPUT);
  pinMode(in4, OUTPUT);

  // Turn off motors - Initial state
  digitalWrite(in1, LOW);
  digitalWrite(in2, LOW);
  digitalWrite(in3, LOW);
  digitalWrite(in4, LOW);

  pinMode(IRSensorPin0, INPUT);
  pinMode(IRSensorPin1, INPUT);
  delay(5000);
}

void loop() {
if ((digitalRead(IRSensorPin0)==0) && (digitalRead(IRSensorPin1)==0)) {forward();}
while ((digitalRead(IRSensorPin0)==0) && (digitalRead(IRSensorPin1)==1)) {turnleft();}
while ((digitalRead(IRSensorPin0)==1) && (digitalRead(IRSensorPin1)==0)) {turnright();}
if ((digitalRead(IRSensorPin0)==1) && (digitalRead(IRSensorPin1)==1)) {stopping();}
}


void forward(){
  analogWrite(enA, 150);
  analogWrite(enB, 150);

  digitalWrite(in1, HIGH);
  digitalWrite(in2, LOW);
  digitalWrite(in3, HIGH);
  digitalWrite(in4, LOW);
  //delay(2000);
}

void backward(){
  analogWrite(enA, 100);
  analogWrite(enB, 100);

  digitalWrite(in1, LOW);
  digitalWrite(in2, HIGH);
  digitalWrite(in3, LOW);
  digitalWrite(in4, HIGH);
  //delay(500);
}

void turnleft(){
  analogWrite(enA, 250);
  analogWrite(enB, 250);

  digitalWrite(in1, HIGH);
  digitalWrite(in2, LOW);
  digitalWrite(in3, LOW);
  digitalWrite(in4, HIGH  );
  //delay(120);
}

void turnright(){
  analogWrite(enA, 250);
  analogWrite(enB, 250);

  digitalWrite(in1, LOW);
  digitalWrite(in2, HIGH);
  digitalWrite(in3, HIGH);
  digitalWrite(in4, LOW);
  //delay(120);
}

void stopping(){

  digitalWrite(in1, LOW);
  digitalWrite(in2, LOW);
  digitalWrite(in3, LOW);
  digitalWrite(in4, LOW);
  //delay(2000);
}
```

<!-- ## In Action

Hasilnya akan seperti pada video pendek berikut -->
