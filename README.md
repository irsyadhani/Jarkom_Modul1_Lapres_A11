# Jarkom_Modul1_Lapres_A11
Kelompok A11:
* _Irsyadhani Dwi Shubhi (0511184000022)_
* _Anggun Wahyuni (05111840000154)_

----------------------------------------------------------------
## Soal
* [Display Filter](#display-filter)
  * [Soal 1](#soal-1)
  * [Soal 2](#soal-2)
  * [Soal 3](#soal-3)
  * [Soal 4](#soal-4)
  * [Soal 5](#soal-5)
  * [Soal 6](#soal-6)
  * [Soal 7](#soal-7)
  * [Soal 8](#soal-8)
  * [Soal 9](#soal-9)
  * [Soal 10](#soal-10)
* [Capture Filter](#capture-filter)
  * [Soal 11](#soal-11)
  * [Soal 12](#soal-12)
  * [Soal 13](#soal-13)
  * [Soal 14](#soal-14)
  * [Soal 15](#soal-15)
----------------------------------------------------------------
# Display Filter

#### Soal 1:
Sebutkan webserver yang digunakan pada "testing.mekanis.me"!

_**Penyelesaian:**_
```
http.host == "testing.mekanis.me"
```
![alt text](/gambar/soal1.1.png)

● Klik kanan lalu follow tcp stream. Web server yang digunakan adalah nginx
![alt text](https://github.com/irsyadhani22/Jarkom_Modul1_Lapres_A11/blob/master/gambar/soal1.1.png)
#
#### Soal 2:
Simpan gambar "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"!
_**Penyelesaian:**_
```
http contains Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg
```
![alt text](https://github.com/irsyadhani22/Jarkom_Modul1_Lapres_A11/blob/master/gambar/soal2.1.png)
● Kemudian export object dan save untuk menyimpan gambar
![alt text](https://github.com/irsyadhani22/Jarkom_Modul1_Lapres_A11/blob/master/gambar/soal2.2.png)
● Gambar yang tersimpan
![alt text](https://github.com/irsyadhani22/Jarkom_Modul1_Lapres_A11/blob/master/gambar/soal2.3.png)
#
#### Soal 3:
Cari username dan password ketika login di "ppid.dpr.go.id"!
Simpan gambar "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"!
_**Penyelesaian:**_
```
http.host == "ppid.dpr.go.id" && http.request.method == POST && http contains login
```
● Dari display filter tersebut didapatkan username : 10pemuda dan password : guncangdunia
![alt text](https://github.com/irsyadhani22/Jarkom_Modul1_Lapres_A11/blob/master/gambar/soal3.png)
#
#### Soal 4:
Temukan paket dari web-web yang menggunakan basic authentication method!
_**Penyelesaian:**_
```
http.authbasic
```
Ada 5 paket yang menggunakan basic authentication
![alt text](https://github.com/irsyadhani22/Jarkom_Modul1_Lapres_A11/blob/master/gambar/soal4.1.png)
![alt text](https://github.com/irsyadhani22/Jarkom_Modul1_Lapres_A11/blob/master/gambar/soal4.2.png)
● Webserver yang menggunakan basic authentication adalah testing.mekanis.me dan aku.pengen.pw
#
#### Soal 5:
Ikuti perintah di aku.pengen.pw! Username dan password bisa didapatkan dari file .pcapng!
_**Penyelesaian:**_
● Open File soal_jarkom_modul1_no1-5
```
http.host contains "aku.pengen.pw"
```
![alt text](https://github.com/irsyadhani22/Jarkom_Modul1_Lapres_A11/blob/master/gambar/soal5.1.png)
● aku.pengen.pw (user: kakagamtenk pass: hartatahtabermuda)
![alt text](https://github.com/irsyadhani22/Jarkom_Modul1_Lapres_A11/blob/master/gambar/soal5.2.png)
![alt text](https://github.com/irsyadhani22/Jarkom_Modul1_Lapres_A11/blob/master/gambar/soal5.3.png)
#
#### Soal 6:
Seseorang menyimpan file zip melalui FTP dengan nama "Answer.zip". Simpan dan Buka file "Open This.pdf" di Answer.zip. Untuk mendapatkan password zipnya, temukan dalam file zipkey.txt (passwordnya adalah isi dari file txt tersebut).
_**Penyelesaian:**_
● Open File -> Display `filter:ftp-data` -> find -> answer.zip -> Save as RAW -> find -> zipkey.txt -> (hey997400323051)
![alt text](https://github.com/irsyadhani22/Jarkom_Modul1_Lapres_A11/blob/master/gambar/soal6.png)
#
#### Soal 7:
Ada 500 file zip yang disimpan ke FTP Server dengan nama 1.zip, 2.zip, ..., 500.zip. Salah satunya berisi pdf yang berisi puisi. Simpan dan Buka file pdf tersebut.
Your Super Mega Ultra Rare Hint = nama pdf-nya "Yes.pdf"
_**Penyelesaian:**_
● Open File soal_jarkom_modul1_no6,7,9 -> frame contains “Yes.pdf” -> Klik Kanan -> follow -> TCP Stream -> raw -> Save as .zip -> klik Yes.pdf
![alt text](https://github.com/irsyadhani22/Jarkom_Modul1_Lapres_A11/blob/master/gambar/soal7.png)
#
#### Soal 8:
Cari objek apa saja yang didownload (RETR) dari koneksi FTP dengan Microsoft FTP Service!
_**Penyelesaian:**_
● Pertama, display filter `ftp contains “Microsoft”` untuk mendapatkan IP Microsoft FTP Service. IP nya adalah 198.246.117.106
![alt text](https://github.com/irsyadhani22/Jarkom_Modul1_Lapres_A11/blob/master/gambar/soal8.1.png)
● Kemudian, display filter `ftp.request.command == RETR && ip.dst == 198.246.117.106`
![alt text](https://github.com/irsyadhani22/Jarkom_Modul1_Lapres_A11/blob/master/gambar/soal8.2.png)
Klik kanan -> Follow -> TCP Stream.
![alt text](https://github.com/irsyadhani22/Jarkom_Modul1_Lapres_A11/blob/master/gambar/soal8.2.png)
objek yang didownload (RETR) dari koneksi FTP dengan Microsoft FTP Service adalah readme
#
#### Soal 9:
Cari username dan password ketika login FTP pada localhost!
_**Penyelesaian:**_
● Open File soal_jarkom_modul1_no6,7,9 -> Display Filter `ftp.request.command == USER || ftp.request.command == PASS`
user: dhana pass: dhana123
![alt text](https://github.com/irsyadhani22/Jarkom_Modul1_Lapres_A11/blob/master/gambar/soal9.1.png)
![alt text](https://github.com/irsyadhani22/Jarkom_Modul1_Lapres_A11/blob/master/gambar/soal9.2.png)
#
#### Soal 10:
Cari file .pdf di wireshark lalu download dan buka file tersebut!
clue: "25 50 44 46"
_**Penyelesaian:**_
● ctrl + f -> ganti tipe pencarian menjadi hex value dengan nilai 25 50 44 46 (pdf signature) -> follow tcp stream -> ganti tipe dari ascii menjadi raw -> save as jarkom.pdf
![alt text](https://github.com/irsyadhani22/Jarkom_Modul1_Lapres_A11/blob/master/gambar/soal10.1.png)
![alt text](https://github.com/irsyadhani22/Jarkom_Modul1_Lapres_A11/blob/master/gambar/soal10.2.png)
#
# Capture Filter
#### Soal 11:
Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!
_**Penyelesaian:**_
```
port 21
```
![alt text](https://github.com/irsyadhani22/Jarkom_Modul1_Lapres_A11/blob/master/gambar/soal11.1.png)
![alt text](https://github.com/irsyadhani22/Jarkom_Modul1_Lapres_A11/blob/master/gambar/soal11.2.png)
#
#### Soal 12:
Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!
_**Penyelesaian:**_
```
src port 80
```
![alt text](https://github.com/irsyadhani22/Jarkom_Modul1_Lapres_A11/blob/master/gambar/soal12.1.png)
![alt text](https://github.com/irsyadhani22/Jarkom_Modul1_Lapres_A11/blob/master/gambar/soal12.2.png)
#
#### Soal 13:
Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!
_**Penyelesaian:**_
```
dst port 443
```
![alt text](https://github.com/irsyadhani22/Jarkom_Modul1_Lapres_A11/blob/master/gambar/soal13.2.png)
![alt text](https://github.com/irsyadhani22/Jarkom_Modul1_Lapres_A11/blob/master/gambar/soal13.2.png)
#
#### Soal 14:
Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!
_**Penyelesaian:**_
```
src host 192.168.100.139
```
![alt text](https://github.com/irsyadhani22/Jarkom_Modul1_Lapres_A11/blob/master/gambar/soal14.1.png "Hasil Soal 14")
![alt text](https://github.com/irsyadhani22/Jarkom_Modul1_Lapres_A11/blob/master/gambar/soal14.2.png)
#
#### Soal 15:
Filter sehingga wireshark hanya mengambil paket yang tujuannya ke monta.if.its.ac.id!
_**Penyelesaian:**_
```
dst host 103.94.190.11
```
![alt text](https://github.com/irsyadhani22/Jarkom_Modul1_Lapres_A11/blob/master/gambar/soal15.1.png)
![alt text](https://github.com/irsyadhani22/Jarkom_Modul1_Lapres_A11/blob/master/gambar/soal15.2.png)
