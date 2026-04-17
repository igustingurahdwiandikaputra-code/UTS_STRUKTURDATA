# UTS_STRUKTURDATA

# NAMA KELOMPOK

I Gusti Ngurah Dwi Andika Putra (2501010016)

# Sistem Antrean Pasien Rumah Sakit Menggunakan Queue Berbasis Array

# 1. Rumusan Masalah dan Solusi
# Rumusan Masalah
1.	Bagaimana struktur data queue dapat digunakan untuk mengelola antrean pasien di rumah sakit secara teratur? 
2.	Bagaimana implementasi array dapat digunakan untuk menyimpan data antrean pasien secara sederhana? 
3.	Bagaimana sistem ini dapat membantu meningkatkan efisiensi pelayanan pasien di rumah sakit?

# Solusi
Sistem ini menggunakan struktur data queue dengan prinsip FIFO (First In First Out), yaitu pasien yang datang lebih awal akan dilayani terlebih dahulu.
Masalah yang sering terjadi:

a. antrean tidak teratur 

b. pasien saling mendahului 

c. pelayanan menjadi lambat 

Solusi sistem:

a. pasien dimasukkan ke dalam antrian array 

b. dilayani sesuai urutan masuk 

a. sistem menjadi lebih tertib dan efisien 

Array dipilih karena:

a. mudah dipahami 

b. implementasi sederhana 

c. cocok untuk sistem dasar 

# 2. Landasan Teori
Struktur data adalah cara untuk menyimpan dan mengatur data agar dapat digunakan secara efisien. Struktur data sangat penting dalam pemrograman karena mempengaruhi cara kerja sistem.
Queue adalah struktur data dengan prinsip FIFO (First In First Out), yaitu data yang pertama masuk akan diproses terlebih dahulu. Queue banyak digunakan dalam sistem antrean seperti rumah sakit, printer, dan call center.
Stack adalah struktur data dengan prinsip LIFO (Last In First Out), yaitu data terakhir yang masuk akan diproses terlebih dahulu. Stack biasanya digunakan pada fitur undo/redo.
Array adalah struktur data yang menyimpan elemen secara berurutan dalam satu variabel dengan indeks tertentu. Array digunakan karena sederhana dan mudah diimplementasikan untuk queue dasar.


Referensi

•	Introduction to Algorithms 

•	Data Structures and Algorithms in Java 

•	Fundamentals of Data Structures 

# 3. Desain Sistem dan Implementasi
Alur Sistem (Input → Proses → Output)
•	Input: Nama pasien

•	Proses: 

o	Enqueue (tambah pasien ke antrian) 

o	Dequeue (menghapus pasien yang dilayani) 

o	Peek (melihat pasien terdepan) 

o	Display (menampilkan semua antrean) 

•	Output: 

o	Daftar antrean pasien

o	Pasien yang sedang dilayani 

Flowchart (Teks)

Mulai

  ↓
  
Input pasien

  ↓
  
Pilih menu

  ├─ Enqueue (tambah antrian)
  
  ├─ Dequeue (layani pasien)
  
  ├─ Peek (lihat depan)
  
  ├─ Display (tampilkan semua)
  
  ↓
  
Tampilkan hasil

  ↓
  
Selesai

Pseudocode

Inisialisasi queue array

MAX = 5

front = -1

rear = -1

ENQUEUE(data):

    jika rear == MAX-1:
    
        tampilkan "Antrian penuh"    
        
    jika front == -1:
    
        front = 0
        
    rear = rear + 1
    
    queue[rear] = data
    
DEQUEUE():

    jika front == -1:
    
        tampilkan "Antrian kosong"
        
    tampilkan queue[front]
    
    jika front == rear:
    
        front = rear = -1
        
    else:
    
        front = front + 1

PEEK():

    tampilkan queue[front]

DISPLAY():

    tampilkan semua dari front sampai rear

# 4. Kesimpulan

•	Sistem berhasil menerapkan queue berbasis array 

•	Sistem berjalan sesuai prinsip Firts In First Out (FIFO) 

•	Pasien yang datang lebih awal dilayani lebih dulu 

•	Array membuat implementasi sederhana dan mudah dipahami 

•	Sistem ini membantu meningkatkan keteraturan antrean pasien di rumah sakit 

