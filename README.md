# UTS_STRUKTURDATA

# Link PPT
https://canva.link/qbc0njolucvnl3e

# NAMA KELOMPOK

I Gusti Ngurah Dwi Andika Putra (2501010016) (igustingurahdwiandikaputra-code)

I Made Pande Raditya Prameswara (2501010365) (maderadit22-lang)

Ni Putu Riska Pramesti Cahya Dewi (2501010315) (niputuriskapramesticahyadewi-maker)

# Sistem Antrian Rumah Sakit

# 1. Rumusan Masalah
Pada banyak rumah sakit konvensional, pengelolaan pasien seringkali mengalami kendala dalam hal ketertiban urutan pendaftaran. Tanpa sistem yang terautomasi, sulit untuk memastikan pasien mana yang harus dilayani terlebih dahulu, yang seringkali menyebabkan penumpukan di loket dan ketidakpuasan pasien karena adanya "penyerobotan" antrian.

# Solusi
Membangun sistem antrian digital berbasis First-In-First-Out (FIFO). Sistem ini akan mencatat setiap pasien yang datang (Enqueue), memanggil pasien sesuai urutan kedatangan (Dequeue), dan memungkinkan petugas melihat siapa yang berada di urutan terdepan tanpa menghapusnya (Peek).

# 2. Landasan Teori
Struktur data adalah cara penyimpanan, pengorganisasian, dan pengaturan data di dalam media penyimpanan komputer sehingga data tersebut dapat digunakan secara efisien. Dalam dunia pemrograman, pemilihan struktur data yang tepat sangat krusial karena memengaruhi performa algoritma. Struktur data terbagi menjadi linear (seperti Array dan Stack) serta non-linear (seperti Tree dan Graph). Pemahaman yang mendalam mengenai struktur data memungkinkan pengembang untuk mengelola volume data yang besar dengan penggunaan memori yang optimal.

Konsep Queue (Antrian) adalah struktur data linear yang menerapkan prinsip FIFO (First-In-First-Out), di mana elemen yang pertama kali masuk akan menjadi yang pertama kali keluar, mirip dengan antrian nyata di kasir atau bank. Sebaliknya, Stack (Tumpukan) menggunakan prinsip LIFO (Last-In-First-Out), di mana elemen yang terakhir masuk akan menjadi yang pertama keluar, seperti tumpukan piring. Dalam kasus pelayanan rumah sakit, Queue adalah pilihan yang paling logis dan adil karena menjamin kronologi pelayanan yang tepat sesuai waktu kedatangan pasien.

Implementasi Queue dapat dilakukan menggunakan Array atau Linked List. Menggunakan Array cenderung lebih sederhana namun memiliki batasan ukuran (statik), kecuali jika diimplementasikan sebagai circular queue. Sementara itu, Linked List menawarkan fleksibilitas karena ukurannya dinamis, namun memerlukan penggunaan pointer yang lebih kompleks. Dalam sistem rumah sakit dengan jumlah pasien yang fluktuatif, Linked List sering dianggap lebih unggul karena tidak memerlukan alokasi memori tetap di awal dan menghindari risiko overflow selama memori komputer masih tersedia.

Referensi:

Sitorus, L. (2015). Algoritma dan Struktur Data. Yogyakarta: Penerbit Andi.

Goodrich, M. T., Tamassia, R., & Goldwasser, M. H. (2014). Data Structures and Algorithms in Java. Wiley.

Nasir, M. (2018). "Analisis Perbandingan Kinerja Queue Menggunakan Array dan Linked List". Jurnal Teknologi Informasi dan Ilmu Komputer (JTIIK).

# 3. Desain Sistem (Pseudocode)
Berikut adalah logika dasar sistem antrian menggunakan pendekatan Array:

Plaintext
```
ALGORITMA Antrian Rumah Sakit

Deksripsi:
  MaksAntrian = 100
  Antrian[MaksAntrian]
  depan = -1
  belakang = -1

PROSEDUR Enqueue(pasienBaru):

  JIKA belakang == MaksAntrian - 1 MAKA:
    CETAK "Antrian Penuh"
  SELAIN ITU:
    JIKA depan == -1 MAKA depan = 0
    belakang = belakang + 1
    Antrian[belakang] = pasienBaru
    CETAK pasienBaru + " berhasil masuk antrian"

PROSEDUR Dequeue():

  JIKA depan == -1 MAKA:
    CETAK "Antrian Kosong"
  SELAIN ITU:
    CETAK "Melayani pasien: " + Antrian[depan]
    JIKA depan == belakang MAKA:
      depan = -1, belakang = -1
    SELAIN ITU:
      depan = depan + 1

PROSEDUR Peek():

  JIKA depan != -1 MAKA:
    CETAK "Pasien berikutnya: " + Antrian[depan]

PROSEDUR Display():

  JIKA depan == -1 MAKA:
    CETAK "Antrian Kosong"
  SELAIN ITU:
    TAMPILKAN semua elemen dari Antrian[depan] hingga Antrian[belakang]
```
Alur Kerja:

Input: Petugas memasukkan nama atau ID pasien ke dalam sistem.

Proses: Sistem memasukkan data ke posisi belakang (Enqueue). Jika ada pemanggilan, sistem mengambil data dari posisi depan (Dequeue).

Output: Layar menampilkan nomor urut yang sedang dilayani dan daftar pasien yang masih menunggu.

# Desain Sistem Dan Implementasi

<img width="1882" height="3158" alt="Flowchart" src="https://github.com/user-attachments/assets/e75a6cbb-9598-4312-8f95-959e560c1790" />

# Penjelasan Alur Flowchart
Flowchart tersebut menggambarkan alur kerja sistem antrean rumah sakit yang dimulai dari proses Mulai, kemudian sistem melakukan inisialisasi data antrean beserta kapasitas maksimalnya. Setelah itu, pengguna diarahkan ke menu utama untuk memilih beberapa opsi yang tersedia. Jika pengguna memilih untuk menampilkan semua antrean, sistem akan terlebih dahulu mengecek apakah antrean kosong; jika kosong maka akan ditampilkan pesan “Antrian Kosong”, sedangkan jika tidak kosong maka sistem akan menampilkan seluruh data pasien dalam antrean. Pada pilihan melihat pasien terdepan (peek), sistem juga melakukan pengecekan yang sama, yaitu jika antrean kosong maka akan muncul pesan “Antrian Kosong”, dan jika tidak maka pasien paling depan akan ditampilkan. Selanjutnya, pada proses menghapus pasien terdepan (dequeue), sistem kembali memeriksa apakah antrean kosong; jika ya maka tidak ada data yang bisa dihapus, namun jika tidak maka pasien terdepan akan dikeluarkan dari antrean. Pada opsi menambahkan pasien ke antrean (enqueue), sistem akan mengecek apakah antrean sudah penuh; jika penuh maka muncul pesan “Antrian Penuh”, sedangkan jika belum penuh maka pasien baru akan ditambahkan ke dalam antrean. Setelah setiap proses dijalankan, alur akan kembali ke menu utama sehingga pengguna dapat memilih operasi lain. Proses ini akan terus berulang hingga pengguna memilih opsi keluar, yang kemudian mengakhiri program pada bagian Selesai. Flowchart ini menerapkan konsep struktur data antrean (queue) dengan prinsip FIFO (First In First Out), yaitu pasien yang datang lebih dulu akan dilayani lebih dulu.

# kesimpulan
Dengan adanya sistem digital berbasis Queue, potensi terjadinya penyerobotan antrian oleh pasien yang datang belakangan dapat dihilangkan secara total. Setiap pasien mendapatkan kepastian nomor urut dan estimasi waktu pelayanan yang lebih transparan, sehingga ketertiban di loket pendaftaran rumah sakit dapat terjaga dengan baik.

Implementasi program berjalan sepenuhnya sesuai dengan landasan teori struktur data Queue. Operasi Enqueue berhasil menempatkan data di posisi belakang (rear), dan operasi Dequeue secara konsisten menghapus data dari posisi depan (front). Hal ini membuktikan bahwa prinsip FIFO (First-In-First-Out) merupakan mekanisme yang paling tepat dan adil secara logis untuk diterapkan pada sistem pelayanan publik yang bersifat kronologis.

Penggunaan struktur data Queue (dibandingkan dengan Stack) memberikan manfaat krusial dalam menjaga keadilan pelayanan. Jika menggunakan Stack (LIFO), pasien yang terakhir datang justru akan dilayani terlebih dahulu, yang tentu saja akan menimbulkan konflik di lapangan. Dengan Queue, manajemen memori data pasien menjadi lebih terorganisir, memudahkan petugas dalam memantau beban kerja secara real-time melalui fungsi Display, dan memastikan tidak ada data pasien yang terlewat dalam proses pelayanan.
