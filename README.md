# UTS_STRUKTURDATA

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

# kesimpulan
Dengan adanya sistem digital berbasis Queue, potensi terjadinya penyerobotan antrian oleh pasien yang datang belakangan dapat dihilangkan secara total. Setiap pasien mendapatkan kepastian nomor urut dan estimasi waktu pelayanan yang lebih transparan, sehingga ketertiban di loket pendaftaran rumah sakit dapat terjaga dengan baik.

Implementasi program berjalan sepenuhnya sesuai dengan landasan teori struktur data Queue. Operasi Enqueue berhasil menempatkan data di posisi belakang (rear), dan operasi Dequeue secara konsisten menghapus data dari posisi depan (front). Hal ini membuktikan bahwa prinsip FIFO (First-In-First-Out) merupakan mekanisme yang paling tepat dan adil secara logis untuk diterapkan pada sistem pelayanan publik yang bersifat kronologis.

Penggunaan struktur data Queue (dibandingkan dengan Stack) memberikan manfaat krusial dalam menjaga keadilan pelayanan. Jika menggunakan Stack (LIFO), pasien yang terakhir datang justru akan dilayani terlebih dahulu, yang tentu saja akan menimbulkan konflik di lapangan. Dengan Queue, manajemen memori data pasien menjadi lebih terorganisir, memudahkan petugas dalam memantau beban kerja secara real-time melalui fungsi Display, dan memastikan tidak ada data pasien yang terlewat dalam proses pelayanan.
