
# MODUL 06 : DISTRIBUTED FILE SYSTEM

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
5. Mempertahankan contoh teknologi, arsitektur, dan studi kasus yang terdapat dalam materi dosen.

---

# 1. PENGERTIAN FILE SYSTEM

File System (FS) merupakan metode yang digunakan oleh sistem operasi untuk mengelola dan mengatur file pada media penyimpanan, seperti hard disk, USB flashdisk, dan SSD.

File System berfungsi mengatur bagaimana data disimpan, diberi nama, diakses, dan dikelola sehingga pengguna dapat menggunakan file dengan mudah.

File System sering ditulis sebagai filesystem atau disingkat FS.

### 1.1 Jenis File System Berdasarkan Sistem Operasi

Setiap sistem operasi memiliki jenis File System yang berbeda.

1. **Linux:** ext4, XFS, btrfs, dan ReiserFS.
2. **DOS/Windows:** FAT16, FAT32, dan NTFS.
3. **Mac:** APFS (Apple File System).

Setiap File System memiliki karakteristik dan mekanisme pengelolaan penyimpanan masing-masing.

### 1.2 Cara Sistem Operasi Mengakses File System

File System dapat diakses melalui File System Driver yang dikelola oleh kernel sistem operasi.

Kernel menyediakan Virtual File System (VFS) sebagai lapisan abstraksi sehingga aplikasi dapat mengakses berbagai jenis File System menggunakan antarmuka yang seragam.

Dengan demikian, aplikasi tidak harus mengetahui secara langsung bagaimana setiap jenis File System bekerja.

### 1.3 Perbedaan File System dan Hirarki File System

File System berbeda dengan hirarki File System.

- **File System:** Metode yang digunakan untuk mengatur dan mengelola penyimpanan data.
- **Hirarki File System:** Struktur pengaturan file dan direktori dalam sistem operasi.

Pengguna biasanya berinteraksi dengan hirarki file dan direktori tanpa perlu memperhatikan jenis File System yang digunakan.

### 1.4 Alur Akses File System pada Linux

Berdasarkan diagram arsitektur Linux pada halaman 5–6, proses akses penyimpanan dapat dijelaskan sebagai berikut:

1. Aplikasi melakukan permintaan untuk membaca atau menulis file.
2. Permintaan diteruskan melalui System Call Interface.
3. Virtual File System menerima dan mengelola permintaan tersebut.
4. File System Driver menerjemahkan operasi sesuai jenis File System.
5. Kernel mengakses perangkat keras melalui mekanisme yang sesuai.
6. Data dibaca dari atau ditulis ke media penyimpanan.

Alur sederhananya:

```text
Application
     |
     v
System Call Interface
     |
     v
Virtual File System
     |
     v
File System Driver
     |
     v
Hardware
(Media Penyimpanan)
```

### 1.5 Hirarki Direktori Linux

Dalam Linux, file dan direktori disusun menggunakan struktur hirarki yang dimulai dari direktori root (`/`).

Beberapa direktori penting dalam Linux adalah:

| Direktori | Fungsi |
|---|---|
| `/bin` | Berisi perintah dasar sistem. |
| `/boot` | Menyimpan file yang diperlukan untuk proses booting. |
| `/dev` | Berisi representasi perangkat keras. |
| `/etc` | Menyimpan file konfigurasi sistem. |
| `/home` | Direktori utama pengguna. |
| `/lib` | Menyimpan library yang diperlukan sistem. |
| `/media` | Tempat mount media penyimpanan yang dapat dilepas. |
| `/mnt` | Tempat mount sementara. |
| `/opt` | Menyimpan perangkat lunak tambahan. |
| `/proc` | Menyediakan informasi proses dan kernel. |
| `/root` | Direktori home pengguna root. |
| `/run` | Menyimpan data runtime sistem. |
| `/sbin` | Berisi utilitas administrasi sistem. |
| `/srv` | Menyimpan data yang disediakan oleh layanan sistem. |
| `/sys` | Menyediakan informasi perangkat dan kernel. |
| `/tmp` | Menyimpan file sementara. |
| `/usr` | Menyimpan aplikasi dan data pendukung sistem. |
| `/var` | Menyimpan data yang sering berubah, seperti log. |

Standar pengaturan direktori Linux dapat dipelajari melalui Filesystem Hierarchy Standard (FHS).

Referensi:
https://specifications.freedesktop.org/fhs/latest/

---

# 2. BERBAGAI FILE SYSTEM

File System memiliki beberapa jenis berdasarkan teknologi dan kebutuhan sistem operasi.

Dalam materi dosen, jenis File System yang diperkenalkan meliputi:

### 2.1 ext4

ext4 merupakan salah satu File System yang umum digunakan pada sistem operasi Linux.

ext4 merupakan pengembangan dari keluarga Extended File System dan mendukung pengelolaan file serta penyimpanan berukuran besar.

### 2.2 XFS

XFS merupakan File System yang digunakan pada Linux dan dirancang untuk mendukung pengelolaan data serta operasi penyimpanan berskala besar.

### 2.3 btrfs

Btrfs merupakan File System Linux yang mendukung berbagai fitur pengelolaan penyimpanan, termasuk snapshot dan pemeriksaan integritas data.

### 2.4 ReiserFS

ReiserFS merupakan salah satu jenis File System yang pernah digunakan pada Linux untuk mengelola file dan direktori.

### 2.5 FAT16 dan FAT32

FAT16 dan FAT32 merupakan jenis File System yang dikembangkan dari keluarga File Allocation Table.

Keduanya digunakan pada berbagai media penyimpanan, termasuk perangkat penyimpanan portabel.

### 2.6 NTFS

NTFS merupakan File System yang digunakan pada sistem operasi Windows.

NTFS mendukung pengelolaan file dan direktori serta berbagai fitur pengaturan penyimpanan.

### 2.7 APFS

APFS (Apple File System) merupakan File System yang dikembangkan oleh Apple untuk perangkat dan sistem operasinya.

---

# 3. CARA KERJA FILE SYSTEM

File System bekerja dengan mengatur bagaimana data disimpan dan diakses pada media penyimpanan.

Sistem operasi menggunakan File System Driver dan Virtual File System untuk menerjemahkan permintaan aplikasi menjadi operasi penyimpanan.

### 3.1 Proses Penyimpanan File

Ketika pengguna menyimpan file, prosesnya secara umum adalah:

1. Pengguna membuat atau menyimpan file melalui aplikasi.
2. Aplikasi mengirimkan permintaan kepada sistem operasi.
3. Kernel menerima permintaan melalui System Call Interface.
4. Virtual File System mengelola permintaan tersebut.
5. File System Driver menentukan mekanisme penyimpanan berdasarkan jenis File System.
6. Data ditulis ke media penyimpanan.

### 3.2 Proses Membaca File

Ketika pengguna membuka file, prosesnya berlangsung sebagai berikut:

1. Pengguna meminta aplikasi untuk membuka suatu file.
2. Aplikasi mengirimkan permintaan kepada sistem operasi.
3. Kernel memproses permintaan melalui Virtual File System.
4. File System Driver mencari dan membaca data dari media penyimpanan.
5. Data diteruskan kembali kepada aplikasi.
6. Aplikasi menampilkan isi file kepada pengguna.

### 3.3 Virtual File System (VFS)

Virtual File System merupakan lapisan abstraksi pada kernel yang memungkinkan aplikasi mengakses berbagai jenis File System melalui antarmuka yang seragam.

Dengan adanya VFS, aplikasi tidak perlu menggunakan mekanisme yang berbeda untuk setiap jenis File System.

---

# 4. PENGERTIAN DISTRIBUTED FILE SYSTEM

Distributed File System (DFS) merupakan sistem File System yang mengoordinasikan sekumpulan media penyimpanan yang berada pada beberapa node atau mesin sehingga dapat digunakan sebagai satu kesatuan penyimpanan.

DFS bukan hanya File System yang tersebar pada lebih dari satu komputer, tetapi merupakan sistem abstraksi terkoordinasi yang mampu mengelola:

1. Heterogenitas perangkat penyimpanan.
2. Kegagalan pada komponen sistem.
3. Akses secara bersamaan atau concurrency.
4. Distribusi data pada beberapa node.

DFS membuat sekumpulan media penyimpanan yang berbeda terlihat sebagai satu sistem penyimpanan terintegrasi dari sisi pengguna.

### 4.1 Karakteristik Distributed File System

Beberapa karakteristik DFS adalah:

1. **Distributed Storage:** Data disimpan pada beberapa node.
2. **Transparency:** Pengguna dapat mengakses data tanpa harus mengetahui lokasi fisik penyimpanannya.
3. **Scalability:** Kapasitas penyimpanan dapat ditingkatkan dengan menambahkan node.
4. **Fault Tolerance:** Sistem dapat menangani kegagalan pada sebagian komponen.
5. **Concurrency:** Beberapa pengguna dapat mengakses data secara bersamaan.
6. **Reliability:** Data dikelola agar tetap tersedia dan dapat diakses meskipun terdapat gangguan.

### 4.2 Perbedaan DAS, DFS, NAS, dan SAN

Dalam materi dosen dijelaskan beberapa konsep teknologi penyimpanan yang perlu dibedakan.

**A. DAS (Direct-Attached Storage)**

DAS merupakan media penyimpanan yang terhubung secara langsung ke satu komputer atau server.

Contohnya adalah hard disk atau SSD yang dipasang langsung pada komputer.

Karakteristik:
- Terhubung langsung dengan perangkat.
- Umumnya dikelola oleh sistem operasi perangkat tersebut.
- Tidak membutuhkan jaringan untuk mengakses media penyimpanannya.

**B. DFS (Distributed File System)**

DFS merupakan sistem penyimpanan yang mengelola data dalam bentuk file dan direktori yang didistribusikan ke beberapa node.

Karakteristik:
- Data dapat tersebar di beberapa mesin.
- Pengguna melihat penyimpanan sebagai satu kesatuan.
- Menggunakan abstraksi pada tingkat software.

**C. NAS (Network-Attached Storage)**

NAS merupakan perangkat penyimpanan yang menyediakan akses file melalui jaringan.

Karakteristik:
- Penyimpanan dibagikan melalui jaringan.
- Menggunakan protokol berbasis file seperti NFS dan SMB.
- Memudahkan pengguna atau perangkat lain mengakses file secara bersama.

**D. SAN (Storage Area Network)**

SAN merupakan jaringan khusus yang menyediakan akses terhadap penyimpanan pada tingkat block.

Karakteristik:
- Menyediakan block-level storage.
- Server dapat mengakses perangkat penyimpanan melalui jaringan khusus.
- Penyimpanan dapat diformat menggunakan File System milik server.

### 4.3 Perbedaan DFS dan SAN

DFS dan SAN memiliki perbedaan pada tingkat abstraksi penyimpanan yang diberikan.

| Aspek | DFS | SAN |
|---|---|---|
| Tingkat abstraksi | File-level | Block-level |
| Pengelolaan | File dan direktori | Blok penyimpanan |
| Distribusi | Data dikelola pada beberapa node | Menyediakan akses ke perangkat block storage |
| Pengguna | Mengakses file melalui sistem terdistribusi | Server mengelola block storage menggunakan File System sendiri |
| Contoh penggunaan | Penyimpanan file terdistribusi | Database skala besar dan virtualisasi |

SAN secara konseptual dapat digunakan sebagai storage untuk DFS, meskipun materi dosen menyebutkan bahwa penggunaan tersebut tidak disarankan.

Penggunaan SAN umumnya meliputi:
- Backend database skala besar.
- Backend untuk video dan audio editing.
- Backend untuk virtualisasi skala besar.

Sementara itu, DFS lebih mengarah pada penggunaan DAS di setiap node.

---

# 5. BERBAGAI DISTRIBUTED FILE SYSTEM YANG UMUM

Terdapat beberapa teknologi Distributed File System yang digunakan untuk mengelola penyimpanan data dalam sistem terdistribusi.

Berdasarkan materi dosen, beberapa DFS yang umum digunakan adalah:

### 5.1 Google File System (GFS)

Google File System merupakan sistem penyimpanan terdistribusi yang dikembangkan oleh Google untuk mengelola data dalam skala besar.

GFS dirancang untuk mendukung penyimpanan dan pemrosesan data pada banyak mesin.

### 5.2 Colossus

Colossus merupakan penerus Google File System yang digunakan oleh Google untuk mendukung layanan dan penyimpanan data berskala besar.

Berdasarkan materi dosen, Colossus digunakan dalam berbagai layanan Google, seperti:

- YouTube.
- Gmail.
- Google Docs.

### 5.3 CephFS

CephFS merupakan Distributed File System yang menjadi bagian dari ekosistem Ceph.

CephFS menyediakan penyimpanan berbasis file yang dapat digunakan pada lingkungan terdistribusi.

Website:
https://ceph.io/en/

### 5.4 Gluster

Gluster merupakan sistem penyimpanan terdistribusi yang digunakan untuk mengelola dan menggabungkan kapasitas penyimpanan dari beberapa server.

Website:
https://www.gluster.org/

### 5.5 HDFS (Hadoop Distributed File System)

HDFS merupakan File System terdistribusi yang menjadi bagian dari Apache Hadoop.

HDFS dirancang untuk menyimpan dan mengelola dataset berukuran besar pada cluster komputer.

Website:
https://hadoop.apache.org/

### 5.6 Lustre

Lustre merupakan Distributed File System yang digunakan untuk kebutuhan penyimpanan dan pengelolaan data dalam skala besar.

Website:
https://www.lustre.org/

---

# 6. CARA KERJA DISTRIBUTED FILE SYSTEM

Distributed File System bekerja dengan menggabungkan beberapa media penyimpanan yang berada pada node berbeda sehingga pengguna dapat mengaksesnya melalui satu sistem penyimpanan terintegrasi.

Berdasarkan diagram pada halaman 12, DFS menyediakan Global Namespace yang menjadi lapisan abstraksi bagi pengguna dan aplikasi.

### 6.1 Global Namespace

Global Namespace merupakan ruang nama atau struktur direktori terpusat secara logis yang memungkinkan pengguna mengakses file dari berbagai lokasi penyimpanan melalui satu tampilan.

Pengguna tidak harus mengetahui lokasi fisik setiap file.

### 6.2 Proses Kerja DFS

Secara umum, proses kerja DFS dapat dijelaskan sebagai berikut:

1. Pengguna atau aplikasi melakukan permintaan akses terhadap file.
2. Permintaan diterima oleh sistem DFS melalui Global Namespace.
3. DFS menentukan lokasi penyimpanan data yang diminta.
4. DFS menghubungkan permintaan dengan node penyimpanan yang sesuai.
5. Data dibaca atau ditulis pada node terkait.
6. Hasil operasi dikembalikan kepada pengguna atau aplikasi.

### 6.3 Integrasi Berbagai Lokasi Penyimpanan

Berdasarkan diagram pada halaman 12, DFS dapat mengintegrasikan berbagai sumber penyimpanan, seperti:

- NAS 1.
- NAS 2.
- Linux NFS.
- Windows SMB.
- Public Cloud.

Meskipun penyimpanan berasal dari lokasi dan teknologi yang berbeda, pengguna dapat mengaksesnya melalui satu sistem yang terintegrasi.

Dengan demikian, DFS menyederhanakan pengelolaan penyimpanan yang tersebar di berbagai lokasi.

---

# 7. STUDI KASUS: HDFS

Hadoop Distributed File System (HDFS) merupakan File System terdistribusi yang bersifat open source, scalable, dan fault-tolerant.

HDFS dirancang untuk menyimpan serta mengelola dataset berukuran besar pada cluster yang terdiri dari commodity hardware.

### 7.1 Commodity Hardware

Commodity Hardware merupakan perangkat keras komputer yang diproduksi secara massal, memiliki harga relatif murah, mudah dipertukarkan, dan tersedia dari berbagai vendor.

HDFS dirancang agar dapat berjalan menggunakan kumpulan perangkat keras tersebut.

### 7.2 Fungsi HDFS

HDFS merupakan salah satu komponen utama Apache Hadoop yang digunakan untuk pemrosesan data berskala besar.

HDFS bekerja dengan cara:

1. Membagi file menjadi beberapa blok data.
2. Mendistribusikan blok data ke beberapa server.
3. Menyimpan salinan blok pada node lainnya melalui mekanisme replikasi.
4. Menyediakan akses data ketika pengguna atau aplikasi membutuhkannya.

Mekanisme tersebut membantu meningkatkan ketersediaan dan ketahanan data.

### 7.3 Komponen Arsitektur HDFS

Berdasarkan diagram arsitektur pada halaman 14–16, HDFS memiliki beberapa komponen utama.

**A. NameNode**

NameNode merupakan komponen utama yang mengelola metadata pada HDFS.

Tugas NameNode meliputi:

1. Mengelola informasi nama file dan direktori.
2. Menyimpan informasi lokasi blok data.
3. Mengelola jumlah replika setiap blok.
4. Mengatur operasi metadata.
5. Mengelola koordinasi terhadap DataNode.

NameNode tidak menyimpan isi file secara langsung, melainkan mengelola informasi mengenai penyimpanan file.

**B. DataNode**

DataNode merupakan komponen yang bertugas menyimpan blok data secara fisik.

Tugas DataNode meliputi:

1. Menyimpan blok data.
2. Melayani permintaan pembacaan data.
3. Melayani permintaan penulisan data.
4. Melakukan replikasi blok sesuai instruksi NameNode.

**C. Client**

Client merupakan aplikasi atau pengguna yang melakukan operasi terhadap file pada HDFS.

Client berkomunikasi dengan NameNode untuk memperoleh informasi metadata dan berkomunikasi dengan DataNode untuk membaca atau menulis isi file.

### 7.4 Metadata pada HDFS

Metadata merupakan informasi yang menjelaskan karakteristik dan lokasi suatu file.

Berdasarkan diagram pada materi dosen, metadata dapat mencakup:

- Nama file.
- Lokasi blok data.
- Jumlah replika.

Contoh metadata:

```text
Name: /home/foo/data
Replicas: 3
```

Informasi tersebut digunakan oleh NameNode untuk mengetahui lokasi penyimpanan blok file dan jumlah replika yang dimiliki.

### 7.5 Block Storage pada HDFS

HDFS membagi file berukuran besar menjadi beberapa blok.

Setiap blok dapat disimpan pada DataNode yang berbeda.

Pembagian tersebut memungkinkan data didistribusikan ke beberapa perangkat penyimpanan sehingga proses pengelolaan dataset besar menjadi lebih mudah.

### 7.6 Replikasi Data pada HDFS

HDFS menggunakan mekanisme replikasi untuk membuat beberapa salinan blok data.

Tujuannya adalah meningkatkan ketersediaan dan ketahanan data apabila salah satu DataNode mengalami kegagalan.

Berdasarkan contoh metadata pada materi dosen, jumlah replika dapat bernilai tiga.

Artinya, suatu blok data memiliki tiga salinan yang disimpan pada beberapa DataNode.

### 7.7 Proses Membaca Data pada HDFS

Proses membaca data pada HDFS dapat dijelaskan sebagai berikut:

1. Client meminta informasi file kepada NameNode.
2. NameNode memberikan informasi lokasi blok data.
3. Client menghubungi DataNode yang menyimpan blok tersebut.
4. DataNode mengirimkan isi blok kepada Client.
5. Client menggabungkan blok-blok yang diperlukan untuk memperoleh file secara utuh.

Dengan demikian, NameNode bertugas menyediakan informasi lokasi, sedangkan DataNode menyediakan isi data.

### 7.8 Proses Menulis Data pada HDFS

Proses penulisan data pada HDFS berlangsung melalui beberapa tahapan:

1. Client mengirim permintaan penulisan file kepada NameNode.
2. NameNode menentukan DataNode yang akan digunakan untuk menyimpan blok.
3. Client mengirimkan blok data kepada DataNode pertama.
4. DataNode pertama meneruskan data ke DataNode berikutnya sesuai pipeline replikasi.
5. DataNode menyimpan blok yang diterima.
6. Konfirmasi penyimpanan dikirimkan kembali kepada Client.
7. Proses berlanjut sampai seluruh blok file berhasil disimpan.

### 7.9 Rack Awareness

Pada diagram arsitektur HDFS halaman 15–16, DataNode ditampilkan dalam beberapa kelompok Rack.

Rack Awareness merupakan konsep penempatan replika dengan mempertimbangkan lokasi fisik atau kelompok jaringan DataNode.

Tujuannya adalah membantu meningkatkan ketersediaan data ketika terjadi kegagalan pada perangkat atau jaringan dalam suatu rack.

### 7.10 Persyaratan Apache Hadoop 3.5.0

Berdasarkan materi dosen, Apache Hadoop 3.5.0 dikompilasi menggunakan JDK 17.

Persyaratan Java yang dicantumkan adalah:

- **Server:** Java 17.
- **Client:** Java 17 atau Java 21.

Informasi ini perlu diperhatikan sebelum melakukan instalasi dan konfigurasi Hadoop.

### 7.11 Praktik Instalasi dan Penggunaan HDFS

Materi dosen mengarahkan mahasiswa untuk mempraktikkan penggunaan HDFS berdasarkan dokumen yang disediakan melalui EL-UTDI.

Praktik tersebut bertujuan agar mahasiswa memahami proses instalasi, konfigurasi, dan cara kerja HDFS secara langsung.

Dokumen praktik yang ditunjukkan dalam slide berjudul:

`Menggunakan Apache Hadoop - HDFS`

Praktik dilakukan dengan mengikuti petunjuk yang tersedia dalam dokumen tersebut.

---

# 8. PENGERTIAN CLOUD STORAGE

Cloud Storage merupakan layanan penyimpanan data secara online yang memungkinkan pengguna menyimpan dan mengakses data melalui jaringan internet tanpa harus menyimpan seluruh data pada hard drive lokal atau perangkat fisik milik pengguna.

Cloud Storage menggunakan model penyimpanan data pada kumpulan sumber daya penyimpanan yang dikelola secara remote oleh penyedia layanan cloud.

### 8.1 Karakteristik Cloud Storage

1. **Remote Storage:** Data disimpan pada server yang berada di lokasi berbeda dari pengguna.
2. **Network Access:** Data dapat diakses melalui jaringan, biasanya internet.
3. **Scalability:** Kapasitas penyimpanan dapat disesuaikan dengan kebutuhan.
4. **Managed Infrastructure:** Infrastruktur fisik biasanya dimiliki dan dikelola oleh penyedia cloud.
5. **Distributed Infrastructure:** Penyimpanan fisik dapat terdiri dari beberapa server dan bahkan beberapa lokasi.

### 8.2 Contoh Cloud Storage

Beberapa layanan Cloud Storage yang disebutkan dalam materi dosen adalah:

**1. Amazon S3**

Amazon Simple Storage Service merupakan layanan penyimpanan objek yang disediakan oleh Amazon Web Services.

Website:
https://aws.amazon.com/s3/

**2. Azure Blob Storage**

Azure Blob Storage merupakan layanan penyimpanan objek yang disediakan oleh Microsoft Azure.

**3. Google Cloud Storage (GCS)**

Google Cloud Storage merupakan layanan penyimpanan data yang disediakan oleh Google Cloud.

---

# 9. RELASI CLOUD STORAGE DENGAN DISTRIBUTED FILE SYSTEM

Cloud Storage dan Distributed File System memiliki hubungan dalam pengelolaan serta penyimpanan data pada lingkungan terdistribusi.

Cloud Storage berfungsi sebagai tempat penyimpanan data, sedangkan DFS dapat digunakan untuk mengelola dan mengorganisasikan data dalam bentuk file dan direktori.

Dengan demikian, keduanya dapat bekerja sama untuk menyediakan sistem penyimpanan yang terintegrasi.

### 9.1 Hubungan Cloud Storage dengan DFS

Cloud Storage menyediakan media penyimpanan yang dapat diakses melalui jaringan.

Sementara itu, DFS menyediakan mekanisme pengelolaan file dan direktori yang dapat mengakses penyimpanan tersebut.

### 9.2 Contoh Integrasi Amazon S3 dengan HDFS

Berdasarkan materi dosen, Amazon S3 dapat digunakan bersama HDFS.

Dalam konfigurasi tersebut:

- Amazon S3 berperan sebagai Cloud Storage.
- HDFS menyediakan mekanisme operasi File System.
- Konfigurasi dilakukan melalui file `core-site.xml`.

### 9.3 Contoh Konfigurasi core-site.xml

Materi dosen menampilkan contoh konfigurasi akses Amazon S3 menggunakan properti berikut:

```xml
<property>
    <name>fs.s3a.access.key</name>
    <value>YOUR_AWS_ACCESS_KEY_ID</value>
</property>

<property>
    <name>fs.s3a.secret.key</name>
    <value>YOUR_AWS_SECRET_ACCESS_KEY</value>
</property>

<property>
    <name>fs.s3a.endpoint</name>
    <value>s3.amazonaws.com</value>
</property>
```

Keterangan:

1. `fs.s3a.access.key` digunakan untuk menentukan Access Key yang digunakan dalam autentikasi.
2. `fs.s3a.secret.key` digunakan untuk menentukan Secret Access Key.
3. `fs.s3a.endpoint` digunakan untuk menentukan endpoint layanan Amazon S3.

**Catatan keamanan:** Access Key dan Secret Access Key harus menggunakan kredensial milik sendiri dan tidak boleh dipublikasikan ke repository GitHub. Untuk konfigurasi nyata, gunakan pengelolaan kredensial yang aman.

---

# 10. TIPE CLOUD STORAGE

Cloud Storage memiliki beberapa jenis berdasarkan cara data disimpan dan diakses.

Dalam materi perkuliahan, terdapat tiga tipe utama Cloud Storage, yaitu Object Storage, File Storage, dan Block Storage.

### 10.1 Object Storage

Object Storage merupakan metode penyimpanan data dalam bentuk objek.

Setiap objek biasanya memiliki:

1. Data atau isi objek.
2. Metadata.
3. Identifier unik.

Object Storage umumnya diakses melalui protokol berbasis HTTP dan REST API.

**Karakteristik:**

- Data disimpan sebagai objek.
- Menggunakan metadata untuk mendeskripsikan objek.
- Cocok untuk penyimpanan data tidak terstruktur.
- Mendukung skalabilitas penyimpanan yang besar.

**Contoh:**

Amazon S3.

### 10.2 File Storage

File Storage merupakan metode penyimpanan data dalam bentuk file dan direktori.

Data disusun menggunakan struktur hirarki sehingga pengguna dapat mengakses file melalui folder dan direktori.

**Karakteristik:**

- Menggunakan struktur file dan direktori.
- Memudahkan pengelolaan data berbasis file.
- Dapat digunakan untuk berbagi file antar-pengguna.
- Umumnya menggunakan protokol NFS dan SMB.

### 10.3 Block Storage

Block Storage merupakan metode penyimpanan data dengan membagi data menjadi blok-blok berukuran tertentu.

Setiap blok dikelola sebagai unit penyimpanan yang dapat diakses oleh sistem operasi atau aplikasi.

**Karakteristik:**

- Data disimpan dalam bentuk blok.
- Mendukung akses penyimpanan pada tingkat block.
- Memiliki latensi rendah untuk penggunaan tertentu.
- Cocok untuk kebutuhan database dan penyimpanan terstruktur.

### 10.4 Perbedaan Object, File, dan Block Storage

| Aspek | Object Storage | File Storage | Block Storage |
|---|---|---|---|
| Bentuk penyimpanan | Objek | File dan direktori | Blok data |
| Akses | HTTP, REST | NFS, SMB | FC, iSCSI |
| Antarmuka | API | Sistem file | Block device |
| Penggunaan | Data tidak terstruktur dan objek | Berbagi file dan direktori | Database dan penyimpanan terstruktur |
| Karakteristik | Mudah diskalakan | Pengelolaan berbasis file | Latensi rendah |

---

# 11. STUDI KASUS CLOUD STORAGE

Pada bagian akhir materi, dosen memberikan beberapa contoh teknologi yang berkaitan dengan penerapan Cloud Storage dan Distributed Storage.

### 11.1 Ceph

Ceph merupakan sistem penyimpanan terdistribusi open source yang dirancang untuk menyediakan penyimpanan yang andal dan scalable.

Ceph mendukung beberapa jenis layanan penyimpanan, termasuk:

- Object Storage.
- Block Storage.
- File Storage melalui CephFS.

Website:
https://ceph.io/en/

### 11.2 CubeFS

CubeFS merupakan sistem penyimpanan terdistribusi berbasis cloud-native yang mendukung berbagai protokol akses, seperti:

- S3.
- HDFS.
- POSIX.

CubeFS dapat digunakan untuk kebutuhan penyimpanan data berskala besar, termasuk Big Data, AI/ML, dan lingkungan container.

Pada halaman 22–26 materi dosen, ditampilkan beberapa gambaran antarmuka serta arsitektur CubeFS.

Website:
https://cubefs.io/

### 11.3 RustFS

RustFS merupakan teknologi penyimpanan berbasis objek yang ditampilkan dalam materi sebagai salah satu alternatif penyimpanan yang kompatibel dengan S3.

Materi memperlihatkan RustFS sebagai solusi penyimpanan multi-cloud dengan fokus pada throughput dan pengelolaan objek.

Website:
https://rustfs.com/

### 11.4 Silo (PGSTY Silo)

Silo merupakan implementasi S3 Interface Libre Object Storage yang ditampilkan dalam materi dosen.

Materi memperlihatkan Silo sebagai salah satu contoh teknologi penyimpanan objek yang berkaitan dengan ekosistem S3.

Website:
https://silo.pgstsy.com/

### 11.5 Rook

Rook merupakan proyek open source yang menyediakan pengelolaan sistem penyimpanan cloud-native pada lingkungan Kubernetes.

Berdasarkan gambar halaman 25, Rook ditampilkan sebagai solusi untuk mengelola penyimpanan File, Block, dan Object.

Website:
https://rook.io/

### 11.6 Arsitektur CubeFS

Berdasarkan diagram arsitektur pada halaman 26, CubeFS memiliki beberapa komponen utama.

**A. Client**

Client merupakan aplikasi atau pengguna yang mengakses layanan penyimpanan.

Client dapat menggunakan antarmuka seperti POSIX, HDFS, maupun AWS S3 SDK.

**B. Master**

Master bertugas mengelola koordinasi dan metadata dalam sistem penyimpanan CubeFS.

**C. MetaNode**

MetaNode bertugas mengelola metadata file dan direktori.

**D. DataNode**

DataNode bertugas menyimpan dan mengelola data yang dibagi ke dalam beberapa partisi.

**E. Object Node**

Object Node berperan dalam pengelolaan penyimpanan objek.

**F. Blob Node**

Blob Node merupakan komponen yang berkaitan dengan penyimpanan blob atau bagian data objek.

### 11.7 Cara Kerja Arsitektur CubeFS

Secara umum, alur kerja berdasarkan diagram pada halaman 26 dapat dijelaskan sebagai berikut:

1. Client mengirimkan permintaan penyimpanan atau pembacaan data.
2. Permintaan diterima melalui antarmuka yang sesuai.
3. Master mengoordinasikan pengelolaan sistem.
4. Metadata dikelola melalui Metadata Subsystem.
5. Data dikelola melalui Data Subsystem.
6. Data disimpan pada node penyimpanan yang sesuai.
7. Sistem menyediakan akses kembali kepada Client sesuai permintaan.

Arsitektur tersebut memperlihatkan bagaimana CubeFS memisahkan pengelolaan metadata dan penyimpanan data agar dapat menangani kebutuhan penyimpanan terdistribusi.

---

# KESIMPULAN

Distributed File System merupakan sistem penyimpanan yang menggabungkan beberapa media penyimpanan pada node berbeda menjadi satu kesatuan yang dapat diakses oleh pengguna.

Sebelum memahami DFS, penting untuk mengetahui konsep dasar File System, yaitu metode yang digunakan sistem operasi untuk mengatur file dan direktori pada media penyimpanan.

DFS memiliki beberapa karakteristik penting, seperti distribusi data, transparansi lokasi penyimpanan, skalabilitas, concurrency, dan fault tolerance.

Beberapa teknologi DFS yang umum digunakan adalah Google File System, Colossus, CephFS, Gluster, HDFS, dan Lustre.

Salah satu contoh penerapan DFS adalah HDFS yang merupakan bagian dari Apache Hadoop. HDFS menggunakan NameNode untuk mengelola metadata dan DataNode untuk menyimpan blok data. File dibagi menjadi beberapa blok dan direplikasi ke beberapa node untuk meningkatkan ketersediaan data.

Selain DFS, Cloud Storage juga menjadi bagian penting dalam sistem penyimpanan modern. Cloud Storage menyediakan media penyimpanan melalui jaringan, sedangkan DFS dapat membantu mengorganisasikan dan mengakses data tersebut.

Terdapat tiga tipe utama Cloud Storage, yaitu Object Storage, File Storage, dan Block Storage. Contoh teknologi yang dibahas dalam materi adalah Ceph, CubeFS, RustFS, Silo, dan Rook.

Dengan memahami File System, DFS, dan Cloud Storage, mahasiswa dapat mengetahui bagaimana sistem penyimpanan modern bekerja dalam lingkungan terdistribusi.

---

# REFERENSI

1. Materi Perkuliahan Sistem Terdistribusi dan Terdesentralisasi. Dr. Bambang Purnomosidi D. P. Fakultas Teknologi Informasi, UTDI. Materi 06: Distributed File System.

2. Filesystem Hierarchy Standard (FHS).  
   https://specifications.freedesktop.org/fhs/latest/

3. Linux Storage Stack Diagram.  
   https://www.thomas-krenn.com/en/wiki/Linux_Storage_Stack_Diagram

4. Apache Hadoop Documentation.  
   https://hadoop.apache.org/

5. HDFS Architecture Guide.  
   https://hadoop.apache.org/docs/current/hadoop-project-dist/hadoop-hdfs/HdfsDesign.html

6. Ceph Documentation.  
   https://ceph.io/en/

7. Gluster Documentation.  
   https://www.gluster.org/

8. Lustre Documentation.  
   https://www.lustre.org/

9. Amazon S3 Documentation.  
   https://aws.amazon.com/s3/

10. CubeFS Documentation.  
    https://cubefs.io/docs/master/overview/architecture.html#architecture

11. Cloud Storage Types.  
    https://cloudian.com/guides/object-storage/object-storage-care/

---

**AKHIR MATERI MINGGU 6**
