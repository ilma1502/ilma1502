<h1>TUGAS UAS PRAKTEK PEMROGRAMAN BERBASIS OBJECT</h1> 
Nama  : Ilma Amalia <br>
Nim   : 2203010566 <br>
Kelas : G22 <br>
![Image Alt](https://github.com/ilma1502/ilma1502/blob/main/sc/1.png?raw=true)
<h3>1. Penjelasan Singkat Program </h3>
<p>Tema : Sistem Manajemen Hotel</p>
<p>Aplikasi Sistem Manajemen Hotel merupakan sistem yang yang dibangun menggunakan bahasa pemrograman Java di NetBeans. Sistem ini
  berisi data manajer, data karyawan, data tamu, data kamar, dan data Pemesanan. Program Sistem Manajemen Hotel ini terdiri dari 4 Package :</p>
  <h4>A. Package "hotelmanajemensystem"</h4>
  <p align="justify">Package "hotelmanajemensystem" berisi main class "SistemManajemenHotel_ilma.java". main calss "SistemManajemenHotel_ilma" berfungsi sebagai pengelola utama, 
    yang menghubungkan berbagai komponen melalui daftar (list) untuk menyimpan data seperti daftarKamar_ilma, daftarTamu_ilma, daftarKaryawan_ilma, dan daftarPemesanan_ilma.
    Dalam metode main, data karyawan, tamu, dan kamar dibuat dan ditampilkan di konsol, kemudian disimpan dalam file terkait (misalnya, data/pemesanan_ilma.txt untuk pemesanan). 
    Metode seperti buatPemesanan_ilma bertugas membuat pemesanan baru dengan memvalidasi apakah kamar tersedia, menghitung biaya total, serta memperbarui status kamar menjadi terisi. 
    Selain itu, terdapat fitur untuk menyimpan data ke file menggunakan metode seperti simpanDaftarPemesanan_ilma dan simpan_ilma di setiap kelas terkait. Output program akan 
    menampilkan daftar karyawan, tamu, kamar, dan detail pemesanan yang berhasil dibuat. Program ini memanfaatkan konsep exception handling untuk menangani kesalahan, seperti 
    mencoba memesan kamar yang sudah terisi.</p>
  <h4>B. Package "hotelmanajemensystem.exceptions"</h4>
  <p align="justify">Package "hotelmanajemensystem.exceptions" berisi class "Exception_ilma.java". class ini berisi implementasi kelas custom exception bernama Exceptions_ilma, 
    yang merupakan turunan dari RuntimeException. Kelas ini digunakan untuk menangani error atau kondisi khusus yang terjadi dalam program Sistem Manajemen Hotel dengan 
    memberikan pesan kesalahan spesifik. Konstruktor Exceptions_ilma menerima sebuah string (pesan_ilma) yang mewakili pesan kesalahan, kemudian meneruskan pesan tersebut ke 
    konstruktor superclass (RuntimeException). Dengan menggunakan kelas ini, program dapat memberikan pesan kesalahan yang lebih informatif ketika terjadi 
    situasi seperti pemesanan kamar yang tidak valid atau data yang tidak ditemukan.</p>
  <h4>C. Package "hotelmanajemensystem.interfaces"</h4>
  <p align="justify">Package "hotelmanajemensystem.interfaces" berisi 2 buah interface yaitu "IDibayar_ilma.java" dan "IManageable_ilma.java"</p>
  <h5>1) Interface "IDibayar_ilma.java"</h5>
  <p align="justify">Interface ini mendefinisikan dua metode abstrak, yaitu hitungPembayaran_ilma() dan prosesPembayaran_ilma(). Metode hitungPembayaran_ilma() bertujuan 
    untuk menghitung jumlah pembayaran yang harus dilakukan, sedangkan prosesPembayaran_ilma() digunakan untuk menangani logika terkait proses pembayaran. Interface ini 
    memastikan bahwa setiap kelas yang mengimplementasikannya harus menyediakan implementasi untuk kedua metode tersebut, sehingga memungkinkan pengelolaan pembayaran
    secara konsisten di seluruh sistem.</p>
  <h5>2) Interface "IManageable_ilma.java"</h5>
  <p align="justify">Interface ini digunakan untuk mendefinisikan kontrak atau perilaku umum bagi kelas-kelas yang mengimplementasikannya dalam Sistem Manajemen Hotel. 
    Interface ini memiliki dua metode abstrak, yaitu simpan_ilma() dan perbarui_ilma(). Metode simpan_ilma() bertujuan untuk menyimpan data, sementara perbarui_ilma() 
    digunakan untuk memperbarui data.</p>
  <h4>D. Package "hotelmanajemensystem.models"</h4>
  <p align="justify">Package "hotelmanajemensystem.models" berisi  6 class yaitu "Person.java", "Kamar_ilma.java", "Karyawan_ilma.java", "Manajer_ilma.java", "Tamu_ilma.java", 
    dan "Pemesanan_ilma.java".</p>
    <h5>1) Class "Person.java"</h5>
    <p align="justify">Class ini merupakan abstract class yang menjadi dasar untuk kelas-kelas lainnya dalam program Sistem Manajemen Hotel. Kelas ini memiliki tiga atribut: 
      id_ilma (identitas unik), nama_ilma (nama), dan nomorTelepon_ilma (nomor telepon). Konstruktor Person digunakan untuk menginisialisasi atribut-atribut ini ketika 
      sebuah objek dibuat. Ada juga metode getter getId_ilma() untuk mengakses nilai atribut id_ilma. Karena kelas ini abstrak, ia tidak dapat diinstansiasi secara langsung 
      dan memaksa kelas turunannya untuk mengimplementasikan metode abstrak tampilkanInfo_ilma(), yang bertujuan untuk menampilkan informasi lengkap tentang objek Person. 
      Kelas ini dirancang untuk digunakan sebagai superclass bagi entitas seperti tamu, karyawan, atau lainnya yang memiliki atribut dasar yang sama.</p>
    <h5>2) Class "Kamar_ilma.java"</h5>
    <p align="justify">Class ini berisi data sebuah kamar, termasuk atribut seperti nomor kamar, tipe kamar, tarif per malam, dan status apakah kamar terisi. Kelas ini 
      mengimplementasikan antarmuka IManageable_ilma dan menyediakan dua metode utama:</p>
      <ol>
        <li>simpan_ilma: Metode ini menyimpan data kamar ke file kamar_ilma.txt. Jika file sudah ada, metode ini memastikan nomor kamar tidak duplikat sebelum menambahkan 
          data baru. Jika data berhasil disimpan, pesan konfirmasi ditampilkan.</li>
        <li>perbarui_ilma: Metode ini memperbarui data kamar yang sudah ada di file kamar_ilma.txt. Metode ini membaca data dari file, memodifikasi data kamar sesuai nomor 
          kamar, dan menulis ulang data ke file. Jika nomor kamar tidak ditemukan, metode memberikan pesan bahwa tidak ada data yang diperbarui.</li>
      </ol>
    <h5>3) Class "Karyawan_ilma.java"</h5>
    <p align="justify">Class ini merupakan turunan dari kelas Person dan mengimplementasikan antarmuka IManageable_ilma. Kelas ini digunakan untuk merepresentasikan data 
      karyawan dalam sistem manajemen hotel. Setiap objek karyawan memiliki atribut seperti id_ilma, nama_ilma, nomorTelepon_ilma, posisi_ilma, dan gaji_ilma. Method 
      tampilkanInfo_ilma menampilkan informasi dasar karyawan, seperti ID, nama, dan posisi. Method simpan_ilma bertanggung jawab untuk menyimpan data karyawan ke file 
      karyawan_ilma.txt di dalam folder data. Sebelum menyimpan, program memeriksa apakah ID karyawan sudah ada di file untuk mencegah data duplikat. Jika ID belum ada, 
      data karyawan akan ditambahkan ke file. Jika terjadi kesalahan selama proses penyimpanan, exception khusus Exceptions_ilma akan dilempar dengan pesan kesalahan yang 
      relevan. Kode ini juga menyediakan metode perbarui_ilma, yang belum diimplementasikan, untuk memungkinkan pembaruan data karyawan di masa depan.</p>
    <h5>4) Class "Manajer_ilma.java"</h5>
    <p align="justify"> Class ini merupakan subclass dari kelas Karyawan_ilma. Kelas ini menambahkan atribut spesifik bernama departemen_ilma, yang menunjukkan departemen 
      tempat manajer bertanggung jawab. Konstruktor kelas ini memanggil konstruktor kelas induk (Karyawan_ilma) untuk menginisialisasi data seperti ID, nama, nomor telepon, 
      posisi sebagai "Manajer," dan gaji. Selain itu, kelas ini memiliki dua metode berikanTugas_ilma untuk memberikan tugas kepada karyawan. Metode pertama memberikan tugas 
      tanpa deskripsi tambahan, sedangkan metode kedua memungkinkan menambahkan deskripsi tugas.</p>
    <h5>5) Class "Tamu_ilma.java"</h5>
    <p align="justify">Class ini merupakan turunan dari kelas Person dan mengimplementasikan antarmuka IManageable_ilma. Setiap tamu memiliki atribut seperti id_ilma, 
      nama_ilma, nomorTelepon_ilma, email_ilma, dan daftar riwayat pemesanan (riwayatPemesanan_ilma). Metode tampilkanInfo_ilma digunakan untuk menampilkan detail informasi 
      tamu di konsol, sedangkan metode simpan_ilma bertanggung jawab untuk menyimpan data tamu ke file tamu_ilma.txt. Sebelum menyimpan, metode ini memeriksa apakah ID tamu 
      sudah ada di file untuk menghindari duplikasi. Jika ID ditemukan, proses penyimpanan dibatalkan dengan pesan notifikasi.</p>
    <h5>6) Class "Pemesanan_ilma.java"</h5>
    <p align="justify">Class ini mengimplementasikan antarmuka IDibayar_ilma, yang mencakup metode untuk menghitung dan memproses pembayaran. Kelas ini memiliki atribut 
      seperti idPemesanan_ilma (ID pemesanan), tamu_ilma (data tamu), kamar_ilma (data kamar), checkIn_ilma dan checkOut_ilma (tanggal check-in dan check-out), serta 
      totalBiaya_ilma (biaya total). Saat sebuah objek pemesanan dibuat, biaya total dihitung berdasarkan jumlah hari menginap dikalikan dengan tarif kamar per malam. 
      Metode hitungPembayaran_ilma menghitung total biaya berdasarkan durasi menginap, sementara metode prosesPembayaran_ilma menampilkan informasi proses pembayaran, 
      termasuk ID pemesanan dan jumlah total biaya. Kelas ini juga menyediakan metode getter untuk mengakses data pemesanan.</p>
      
<h3>2. Cara menjalankan program </h3>
  <p align="justify">Cara menjalankan program ini adalah dengan mengklik kanan pada File/Class "SistemManajemenHotel_ilma.java" dan pilih "Run file". Bisa juga dengan cara
  membuka class "SistemManajemenHotel_ilma.java", pada bagian atas terdapat icon play berwarna hijau "Run Project" atau mengklik F6 pada keyboard. Pastikan untuk mengisi
  data-data yang diperlukan pada method main di class "SistemManajemenHotel_ilma.java" agar saat di run, output yang dihasilkan sesuai.</p>
<h3>3. Screenshot program </h3>
  <h5>1) Screenshot program "SistemManajemenHotel_ilma.java"</h5>
  <h5>2) Screenshot program "Exception_ilma.java"</h5>
  <h5>3) Screenshot program "IDibayar_ilma.java"</h5>
  <h5>4) Screenshot program "IManageable_ilma.java"</h5>
  <h5>5) Screenshot program "Person.java"</h5>
  <h5>6) Screenshot program "Kamar_ilma.java"</h5>
  <h5>7) Screenshot program "Karyawan_ilma.java"</h5>
  <h5>8) Screenshot program "Manajer_ilma.java"</h5>
  <h5>9) Screenshot program "Tamu_ilma.java"</h5>
  <h5>10) Screenshot program "Pemesanan_ilma.java"</h5>
<h3>3. Video Demo Program </h3>
  <p align="justify"></p>
- 👋 Hi, I’m @ilma1502
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
ilma1502/ilma1502 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
