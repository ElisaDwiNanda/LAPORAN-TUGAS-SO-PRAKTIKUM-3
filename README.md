# LAPORAN TUGAS SO PRAKTIKUM 3
## Pendahuluan 
### Latar Belakang Sistem File dalam Linux
Sistem file adalah komponen fundamental dalam sistem operasi yang mengatur bagaimana data disimpan, diakses, dan dikelola di perangkat penyimpanan. Dalam konteks Linux, sistem file memainkan peran penting dalam pengelolaan data, memungkinkan pengguna untuk menyimpan, mengatur, dan mengakses informasi dengan cara yang efisien dan terstruktur. Linux, sebagai sistem operasi open-source yang mendukung berbagai jenis perangkat keras dan aplikasi, menyediakan berbagai opsi sistem file yang memungkinkan penyesuaian dan optimasi untuk berbagai kebutuhan.

Linux menggunakan struktur hierarki yang unik untuk mengatur file dan direktori. Semua file dan direktori berada di bawah direktori root (/), menciptakan satu pohon direktori yang konsisten dan memudahkan akses data di seluruh sistem. Setiap file dalam sistem file Linux memiliki inode, yang menyimpan metadata seperti ukuran, hak akses, dan lokasi data di disk. Inode memungkinkan sistem untuk mengelola file dengan efisiensi tinggi tanpa menyimpan nama file, yang disimpan dalam direktori terpisah.

Sistem file di Linux tidak hanya tentang pengelolaan data, tetapi juga mencakup kontrol akses yang ketat, yang memungkinkan pengaturan hak akses yang terperinci untuk file dan direktori. Ini memastikan integritas dan keamanan data dalam lingkungan multi-pengguna. Selain itu, Linux mendukung berbagai jenis sistem file, masing-masing dengan fitur dan kelebihan tersendiri, seperti ext4, XFS, Btrfs, F2FS, serta sistem file yang kompatibel dengan Windows seperti NTFS dan VFAT.

ext4, sebagai salah satu sistem file yang paling banyak digunakan di Linux, dikenal karena stabilitas, kecepatan, dan dukungannya untuk fitur-fitur modern seperti pemulihan setelah kegagalan. XFS, di sisi lain, terkenal dengan kemampuannya untuk menangani file besar dan volume data yang besar, serta fitur-fitur seperti snapshot dan manajemen volume. Btrfs, sistem file yang lebih baru, menawarkan fitur-fitur canggih seperti snapshot dan pengelolaan ruang yang efisien, dirancang untuk memenuhi kebutuhan penyimpanan yang lebih kompleks. F2FS, yang dioptimalkan untuk perangkat penyimpanan berbasis flash seperti SSD, memberikan kinerja baca/tulis yang lebih baik.

Dengan berbagai jenis sistem file yang tersedia, Linux memberikan fleksibilitas yang luas dalam pengelolaan data, memungkinkan pengguna untuk memilih sistem file yang paling sesuai dengan kebutuhan mereka. Dukungan untuk berbagai alat dan perintah dalam Linux juga memudahkan manajemen sistem file, mulai dari pembuatan dan pemeriksaan sistem file hingga pengelolaan partisi dan volume.

Secara keseluruhan, sistem file dalam Linux adalah elemen penting yang mempengaruhi kinerja, keamanan, dan efisiensi sistem. Kemampuan Linux untuk mendukung berbagai sistem file dan mengintegrasikan berbagai media penyimpanan dalam satu struktur direktori menunjukkan fleksibilitas dan kekuatan dari sistem operasi ini.

### Alat dan Bahan
- Laptop/PC
- Virtual Box
- Linux Ubuntu 24.04 LTS

### Dasar Teori
Sistem file dalam Linux adalah struktur yang mengatur bagaimana data disimpan dan diakses pada perangkat penyimpanan. Konsep dasar sistem file melibatkan penggunaan struktur hierarki, di mana semua file dan direktori berada di bawah direktori root (/). Setiap file diidentifikasi oleh inode, yang menyimpan metadata seperti ukuran, hak akses, dan lokasi data di disk, sementara nama file disimpan dalam direktori.

Sistem file Linux mengelola ruang penyimpanan dengan membagi disk menjadi blok, yang dialokasikan untuk file. Teknik mounting memungkinkan berbagai sistem file dan partisi diintegrasikan ke dalam hierarki direktori, memberikan fleksibilitas dalam pengelolaan penyimpanan.

Untuk meningkatkan keandalan, banyak sistem file Linux menggunakan journaling, yang mencatat perubahan sebelum diterapkan untuk melindungi data dari kerusakan. Sistem file modern seperti Btrfs dan F2FS menawarkan fitur canggih seperti snapshot dan optimasi untuk media penyimpanan berbasis flash. Linux juga mendukung sistem file dari platform lain, seperti NTFS dan VFAT, untuk kompatibilitas lintas platform.

Memahami dasar teori sistem file ini penting untuk mengelola data secara efisien dan memanfaatkan berbagai fitur yang disediakan oleh sistem file Linux.

## Pembahasan

### Sebelum mengerjakan tugas, login terlebih dahulu ke sistem operasi Linux
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

## Kesimpulan
Sistem file dalam Linux memainkan peran krusial dalam pengelolaan data pada perangkat penyimpanan. Dengan struktur hierarki yang dimulai dari direktori root, sistem file Linux mengatur file dan direktori secara terstruktur, memudahkan akses dan pengorganisasian data. Konsep inode memungkinkan pengelolaan metadata file secara efisien, sedangkan teknik mounting memberikan fleksibilitas dalam mengintegrasikan berbagai sistem file dan partisi ke dalam satu struktur direktori.

Teknik journaling yang diterapkan pada banyak sistem file Linux, seperti ext4 dan XFS, meningkatkan keandalan dengan mencatat perubahan sebelum diterapkan, melindungi data dari kerusakan. Sistem file modern, termasuk Btrfs dan F2FS, menawarkan fitur tambahan seperti snapshot dan optimasi untuk media penyimpanan berbasis flash, meningkatkan kinerja dan pengelolaan data. Dukungan untuk sistem file lintas platform seperti NTFS dan VFAT juga mempermudah interoperabilitas dengan sistem lain.

Secara keseluruhan, sistem file Linux menyediakan kerangka kerja yang fleksibel dan kuat untuk pengelolaan data, menawarkan berbagai fitur dan opsi yang dapat disesuaikan untuk memenuhi kebutuhan spesifik pengguna dan aplikasi.
