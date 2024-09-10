# LAPORAN TUGAS SO PRAKTIKUM 3
## Sebelum mengerjakan tugas, login terlebih dahulu ke sistem operasi Linux
-	Login ke root dengan perintah sudo su
-	Kemudian masukan password
  ![image](https://github.com/user-attachments/assets/41c6141c-688c-49fa-af39-b3ba3fa1aaba)

### 1.	Lihat peralatan I/O, character device, yang ada pada system computer
Pada sistem operasi Linux, peralatan I/O yang berupa character device dapat dilihat pada direktori /dev. Contoh peralatan I/O yang ada di /dev adalah:<br/>
-	Terminal: /dev/ttyS0, /dev/ttyS1
-	Modem: /dev/modem
-	Mouse: /dev/mouse
-	Paralel Port: /dev/lp0, /dev/lp1
-	Serial Port: /dev/ttyS0, /dev/ttyS1 <br/>

Untuk melihat daftar lengkap peralatan I/O, kita dapat menggunakan perintah ls dengan opsi -l untuk menampilkan informasi detail tentang file dan direktori, termasuk peralatan I/O yang ada di /dev.<br/>

![image](https://github.com/user-attachments/assets/31344a89-31a7-4e1f-b6a2-c8ab1a946829)

### 2.	Buatlah sub direktori januari, februari dan maret sekaligus pada direktori latihan5.
Untuk membuat sub direktori Januari, Februari, dan Maret secara bersamaan pada direktori Latihan, Anda dapat menggunakan perintah mkdir dengan opsi -p untuk membuat pohon direktori secara rekursif.<br/>

- mkdir -p Latihan/Januari Latihan/Februari Latihan/Maret

![image](https://github.com/user-attachments/assets/ccdd790a-d624-4164-94b9-808766203555)

### 3.	Buatlah file dataku yang berisi nama, nim dan alamat anda pada sub direktori januari dan copy-kan file tersebut ke sub direktori februari dan maret.
Untuk membuat file dataku yang berisi nama, nim, dan alamat Anda pada sub direktori januari, Anda dapat menggunakan perintah touch untuk membuat file kosong dan kemudian menambahkan konten ke dalamnya. echo -e ... > Latihan/Januari/Data: Menyimpan output teks ke dalam file Data di direktori Latihan/Januari.<br/>

- touch Latihan/Januari/Data
- echo -e "Nama: Elisa Dwi Nanda \nNim: 09011182328107 \nAlamat: Jl. Yos Sudarso, Bangka Belitung" > Latihan/Januari/Data

![image](https://github.com/user-attachments/assets/cbc9fd54-4692-4eb7-a9b0-5917d2d872aa)

Setelah itu, Anda dapat menyalin file tersebut ke sub direktori februari dan maret menggunakan perintah cp.

- cp Latihan/Januari/Data Latihan/Februari/<br/>
- cp Latihan/Januari/Data Latihan/Maret/<br/>

![image](https://github.com/user-attachments/assets/9162e85d-e7b2-48c7-8eb3-1958d50c746a)

### 4.	Ubahlah ijin akses file dataku pada sub direktori januari sehingga group dan others dapat melakukan write.
Untuk mengubah ijin akses file dataku pada sub direktori januari sehingga group dan others dapat melakukan write, Anda dapat menggunakan perintah chmod.<br/>

- chmod g+w,o+w Latihan/Januari/Data

![image](https://github.com/user-attachments/assets/d1f7666e-3752-4911-83de-68733ecdea9b)

Perintah di atas akan menambahkan hak write (w) untuk group (g) dan others (o) pada file dataku.

### 5.	Ubahlah ijin akses file dataku pada sub direktori februari sehingga user dapat melakukan baik write, read maupun execute, tetapi group dan others hanya bisa read dan execute.
Untuk mengubah ijin akses file dataku pada sub direktori februari sehingga user dapat melakukan write, read, dan execute, tetapi group dan others hanya bisa read dan execute, Anda dapat menggunakan perintah chmod.

- chmod u=rwx,g=r,o=rX Latihan/Februari/Data

![image](https://github.com/user-attachments/assets/5bb30903-0faf-4624-a21c-c63f50d7fb71)

Perintah di atas akan memberikan hak write (w), read (r), dan execute (X) untuk user, dan hanya read (r) dan execute (X) untuk group dan others.

### 6.	Ubahlah ijin akses file dataku pada sub direktori maret sehingga semua dapat melakukan write, read dan execute.
Untuk mengubah ijin akses file dataku pada sub direktori maret sehingga semua dapat melakukan write, read, dan execute, Anda dapat menggunakan perintah chmod.

- chmod u=rwx,g=rwx,o=rwx Latihan/Maret/Data 

![image](https://github.com/user-attachments/assets/dd894b30-7132-4195-90f6-dda503e3cc66)

Perintah di atas akan memberikan hak write (w), read (r), dan execute (X) untuk user, group, dan others.

### 7.	Hapuslah direktori maret.
Untuk menghapus direktori maret, Anda dapat menggunakan perintah rmdir jika direktori tersebut kosong, atau perintah rm -rf jika direktori tersebut tidak kosong.

- rmdir Latihan/Maret  # Jika direktori kosong
- rm -rf Latihan/Maret  # Jika direktori tidak kosong

![image](https://github.com/user-attachments/assets/d0dfbcbb-a837-4698-bc46-ce064d9ed960)

### 8.	Ubahkan kepemilikan sub direktori februari sehingga user dan group hanya dapat melakukan read, dan cobalah untuk membuat direktori baru haha pada sub direktori februari.
Untuk mengubah kepemilikan sub direktori februari sehingga user dan group hanya dapat melakukan read, Anda dapat menggunakan perintah chown.

- chown u=r,g=r Latihan/Februari  # Ubah kepemilikan dan hak akses
- mkdir Latihan/Februari/HAHA  # Buat direktori baru

![image](https://github.com/user-attachments/assets/df4bc664-26da-4fbf-8485-4b07b8b8b967)

Permission denied dikarenakan direktori Februari sudah diubah kepemilikan dan hak akses hanya dapat di read.

### 9.	Modifikasi umask dari file dataku pada sub direktori januari menjadi 027 dan berapakan nilai default-nya?
Umask adalah nilai default yang digunakan untuk menghitung hak akses awal pada saat file atau direktori dibuat. Nilai umask default pada Linux adalah 022 (dalam format octal). Untuk mengubah umask dari file dataku pada sub direktori januari menjadi 027, Anda dapat menggunakan perintah umask.

- umask 027

![image](https://github.com/user-attachments/assets/405569e4-a385-4b3f-b677-0ff58c879147)

Namun, perlu diingat bahwa umask hanya berlaku untuk proses saat ini dan tidak secara permanen mengubah nilai umask sistem. Jika Anda ingin mengubah nilai umask secara permanen, Anda harus mengedit file konfigurasi umask yang biasanya berada di '/etc/login.defs'.

### 10.	Buatlah link dari file dataku ke file dataku.ini dan file dataku.juga dan dengan perintah list perhatikan berapa link yang terjadi.
Untuk membuat link dari file dataku ke file dataku.ini dan dataku.juga, Anda dapat menggunakan perintah ln.

- ln Latihan/Januari/Data Latihan/Januari/Data.ini 
- ln Latihan/Januari/Data Latihan/Januari/Data.juga 

- ls -l Latihan/Januari/  # Perhatikan berapa link yang terjadi

![image](https://github.com/user-attachments/assets/807084e7-6ddb-4faf-8005-e38272693063)

Perintah ls -l akan menampilkan informasi detail tentang file dan direktori, termasuk jumlah link (hard link atau symbolic link) yang ada. Dalam kasus ini, Anda akan melihat bahwa dataku.ini dan dataku.juga memiliki satu link simbolis masing-masing ke dataku.
