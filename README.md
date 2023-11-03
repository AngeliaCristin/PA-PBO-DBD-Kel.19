# PA-PBO-DBD-Kel.19
Nama Kelompok:
- Angelia Cristin (2209116015)
- Adham Khautsar Leswono (2209116021)

# Manajemen Shift Pada Restoran

## Deskripsi Project
Proyek ini bertujuan untuk menciptakan sebuah aplikasi berbasis web yang memungkinkan manajer restoran untuk mengatur jadwal kerja karyawan dengan lebih efisien. Dalam pengembangan aplikasi ini, alat bantu desain sistem seperti flowchart digunakan untuk merinci alur kerja dan proses yang ada dalam sistem. Selain itu, ERD (Entity Relationship Diagram) yang dibuat dengan bantuan ORACLE SQL Developer Data Modeler digunakan untuk merancang struktur data yang akan disimpan dalam database. Aplikasi ini diimplementasikan dan diuji menggunakan teknologi seperti XAMPP, MySQL, localhost, phpMyAdmin, dan Apache NetBeans dengan Java Maven. 

Dengan adanya aplikasi ini, diharapkan manajer dapat dengan lebih efektif mengelola jadwal kerja karyawan dan memantau absensi atau kehadiran karyawan. Adapun model-model yang digunakan dalam pengembangan sistem ini adalah:

1. **Logical ERD (Entity Relationship Diagram)**:
   Logical ERD adalah representasi model data yang menggambarkan struktur data yang akan digunakan dalam database yg mencakup entitas (seperti jadwal_shift, akun (manajer dan karyawan) dan Laporan_kehadiran (hadir, izin, tanpa keterangan) serta atribut-atribut yang terkait dengan setiap entitas. Logical ERD membantu dalam pemahaman dan perencanaan dasar database, memastikan bahwa data yang diperlukan akan tersimpan dengan benar.

2. **Relational ERD (Entity Relationship Diagram)**:
   Relational ERD adalah model yang menggambarkan hubungan antar tabel dalam database yang menunjukkan bagaimana entitas terkait satu sama lain melalui kunci asing. Relational ERD membantu dalam merancang hubungan antar data, yang penting untuk menjaga konsistensi dan integritas data.

3. **Hirarki Kelas (Class Hierarchy)**:
   Hirarki kelas adalah struktur kelas yang digunakan dalam pengembangan perangkat lunak. hirarki kelas mencakup kelas-kelas yang mungkin ada dalam program, seperti Karyawan, Jadwal_Shift, dan Laporan_kehadiran. Setiap kelas memiliki metode dan atribut yang relevan. Ini membantu dalam merinci komponen-komponen program dan menjelaskan bagaimana kelas-kelas tersebut berinteraksi.

## Flowchart
![flowchart](https://github.com/AngeliaCristin/PA-PBO-DBD-Kel.19/assets/126650418/a227074a-7d61-4660-9115-007f453589e8)

-	Program ini dimulai dengan tampilan awal yaitu halaman login dimana ada dua role, yaitu karyawan dan manager
-	Apabila akan login dengan role karyawan, maka ada 2 pengkondisian dimana jika karyawan belum mempunyai akun maka harus melakukan registrasi terlebih dahulu.
-	Karyawan menginput username dan password untuk digunakan login ke sistem, menginput nama, gender, jabatan dan posisi untuk data karyawan dalam database.
-	Namun, jika karyawan sudah memiliki akun maka dapat langsung login di halaman menu login.
-	Apabila akan login sebgai manager, maka karena manager hanya satu, pengguna dapat langsung  melakukan login pada halamam login.
-	Untuk manager dan karyawan yang akan melakukan login, harus menginput username dengan benar yang sudah terdaftar dalam database.
-	Masukkan password, kemudian pilih jabatan, yang akan membawa pengguna ke tampilan yang sesuai role atau jabatan yang dipilih.
-	Dalam login, bila pengguna salah memasukkan data login yang sudah terdaftar, maka login tidak akan berhasil dan akan melakukan looping ke input username kembali.
-	 Login dengan jabatan karyawan, maka pengguna akan masuk ke menu karyawan.
-	Ada beberapa menu yang terdapat dalam karyawan, yaitu home yang merupakan tampilan awal ketika sesudah berhasil login
-	Menu jadwal shift. Apabila mengkilik menu ini maka aka nada output yaitu tampilan jadwal shift yang sudah dibuat oleh manager.
-	Laporan kehadiran adalah menu untuk melihat laporan kehadiran.
-	Untuk keluar dari menu karyawan, pengguna dapa mengklik keluar yang membawa pengguna dalam mengakhiri sistem.
-	Selanjutnya apabila saat login, pengguna memilih jabatan manager maka pengguna akau masuk ke meu manager
-	Menu pada manager sama dengan karyawan namun pada karyawan terdapat crud.
-	Pada menu jadwal shift terdapat beberapa fungsi yaitu crud (create, read, update dan delete)
-	Untuk create, manager perlu memasukkan id_jadwal, kemudian masukkan nama_karyawan lalu tanggal, masukkan jam masuk kemudian masukkan jam pulang.
-	Data jadwal shift yang di create dapat ditampilkan pada menu read jadwal.
-	Apabila manager memilik menu delete jadwal maka hal ini berfunhgsi untuk menghapus jadwal yang ada dalama database.
-	Delete jadwal dengan masukkan id_jadwal, kemudian masukkan nama karyawan,masukkan tanggal, jam masuk dan jam keluar, maka sistem akan melakukan penghapusan jadwal sesuai data yang diinput
-	Data yang di create, update dan delete akan mengubah database jadwal shift karena setiap perubahan yang ada akan disimpan ke database yang terhubung.
-	Menu selanjutnya yang ada pada menu karyawan adalah laporan kehadiran, dimana pada menu laporan kehadiran terdapat dua fungsi, yaitu create dan read laporan kehadiran.
-	Apabila manager memilih create, maka akan melakukan proses pembuatan laporan kehadiran dengan menginput id_laporan, kemudian input nama karyawan yang bertugas pada shift tersebut, masukkan tanggal, dana pilih status kehadiran yaitu salah satu dari pilihan hadir, izin dan tanpa keterangan. 
-	Laporan kehadiran yang sudah di create akan disimpan ke dalam database laporan kehadiran
-	Sehingga paada saat manager memilih menu read pada menu laporan kehadiran, maka akan ditampilkan data laporan kehadiran yang ada dalam database tersebut.
-	Menu keluar dapat digunakan untuk keluar dari sistem.
-	Apabila pengguna baik karyawan maupun manager telah mengklik menu keluar, artinya pengguna mengakhiri program dan program selesai.


## ERD
### Logical ERD
![ERD Logical](https://github.com/AngeliaCristin/PA-PBO-DBD-Kel.19/assets/126650418/b781f92b-36b8-4ffa-b175-fe5f1aacfdcc)

Manajemen shift kerja pada restoran memiliki rancangan database seperti gambar diatas, dimana terdapat beberapa entitas dengan atribut pada setiap entitas yang menjadi informasi atau ciri dari entitas tersebut.

#### Jadwal_Shift 
memiliki primary key id_jadwal, dan entitas ini memiliki relasi dengan entitas lainnya, yaitu jadwal_shift harus diakses akun. 
Entitas ini memiliki atribut:
-	Id_Jadwal dengan tipe sebagai primary key(pk). 
-	Nama_karyawan.
-	Tanggal
-	Jam_masuk 
-	Jam_keluar 

#### Akun
Pada entitas akun terdapat primary key username yang merupakan kunci relasi atau foreign key pada entitas lain yang berelasi dengannya. Entitas akun merupakan sebuah supertype yang memiliki dua subtype yang menjadi ciri lebih spesifik, yaitu karyawan dan manager. Jadi pada subtype ini, akan memiliki primary key yang sama yang ada pada supertype akun, sehingga karyawan dan manager memiliki primary key username. Sebagai sebuah subtype harus ada yang membedakannya dengan subtype lain, yaitu memiliki atribut pembeda. Pada logical erd diatas dapat dilihat bahwa pada karyawan terdapat atribut yang menjadi atribut pembeda dengan subtype manager, yaitu subtype karyawan memiliki atribut posisi yang tidak dimiliki oleh atribut manager. 
-	Supertype: akun
-	Subtype: manager, karyawan

#### Laporan_Kehadiran
Laporan_Kehadiran memiliki id_laporan sebagai primary key. Laporan kehadiran juga merupakan sebuah entitas yang memiliki tiga subentitas yang berelasi dengannya. Dimana ketiga subentitas ini memiliki sifat XOR yaitu bisa ada dan bisa tidak ada. Ketiga subentitas tersebut adalah 
-	Hadir
-	Izin
-	Tanpa_keterangan.


### Relational ERD
![ERD Relational](https://github.com/AngeliaCristin/PA-PBO-DBD-Kel.19/assets/126650418/07ac0912-23c2-4b97-90df-24d85bcf8fbd)

Relational erd sama dengan Logical erd, hanya saja pada relational erd ditampilkan tipe data dari atribut, primary key setiap entitas, serta foreign key yang muncul karena hubungan atau relasi yang terjadi pada suatu entitas dengan entitas lainnya. 

#### Jadwal_Shift 
Pada jadwal shift terdapat username yang menjadi primary key, dengan foreign key username yang diambil dari entitas akun karena entitas jadwal_shift yang memiliki relasi dengan entitas akun.

#### Akun 
Pada entitas akun terdapat primary key yaitu username, dimana primary key pada username dijadikan sebagai foreign key pada beberapa entitas karena memiliki relasi dengan entitas ini, seperti diajdikan sebagai foreign key pada entitas jadwal_shift dan entitas laporan_kehadiran. Selain itu primary key ini juga diwarisi kepada subtypenya, sehingga username juga menjadi primary key pada subtype manager dan subtype karyawan. 

#### Laporan_Kehadiran 
Entitas laporan_kehadiran memiliki id_laporan sebagai primary key, dimana dalam relational model dapat dilihat bahwa entitas ini memiliki beberapa foreign key, yaitu: 
- Username, karena memiliki relasi dengan entitas akun 
- Hadir_id. Atribut yang terlekat di entitas ini pada logical erd adalah absensi dan subentitas hadir sebenarnya tidak memiliki primary key, namum pada relational erd subentitas  hadir muncul  hadir_id secara otomatis  dijadikan sebagai foreign_key pada laporan_kehadiran dan primary key pada subnetas hadir. 
- Izin_id. Pada subentitas Izin juga tidak ada primary key di logical erd dan hanya ada atribut lama_hari. Namun, pada relational erd muncul secara otomatis atribut izin_id sebagai primary key di subentitas izin dan foreign key pada entitas laporan_kehadiran. 
- Tanpa_keterangan_id. Sama halnya dengan subentitas hadir dan izin, pada subentitas tanpa_keterangan juga muncul primary key secara otomatis yaitu tanpa_keterangan_id yang juga dijadikan sebagai foreign key pada entitas laporan_kehadiran. 

## Hierarki Class
### Hierarki Class Akun
![hierarki akun](https://github.com/AngeliaCristin/PA-PBO-DBD-Kel.19/assets/126650418/2a0b5532-48ac-491d-856d-cdb50ebd5612)

entitas akun merupakan sebuah supertype yang memiliki subtype manager dan karyawan.
pada entitas ini manager dan karyawan memiliki atribut yang menjadi informasi yang lebih spesifik dari entis akun.
akun sebagai supertype memiliki atribut:
- username
- password
- gender
- jabatan

sedangkan manager dan karyawan sebagai subtype entitas akun harus memiliki atribut pembeda yang menjadi ciri spesifik yang membedakan kedua subtype. atribut prmbrda itu ada dalam subtype karyawan yaitu:
- posisi, dimana atribut posisi ini hanya dimiliki oleh karyawan dan tidak dimiliki oleh entitas manager

  
### Hierarki Class Laporan Kehadiran
![hierarki l kehadiran](https://github.com/AngeliaCristin/PA-PBO-DBD-Kel.19/assets/126650418/5664eef3-aa79-4928-a136-d2c00664bc2e)

laporan kehadiran memiliki hubungan arcs, dimana dalam hal ini laporan kehadiran merupakan entitas yang berelasi dengan tiga subentitas yaitu hadir, izin dan tanpas keterangan.
ketiga subentitas tersebut bersifar XOR dalan laporan kehadiran, jadi bisa ada dan bisa tidak ada. misalnya apabila status kehadiran sudah diisi dengan hadir, maka izin dan tanpa keterangan tidak dapat lagi mengisi laporan kehadiran seorang karywana tersebut.
- hadir, memiliki atribut absensi
- izin memiliki atribut lama hari
- tanpa keterangan memiliki atribut pesan peringatan

  
## Screenshot Source & Penjelasannya

## Screenshot Output

Halaman Login

<img width="596" alt="image" src="https://github.com/AngeliaCristin/PA-PBO-DBD-Kel.19/assets/127503774/7e141b0d-c974-45bc-9f84-64e843b83416">

g


Halaman Register

<img width="593" alt="image" src="https://github.com/AngeliaCristin/PA-PBO-DBD-Kel.19/assets/127503774/c096c9da-59f3-4eb0-a585-33bb732e772a">

g


Halaman Utama Manajer

<img width="594" alt="image" src="https://github.com/AngeliaCristin/PA-PBO-DBD-Kel.19/assets/127503774/13819f10-619b-427c-9640-a1afcaa56875">

g


Halaman Jadwal Shift Manajer

<img width="593" alt="image" src="https://github.com/AngeliaCristin/PA-PBO-DBD-Kel.19/assets/127503774/5486c32b-7a1a-414d-828f-db11d0325caf">

g


Halaman Laporan Kehadiran


