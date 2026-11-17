
# MODUL 05 : FAULT TOLERANCE

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
5. Mempertahankan contoh, teknik, design patterns, dan library yang terdapat dalam materi dosen.

---

# 1. PENGERTIAN FAULT TOLERANCE

Fault Tolerance merupakan kemampuan suatu sistem untuk tetap mempertahankan operasionalnya dengan baik meskipun terjadi kegagalan atau kesalahan pada satu atau lebih komponennya.

Konsep ini sangat penting dalam pengembangan sistem teknologi informasi yang membutuhkan ketersediaan dan keandalan tinggi.

### 1.1 Tujuan Fault Tolerance

Tujuan utama Fault Tolerance adalah memastikan sistem tetap dapat beroperasi ketika terjadi gangguan pada komponen tertentu.

Fault Tolerance diperlukan terutama pada:

1. **High Availability:** Sistem harus tetap tersedia dan dapat digunakan oleh pengguna.
2. **Mission Critical System:** Sistem yang memiliki peran penting dan tidak boleh mengalami gangguan operasional yang serius.
3. **Life-Critical System:** Sistem yang kegagalannya dapat berdampak terhadap keselamatan manusia.

Dengan menerapkan Fault Tolerance, kegagalan pada satu komponen tidak harus menyebabkan seluruh sistem berhenti beroperasi.

---

# 2. ARTI PENTING FAULT TOLERANCE PADA SISTEM TERDISTRIBUSI DAN TERDESENTRALISASI

Fault Tolerance memiliki peran penting dalam sistem terdistribusi dan terdesentralisasi karena sistem tersebut terdiri dari banyak komponen yang saling terhubung dan bekerja sama.

Koneksi antar-komponen dapat mengalami gangguan, baik karena masalah perangkat keras, perangkat lunak, maupun jaringan komunikasi.

Semakin kritis suatu aplikasi, semakin tinggi pula tuntutan agar sistem tetap berfungsi dengan baik meskipun terjadi kegagalan.

### 2.1 Alasan Fault Tolerance Diperlukan

1. Sistem terdistribusi memiliki banyak komponen yang berpotensi mengalami kegagalan.
2. Koneksi antar-komponen tidak selalu berjalan dengan stabil.
3. Kegagalan satu komponen dapat memengaruhi proses kerja komponen lainnya.
4. Sistem yang bersifat kritis membutuhkan ketersediaan layanan yang tinggi.
5. Diperlukan mekanisme untuk mendeteksi, menangani, dan memulihkan sistem ketika terjadi kegagalan.

Dengan demikian, Fault Tolerance membantu menjaga keandalan sistem agar tetap dapat memberikan layanan meskipun terdapat komponen yang mengalami masalah.

---

# 3. JENIS FAULT

Fault merupakan kondisi ketika suatu komponen mengalami kesalahan atau kegagalan yang dapat mengganggu proses kerja sistem.

Dalam materi perkuliahan, terdapat empat jenis Fault yang perlu dipahami.

### 3.1 Transient Fault

Transient Fault merupakan jenis kegagalan yang terjadi sementara dan biasanya dapat hilang dengan sendirinya setelah kondisi penyebabnya berakhir.

**Contoh:**

Gangguan akibat petir yang menyebabkan gangguan sementara pada perangkat atau sistem elektronik.

### 3.2 Intermittent Fault

Intermittent Fault merupakan jenis kegagalan yang muncul dan menghilang secara berulang.

Kegagalan ini tidak terjadi secara terus-menerus, tetapi dapat muncul kembali ketika kondisi tertentu terpenuhi.

**Contoh:**

Overheat pada perangkat keras yang menyebabkan sistem mengalami gangguan secara berulang.

### 3.3 Permanent Fault

Permanent Fault merupakan jenis kegagalan yang bersifat tetap atau berlangsung terus-menerus.

Kegagalan ini biasanya membutuhkan tindakan perbaikan atau penggantian komponen agar sistem dapat beroperasi kembali.

### 3.4 Byzantine Fault

Byzantine Fault merupakan jenis kegagalan ketika suatu komponen memberikan hasil yang tidak konsisten, salah, atau bahkan berbeda-beda kepada komponen lainnya.

Kondisi ini dapat menyebabkan node dalam sistem memiliki informasi yang berbeda sehingga sulit mencapai kesepakatan.

**Contoh:**

Dalam suatu sistem terdistribusi, terdapat node yang memberikan informasi berbeda mengenai status atau nilai data kepada node lainnya.

---

# 4. KLASIFIKASI FAULT BERDASARKAN SUMBER

Berdasarkan sumber penyebabnya, Fault dapat dikelompokkan menjadi tiga kategori utama, yaitu Hardware Faults, Software Faults, dan Communication Faults.

### 4.1 Hardware Faults

Hardware Faults merupakan kegagalan yang berasal dari komponen perangkat keras komputer atau server.

Kegagalan ini dapat mengakibatkan sistem tidak dapat menjalankan proses sebagaimana mestinya.

**Contoh:**

1. Disk crash atau kerusakan media penyimpanan.
2. Power failure atau kegagalan pasokan daya listrik.

### 4.2 Software Faults

Software Faults merupakan kegagalan yang disebabkan oleh kesalahan pada perangkat lunak atau program yang dijalankan.

Kesalahan ini dapat menyebabkan aplikasi tidak berjalan dengan benar atau mengalami gangguan operasional.

**Contoh:**

1. Bugs, yaitu kesalahan dalam kode program.
2. Memory leak, yaitu kondisi ketika penggunaan memori terus meningkat karena memori yang tidak lagi diperlukan tidak dilepaskan dengan benar.
3. Race condition, yaitu kondisi ketika hasil proses dipengaruhi oleh urutan atau waktu eksekusi beberapa operasi yang berjalan bersamaan.

### 4.3 Communication Faults

Communication Faults merupakan kegagalan yang terjadi pada proses komunikasi atau pertukaran data antar-komponen dalam suatu sistem.

Gangguan ini dapat menyebabkan data tidak sampai ke tujuan atau node tidak dapat berkomunikasi dengan node lainnya.

**Contoh:**

1. Packet loss, yaitu hilangnya paket data selama proses pengiriman.
2. Network partition, yaitu kondisi ketika jaringan terputus sehingga beberapa node tidak dapat saling berkomunikasi.

---

# 5. DESIGN PATTERNS UNTUK MENCAPAI FAULT TOLERANCE

Design Patterns merupakan pola atau pendekatan yang digunakan untuk membangun sistem agar mampu menghadapi berbagai kemungkinan kegagalan.

Berdasarkan materi dosen, terdapat beberapa teknik utama untuk mencapai Fault Tolerance, yaitu Redundancy and Replication, Load Balancing, Checkpointing and Rollback Recovery, Heartbeat and Failure Detection, serta Consensus and Coordination.

### 5.1 Redundancy and Replication

Redundancy and Replication merupakan teknik menyediakan sumber daya atau salinan komponen pada beberapa node agar sistem tidak hanya bergantung pada satu komponen.

Tujuan utamanya adalah mencegah terjadinya Single Point of Failure, yaitu kondisi ketika kegagalan satu komponen menyebabkan seluruh sistem berhenti beroperasi.

**Cara Kerja:**

1. Sistem memiliki sumber daya atau komponen utama.
2. Komponen tersebut dibuatkan salinan pada beberapa node.
3. Salinan digunakan sebagai cadangan apabila komponen utama mengalami kegagalan.
4. Sistem dapat tetap beroperasi menggunakan komponen lain yang tersedia.

Teknik ini berkaitan dengan materi sebelumnya mengenai replikasi data pada sistem terdistribusi.

### 5.2 Load Balancing

Load Balancing merupakan teknik untuk membagi beban permintaan pengguna ke beberapa instance aplikasi.

Satu instance merupakan satu proses aplikasi penuh yang aktif.

Teknik ini dilakukan dengan menggunakan Load Balancer yang mengarahkan permintaan ke beberapa instance aplikasi.

**Contoh perangkat Load Balancer:**

1. HAProxy.
2. Nginx.

**Cara Kerja:**

1. Aplikasi dijalankan dalam beberapa instance.
2. Pengguna mengirimkan permintaan kepada aplikasi.
3. Load Balancer menerima permintaan tersebut.
4. Load Balancer mendistribusikan permintaan ke beberapa instance.
5. Beban kerja tidak hanya ditangani oleh satu instance.

Load Balancing membantu proses scaling aplikasi dan mendukung ketersediaan layanan.

### 5.3 Checkpointing and Rollback Recovery

Checkpointing and Rollback Recovery merupakan teknik yang digunakan untuk memulihkan sistem setelah mengalami kegagalan.

Terdapat dua konsep utama dalam teknik ini.

**A. Checkpointing**

Checkpointing merupakan proses menyimpan status atau kondisi sistem secara berkala ke media penyimpanan.

Penyimpanan status ini bertujuan agar sistem memiliki titik pemulihan ketika terjadi kegagalan.

**B. Rollback Recovery**

Rollback Recovery merupakan proses mengembalikan sistem ke checkpoint yang telah tercatat sebelumnya setelah terjadi kegagalan.

**Cara Kerja:**

1. Sistem menyimpan status secara berkala.
2. Status tersebut digunakan sebagai checkpoint.
3. Ketika terjadi kegagalan, sistem melakukan proses pemulihan.
4. Sistem kembali ke checkpoint yang tersimpan sebelumnya.
5. Proses dapat dilanjutkan tanpa harus memulai seluruh pekerjaan dari awal.

Kedua teknik ini bertujuan meminimalkan kehilangan data dan waktu pemrosesan.

### 5.4 Heartbeat and Failure Detection

Heartbeat and Failure Detection merupakan teknik yang digunakan untuk memantau kondisi suatu komponen dalam sistem terdistribusi.

Terdapat dua konsep utama.

**A. Heartbeat**

Heartbeat merupakan sinyal periodik yang dikirimkan antar-komponen dalam suatu sistem untuk menunjukkan bahwa komponen tersebut masih aktif.

**B. Failure Detection**

Failure Detection merupakan proses menggunakan informasi Heartbeat untuk menentukan apakah suatu komponen mengalami kegagalan.

Jika suatu komponen pemantau tidak menerima Heartbeat dari komponen lain dalam jangka waktu tertentu, komponen tersebut dapat diasumsikan mengalami kegagalan atau tidak responsif.

**Cara Kerja:**

1. Komponen mengirimkan sinyal Heartbeat secara berkala.
2. Komponen lain menerima dan memantau sinyal tersebut.
3. Jika Heartbeat tidak diterima dalam batas waktu tertentu, sistem mengidentifikasi kemungkinan kegagalan.
4. Sistem dapat melakukan tindakan penanganan sesuai mekanisme yang diterapkan.

**Contoh Praktik:**

Pada materi dosen terdapat file `check-server.py` yang digunakan untuk melakukan pengecekan sederhana terhadap kondisi server.

Program tersebut dapat memberikan hasil:

- Server up, apabila server dapat diakses.
- Server down, apabila server tidak dapat diakses.

### 5.5 Retry Mechanism Menggunakan Tenacity

Dalam sistem terdistribusi, aplikasi sering kali harus berkomunikasi dengan komponen di luar aplikasi.

Koneksi tersebut dapat mengalami kegagalan sehingga diperlukan mekanisme percobaan ulang atau Retry.

Materi dosen memperkenalkan library Tenacity yang dapat digunakan untuk mengelola proses yang membutuhkan koneksi dengan komponen eksternal.

**Library:**

Tenacity  
https://github.com/jd/tenacity

**Fungsi:**

1. Melakukan percobaan ulang ketika koneksi mengalami kegagalan.
2. Mengelola proses yang membutuhkan komunikasi dengan layanan eksternal.
3. Memberikan kesempatan kepada sistem untuk mencoba kembali ketika terjadi gangguan sementara.

**Contoh pada materi:**

File `check-retry.py` digunakan untuk mencoba mengakses suatu URL.

Apabila akses berhasil, program menampilkan pesan:

```text
Attempting to access http://localhost:44777...
Successfully accessed http://localhost:44777
```

Apabila koneksi terus mengalami kegagalan hingga batas percobaan tercapai, program menampilkan pesan kegagalan akses.

### 5.6 Circuit Breaker

Circuit Breaker merupakan design pattern yang digunakan dalam arsitektur Microservices untuk mencegah terjadinya kegagalan berantai atau Cascading Failure.

Pola ini bekerja seperti sebuah State Machine yang memiliki tiga status utama.

**A. Closed**

Pada status Closed, permintaan masih diizinkan untuk diteruskan ke layanan.

Sistem tetap memantau apakah permintaan tersebut mengalami kegagalan.

**B. Open**

Ketika jumlah kegagalan mencapai ambang batas yang ditentukan, Circuit Breaker berpindah ke status Open.

Pada kondisi ini, permintaan berikutnya akan langsung ditolak sementara agar layanan yang mengalami gangguan memiliki waktu untuk pulih.

**C. Half-Open**

Setelah melewati batas waktu tertentu, Circuit Breaker berpindah ke status Half-Open.

Pada kondisi ini, sejumlah permintaan terbatas diizinkan untuk menguji apakah layanan sudah kembali normal.

Jika pengujian berhasil, status kembali menjadi Closed. Namun, jika pengujian gagal, status kembali menjadi Open.

**Alur Circuit Breaker:**

```text
CLOSED
  |
  | Kegagalan mencapai batas
  v
OPEN
  |
  | Waktu pemulihan tercapai
  v
HALF-OPEN
  |
  | Pengujian berhasil
  v
CLOSED
```

Jika pengujian pada status Half-Open gagal, sistem kembali ke status Open.

**Contoh Implementasi:**

Materi dosen menggunakan library PyBreaker untuk menerapkan Circuit Breaker pada permintaan HTTP.

Contoh kode yang ditampilkan dalam materi:

```python
import pybreaker
import requests

breaker = pybreaker.CircuitBreaker(
    fail_max=4,
    reset_timeout=20
)

@breaker
def make_http_request(url):
    print(f"Attempting to access {url}...")
    response = requests.get(url)
    response.raise_for_status()
    print(f"Successfully accessed {url}")
    return response.text

try:
    content = make_http_request(
        "http://localhost:44777"
    )
except Exception as e:
    print(e)
```

Keterangan:

- `fail_max=4` menentukan batas kegagalan sebelum Circuit Breaker terbuka.
- `reset_timeout=20` menentukan waktu tunggu sebelum sistem mencoba kembali.
- `@breaker` digunakan untuk menerapkan mekanisme Circuit Breaker pada fungsi.
- `requests.get(url)` digunakan untuk melakukan permintaan HTTP.
- `response.raise_for_status()` digunakan untuk menghasilkan exception apabila respons HTTP menunjukkan kesalahan.

Dengan demikian, Circuit Breaker membantu mencegah aplikasi terus-menerus melakukan permintaan kepada layanan yang sedang mengalami gangguan.

### 5.7 Consensus and Coordination

Consensus and Coordination merupakan konsep yang digunakan untuk memastikan beberapa node dapat bekerja sama dan mencapai kesepakatan dalam sistem terdistribusi.

**A. Consensus**

Consensus merupakan proses ketika beberapa node menyepakati satu nilai, status, atau urutan operasi meskipun terjadi kegagalan atau keterlambatan jaringan.

**B. Coordination**

Coordination merupakan proses pengelolaan interaksi antar-node agar seluruh komponen dapat bekerja sama secara efektif dan konsisten.

Coordination sering kali menggunakan Consensus sebagai salah satu komponen penting.

**Contoh Penerapan:**

1. **Database Leader Election:** Dalam cluster database yang menggunakan replikasi, diperlukan pemilihan leader untuk menangani operasi write. Algoritma Raft dapat digunakan untuk proses consensus.
2. **Cloud Storage File Updates:** Ketika file diperbarui pada layanan seperti Google Drive, sistem menggunakan consensus untuk memastikan perubahan disetujui oleh mayoritas server sebelum dianggap final.
3. **Cryptocurrency and Blockchain:** Teknologi blockchain menggunakan mekanisme consensus untuk memvalidasi dan menyepakati transaksi.

---

# 6. ACTOR MODEL UNTUK SUPERVISI PROSES

Actor Model merupakan model komputasi yang menggunakan actor sebagai unit utama dalam menjalankan proses dan berkomunikasi dengan actor lainnya melalui pengiriman pesan.

Dalam materi perkuliahan, Actor Model dibahas sebagai salah satu pendekatan untuk melakukan supervisi proses dalam sistem terdistribusi.

### 6.1 Konsep Actor Model

Setiap actor memiliki mailbox yang digunakan untuk menerima pesan dari actor lain.

Berdasarkan diagram pada materi dosen, komunikasi antar-actor dilakukan melalui pengiriman pesan yang diterima oleh mailbox masing-masing actor.

**Komponen Actor Model:**

1. **Actor:** Unit yang menjalankan proses atau tugas tertentu.
2. **Mailbox:** Tempat menerima pesan yang dikirimkan oleh actor lain.
3. **Message:** Informasi atau perintah yang dikirimkan antar-actor.

### 6.2 Supervisor dan Worker

Pada Actor Model, supervisi proses dapat dilakukan menggunakan hubungan antara Supervisor dan Worker.

**A. Supervisor**

Supervisor merupakan actor yang bertugas mengawasi actor atau proses lain yang berada di bawah tanggung jawabnya.

**B. Worker**

Worker merupakan actor yang menjalankan tugas atau proses tertentu.

Jika terdapat worker yang mengalami kegagalan, supervisor dapat melakukan tindakan penanganan, seperti memulai ulang proses yang mengalami masalah.

### 6.3 Hierarki Supervisi

Berdasarkan diagram pada halaman 21 materi dosen, supervisi dapat disusun secara bertingkat.

1. Top Level Supervisor bertugas mengawasi beberapa supervisor.
2. Supervisor bertugas mengawasi actor atau worker di bawahnya.
3. Worker menjalankan tugas sesuai fungsinya.
4. Jika worker mengalami kegagalan, supervisor dapat melakukan tindakan pemulihan, seperti restart.

Struktur ini memungkinkan proses pengawasan dilakukan secara terorganisasi sehingga kegagalan pada satu actor dapat ditangani tanpa harus menghentikan seluruh sistem.

---

# 7. IMPLEMENTASI FAULT TOLERANCE PADA BERBAGAI BAHASA PEMROGRAMAN DAN PERANTI PENGEMBANGAN

Implementasi Fault Tolerance dapat dilakukan menggunakan berbagai bahasa pemrograman dan library yang menyediakan mekanisme untuk menangani kegagalan sistem.

Dalam materi dosen, terdapat beberapa bahasa pemrograman dan teknologi yang mendukung penerapan Fault Tolerance.

### 7.1 Erlang dan Elixir

Erlang dan Elixir memiliki mekanisme bawaan untuk mendukung Actor Model serta pola Supervisor-Worker.

Keduanya menyediakan pendekatan untuk mengelola proses dan menangani kegagalan melalui mekanisme supervisi.

### 7.2 Pony

Pony merupakan bahasa pemrograman yang secara khusus mengembangkan konsep Actor Model.

Informasi lebih lanjut:

https://www.ponylang.io

### 7.3 Python

Python dapat menerapkan Fault Tolerance dengan menggunakan library pihak ketiga.

Beberapa library yang disebutkan dalam materi dosen adalah:

1. **Xoscar:** Library yang berkaitan dengan penerapan Actor Model.
   https://xoscar.dev
2. **Tenacity:** Library untuk mengelola mekanisme Retry ketika suatu proses mengalami kegagalan.
   https://github.com/jd/tenacity
3. **Circuit Breaker:** Pola yang digunakan untuk mencegah kegagalan berantai dalam komunikasi antar-layanan.

### 7.4 Java

Java juga memiliki beberapa library untuk mendukung implementasi Fault Tolerance.

**A. Apache Pekko**

Apache Pekko dapat digunakan untuk menerapkan Actor Model serta pola Supervisor-Worker.

**B. Resilience4j**

Resilience4j merupakan library yang menyediakan berbagai mekanisme untuk meningkatkan ketahanan aplikasi terhadap kegagalan.

Informasi lebih lanjut:

https://github.com/resilience4j/resilience4j

### 7.5 Bahasa Pemrograman Lainnya

Selain Python dan Java, penerapan Fault Tolerance juga dapat dipelajari melalui berbagai ekosistem bahasa pemrograman lainnya.

Contohnya:

1. JavaScript melalui ekosistem npm.
2. Rust melalui crates.io.

Materi dosen juga mengarahkan mahasiswa untuk mencari berbagai library yang dapat digunakan dalam penerapan Fault Tolerance pada bahasa pemrograman tersebut.

---

# KESIMPULAN

Fault Tolerance merupakan kemampuan sistem untuk tetap beroperasi meskipun mengalami kegagalan pada satu atau beberapa komponennya.

Dalam sistem terdistribusi dan terdesentralisasi, Fault Tolerance sangat penting karena sistem terdiri dari banyak komponen yang saling terhubung dan memiliki kemungkinan mengalami gangguan.

Terdapat beberapa jenis kegagalan, yaitu Transient Fault, Intermittent Fault, Permanent Fault, dan Byzantine Fault. Berdasarkan sumbernya, kegagalan dapat berasal dari perangkat keras, perangkat lunak, maupun komunikasi jaringan.

Untuk mengatasi berbagai kegagalan tersebut, sistem dapat menerapkan beberapa teknik, seperti Redundancy and Replication, Load Balancing, Checkpointing and Rollback Recovery, Heartbeat and Failure Detection, Retry Mechanism, Circuit Breaker, serta Consensus and Coordination.

Selain itu, Actor Model dengan mekanisme Supervisor-Worker dapat digunakan untuk mengawasi dan menangani kegagalan proses. Berbagai bahasa pemrograman seperti Erlang, Elixir, Python, Java, dan Pony juga menyediakan dukungan untuk menerapkan Fault Tolerance.

Dengan menerapkan teknik dan mekanisme tersebut, sistem dapat menjadi lebih andal, tersedia, dan mampu menghadapi berbagai kemungkinan kegagalan.

---

# REFERENSI

1. Materi Perkuliahan Sistem Terdistribusi dan Terdesentralisasi. Dr. Bambang Purnomosidi D. P. Fakultas Teknologi Informasi, UTDI. Materi 05: Fault Tolerance.

2. Tenacity Documentation.  
   https://github.com/jd/tenacity

3. Xoscar Documentation.  
   https://xoscar.dev

4. Pony Programming Language.  
   https://www.ponylang.io

5. Resilience4j Documentation.  
   https://github.com/resilience4j/resilience4j

6. Design Patterns for Fault Tolerance.  
   https://www.designgurus.io/kb/design-patterns-5-expert-techniques-for-boosting-fault-tolerance-in-distributed-systems

7. Byzantine Fault Tolerance.  
   https://medium.com/coinmonks/byzantine-fault-tolerance-222a8134be7

8. Introduction to Actor Model.  
   https://medium.com/@nguyenthanhquang.cse/introduction-to-actor-model-2c82d25d1b83

---

**AKHIR MATERI MINGGU 5**
