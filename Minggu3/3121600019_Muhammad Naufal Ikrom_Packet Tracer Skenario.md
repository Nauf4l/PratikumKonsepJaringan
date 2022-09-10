# PRATIKUM KONSEP JARINGAN
# Laporan Packet Tracer

Pada laporan kali ini, saya mengamati bagaimana sebuah jaringan berjalan pada komputer/pc. Laporan ini terdapat 3 Skenario yaitu PC1 ngeping PC2 (awal), PC1 ngeping PC2, dan PC2 ngeping PC1.

Pertama kita menghubungkan PC terlebih dahulu pada apk Packet Tracer, kemudian set IP pada setiap PC
![gambar1](assets/WhatsApp%20Image%202022-09-09%20at%2015.05.51.jpeg)
![Ippc0](assets/WhatsApp%20Image%202022-09-09%20at%2015.06.11.jpeg)
![IPpc1](assets/WhatsApp%20Image%202022-09-09%20at%2015.06.31.jpeg)
![IPpc2](assets/WhatsApp%20Image%202022-09-09%20at%2015.07.30.jpeg)

Setelah IP pada setiap pc sudah diberikan maka masuk ke Skenario yang akan di bahas.

## Skenario 1, PC0 ke PC1
- Pertama check arp dan ping PC1 pada cmd PC0
 ![ping](assets/2.jpeg)
- Setelah ngeping maka akan ada massage seperti ini
  ![msg1](assets/3.jpeg)
  Dikarenakan MAC IP Address destination tidak ditemukan maka proses encapsulasi pada layer 2. Sehingga PC0 mengirim broadcast yang berisi paket arp yang disebarkan ke semua MAC
  ![](assets/4.jpeg)
  ![](assets/5.jpeg)
  Setelah disebarkan ke MAC, ternyata ada kesamaan pada MAC1
- Setelah terdapat kesamaan, maka isi dari paket arp diisikan oleh MAC IP destination yang akan dikembalikan pada MAC0
  ![](assets/6.jpeg)
  ![](assets/7.jpeg)
  ![](assets/8.jpeg)
- Kemudian diganti alamat yang sebelumnya FFFF.FFFF.FFFF menjadi alamat MAC1
![](assets/9.jpeg)
![](assets/10.jpeg)
- Setelah melakukan ping, ketika di test arp maka MAC1 akan tersimpan
![](assets/12.jpeg)

## Skenario 2, PC0 ke PC1
- Pertama check arp dan ping PC1 pada cmd PC0
  ![](assets/13.jpeg)
- Setelah ngeping maka akan ada massage seperti ini
  ![](assets/14.jpeg)
  Sama seperti skenario 1, namun kali ini tidak melakukan broadcast lagi karena syarat encapsulasi pada layer ke-2 sudah terpenuhi yaitu MAC IP address destination.
  ![](assets/15.jpeg)
  ![](assets/16.jpeg)
  ![](assets/17.jpeg)
  Terdapat kesamaan dalam PC1 dengan MAC IP addres destination, kemudian dikembalikan ke alamat utama dan diterima pada PC0
  ![](assets/18.jpeg)
  ![](assets/19.jpeg)

- Apakah proses ping ini harus melakukan broadcast lagi ?
  Tidak terjadi broadcast karena IP pada MAC1 sudah disimpan pada arp MAC0

## Skenario 3, PC1 ke PC0
- Pertama check arp dan ping PC0 pada cmd PC1
  ![](assets/20.jpeg)
- Ketika sudah melakukan pratikum ternyata skenario 3 sama seperti skenario 2 pada penjelasannya
  ![](assets/21.jpeg)
  ![](assets/22.jpeg)
  ![](assets/23.jpeg)
  ![](assets/24.jpeg)
  ![](assets/25.jpeg)
  ![](assets/26.jpeg)

- Apakah proses ping ini harus melakukan broadcast lagi ?
  Tidak terjadi broadcast karena IP pada MAC0 sudah disimpan pada arp MAC1 pada saat awal melakukan broadcast.