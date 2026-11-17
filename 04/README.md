
# MODUL 04 : KONSISTENSI DAN REPLIKASI PADA SISTEM TERDISTRIBUSI

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
5. Mempertahankan contoh, algoritma, protokol, dan studi kasus yang terdapat dalam materi dosen.

---

# 1. APA ITU KONSISTENSI PADA SISTEM TERDISTRIBUSI?

Konsistensi pada sistem terdistribusi merupakan kondisi ketika seluruh node atau server dalam suatu sistem memiliki data yang sama atau menampilkan data yang sama pada waktu tertentu. Hal ini diperlukan karena data dalam sistem terdistribusi dapat disimpan pada beberapa server yang berada di lokasi berbeda dan dapat mengalami perubahan secara bersamaan.

Ketika suatu aplikasi melakukan perubahan data pada salah satu server, sistem harus memastikan bahwa perubahan tersebut juga diterapkan pada server lainnya sesuai dengan model konsistensi yang digunakan.

### 1.1 Cara Kerja Konsistensi

Proses konsistensi dapat dijelaskan melalui beberapa tahapan:

1. Aplikasi memiliki beberapa salinan data yang tersimpan pada server berbeda.
2. Pengguna melakukan perubahan data pada salah satu server.
3. Sistem mengirimkan perubahan tersebut ke server lainnya.
4. Server lain memperbarui salinan datanya.
5. Seluruh salinan data akan mengikuti aturan konsistensi yang diterapkan oleh sistem.

Dengan demikian, pengguna dapat memperoleh informasi yang benar ketika mengakses data dari berbagai server.

---

# 2. MENGAPA KONSISTENSI PENTING PADA SISTEM TERDISTRIBUSI?

Konsistensi sangat penting karena data disimpan pada banyak node sehingga berpotensi mengalami perbedaan antara satu server dengan server lainnya.

Jika konsistensi tidak diperhatikan, pengguna dapat melihat versi data yang berbeda tergantung pada server yang melayani permintaan tersebut.

### 2.1 Contoh Kasus pada Sistem Perbankan

Misalnya, seorang nasabah melakukan transfer uang dari rekening A ke rekening B.

1. Server 1 berhasil mengurangi saldo rekening A.
2. Server 2 belum melakukan penambahan saldo rekening B.
3. Nasabah mencoba menggunakan saldo rekening B untuk melakukan transaksi.
4. Sistem menolak transaksi karena saldo pada server 2 belum diperbarui.
5. Kondisi tersebut menunjukkan adanya ketidakkonsistenan data antar-server.

### 2.2 Tujuan Konsistensi

Tujuan utama konsistensi adalah memastikan pengguna mendapatkan data yang benar dan terbaru meskipun data disimpan pada beberapa node.

Konsistensi juga berkaitan dengan keseimbangan antara tiga aspek utama sistem terdistribusi, yaitu Consistency, Availability, dan Partition Tolerance yang dikenal sebagai Teorema CAP.

---

# 3. TEOREMA CAP

Teorema CAP merupakan konsep dalam sistem terdistribusi yang menjelaskan hubungan antara tiga karakteristik utama, yaitu Consistency, Availability, dan Partition Tolerance.

Ketiga karakteristik tersebut menjadi pertimbangan dalam menentukan bagaimana sistem tetap bekerja ketika terjadi gangguan komunikasi jaringan.

### 3.1 Consistency (C)

Consistency merupakan kondisi ketika setiap pembacaan data mendapatkan nilai yang konsisten sesuai dengan perubahan yang telah berhasil dilakukan.

Dalam materi perkuliahan, konsistensi dijelaskan sebagai kondisi ketika seluruh node memiliki data yang sama.

### 3.2 Availability (A)

Availability merupakan kemampuan sistem untuk tetap memberikan respons terhadap permintaan pengguna ketika data dibutuhkan.

Sistem yang memiliki availability tinggi berusaha tetap melayani permintaan meskipun terdapat gangguan pada sebagian komponen.

### 3.3 Partition Tolerance (P)

Partition Tolerance merupakan kemampuan sistem untuk tetap berjalan meskipun terdapat satu atau beberapa komponen jaringan yang mengalami kegagalan komunikasi atau terputus.

Network Partition dapat terjadi ketika node dalam sistem tidak dapat saling berkomunikasi.

### 3.4 Hubungan Ketiga Komponen CAP

Teorema CAP menjelaskan adanya trade-off antara ketiga karakteristik tersebut ketika terjadi network partition.

Dalam kondisi partisi jaringan, sistem perlu menentukan prioritas antara konsistensi dan ketersediaan.

Dua pendekatan yang dijelaskan dalam materi adalah:

**1. AP (Availability dan Partition Tolerance)**

- Sistem tetap melayani permintaan pengguna meskipun jaringan mengalami gangguan.
- Data pada beberapa server dapat mengalami perbedaan sementara.
- Sistem mengutamakan ketersediaan layanan.

**2. CP (Consistency dan Partition Tolerance)**

- Sistem mengutamakan konsistensi data.
- Transaksi tertentu dapat ditolak atau ditunda sampai jaringan kembali normal.
- Ketersediaan layanan dikorbankan untuk menjaga konsistensi.

### 3.5 Contoh Kasus Teorema CAP pada E-Commerce

Misalnya terdapat aplikasi e-commerce dengan dua server:

- Server A melayani wilayah Indonesia bagian barat.
- Server B melayani wilayah Indonesia bagian timur.

Ketika jaringan antara kedua wilayah terputus, terdapat dua kemungkinan pendekatan:

1. Jika sistem memilih AP, pengguna di kedua wilayah tetap dapat melakukan pembelian. Namun, informasi stok barang mungkin belum sinkron.
2. Jika sistem memilih CP, sistem dapat menolak transaksi sampai jaringan kembali normal agar informasi stok tetap konsisten.

Dengan demikian, Teorema CAP membantu menentukan prioritas sistem ketika terjadi gangguan jaringan.

---

# 4. MODEL KONSISTENSI

Model konsistensi merupakan aturan atau jaminan yang menentukan bagaimana dan kapan perubahan data pada suatu node dapat dilihat oleh node atau klien lainnya.

Setiap model memiliki tingkat jaminan yang berbeda mengenai penyebaran perubahan data ke seluruh salinan.

### 4.1 Strong Consistency

Strong Consistency merupakan model konsistensi yang memastikan seluruh node dapat melihat versi data terbaru setelah perubahan dilakukan.

Setiap operasi pembacaan setelah penulisan harus memperoleh nilai yang sesuai dengan hasil penulisan tersebut.

Model ini biasanya menggunakan protokol seperti Two-Phase Commit atau Paxos.

**Contoh:**

Pada sistem perbankan, ketika saldo rekening mengalami perubahan, seluruh server harus menggunakan nilai saldo terbaru agar tidak terjadi kesalahan transaksi.

### 4.2 Eventual Consistency

Eventual Consistency merupakan model konsistensi yang tidak mengharuskan seluruh node memiliki data yang sama secara langsung.

Namun, apabila tidak terdapat pembaruan data baru, seluruh replika pada akhirnya akan memiliki nilai yang sama.

Model ini cocok digunakan pada sistem yang mengutamakan availability dan kecepatan respons.

**Contoh:**

- Amazon DynamoDB.
- Apache Cassandra.

Pada sistem tersebut, perubahan data mungkin membutuhkan waktu untuk menyebar ke seluruh node.

### 4.3 BASE

BASE merupakan pendekatan yang berkaitan dengan Eventual Consistency.

BASE terdiri dari tiga prinsip:

1. **Basically Available:** Sistem berusaha memastikan layanan tetap tersedia sehingga data dapat dibaca atau ditulis meskipun terjadi sebagian kegagalan.
2. **Soft State:** Kondisi data pada replika dapat berubah seiring waktu karena proses sinkronisasi masih berlangsung.
3. **Eventual Consistency:** Data pada seluruh node pada akhirnya akan konsisten apabila tidak ada pembaruan baru dalam jangka waktu tertentu.

### 4.4 Causal Consistency

Causal Consistency merupakan model konsistensi yang menjaga urutan operasi berdasarkan hubungan sebab-akibat.

Jika suatu operasi bergantung pada operasi lainnya, urutan tersebut harus tetap dipertahankan.

Sementara itu, operasi yang tidak memiliki hubungan sebab-akibat dapat terlihat dalam urutan berbeda pada node lainnya.

**Contoh:**

Pada media sosial, seseorang membuat sebuah postingan kemudian pengguna lain memberikan komentar atau reaksi.

Komentar dan reaksi tersebut tidak boleh muncul sebelum postingan yang menjadi penyebabnya.

### 4.5 Read-Your-Writes Consistency

Read-Your-Writes Consistency merupakan model konsistensi yang memastikan pengguna dapat melihat hasil perubahan data yang telah ditulisnya sendiri ketika melakukan pembacaan berikutnya.

Model ini tidak menjamin bahwa pengguna lain langsung melihat perubahan yang sama pada waktu bersamaan.

**Contoh:**

Ketika pengguna mengirim pesan melalui aplikasi messaging, pesan tersebut langsung muncul pada layar pengirim meskipun penerima belum melihatnya.

### 4.6 Monotonic Read Consistency

Monotonic Read Consistency merupakan model konsistensi yang memastikan pengguna tidak melihat versi data yang lebih lama dari versi yang sebelumnya telah dibaca.

Dengan kata lain, setelah pengguna memperoleh suatu versi data, pembacaan berikutnya tidak boleh kembali menampilkan versi yang lebih lama.

**Contoh:**

Pada aplikasi media sosial, timeline tidak seharusnya kembali menampilkan versi lama setelah pengguna melakukan refresh.

### 4.7 Sequential Consistency

Sequential Consistency merupakan model konsistensi yang memastikan seluruh operasi pada sistem terlihat seolah-olah dijalankan dalam urutan yang sama oleh seluruh node.

Namun, urutan tersebut tidak harus sesuai dengan waktu nyata.

**Contoh:**

Pada media sosial, seluruh pengguna melihat urutan postingan yang sama meskipun terdapat sedikit keterlambatan dalam penyebaran data.

### 4.8 Linearizability

Linearizability merupakan salah satu bentuk konsistensi yang paling kuat dan menjadi varian dari Strong Consistency.

Model ini memastikan operasi terlihat seolah-olah dilakukan secara atomik dan langsung dalam satu urutan global yang sesuai dengan waktu nyata.

Setelah suatu operasi penulisan selesai, pembacaan berikutnya oleh klien mana pun harus mencerminkan hasil penulisan tersebut atau penulisan setelahnya.

**Contoh penerapan:**

- etcd.
- ZooKeeper.
- Google Spanner.

**Contoh kasus:**

Pada proses pengecekan keunikan ID atau username, sistem harus memastikan dua pengguna tidak dapat mendaftarkan username yang sama secara bersamaan.

### 4.9 Perbedaan Model Konsistensi

| Model | Karakteristik Utama |
|---|---|
| Strong Consistency | Seluruh pembacaan mendapatkan data terbaru sesuai urutan operasi yang dijamin sistem. |
| Eventual Consistency | Data akan sama pada akhirnya jika tidak ada pembaruan baru. |
| Causal Consistency | Menjaga urutan operasi yang memiliki hubungan sebab-akibat. |
| Read-Your-Writes | Pengguna dapat melihat perubahan yang telah ditulisnya sendiri. |
| Monotonic Read | Pengguna tidak melihat versi data yang lebih lama dari yang pernah dibaca. |
| Sequential Consistency | Seluruh node melihat urutan operasi yang sama, tetapi tidak harus real-time. |
| Linearizability | Operasi terlihat atomik dan mengikuti urutan global berdasarkan waktu nyata. |

---

# 5. TRADE-OFF LATENSI DENGAN KONSISTENSI

Trade-off latensi dengan konsistensi merupakan kompromi yang harus dipertimbangkan dalam sistem terdistribusi.

Semakin tinggi tingkat konsistensi yang ingin dijamin, biasanya semakin besar latensi atau waktu respons yang harus ditanggung pengguna.

Hubungan keduanya dapat dijelaskan sebagai berikut:

- Konsistensi meningkat → latensi cenderung meningkat.
- Konsistensi menurun → latensi cenderung menurun.

### 5.1 Strong Consistency dan Latensi

Pada Strong Consistency, sistem harus memastikan bahwa data pada node terkait sudah memenuhi aturan konsistensi sebelum memberikan respons kepada pengguna.

**Dampak:**

1. Sistem perlu menunggu komunikasi antar-server.
2. Proses sinkronisasi membutuhkan waktu.
3. Latensi menjadi lebih tinggi.
4. Data yang diberikan memiliki jaminan konsistensi lebih kuat.

### 5.2 Eventual Consistency dan Latensi

Pada Eventual Consistency, sistem dapat memberikan respons tanpa harus menunggu seluruh replika selesai melakukan sinkronisasi.

**Dampak:**

1. Sistem dapat memberikan respons lebih cepat.
2. Tidak perlu menunggu seluruh server memperbarui data.
3. Latensi cenderung lebih rendah.
4. Data dapat berbeda sementara pada beberapa server.

### 5.3 Contoh Kasus Dua Pusat Data

Misalnya terdapat dua pusat data yang berada di:

- Jakarta.
- Yogyakarta.

Seorang pengguna melakukan perubahan data di pusat data Jakarta. Sistem kemudian perlu menyebarkan perubahan tersebut ke pusat data Yogyakarta.

Terdapat dua pendekatan:

**1. Menggunakan Strong Consistency**

- Sistem menunggu sampai data Jakarta dan Yogyakarta memenuhi konsistensi.
- Setelah proses sinkronisasi selesai, sistem memberikan respons.
- Data lebih konsisten, tetapi waktu respons lebih lambat.

**2. Menggunakan Eventual Consistency**

- Sistem dapat langsung memberikan respons dari Jakarta.
- Perubahan data akan dikirimkan ke Yogyakarta setelahnya.
- Respons lebih cepat, tetapi kedua pusat data dapat memiliki data berbeda untuk sementara waktu.

---

# 6. PENGERTIAN REPLIKASI DATA

Replikasi data merupakan proses membuat dan memelihara salinan data yang sama pada beberapa node atau server dalam sistem terdistribusi.

Tujuan utama replikasi adalah meningkatkan ketersediaan, keandalan, dan kecepatan sistem meskipun terdapat salah satu node yang mengalami kegagalan.

### 6.1 Cara Kerja Replikasi Data

Proses replikasi dapat dijelaskan melalui tahapan berikut:

1. Sistem memiliki database utama atau source.
2. Data disimpan pada database utama.
3. Sistem membuat salinan data pada beberapa server replika.
4. Ketika terjadi perubahan data, sistem menyebarkan perubahan tersebut ke replika.
5. Replika memperbarui data sesuai mekanisme replikasi yang digunakan.

### 6.2 Contoh Replikasi Data

Misalnya sebuah perusahaan memiliki database utama di Jakarta.

Untuk meningkatkan ketersediaan data, perusahaan membuat salinan database di Yogyakarta dan Denpasar.

Dengan demikian, apabila server utama mengalami gangguan, server lain tetap memiliki salinan data yang dapat digunakan sesuai kebijakan sistem.

### 6.3 Tujuan Replikasi Data

1. **Availability:** Jika satu server mengalami kegagalan, server lain masih memiliki salinan data.
2. **Performance:** Pengguna dapat membaca data dari server terdekat sehingga waktu akses lebih cepat.
3. **Reliability:** Risiko kehilangan data dapat dikurangi karena terdapat salinan data di beberapa lokasi.
4. **Scalability:** Beban pembacaan data atau read load dapat dibagi ke beberapa server.

---

# 7. JENIS REPLIKASI

Jenis replikasi merupakan metode yang digunakan untuk menentukan bagaimana data ditulis, dibaca, dan disinkronkan pada beberapa node.

Dalam materi perkuliahan, terdapat empat jenis replikasi utama.

### 7.1 Master-Slave (Primary-Secondary)

Master-Slave merupakan jenis replikasi yang menggunakan satu server utama sebagai master dan beberapa server lain sebagai slave atau secondary.

Master bertugas melakukan penulisan data, sedangkan slave digunakan untuk membaca data.

**Karakteristik:**

- Penulisan data dilakukan pada master.
- Slave menerima salinan perubahan dari master.
- Dapat menjaga konsistensi sesuai mekanisme replikasi yang digunakan.
- Master berpotensi menjadi bottleneck.

**Contoh:**

PostgreSQL Streaming Replication.

### 7.2 Multi-Master (Peer-to-Peer)

Multi-Master merupakan jenis replikasi yang memungkinkan beberapa node melakukan operasi baca dan tulis.

Setiap node memiliki kemampuan untuk memperbarui data dan menyebarkan perubahan ke node lainnya.

**Karakteristik:**

- Semua node dapat membaca dan menulis data.
- Lebih fleksibel dibandingkan Master-Slave.
- Memerlukan mekanisme penanganan konflik data.
- Memiliki risiko konflik ketika beberapa node memperbarui data yang sama.

**Contoh:**

- PostgreSQL Logical Replication.
- Apache Cassandra.
- MongoDB.
- Apache Ignite.

### 7.3 Synchronous Replication

Synchronous Replication merupakan metode replikasi yang mengharuskan perubahan data dikonfirmasi oleh replika sesuai persyaratan sinkronisasi sebelum operasi dianggap selesai.

**Karakteristik:**

- Mengutamakan konsistensi data.
- Proses penulisan membutuhkan komunikasi dengan replika.
- Waktu respons cenderung lebih lambat.

**Contoh:**

Google Spanner.

### 7.4 Asynchronous Replication

Asynchronous Replication merupakan metode replikasi yang mengirimkan perubahan data ke node lain setelah transaksi selesai pada master.

**Karakteristik:**

- Tidak perlu menunggu seluruh replika selesai memperbarui data.
- Memiliki performa lebih cepat.
- Dapat terjadi keterlambatan penyebaran data atau data delay.

**Contoh:**

- MySQL Asynchronous Replication.
- DynamoDB.

---

# 8. STRATEGI SINKRONISASI REPLIKA

Strategi sinkronisasi replika merupakan metode untuk mengatur bagaimana perubahan data disebarkan dan diselaraskan pada beberapa replika.

Dalam materi dosen, strategi sinkronisasi dibagi berdasarkan waktu sinkronisasi, arah replikasi, cara sinkronisasi, dan penanganan konflik.

### 8.1 Berdasarkan Waktu Sinkronisasi

Terdapat tiga pendekatan berdasarkan waktu sinkronisasi:

1. Synchronous.
2. Asynchronous.
3. Semi-Synchronous.

**A. Asynchronous**

Sumber melakukan commit tanpa menunggu replika menerima atau menyelesaikan perubahan data.

Karakteristik:

- Performa paling cepat.
- Tidak perlu menunggu replika.
- Memiliki risiko kehilangan data tertinggi apabila terjadi kegagalan sebelum perubahan tersinkronisasi.

**B. Semi-Synchronous**

Sumber menunggu setidaknya satu replika menerima data sebelum melanjutkan proses sesuai mekanisme yang digunakan.

Karakteristik:

- Menjadi kompromi antara konsistensi dan performa.
- Lebih aman dibandingkan asynchronous.
- Digunakan pada MySQL.

**C. Synchronous**

Sumber menunggu seluruh replika melakukan commit data sebelum proses dianggap selesai.

Karakteristik:

- Memiliki konsistensi paling tinggi.
- Membutuhkan komunikasi dengan seluruh replika.
- Performa cenderung lebih rendah.

### 8.2 Berdasarkan Arah Replikasi

Strategi berdasarkan arah replikasi terdiri dari:

**1. Master-Slave**

Satu node bertugas melakukan operasi baca dan tulis, sedangkan node lainnya berperan sebagai replika untuk membaca data.

**2. Master-Master**

Seluruh node memiliki peran dan kemampuan yang setara dalam melakukan operasi baca dan tulis.

**3. Master-Master Asymmetric**

Beberapa node dapat melakukan operasi baca dan tulis, tetapi memiliki perbedaan peran, sumber daya, atau kemampuan.

### 8.3 Berdasarkan Cara Sinkronisasi

Terdapat tiga cara sinkronisasi replika:

**1. Pull-Based**

Replika secara berkala memeriksa apakah terdapat perubahan data pada source.

Jika ditemukan perubahan, replika mengambil dan memperbarui data. Jika tidak terdapat perubahan, replika tidak melakukan pembaruan.

**2. Push-Based**

Source secara aktif mengirimkan perubahan data kepada replika ketika terjadi pembaruan.

Dalam materi dosen, pendekatan ini dapat menggunakan CDC (Change Data Capture) pada source, kemudian mengirimkan perubahan melalui WebSockets atau SSE (Server-Sent Events).

**3. Hybrid**

Hybrid merupakan gabungan antara metode Pull-Based dan Push-Based.

### 8.4 Berdasarkan Penanganan Konflik

Ketika beberapa node melakukan pembaruan data secara bersamaan, sistem membutuhkan mekanisme untuk menyelesaikan konflik.

Beberapa metode yang digunakan adalah:

1. LWW (Last Write Wins).
2. Vector Clock.
3. CRDT (Conflict-free Replicated Data Types).
4. OT (Operational Transformation).

### 8.5 LWW (Last Write Wins)

Last Write Wins merupakan metode penyelesaian konflik yang memilih pembaruan berdasarkan timestamp terbaru.

Perubahan dengan timestamp terbaru akan dipertahankan, sedangkan perubahan lainnya tidak digunakan.

### 8.6 Vector Clock

Vector Clock merupakan metode yang menggunakan sekumpulan nilai penghitung untuk mengetahui hubungan sebab-akibat antara perubahan data.

Metode ini membantu sistem mengetahui apakah suatu perubahan terjadi sebelum perubahan lainnya atau berlangsung secara bersamaan.

Konsep Vector Clock telah dibahas pada materi minggu sebelumnya.

### 8.7 CRDT (Conflict-Free Replicated Data Types)

CRDT merupakan struktur data yang dirancang agar beberapa replika dapat melakukan perubahan secara independen dan kemudian digabungkan tanpa menimbulkan konflik yang menghambat konsistensi.

Dalam pendekatan ini, penggabungan perubahan dilakukan berdasarkan aturan struktur data yang digunakan, bukan hanya mengandalkan satu server pusat.

**Contoh:**

Yjs, yaitu teknologi yang digunakan untuk mendukung kolaborasi dalam editor dokumen.

### 8.8 Contoh CRDT

Misalnya Agnes Monica dan Bambang menghitung jumlah pengunjung website menggunakan local map.

**Kondisi awal:**

```text
Agnes Monica = {"Agnes Monica": 0, "Bambang": 0}
Bambang      = {"Agnes Monica": 0, "Bambang": 0}
```

Agnes Monica mencatat lima pengunjung:

```text
{"Agnes Monica": 5, "Bambang": 0}
```

Bambang mencatat tiga pengunjung:

```text
{"Agnes Monica": 0, "Bambang": 3}
```

Ketika kedua perangkat melakukan sinkronisasi, CRDT menggunakan aturan Max untuk setiap nilai.

```text
Agnes Monica = max(5, 0) = 5
Bambang      = max(0, 3) = 3
```

Hasil akhir:

```text
{"Agnes Monica": 5, "Bambang": 3}
```

Total pengunjung:

```text
5 + 3 = 8
```

Dengan demikian, kedua perangkat memperoleh hasil akhir yang sama.

### 8.9 OT (Operational Transformation)

Operational Transformation merupakan metode penyelesaian konflik yang melakukan transformasi operasi berdasarkan perubahan yang dilakukan secara bersamaan oleh pengguna.

Metode ini digunakan agar perubahan yang dilakukan oleh beberapa pengguna pada dokumen bersama tetap menghasilkan isi dokumen yang konsisten.

### 8.10 Contoh Operational Transformation

Misalnya Agnes Monica dan Bambang mengedit dokumen yang berisi teks:

```text
abc
```

Keduanya melakukan perubahan secara bersamaan.

**Perubahan Agnes Monica:**

Agnes menyisipkan huruf x pada indeks 0.

Hasil lokal:

```text
xabc
```

**Perubahan Bambang:**

Bambang menghapus karakter c pada indeks 2.

Hasil lokal:

```text
ab
```

**Terjadinya Konflik:**

Jika perubahan Bambang diterapkan langsung pada dokumen Agnes tanpa penyesuaian posisi, penghapusan indeks 2 akan menghapus huruf b sehingga hasilnya:

```text
xac
```

Sebaliknya, jika perubahan Agnes diterapkan langsung pada dokumen Bambang, hasilnya:

```text
xab
```

Kedua hasil tersebut berbeda sehingga diperlukan mekanisme transformasi operasi.

**Penyelesaian Menggunakan OT:**

1. Perubahan Bambang ditransformasikan agar posisi penghapusan menyesuaikan dokumen terbaru milik Agnes.
2. Penghapusan yang awalnya berada pada indeks 2 berubah menjadi indeks 3.
3. Perubahan Agnes juga disesuaikan dengan posisi dokumen milik Bambang.
4. Kedua pengguna memperoleh hasil dokumen yang sama.

Hasil akhir:

```text
xab
```

Dengan demikian, Operational Transformation membantu menjaga kesamaan dokumen meskipun beberapa pengguna melakukan perubahan secara bersamaan.

---

# 9. PROTOKOL REPLIKASI

Protokol replikasi merupakan mekanisme yang digunakan untuk mengatur proses penyalinan dan penyebaran data antar-node dalam sistem terdistribusi.

Dalam materi dosen, terdapat lima protokol replikasi utama.

### 9.1 Primary-Based (Master-Slave)

Primary-Based merupakan protokol replikasi yang menggunakan satu node utama sebagai tempat melakukan penulisan data.

Node lainnya berperan sebagai replika yang dapat digunakan untuk membaca data.

### 9.2 Quorum-Based

Quorum-Based merupakan mekanisme replikasi yang menentukan jumlah minimum node yang harus memberikan konfirmasi agar operasi baca atau tulis dianggap berhasil.

Dalam protokol ini terdapat tiga komponen utama:

- N = Jumlah seluruh node.
- W = Jumlah minimum node yang harus mengonfirmasi operasi write.
- R = Jumlah minimum node yang harus mengonfirmasi operasi read.

Persyaratan quorum adalah:

```text
W + R > N
```

Artinya, jumlah minimum konfirmasi write dan read harus lebih besar daripada jumlah keseluruhan node.

**Contoh Konfigurasi Quorum:**

Terdapat tiga node dalam sistem:

```text
N = 3
W = 2
R = 2
```

Maka:

```text
W + R > N

2 + 2 > 3

4 > 3
```

Persyaratan quorum terpenuhi.

### 9.3 Skenario Operasi Write

Misalnya klien ingin menyimpan data:

```text
x = 100
```

Prosesnya:

1. Klien mengirim permintaan penulisan data kepada cluster.
2. Permintaan diteruskan ke Node A, Node B, dan Node C.
3. Node A berhasil menyimpan data dan mengirimkan ACK.
4. Node B berhasil menyimpan data dan mengirimkan ACK.
5. Node C mengalami keterlambatan atau timeout.
6. Karena sudah memperoleh dua ACK dan memenuhi W = 2, operasi write dinyatakan berhasil.

### 9.4 Skenario Operasi Read

Ketika klien ingin membaca data x, sistem meminta data dari minimal dua node karena R = 2.

Misalnya:

- Node A memberikan data terbaru x = 100.
- Node C mungkin masih memiliki data versi lama atau belum menerima pembaruan.

Karena konfigurasi quorum memenuhi W + R > N, operasi read dan write memiliki irisan node sehingga sistem dapat memperoleh informasi terbaru melalui mekanisme quorum yang digunakan.

### 9.5 State Machine Replication

State Machine Replication merupakan metode replikasi yang memastikan beberapa server menjalankan perintah yang sama dalam urutan yang sama.

Dalam metode ini, server utama menerima permintaan dari klien, menambahkan perintah ke log, dan mengatur urutan eksekusi. Replika kemudian menerapkan perintah yang telah diurutkan tersebut.

**Contoh:**

Kondisi awal:

```text
Replika A: x = 10
Replika B: x = 10
Replika C: x = 10
```

Klien mengirimkan perintah:

```text
SET x = 20
```

Prosesnya:

1. Klien mengirim permintaan kepada leader atau Replika A.
2. Replika A menentukan nomor urutan dan menambahkan perintah ke log.
3. Replika A mengirimkan perintah kepada Replika B dan C.
4. Replika A menerima konfirmasi bahwa perintah telah tercatat pada log B dan C.
5. Perintah dianggap committed.
6. Seluruh replika menjalankan perintah SET x = 20 pada penyimpanan lokal.
7. Replika A mengirimkan hasil akhir kepada klien.

Hasil akhir:

```text
Replika A: x = 20
Replika B: x = 20
Replika C: x = 20
```

### 9.6 Gossip Protocol

Gossip Protocol merupakan protokol komunikasi yang digunakan untuk menyebarkan informasi antar-node melalui pertukaran pesan secara berkala.

Protokol ini digunakan pada berbagai distributed database, termasuk Apache Cassandra, untuk membantu memeriksa keberadaan node dan menyebarkan informasi perubahan data.

**Cara Kerja:**

1. Node A mendeteksi perubahan data atau mengetahui bahwa node lain mengalami kegagalan.
2. Node A memilih satu atau beberapa peer secara acak.
3. Node A mengirimkan informasi status terbaru kepada peer tersebut.
4. Node B menerima informasi dan memperbarui statusnya.
5. Node B kemudian menyebarkan informasi kepada node lainnya.
6. Proses pertukaran informasi berlangsung secara berulang sampai informasi tersebar ke seluruh cluster.

Dengan mekanisme tersebut, node dapat mengetahui kondisi dan perubahan yang terjadi pada node lainnya.

### 9.7 Chain Replication

Chain Replication merupakan protokol replikasi yang menyusun beberapa node dalam bentuk rantai atau chain.

Berdasarkan diagram pada materi dosen, struktur Chain Replication terdiri dari:

- Head: Node awal yang menerima permintaan write.
- Middle Nodes: Node perantara yang meneruskan perubahan data.
- Tail: Node terakhir dalam rantai yang melayani pembacaan data.

**Cara Kerja:**

1. Klien mengirim permintaan penulisan data kepada Head.
2. Head meneruskan perubahan kepada node berikutnya.
3. Perubahan diteruskan secara berurutan melalui seluruh node.
4. Setelah proses replikasi mencapai Tail, konfirmasi dapat diteruskan kembali kepada klien melalui Head.
5. Permintaan pembacaan data dilayani oleh Tail.

Metode ini membantu menjaga urutan penyebaran perubahan data pada seluruh replika.

---

# 10. STUDI KASUS

Pada bagian akhir materi, dosen memberikan dua studi kasus penerapan replikasi data pada teknologi yang digunakan dalam industri.

### 10.1 PostgreSQL 18 Streaming Replication

PostgreSQL merupakan sistem manajemen basis data yang mendukung mekanisme replikasi.

Streaming Replication merupakan mekanisme yang digunakan untuk mengirimkan perubahan data dari server utama atau primary ke server replika atau standby melalui aliran perubahan log transaksi.

Berdasarkan materi perkuliahan, PostgreSQL 18 Streaming Replication menjadi salah satu studi kasus yang perlu dipelajari untuk memahami penerapan replikasi Master-Slave atau Primary-Secondary.

**Hal yang dipelajari:**

1. Peran server primary sebagai sumber perubahan data.
2. Peran server standby sebagai penerima replikasi.
3. Proses pengiriman perubahan data melalui streaming.
4. Sinkronisasi data antara server utama dan server replika.

### 10.2 Apache Ignite 3 Master-Master

Apache Ignite 3 merupakan teknologi yang dibahas sebagai studi kasus penerapan replikasi Master-Master.

Pada pendekatan Master-Master, beberapa node dapat memiliki peran untuk melakukan pembacaan dan penulisan data.

Hal yang perlu diperhatikan dalam penerapan metode ini adalah:

1. Kemampuan beberapa node melakukan operasi data.
2. Proses sinkronisasi perubahan antar-node.
3. Penanganan konflik ketika terjadi pembaruan bersamaan.
4. Pemeliharaan konsistensi data pada beberapa node.

**Catatan:** Materi presentasi mengarahkan pembahasan lebih lanjut mengenai PostgreSQL 18 Streaming Replication dan Apache Ignite 3 Master-Master pada dokumen lecture notes serta source code yang menyertai perkuliahan.

---

# 11. DISKUSI

Berdasarkan materi yang telah dipelajari, terdapat dua pertanyaan diskusi untuk memperdalam pemahaman mengenai konsistensi dan replikasi.

### 11.1 Apa Kelebihan dan Kekurangan Strong Consistency dan Eventual Consistency?

**Strong Consistency**

Kelebihan:
- Data lebih konsisten pada seluruh node.
- Mengurangi kemungkinan pengguna membaca data yang belum diperbarui.
- Cocok untuk sistem yang membutuhkan ketepatan data, seperti sistem perbankan.

Kekurangan:
- Membutuhkan komunikasi dan sinkronisasi antar-server.
- Waktu respons cenderung lebih lambat.
- Ketersediaan layanan dapat terganggu ketika terjadi masalah jaringan.

**Eventual Consistency**

Kelebihan:
- Respons sistem lebih cepat.
- Mendukung availability yang tinggi.
- Tidak harus menunggu seluruh replika selesai diperbarui.

Kekurangan:
- Data dapat berbeda sementara antar-node.
- Pengguna mungkin mendapatkan versi data yang belum terbaru.
- Membutuhkan mekanisme untuk menyelesaikan konflik pembaruan.

### 11.2 Bagaimana Jika Replikasi Gagal di Satu Node?

Jika proses replikasi gagal pada salah satu node, sistem perlu mendeteksi kegagalan tersebut dan memastikan node lainnya tetap dapat beroperasi sesuai kebijakan sistem.

Beberapa langkah yang dapat dilakukan adalah:

1. Mendeteksi node yang mengalami kegagalan komunikasi atau replikasi.
2. Memastikan node lain tetap menyediakan layanan apabila memungkinkan.
3. Menyimpan atau mempertahankan informasi perubahan data yang belum berhasil direplikasi.
4. Melakukan sinkronisasi ulang ketika node yang mengalami kegagalan kembali aktif.
5. Memeriksa kesesuaian data antara node utama dan replika setelah proses pemulihan.

Dengan demikian, mekanisme pemulihan diperlukan agar kegagalan pada satu node tidak menyebabkan seluruh sistem kehilangan data atau berhenti beroperasi.

---

# REFERENSI

1. Materi Perkuliahan Sistem Terdistribusi dan Terdesentralisasi. Dr. Bambang Purnomosidi D. P. Fakultas Teknologi Informasi, UTDI. Materi 04: Konsistensi dan Replikasi pada Sistem Terdistribusi.

2. PostgreSQL Documentation.  
   https://www.postgresql.org/docs/

3. Apache Ignite Documentation.  
   https://ignite.apache.org/

4. Apache Cassandra Documentation.  
   https://cassandra.apache.org/doc/

5. Yjs Documentation.  
   https://yjs.dev/

6. MySQL Documentation.  
   https://dev.mysql.com/doc/

7. Sumber gambar dan penjelasan Chain Replication.  
   https://medium.com/@m.hassan.def/chain-replication-how-does-azure-storage-handle-replication-under-the-hood-79acbd3ac441

8. Sumber gambar dan penjelasan MySQL Replication.  
   https://medium.com/codex/an-overview-of-mysql-replication-9e5635cc3a8a

---

**AKHIR MATERI MINGGU 4**
