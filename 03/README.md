
# MODUL 03 : SINKRONISASI DAN KOORDINASI PADA SISTEM TERDISTRIBUSI

## Identitas Mahasiswa

**Nama:** Apriliva Putri P
**NIM:** 255410035
**Kelas:** Informatika-1

## Identitas Penggunaan AI

**AI yang digunakan:** ChatGPT (OpenAI)

**Prompt:**

Bertindaklah sebagai mahasiswa Informatika yang memahami mata kuliah Sistem Terdistribusi dan Terdesentralisasi. Buat rangkuman berdasarkan materi PDF perkuliahan yang diberikan dosen. Ikuti seluruh agenda pembahasan secara berurutan. Bahas setiap poin secara terpisah, gunakan bahasa Indonesia baku dan akademis, serta jelaskan konsep-konsep penting secara ringkas, jelas, dan mudah dipahami. Jangan menggabungkan beberapa poin menjadi satu pembahasan dan jangan menambahkan materi yang tidak terdapat dalam slide dosen. Hasil akhir harus menggunakan format Markdown dan siap dimasukkan ke dalam README.md GitHub.

**Bagian yang disesuaikan dari keluaran prompt ada pada:**

1. Meringkas penjelasan agar lebih padat dan sesuai dengan materi presentasi dosen.
2. Memperbaiki susunan kalimat agar lebih mudah dipahami.
3. Menyesuaikan istilah teknis dengan konsep yang disampaikan dalam perkuliahan.
4. Memisahkan setiap agenda pembahasan agar lebih terstruktur.
5. Mempertahankan contoh, algoritma, dan perintah program yang terdapat dalam materi dosen.

---

# 1. APA ITU SINKRONISASI?

Sinkronisasi merupakan proses koordinasi terhadap proses, data, dan sumber daya pada berbagai node dalam sistem terdistribusi untuk memastikan seluruh operasi berjalan secara konsisten dan andal.

Sinkronisasi diperlukan untuk menjaga konsistensi data, mengelola proses yang berjalan secara bersamaan, serta mencegah konflik ketika beberapa node mengakses sumber daya yang sama.

### 1.1 Mengapa Sinkronisasi Penting?

Sinkronisasi memiliki beberapa fungsi penting, yaitu:

1. **Integritas Data:** Mencegah terjadinya data race dan race condition.
2. **Sinkronisasi State:** Memastikan kondisi aplikasi tetap konsisten pada seluruh node.
3. **Koordinasi Tasks:** Mengatur pelaksanaan tugas yang dilakukan oleh beberapa proses.
4. **Pengelolaan Resources:** Mengatur penggunaan sumber daya bersama agar tidak terjadi konflik.
5. **Recovery:** Mempertahankan kondisi sistem agar proses pemulihan dapat dilakukan ketika terjadi kegagalan.
6. **Utilisasi Efisien:** Mencegah terjadinya operasi yang berulang atau tidak diperlukan.
7. **Load Balancing:** Membantu pembagian beban kerja pada beberapa node.
8. **Mencegah Deadlock:** Mengurangi kemungkinan proses saling menunggu tanpa penyelesaian.
9. **Scalable Operations:** Mendukung sistem dalam menangani peningkatan jumlah pengguna dan proses.

### 1.2 Data Race

Data Race merupakan kondisi ketika dua atau lebih thread mengakses lokasi memori yang sama secara bersamaan, setidaknya terdapat satu operasi penulisan, dan tidak terdapat mekanisme sinkronisasi yang tepat.

**Contoh:**

1. Thread 1 membaca nilai variabel X = 10.
2. Thread 2 juga membaca nilai variabel X = 10.
3. Thread 1 melakukan perhitungan 10 + 1 = 11.
4. Thread 2 juga melakukan perhitungan 10 + 1 = 11.
5. Kedua thread menuliskan nilai 11 ke memori.

Hasil akhirnya adalah X = 11, padahal seharusnya X = 12. Hal ini menyebabkan satu proses penambahan nilai tidak tercatat.

### 1.3 Race Condition

Race Condition merupakan kondisi ketika hasil suatu program bergantung pada urutan atau waktu pelaksanaan beberapa proses yang berjalan secara bersamaan.

**Contoh:**

Pada sistem perbankan, saldo awal seseorang adalah Rp100. Dua proses melakukan penarikan sebesar Rp80 secara bersamaan.

1. Proses A memeriksa saldo dan menemukan Rp100.
2. Proses B juga memeriksa saldo dan menemukan Rp100.
3. Kedua proses menganggap saldo mencukupi.
4. Proses A melakukan penarikan Rp80.
5. Proses B juga melakukan penarikan Rp80.

Akibatnya, terjadi double spending dan saldo menjadi minus Rp60.

### 1.4 Perbedaan Data Race dan Race Condition

| Aspek | Data Race | Race Condition |
|---|---|---|
| Fokus | Akses memori secara bersamaan | Urutan dan waktu eksekusi |
| Tingkat | Low-level | High-level |
| Penyebab | Akses memori tanpa sinkronisasi | Urutan eksekusi tidak dapat diprediksi |
| Dampak | Undefined behavior dan inkonsistensi data | Kesalahan hasil atau logika bisnis |
| Solusi | Mutex, Lock, Atomic Operation | Atomic Check-and-Act dan Database Transaction Lock |

---

# 2. TANTANGAN DARI SINKRONISASI

Dalam sistem terdistribusi, sinkronisasi memiliki beberapa tantangan karena proses berjalan pada node yang berbeda dan saling berkomunikasi melalui jaringan.

Tantangan tersebut meliputi:

### 2.1 Network Latency dan Partitioning

Network Latency merupakan keterlambatan waktu dalam pengiriman data melalui jaringan.

Network Partitioning merupakan kondisi ketika sebagian node tidak dapat berkomunikasi dengan node lainnya akibat gangguan jaringan.

Kondisi tersebut dapat menyebabkan keterlambatan komunikasi dan ketidaksesuaian informasi antar-node.

### 2.2 Skalabilitas

Skalabilitas merupakan kemampuan sistem untuk menangani peningkatan jumlah pengguna, proses, dan node.

Semakin banyak node yang terlibat, semakin kompleks proses sinkronisasi dan koordinasi yang diperlukan.

### 2.3 Fault-Tolerant System

Fault Tolerance merupakan kemampuan sistem untuk tetap beroperasi meskipun terdapat komponen yang mengalami kegagalan.

Sistem terdistribusi perlu memiliki mekanisme untuk menghadapi kegagalan node, jaringan, maupun proses tanpa menyebabkan seluruh sistem berhenti bekerja.

### 2.4 Concurrency Control

Concurrency Control merupakan mekanisme untuk mengatur beberapa proses yang berjalan secara bersamaan agar tidak menimbulkan konflik ketika mengakses sumber daya bersama.

### 2.5 Data Consistency

Data Consistency merupakan kondisi ketika informasi yang tersimpan pada berbagai node tetap sesuai dan tidak mengalami perbedaan yang tidak diharapkan.

Sinkronisasi diperlukan agar perubahan data dapat dikelola dengan benar pada seluruh bagian sistem.

### 2.6 Sinkronisasi Waktu

Setiap node dalam sistem terdistribusi memiliki clock atau jam lokal masing-masing. Perbedaan waktu pada setiap perangkat dapat menyebabkan ketidaksesuaian pencatatan kejadian.

Oleh karena itu, diperlukan mekanisme sinkronisasi waktu agar seluruh node memiliki acuan waktu yang sama.

---

# 3. SINKRONISASI WAKTU FISIK

Sinkronisasi waktu fisik merupakan proses penyelarasan real-time clock atau jam nyata pada berbagai komputer dalam sistem terdistribusi menggunakan standar waktu yang sama.

Sinkronisasi ini penting untuk korelasi log, penjadwalan event, dan menjaga konsistensi sistem.

Proses sinkronisasi dapat dilakukan menggunakan protokol jaringan maupun sumber waktu berbasis perangkat keras seperti Atomic Clock dan GPS.

### 3.1 Standar Waktu Umum

Berdasarkan materi perkuliahan, terdapat beberapa standar waktu yang digunakan.

1. **GMT (Greenwich Mean Time):** Standar waktu yang sebelumnya digunakan sebagai acuan waktu dunia dan saat ini sudah tidak digunakan sebagai standar waktu utama.
2. **UTC (Coordinated Universal Time):** Standar waktu internasional yang digunakan sebagai acuan waktu berbagai negara dan sistem komputer.
3. **TAI (International Atomic Time):** Skala waktu atom internasional yang menjadi dasar penting dalam penentuan UTC.
4. **LTC (Coordinated Lunar Time):** Standar waktu yang berkaitan dengan kebutuhan pengukuran waktu di lingkungan Bulan dan masih dalam proses pengembangan.

### 3.2 Sinkronisasi Waktu Menggunakan GPS

GPS dapat digunakan sebagai sumber referensi waktu melalui sinyal yang dikirimkan oleh satelit.

Materi dosen menjelaskan alur sinkronisasi waktu sebagai berikut:

1. Atomic Clock menjadi sumber acuan waktu.
2. Atomic Clock digunakan dalam sistem satelit GPS.
3. Satelit GPS menghasilkan sinyal waktu.
4. GPS Dongle menerima sinyal waktu dari satelit.
5. GPS Dongle terhubung ke server Linux.
6. Server menyediakan layanan sinkronisasi melalui NTP atau PTP.
7. Client seperti Linux, Windows, Mac, dan perangkat mobile melakukan sinkronisasi dengan server.

Dengan mekanisme tersebut, berbagai perangkat dapat menggunakan acuan waktu yang sama.

### 3.3 Sumber Atomic Clock

Berdasarkan materi dosen, beberapa lokasi dan teknologi yang berkaitan dengan Atomic Clock adalah:

1. **GPS Satellites:** Satelit GPS membawa Atomic Clock untuk mendukung navigasi dan penyediaan referensi waktu.
2. **Deep Space Atomic Clock (DSAC):** Teknologi Atomic Clock yang diluncurkan NASA pada tahun 2019 untuk menguji stabilitas jam atom di luar angkasa.
3. **International Space Station (ISS):** Menjadi lokasi pengembangan eksperimen Atomic Clock Ensemble in Space (ACES).
4. **Ground Control:** Pengelolaan referensi waktu dilakukan melalui fasilitas pengendalian di bumi, seperti U.S. Naval Observatory dan Schriever Space Force Base.

### 3.4 Network Time Protocol (NTP)

NTP merupakan protokol jaringan yang digunakan untuk menyinkronkan waktu komputer melalui jaringan.

NTP memungkinkan perangkat memperoleh informasi waktu dari server yang memiliki acuan waktu lebih akurat.

**Fungsi NTP:**

- Menyelaraskan waktu perangkat.
- Mengurangi perbedaan waktu antar-komputer.
- Mendukung pencatatan log.
- Menjaga konsistensi waktu pada sistem terdistribusi.

### 3.5 Chrony

Chrony merupakan implementasi Network Time Protocol yang digunakan untuk menyinkronkan waktu sistem dengan server NTP.

Chrony dapat bekerja pada berbagai kondisi jaringan, termasuk jaringan dengan koneksi yang tidak stabil.

Dalam materi dosen ditunjukkan contoh penggunaan Chrony pada Linux.

**Perintah instalasi Chrony:**

```bash
sudo pacman -S chrony chrony-dinit
```

**Mengaktifkan layanan Chrony:**

```bash
sudo dinitctl enable chrony
```

**Melihat sumber waktu yang digunakan:**

```bash
chronyc -n sources
```

**Melihat informasi sinkronisasi:**

```bash
chronyc -n tracking
```

Chrony membantu administrator memantau sumber waktu, status sinkronisasi, dan perbedaan waktu sistem.

### 3.6 Precision Time Protocol (PTP)

PTP merupakan protokol sinkronisasi waktu dengan presisi tinggi yang distandardisasi melalui IEEE 1588.

PTP digunakan untuk menyelaraskan waktu antarperangkat dengan tingkat ketelitian tinggi, khususnya pada lingkungan jaringan yang membutuhkan ketepatan waktu.

### 3.7 Standar IEEE pada PTP

Berdasarkan materi perkuliahan, perkembangan standar PTP meliputi:

1. **IEEE 1588-2002:** Standar awal Precision Time Protocol.
2. **IEEE 1588-2008:** PTP Version 2 yang tidak kompatibel secara langsung dengan versi 2002.
3. **IEEE 1588-2019:** Pengembangan standar yang menyertakan peningkatan kompatibilitas terhadap standar 2008.
4. **IEEE 802.1AS:** Adaptasi PTP yang disebut gPTP dan digunakan untuk Audio Video Bridging (AVB) serta Time-Sensitive Networking (TSN).

### 3.8 LinuxPTP

LinuxPTP merupakan implementasi Precision Time Protocol untuk sistem operasi Linux.

Dalam materi dosen, terdapat dua program utama yang digunakan dalam implementasi LinuxPTP:

1. **ptp4l:** Program untuk menjalankan dan mengelola sinkronisasi PTP.
2. **phc2sys:** Program untuk menyinkronkan dua atau lebih clock dalam sistem.

Referensi LinuxPTP:

https://linuxptp.nwtime.org/

### 3.9 Hardware Timestamping

Hardware Timestamping merupakan kemampuan perangkat jaringan untuk mencatat waktu pengiriman dan penerimaan paket secara langsung melalui perangkat keras.

Dalam penggunaan PTP, NIC (Network Interface Card) harus mendukung Hardware Timestamping agar sinkronisasi dapat mencapai tingkat presisi yang dibutuhkan.

NIC yang tidak mendukung fitur tersebut memiliki keterbatasan dalam melakukan sinkronisasi waktu berbasis perangkat keras.

---

# 4. SINKRONISASI WAKTU LOGIS

Sinkronisasi waktu logis merupakan metode yang digunakan dalam sistem terdistribusi untuk menentukan urutan sebab-akibat suatu kejadian (causal order of events).

Berbeda dengan sinkronisasi waktu fisik, sinkronisasi waktu logis tidak bergantung pada jam nyata atau real clock.

Prinsip dasarnya adalah apabila kejadian A terjadi sebelum B dan B terjadi sebelum C, maka A juga terjadi sebelum C. Prinsip ini disebut transitivity.

### 4.1 Lamport Logical Clock

Lamport Logical Clock merupakan algoritma yang diperkenalkan oleh Leslie Lamport untuk menentukan urutan kejadian pada sistem terdistribusi.

Algoritma ini menggunakan nilai penghitung logis untuk mencatat urutan kejadian tanpa harus menyamakan waktu fisik setiap komputer.

Aturan dasar Lamport Logical Clock:

1. Setiap terjadi suatu kejadian, nilai logical clock bertambah satu.
2. Ketika mengirim pesan, proses menyertakan nilai logical clock.
3. Ketika menerima pesan, proses membandingkan nilai clock lokal dengan nilai clock dari pesan.
4. Proses mengambil nilai terbesar, kemudian menambahkan satu.

### 4.2 Vector Clocks

Vector Clocks merupakan metode pencatatan waktu logis yang menggunakan sekumpulan nilai penghitung untuk setiap proses dalam sistem terdistribusi.

Berbeda dengan Lamport Logical Clock yang menggunakan satu nilai penghitung, Vector Clocks menggunakan vector untuk mengetahui hubungan sebab-akibat antar-kejadian.

Dalam materi dosen, contoh menggunakan tiga proses:

- Proses A berada pada indeks 0.
- Proses B berada pada indeks 1.
- Proses C berada pada indeks 2.

Kondisi awal seluruh proses adalah:

```text
A = [0, 0, 0]
B = [0, 0, 0]
C = [0, 0, 0]
```

### 4.3 Aturan Vector Clocks

Vector Clocks memiliki beberapa aturan:

1. Setiap proses memiliki vector clock sendiri.
2. Setiap terjadi internal event, proses menambahkan satu pada indeks miliknya.
3. Sebelum mengirim pesan, proses memperbarui vector clock miliknya dan menyertakan nilai tersebut pada pesan.
4. Ketika menerima pesan, proses membandingkan vector clock yang diterima dengan vector lokal menggunakan elemen-wise maximum.
5. Setelah menerima pesan, proses menambahkan satu pada indeks miliknya.

### 4.4 Contoh Proses Vector Clocks

Berdasarkan contoh pada materi dosen, proses komunikasi dilakukan oleh A, B, dan C.

**Tahap 1: Proses A**

Proses A melakukan internal event sehingga vector clock berubah menjadi:

```text
A = [1, 0, 0]
```

Kemudian A akan mengirim pesan kepada B. Sebelum mengirim pesan, A menambahkan satu pada clock miliknya:

```text
A = [2, 0, 0]
```

Nilai tersebut dikirimkan kepada B.

**Tahap 2: Proses B**

Proses B menerima pesan dari A dan membandingkan vector clock yang diterima dengan vector lokal.

```text
[2, 0, 0] vs [0, 0, 0]
```

Hasil elemen-wise maximum:

```text
[2, 0, 0]
```

**Tahap 3: Proses B Mengirim Pesan ke C**

Sebelum mengirim pesan, B menambahkan satu pada indeks miliknya.

```text
B = [2, 1, 0]
```

Kemudian vector clock tersebut dikirim kepada C.

**Tahap 4: Proses C**

C menerima pesan dan membandingkan vector clock yang diterima dengan vector lokal.

```text
[2, 1, 0] vs [0, 0, 0]
```

Hasilnya:

```text
[2, 1, 0]
```

Setelah menerima pesan, C menambahkan satu pada indeks miliknya karena terjadi internal event.

```text
C = [2, 1, 1]
```

C kemudian melakukan internal event berikutnya sehingga menjadi:

```text
C = [2, 1, 2]
```

### 4.5 Hasil Akhir Vector Clocks

Setelah seluruh proses selesai, nilai vector clock adalah:

```text
A = [2, 0, 0]
B = [2, 1, 0]
C = [2, 1, 2]
```

Nilai tersebut menunjukkan perkembangan kejadian yang telah dilakukan oleh masing-masing proses.

### 4.6 Menentukan Hubungan Kejadian

Vector Clocks dapat digunakan untuk menentukan apakah suatu kejadian terjadi sebelum kejadian lainnya atau berlangsung secara bersamaan.

Aturannya:

1. Kejadian A terjadi sebelum B apabila seluruh komponen vector A lebih kecil atau sama dengan komponen vector B dan minimal terdapat satu komponen yang lebih kecil.
2. Dua kejadian disebut concurrent atau independen apabila tidak terdapat hubungan urutan berdasarkan perbandingan seluruh komponennya.

**Contoh:**

```text
A = [2, 0, 0]
B = [2, 1, 0]
C = [2, 1, 2]
```

- A terjadi sebelum B karena seluruh komponen A lebih kecil atau sama dengan B.
- B terjadi sebelum C karena seluruh komponen B lebih kecil atau sama dengan C.
- A terjadi sebelum C karena seluruh komponen A lebih kecil atau sama dengan C.

Namun, C terakhir bersifat independen terhadap A pada contoh perbandingan kejadian yang terdapat dalam slide dosen.

### 4.7 Implementasi Vector Clocks

Dalam materi dosen, implementasi Vector Clocks ditunjukkan menggunakan file Python bernama `vclocks.py`.

Program tersebut digunakan untuk memperlihatkan perubahan nilai vector clock pada beberapa proses dan menentukan hubungan kejadian.

Contoh menjalankan program:

```bash
python vclocks.py
```

---

# 5. TANTANGAN MUTUAL EXCLUSION

Mutual Exclusion merupakan prinsip dalam ilmu komputer yang memastikan hanya satu proses atau thread yang dapat mengakses sumber daya bersama pada satu waktu.

Tujuannya adalah mencegah konflik dan menjaga integritas data ketika beberapa proses membutuhkan akses terhadap sumber daya yang sama.

Contoh sumber daya bersama meliputi printer, file, dan database.

### 5.1 Critical Section

Critical Section merupakan bagian dari kode program yang mengakses atau memodifikasi sumber daya bersama.

Untuk mencegah konflik, diperlukan mekanisme mutual exclusion agar tidak terdapat dua proses yang menjalankan bagian critical section secara bersamaan terhadap sumber daya yang sama.

### 5.2 Prinsip Mutual Exclusion

Terdapat empat prinsip yang perlu diperhatikan:

1. **Mutual Exclusion:** Hanya satu proses yang diperbolehkan mengakses sumber daya bersama pada satu waktu.
2. **Progress:** Apabila tidak ada proses yang sedang menggunakan critical section, proses lain yang membutuhkan akses harus dapat melanjutkan.
3. **Bounded Waiting:** Tidak boleh ada proses yang menunggu selamanya untuk mendapatkan akses ke critical section.
4. **Fairness:** Permintaan akses harus dilayani secara adil berdasarkan urutan yang wajar.

### 5.3 Centralized Algorithm

Centralized Algorithm merupakan algoritma mutual exclusion yang menggunakan satu node sebagai koordinator untuk mengatur akses terhadap critical section.

**Cara kerja:**

1. Proses meminta izin kepada koordinator.
2. Koordinator memeriksa apakah critical section sedang digunakan.
3. Jika tidak digunakan, koordinator memberikan izin.
4. Proses menjalankan critical section.
5. Setelah selesai, proses melepaskan akses.
6. Koordinator memberikan izin kepada proses berikutnya.

**Kelebihan:**
- Mekanisme sederhana.
- Biaya komunikasi relatif rendah.

**Kekurangan:**
- Memiliki single point of failure.
- Koordinator dapat menjadi bottleneck apabila menerima terlalu banyak permintaan.

### 5.4 Ricart-Agrawala Algorithm

Ricart-Agrawala merupakan algoritma mutual exclusion yang bekerja secara terdistribusi tanpa menggunakan satu koordinator pusat.

Algoritma ini menggunakan pesan permintaan yang dilengkapi timestamp untuk menentukan prioritas akses ke critical section.

**Cara kerja:**

1. Proses mengirimkan pesan permintaan akses kepada proses lainnya.
2. Pesan dilengkapi dengan timestamp.
3. Proses menunggu balasan dari seluruh proses lain.
4. Proses dapat memasuki critical section setelah memperoleh jawaban OK dari seluruh proses lainnya.

Jumlah pesan yang diperlukan untuk setiap akses critical section adalah:

```text
2 × (N - 1)
```

Dengan N merupakan jumlah proses dalam sistem.

**Kelebihan:**
- Tidak membutuhkan koordinator pusat.
- Mekanisme koordinasi dilakukan secara terdistribusi.

**Kekurangan:**
- Memiliki overhead komunikasi yang tinggi karena memerlukan banyak pesan.

### 5.5 Token-Based Algorithm

Token-Based Algorithm merupakan algoritma mutual exclusion yang menggunakan satu token unik yang beredar di antara proses.

Hanya proses yang memiliki token yang diperbolehkan memasuki critical section.

**Cara kerja:**

1. Token diberikan atau diedarkan kepada proses.
2. Proses yang memiliki token memperoleh hak akses ke critical section.
3. Setelah selesai, token diteruskan kepada proses berikutnya.
4. Proses lain harus menunggu sampai memperoleh token.

**Kelebihan:**
- Hanya membutuhkan satu pesan per perpindahan token dalam mekanisme akses normal.

**Kekurangan:**
- Apabila token hilang, diperlukan mekanisme pemulihan.
- Deteksi kehilangan token dapat menjadi sulit.

---

# 6. PEMILIHAN KOORDINATOR

Pemilihan koordinator merupakan proses menentukan satu node atau proses yang bertugas mengoordinasikan aktivitas dalam sistem terdistribusi.

Dalam sistem terdistribusi, beberapa node mungkin membutuhkan satu koordinator untuk mengelola sumber daya bersama, menyinkronkan operasi, dan membuat keputusan global.

Ketika koordinator mengalami kegagalan atau terdapat node baru yang bergabung, sistem harus memiliki mekanisme untuk memilih pemimpin baru secara otomatis.

### 6.1 Bully Algorithm

Bully Algorithm merupakan algoritma pemilihan koordinator yang digunakan untuk menentukan pemimpin baru ketika koordinator sebelumnya mengalami kegagalan.

Algoritma ini menggunakan identitas atau ID proses untuk menentukan proses yang memiliki prioritas lebih tinggi.

Proses dengan ID tertinggi yang masih aktif dapat menjadi koordinator baru.

### 6.2 Ring Algorithm

Ring Algorithm merupakan algoritma pemilihan koordinator yang mengatur proses dalam bentuk struktur melingkar atau ring.

Pesan pemilihan dikirimkan dari satu proses ke proses berikutnya sampai proses yang berpartisipasi diketahui.

Melalui mekanisme tersebut, sistem dapat menentukan koordinator baru berdasarkan hasil proses pemilihan.

### 6.3 Raft dan Paxos

Raft dan Paxos merupakan algoritma konsensus yang digunakan dalam sistem terdistribusi untuk mencapai kesepakatan di antara beberapa node.

Algoritma tersebut membantu menjaga konsistensi keputusan meskipun terdapat node yang mengalami kegagalan.

### 6.4 Contoh Penerapan Pemilihan Koordinator

Berdasarkan materi dosen, terdapat beberapa contoh penerapan teknologi koordinasi dan konsensus:

1. **Apache ZooKeeper:** Menggunakan protokol Zab (ZooKeeper Atomic Broadcast) untuk mengatur koordinasi dan konsistensi data dalam sistem terdistribusi. Zab memiliki konsep yang berkaitan dengan protokol konsensus seperti Paxos.
2. **Kubernetes:** Menggunakan Raft melalui etcd untuk mendukung penyimpanan data dan koordinasi cluster.

---

# REFERENSI

1. Materi Perkuliahan Sistem Terdistribusi dan Terdesentralisasi. Dr. Bambang Purnomosidi D. P. Fakultas Teknologi Informasi, UTDI. Materi 03: Sinkronisasi dan Koordinasi pada Sistem Terdistribusi.

2. National Institute of Standards and Technology (NIST).  
   https://www.nist.gov/

3. Chrony Documentation.  
   https://chrony-project.org/

4. Linux PTP Project.  
   https://linuxptp.nwtime.org/

5. GPS NTP Timeserver.  
   https://github.com/bohnelang/gps_ntp_timeserver

6. Distributed System: Types of Distributed Deadlock.  
   https://www.geeksforgeeks.org/operating-systems/distributed-system-types-of-distributed-deadlock/

---

**AKHIR MATERI MINGGU 3**
