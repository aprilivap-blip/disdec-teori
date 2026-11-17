
# MODUL 02 –  PROSES DAN KOMUNIKASI ANTAR PROSES PADA SISTEM TERDISTRIBUSI

## Identitas Mahasiswa

**Nama:** Apriliva Putri P
**NIM:** 255410035
**Kelas:** Informatika-1

## Identitas Penggunaan AI

**AI yang digunakan:** ChatGPT (OpenAI)

**Prompt:**

Bertindaklah sebagai mahasiswa Informatika yang memahami mata kuliah Sistem Terdistribusi dan Terdesentralisasi. Buat rangkuman berdasarkan materi PDF perkuliahan yang diberikan dosen. Ikuti seluruh agenda pembahasan secara berurutan. Bahas setiap poin secara terpisah, gunakan bahasa Indonesia baku dan akademis, serta jelaskan konsep-konsep penting secara ringkas, jelas, dan mudah dipahami. Jangan menggabungkan beberapa poin menjadi satu pembahasan dan jangan menambahkan materi yang tidak relevan dengan slide dosen. Hasil akhir harus menggunakan format Markdown dan siap dimasukkan ke dalam README.md GitHub.

**Bagian yang disesuaikan dari keluaran prompt ada pada:**

1. Meringkas penjelasan agar lebih padat dan sesuai dengan materi presentasi dosen.
2. Memperbaiki susunan kalimat agar lebih mudah dipahami.
3. Mempertahankan istilah teknis sesuai materi perkuliahan.
4. Memisahkan setiap agenda pembahasan agar lebih terstruktur.
5. Menyesuaikan contoh penerapan dengan contoh yang diberikan dosen.

---

# 1. APA ITU PROSES?

Proses merupakan program yang sedang dijalankan oleh sistem operasi. Berbeda dengan program yang masih berupa kumpulan instruksi, proses memiliki status eksekusi, sumber daya, dan ruang memori yang digunakan selama program berjalan.

Dalam sistem operasi, proses dijalankan menggunakan CPU dan dikelola oleh scheduler. Sistem operasi juga mengatur pergantian proses melalui mekanisme context switching agar beberapa proses dapat memperoleh kesempatan untuk menggunakan CPU.

**Komponen proses meliputi:**
- Program yang sedang dijalankan.
- Memori yang digunakan.
- Status atau keadaan proses.
- Informasi sumber daya yang digunakan.
- Thread yang menjalankan instruksi.

# 2. MANAJEMEN PROSES

Manajemen proses merupakan kegiatan sistem operasi dalam mengatur dan mengendalikan proses agar dapat berjalan dengan baik.

Berdasarkan materi perkuliahan, terdapat tiga aktivitas utama manajemen proses:

### 2.1 Process Creation

Process Creation merupakan proses pembuatan proses baru oleh sistem operasi. Sistem akan menyediakan sumber daya yang diperlukan dan mempersiapkan proses agar dapat dijalankan.

### 2.2 Process Migration

Process Migration merupakan pemindahan proses dari satu komputer atau node ke komputer atau node lainnya. Tujuannya dapat berupa pembagian beban kerja, peningkatan performa, atau penanganan kegagalan.

### 2.3 Process Monitoring

Process Monitoring merupakan kegiatan memantau kondisi dan aktivitas proses, seperti status proses, penggunaan CPU, memori, serta performa sistem.

# 3. SISTEM TERDISTRIBUSI DAN KOMUNIKASI

Sistem terdistribusi merupakan sekumpulan komputer atau node independen yang bekerja bersama melalui jaringan dan berkoordinasi sebagai satu kesatuan logis.

Setiap node menjalankan proses masing-masing. Agar seluruh node dapat bekerja sama, diperlukan komunikasi antarproses.

Komunikasi tersebut digunakan untuk:
- Bertukar data dan informasi.
- Melakukan koordinasi antarnode.
- Menjaga konsistensi data.
- Mendukung keandalan sistem.
- Menjalankan layanan secara bersama.

**Contoh penerapan:**

1. **Multiplayer Games:** Memungkinkan beberapa pemain berkomunikasi dan berinteraksi dalam satu permainan.
2. **Gojek/Grab:** Menghubungkan antarmuka pengguna dengan layanan driver, pelacakan lokasi, dan perhitungan biaya.
3. **WhatsApp:** Mendukung komunikasi pesan dan video call melalui infrastruktur terdistribusi.

# 4. MODEL KOMUNIKASI PESAN

Model komunikasi pesan merupakan metode yang digunakan oleh proses untuk bertukar informasi dalam sistem terdistribusi.

Berdasarkan materi dosen, terdapat dua model utama:

### 4.1 Komunikasi Langsung

Komunikasi langsung merupakan pertukaran data antarproses menggunakan socket. Socket memungkinkan aplikasi melakukan komunikasi melalui jaringan dengan menggunakan alamat IP dan nomor port.

**Contoh:** Aplikasi client mengirimkan pesan kepada server melalui koneksi TCP.

### 4.2 Komunikasi Tidak Langsung

Komunikasi tidak langsung merupakan komunikasi melalui perantara, seperti mailbox atau message queue. Pengirim tidak harus berkomunikasi secara langsung dengan penerima.

Contoh yang disebutkan dalam materi adalah mekanisme mailbox, message queue, dan perintah `write` pada Linux.

### 4.3 Publish/Subscribe (Pub/Sub)

Pub/Sub merupakan model komunikasi ketika publisher mengirim pesan ke suatu topic, kemudian subscriber yang berlangganan topic tersebut menerima pesan.

Model ini memungkinkan satu pesan diterima oleh beberapa subscriber tanpa publisher harus mengetahui seluruh penerimanya.

# 5. PROSES PADA SISTEM TERDISTRIBUSI

Pada sistem terdistribusi, proses dapat berjalan pada node atau komputer yang berbeda.

Karena proses berada pada node yang berbeda, setiap proses tidak dapat langsung menggunakan shared memory milik node lainnya.

Oleh karena itu, diperlukan mekanisme komunikasi khusus untuk memungkinkan proses saling bertukar data dan informasi.

# 6. IPC (INTER-PROCESS COMMUNICATION)

IPC (Inter-Process Communication) merupakan mekanisme yang digunakan untuk memungkinkan beberapa proses saling berkomunikasi dan bertukar informasi.

Berdasarkan materi perkuliahan, terdapat empat jenis IPC:

### 6.1 Shared Memory

Shared Memory merupakan mekanisme komunikasi ketika beberapa proses mengakses area memori yang sama untuk bertukar data.

Namun, shared memory tidak cocok digunakan secara langsung pada sistem terdistribusi karena proses dapat berada pada node yang berbeda dan tidak memiliki akses terhadap memori bersama secara fisik.

### 6.2 Message Passing

Message Passing merupakan mekanisme komunikasi dengan cara mengirim dan menerima pesan antarproses melalui media komunikasi tertentu.

### 6.3 Remote Procedure Call (RPC)

RPC merupakan mekanisme yang memungkinkan suatu proses memanggil prosedur atau fungsi pada komputer lain melalui jaringan seolah-olah prosedur tersebut dijalankan secara lokal.

### 6.4 Middleware

Middleware merupakan perangkat lunak perantara yang memfasilitasi komunikasi dan pertukaran data antar aplikasi atau proses dalam sistem terdistribusi.

# 7. MESSAGE PASSING

Message Passing merupakan metode komunikasi antarproses dengan cara mengirimkan pesan melalui jaringan atau mekanisme komunikasi tertentu.

Setiap proses dapat mengirim pesan kepada proses lain tanpa harus menggunakan shared memory.

Salah satu standar yang digunakan adalah MPI (Message Passing Interface), yaitu standar untuk komunikasi antarproses dalam lingkungan komputasi paralel dan terdistribusi.

**Contoh implementasi:**
- MPI (Message Passing Interface).
- OpenMPI.
- mpi4py untuk penggunaan MPI melalui Python.

Dalam komunikasi Message Passing, proses pengirim mengirim pesan, sedangkan proses penerima menerima pesan tersebut melalui mekanisme komunikasi yang disediakan.

# 8. RPC (REMOTE PROCEDURE CALL)

RPC (Remote Procedure Call) merupakan mekanisme yang memungkinkan suatu program memanggil prosedur atau fungsi yang berada pada komputer lain melalui jaringan.

RPC menyederhanakan komunikasi karena pemanggilan fungsi dapat dilakukan tanpa harus mengatur seluruh proses komunikasi jaringan secara manual.

**Cara kerja RPC:**

1. Client melakukan pemanggilan prosedur.
2. Client Stub menerima dan mengemas permintaan.
3. Permintaan dikirimkan melalui jaringan menuju server.
4. Server Stub menerima dan meneruskan permintaan kepada prosedur yang dituju.
5. Server menjalankan prosedur.
6. Hasil pemrosesan dikirimkan kembali kepada client.

**Contoh:** gRPC, yaitu framework komunikasi berbasis RPC yang digunakan untuk komunikasi antarservice melalui jaringan.

# 9. MOM (MESSAGE-ORIENTED MIDDLEWARE)

MOM (Message-Oriented Middleware) merupakan infrastruktur yang memfasilitasi komunikasi dan pertukaran data antar aplikasi melalui pesan.

Dalam MOM, data dikirim dan diterima sebagai unit informasi mandiri yang disebut message.

Komunikasi berbasis MOM umumnya menggunakan mekanisme asinkron sehingga pengirim dan penerima tidak harus aktif berkomunikasi pada waktu yang sama.

### Standar dan Protokol MOM

Berdasarkan materi dosen, standar dan protokol MOM meliputi:

1. **XATMI:** Spesifikasi komunikasi untuk Distributed Transaction Processing.
2. **AMQP (Advanced Message Queuing Protocol):** Protokol messaging yang umumnya digunakan pada aplikasi enterprise.
3. **HLA (High Level Architecture):** Standar IEEE 1516 untuk mendukung interoperabilitas dalam simulasi.
4. **MQTT (MQ Telemetry Transport):** Protokol messaging yang umumnya digunakan pada perangkat dengan sumber daya terbatas.
5. **DDS (Data Distribution Service):** Standar komunikasi data dari OMG (Object Management Group).
6. **XMPP (eXtensible Messaging and Presence Protocol):** Protokol komunikasi berbasis pesan yang mendukung pertukaran informasi dan status kehadiran.

# 10. STUDI KASUS: MICROSERVICES

Microservices merupakan pendekatan arsitektur perangkat lunak yang membagi aplikasi menjadi beberapa layanan kecil yang dapat dikembangkan dan dijalankan secara independen.

Setiap microservice memiliki fungsi tertentu dan dapat berkomunikasi dengan service lainnya melalui jaringan.

Setiap layanan juga dapat memiliki database masing-masing sesuai kebutuhan.

**Contoh penerapan:**

Pada aplikasi e-commerce, sistem dapat dibagi menjadi beberapa layanan, seperti:

- User Service untuk mengelola data pengguna.
- Product Service untuk mengelola produk.
- Payment Service untuk mengelola pembayaran.
- Order Service untuk mengelola pesanan.
- Shipping Service untuk mengelola pengiriman.

Dengan pendekatan tersebut, setiap layanan dapat dikembangkan dan dikelola secara terpisah tanpa harus mengubah seluruh aplikasi.

# 11. KOMUNIKASI SINKRON DAN ASINKRON

Komunikasi sinkron dan asinkron merupakan dua metode komunikasi antarproses dalam sistem terdistribusi.

### 11.1 Komunikasi Sinkron

Komunikasi sinkron merupakan komunikasi ketika proses pengirim harus menunggu respons dari penerima sebelum melanjutkan pekerjaan tertentu.

**Karakteristik:**
- Pengirim menunggu respons.
- Proses komunikasi berlangsung dengan pola permintaan dan jawaban.
- Cocok untuk operasi yang membutuhkan hasil langsung.

**Contoh:** Client mengirim permintaan login kepada server dan menunggu hasil autentikasi.

### 11.2 Komunikasi Asinkron

Komunikasi asinkron merupakan komunikasi ketika pengirim tidak harus menunggu penerima menyelesaikan pemrosesan pesan sebelum melanjutkan pekerjaan lainnya.

**Karakteristik:**
- Pengirim dapat melanjutkan pekerjaan.
- Pesan dapat diproses kemudian oleh penerima.
- Mendukung komunikasi melalui message queue atau middleware.

**Contoh:** Aplikasi mengirim notifikasi melalui message queue tanpa harus menunggu seluruh proses pengiriman selesai.

# 12. BERBAGAI MASALAH PADA KOMUNIKASI ANTAR PROSES

Komunikasi antarproses dalam sistem terdistribusi memiliki beberapa permasalahan yang dapat memengaruhi keandalan dan performa sistem.

### 12.1 Reliability

Reliability merupakan kemampuan sistem untuk memastikan pesan yang dikirim dapat diterima secara lengkap dan sesuai kebutuhan komunikasi.

Masalah yang dapat terjadi adalah kehilangan paket atau sistem mengalami crash.

**Solusi:**
- Acknowledgement untuk memastikan pesan diterima.
- Retransmission atau pengiriman ulang pesan.
- Menggunakan protokol transport yang andal seperti TCP.

### 12.2 Ordering

Ordering merupakan pengaturan urutan pesan agar diproses sesuai urutan yang diharapkan.

**Solusi yang disebutkan dalam materi:**
- Pipes dengan mekanisme FIFO.
- Message Queues.
- Shared Memory.
- Sockets dan Message Passing.
- RPC.

### 12.3 Security

Security merupakan aspek keamanan komunikasi antarproses agar data dan informasi tidak dapat diakses atau dimanipulasi oleh pihak yang tidak berwenang.

**Solusi:**
- Enkripsi.
- Autentikasi.

### 12.4 Performance

Performance berkaitan dengan kemampuan sistem dalam melakukan komunikasi dan pemrosesan data secara efisien.

Dua faktor yang perlu diperhatikan adalah latency dan bandwidth.

- **Latency:** Waktu yang diperlukan untuk mengirimkan dan menerima data.
- **Bandwidth:** Kapasitas jaringan dalam mengirimkan data dalam periode tertentu.

# 13. PROTOKOL KOMUNIKASI

Protokol komunikasi merupakan aturan yang mengatur proses pertukaran data antarperangkat atau proses dalam jaringan.

Berdasarkan materi dosen, protokol komunikasi dibagi menjadi dua kelompok.

### 13.1 Protokol yang Mendasari

1. **TCP (Transmission Control Protocol):** Protokol transport yang menyediakan komunikasi andal dan berurutan.
2. **UDP (User Datagram Protocol):** Protokol transport yang mengirimkan datagram tanpa menjamin pengiriman dan urutan data.
3. **HTTP (Hypertext Transfer Protocol):** Protokol komunikasi yang digunakan untuk pertukaran informasi antara client dan server.

### 13.2 Protokol Utama

Beberapa protokol atau pendekatan komunikasi yang dicantumkan dalam materi adalah:

1. **gRPC:** Framework komunikasi berbasis Remote Procedure Call.
2. **GraphQL:** Bahasa query untuk API yang memungkinkan client meminta data sesuai kebutuhan.
3. **REST:** Gaya arsitektur untuk membangun layanan web menggunakan prinsip dan metode komunikasi HTTP.

# 14. KONSEP SINKRONISASI

Sinkronisasi merupakan proses menyelaraskan waktu pada beberapa komputer atau node dalam sistem terdistribusi.

Setiap node memiliki clock atau jam lokal masing-masing. Perbedaan perangkat keras dan latency jaringan dapat menyebabkan waktu pada setiap node tidak selalu sama.

Sinkronisasi diperlukan untuk:

- Menentukan urutan kejadian secara akurat.
- Menjaga konsistensi data.
- Mendukung koordinasi proses.
- Mengurangi kesalahan akibat perbedaan waktu.

### Metode Sinkronisasi

Berdasarkan materi perkuliahan, metode sinkronisasi meliputi:

1. **Atomic Clock:** Digunakan sebagai sumber waktu yang sangat akurat.
2. **GPS (Global Positioning System):** Dapat digunakan sebagai sumber referensi waktu.
3. **TAI (International Atomic Time):** Skala waktu atom internasional.
4. **UTC (Coordinated Universal Time):** Standar waktu yang digunakan secara internasional.
5. **NTP (Network Time Protocol):** Protokol untuk menyinkronkan waktu perangkat melalui jaringan.
6. **PTP (Precision Time Protocol):** Protokol sinkronisasi waktu dengan presisi lebih tinggi dibandingkan NTP.

# 15. LOGICAL CLOCK

Logical Clock merupakan mekanisme pencatatan urutan kejadian dalam sistem terdistribusi tanpa bergantung langsung pada waktu sebenarnya atau real clock.

Salah satu metode yang dibahas adalah Lamport Logical Clock yang diperkenalkan oleh Leslie Lamport.

### 15.1 Cara Kerja Lamport Logical Clock

Aturan dasar Lamport Logical Clock adalah:

1. Setiap terjadi kejadian, nilai logical clock bertambah satu.
2. Ketika mengirim pesan, proses menyertakan nilai logical clock.
3. Ketika menerima pesan, proses membandingkan nilai clock lokal dengan nilai clock pada pesan.
4. Proses mengambil nilai terbesar, kemudian menambahkan satu.

### 15.2 Contoh Penerapan

Materi dosen memberikan contoh tiga layanan:

- Sales Service.
- Product Service.
- Invoice Service.

Urutan kejadian:

1. Sales Service mencatat transaksi penjualan dan menghasilkan logical clock 1.
2. Product Service menerima pesan dengan nilai 1, kemudian memperbarui logical clock menjadi 2.
3. Invoice Service menerima pesan dengan nilai 2, kemudian memperbarui logical clock menjadi 3 dan menghasilkan faktur.

Dengan demikian, urutan kejadian dapat diketahui melalui logical clock:

**Sales Service (1) → Product Service (2) → Invoice Service (3).**

### 15.3 Pengembangan Logical Clock

Materi juga menyebutkan beberapa pengembangan dari Lamport Logical Clock, yaitu:

1. Vector Clocks oleh Colin Fidge dan Friedemann Mattern (1988).
2. Plausible Clocks oleh Torres-Rojas dan Ahamad (1999).
3. Chain Clocks oleh Agarwal dan Garg (2005).
4. Interval Tree Clocks oleh Almeida dan rekan-rekan (2008).
5. Blum Clocks oleh Lum Ramabaja (2019).

# 16. KOORDINASI PROSES

Koordinasi proses merupakan mekanisme yang memungkinkan beberapa proses independen pada komputer berbeda bekerja sama untuk mencapai tujuan bersama.

Koordinasi diperlukan untuk mengatur komunikasi, sinkronisasi, serta akses terhadap sumber daya agar tidak terjadi konflik.

Beberapa permasalahan yang perlu dihindari adalah:

- **Deadlock:** Kondisi ketika proses saling menunggu sumber daya sehingga tidak dapat melanjutkan eksekusi.
- **Race Condition:** Kondisi ketika hasil proses dipengaruhi oleh urutan atau waktu akses beberapa proses terhadap sumber daya bersama.

Contoh teknologi koordinasi proses yang disebutkan dalam materi:

1. Apache ZooKeeper.
2. etcd.
3. Consul.
4. ClickHouse Keeper.
5. Oxia.
6. KRaft.

# 17. TANTANGAN DAN SOLUSI TERKAIT PROSES PADA SISTEM TERDISTRIBUSI

Dalam sistem terdistribusi terdapat beberapa tantangan yang dapat memengaruhi komunikasi dan koordinasi proses.

Berdasarkan materi perkuliahan, tantangan dan solusinya adalah:

| Tantangan | Penjelasan | Solusi |
|---|---|---|
| Message Loss | Pesan hilang selama proses komunikasi | Retransmission dan acknowledgement |
| Deadlock | Proses saling menunggu sumber daya | Timeout dan detection algorithm |
| Data Inconsistency | Data berbeda antarbagian sistem | Consensus Protocol seperti Raft dan Paxos |
| Security | Risiko akses atau komunikasi tidak aman | SSL/TLS dan OAuth2 |

Penerapan solusi tersebut bertujuan meningkatkan keandalan, keamanan, dan konsistensi sistem terdistribusi.

# 18. CURRENT ISSUES

Perkembangan sistem terdistribusi memunculkan berbagai isu dan teknologi yang terus dikembangkan.

Berdasarkan materi dosen, terdapat tiga topik utama:

### 18.1 Edge dan Fog Computing

Edge Computing dan Fog Computing merupakan pendekatan pemrosesan data yang mendekatkan komputasi ke sumber data atau perangkat pengguna.

Keduanya bertujuan membantu mengurangi latency dan meningkatkan efisiensi pemrosesan data.

### 18.2 Observability dan Tracing

Observability merupakan kemampuan untuk memahami kondisi internal sistem melalui data yang dihasilkan selama sistem berjalan.

Tracing digunakan untuk melacak perjalanan suatu permintaan melalui beberapa layanan dalam sistem terdistribusi.

Salah satu sumber informasi yang digunakan adalah telemetry.

### 18.3 Container Orchestration

Container Orchestration merupakan proses pengelolaan container yang mencakup deployment, penskalaan, dan pengaturan layanan.

Contoh teknologi yang disebutkan dalam materi adalah:
- Kubernetes.
- Docker Swarm.

# 19. DISKUSI

Berdasarkan materi perkuliahan, terdapat tiga pertanyaan diskusi:

### 19.1 Apakah GraphQL merupakan contoh dari RPC?

GraphQL bukan merupakan RPC secara langsung. GraphQL merupakan bahasa query untuk API yang memungkinkan client meminta data sesuai kebutuhan. GraphQL dapat menggunakan HTTP sebagai media komunikasi, tetapi pendekatan utamanya berbeda dengan RPC yang berfokus pada pemanggilan prosedur atau fungsi jarak jauh.

### 19.2 Apakah REST merupakan contoh dari RPC?

REST bukan RPC secara langsung. REST merupakan gaya arsitektur yang menggunakan resource dan representasinya sebagai dasar komunikasi, sedangkan RPC berfokus pada pemanggilan prosedur atau fungsi pada sistem lain.

Keduanya dapat digunakan untuk membangun komunikasi antarservice, tetapi memiliki pendekatan yang berbeda.

### 19.3 Apakah Telemetry merupakan solusi etis?

Telemetry dapat menjadi solusi yang etis apabila pengumpulan data dilakukan secara transparan, memiliki tujuan yang jelas, memperhatikan privasi pengguna, dan menerapkan perlindungan terhadap informasi yang dikumpulkan.

Namun, telemetry dapat menimbulkan masalah etika apabila data dikumpulkan tanpa persetujuan atau digunakan di luar tujuan yang telah diinformasikan.

---

# REFERENSI

1. Materi Perkuliahan Sistem Terdistribusi dan Terdesentralisasi. Dr. Bambang Purnomosidi D. P. Fakultas Teknologi Informasi, UTDI. Materi: Proses dan Komunikasi Antar Proses pada Sistem Terdistribusi.

2. MPI Forum. Message Passing Interface.  
   https://www.mpi-forum.org/

3. mpi4py Documentation.  
   https://mpi4py.readthedocs.io/en/stable/

4. gRPC Documentation.  
   https://grpc.io/docs/what-is-grpc/introduction/

5. Akamai. What Are Microservices?  
   https://www.akamai.com/glossary/what-are-microservices

6. Stackscale. HTTP/3.  
   https://www.stackscale.com/blog/http3/

7. Dashbird. Pub/Sub Messaging.  
   https://dashbird.io/knowledge-base/well-architected/pub-sub-messaging/

---

**AKHIR MATERI MINGGU 2**
