# UTS_STRUKTURDATA

# NAMA KELOMPOK

I Gusti Ngurah Dwi Andika Putra (2501010016) (igustingurahdwiandikaputra-code)

I Made Pande Raditya Prameswara (2501010365) (maderadit22-lang)

Ni Putu Riska Pramesti Cahya Dewi (2501010315)

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


# 3. Desain Sistem dan Implementasi
ALGORITMA Antrean Rumah Sakit

DEKLARASI:

    MAX = 5
    queue = Array[0..MAX-1]
    front = -1
    rear = -1

PROSEDUR ENQUEUE(nama_pasien):

    IF rear == MAX - 1 THEN
        PRINT "Antrean Penuh"
    ELSE
        IF front == -1 THEN front = 0
        rear = rear + 1
        queue[rear] = nama_pasien
        PRINT nama_pasien + " Berhasil Masuk"

FUNGSI DEQUEUE():

    IF front == -1 THEN
        PRINT "Antrean Kosong"
    ELSE
        PRINT "Melayani: " + queue[front]
        IF front == rear THEN
            front = rear = -1
        ELSE
            front = front + 1

PROSEDUR DISPLAY():

    IF front == -1 THEN
        PRINT "Kosong"
    ELSE
        FOR i FROM front TO rear DO
            PRINT queue[i]
# 4. Kesimpulan

•	Sistem berhasil menerapkan queue berbasis array 

•	Sistem berjalan sesuai prinsip Firts In First Out (FIFO) 

•	Pasien yang datang lebih awal dilayani lebih dulu 

•	Array membuat implementasi sederhana dan mudah dipahami 

•	Sistem ini membantu meningkatkan keteraturan antrean pasien di rumah sakit 

