# Tugas Praktikum { Pertemuan ke 13 } <img src=https://logos-download.com/wp-content/uploads/2016/05/MySQL_logo_logotype.png width="130px" >


|*Nama|NIM|Kelas|Matkul*|
|----|---|-----|------|
|CARLOS LOUIS FERNANDO|312310458|TI.23.A.5|Basis Data|

# Studi Kasus: ERD Karyawan

## Soal Latihan

Sebuah perusahaan ingin membuat sistem untuk pengeloalaan data karyawan pada perusahaan , dengan ketentuan sebagai berikut :

-  Perusahaan tersebut terdiri dari beberapa depatemen yang di pimpin oleh seorang manager (Manajer merupakan bagian dari karyawan).

-  Karyawan bekerja pada salah satu departemen.

-  Karyawan memiliki atasan langsung seorang supervisor.

-  Seorang supervisor dapat membawahi dapat karyawan.

-  Setiap karyawan dari lintas departemen dapat bekerja pada satu project yang sama dalam satu waktu.

-  Setiap karyawan dapat mengerjakan beberapa project yang berbeda.

Buatlah desain databasenya (ER-Diagram), beserta tabel datanya ?

# ERD
![database png](https://github.com/crslouis/MYSQL6/assets/147572011/451dbd29-7ef2-456f-916d-c6c45e9d17f7)


# PENGOLAHAN DATA KARYAWAN
# Tabel Departement

# Di bawah ini merupakan perintah dan juga hasil yang di minta
`
CREATE TABLE Departemen ( IDDepartemen INT PRIMARY KEY, NamaDepartemen VARCHAR(255) );
`
![alt text](Screnshoot/ss1.png)

## Tabel Karyawan
### Selanjutnya adalah table karyawan dengan menggunakan perintah seperti di bawah ini beserta hasil

`
CREATE TABLE Karyawan ( IDKaryawan INT PRIMARY KEY, NamaKaryawan VARCHAR(255), IDSupervisor INT, IDDepartemen INT, FOREIGN KEY (IDSupervisor) REFERENCES Karyawan(IDKaryawan), FOREIGN KEY (IDDepartemen) REFERENCES Departemen(IDDepartemen) );
`
![alt text](Screnshoot/ss2.png)

## Tabel Proyek
### Kemudian kita akan melanjutkan pada tabel proyek dengan menggunakan perintah sepert di bawah ini beserta hasilnya

`
CREATE TABLE Proyek ( IDProyek INT PRIMARY KEY, NamaProyek VARCHAR(255), TanggalMulai DATE, TanggalSelesai DATE );
`
![alt text](Screnshoot/ss3.png)

## Tabel Supervisor
### Kemudian kita akan melanjutkan pada tabel supervisor dengan menggunakan perintah sepert di bawah ini beserta hasilnya

`
CREATE TABLE Supervisor ( IDSupervisor INT, IDDepartemen INT, FOREIGN KEY (IDSupervisor) REFERENCES Karyawan(IDKaryawan), FOREIGN KEY (IDDepartemen) REFERENCES Departemen(IDDepartemen) );
`
![alt text](Screnshoot/ss4.png)

## Table Partisipasi
### Kemudian kita akan melanjutkan pada tabel partisipasi dengan menggunakan perintah sepert di bawah ini beserta hasilnya

`
CREATE TABLE Partisipasi ( IDKaryawan INT, IDProyek INT, FOREIGN KEY (IDKaryawan) REFERENCES Karyawan(IDKaryawan), FOREIGN KEY (IDProyek) REFERENCES Proyek(IDProyek) );
`
![alt text](Screnshoot/ss5.png)
