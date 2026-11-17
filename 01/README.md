
# MODUL 01 – PENGENALAN SISTEM TERDISTRIBUSI DAN TERDESENTRALISASI

## Identitas Mahasiswa

**Nama:** Apriliva Putri P
**NIM:** 255410035
**Kelas:** Informatika-1

## Identitas Penggunaan AI

**AI yang digunakan:** ChatGPT (OpenAI)

**Prompt:**

Bertindaklah sebagai mahasiswa Informatika yang memahami mata kuliah Sistem Terdistribusi dan Terdesentralisasi. Buat rangkuman materi berdasarkan PDF atau PPT perkuliahan yang diberikan dosen. Ikuti seluruh agenda pembahasan secara berurutan. Jelaskan setiap poin secara terpisah, mendalam, sistematis, dan menggunakan bahasa Indonesia baku serta akademis. Sertakan pengertian, konsep, karakteristik, mekanisme kerja, contoh penerapan, dan analisis apabila relevan. Jangan menggabungkan beberapa poin menjadi satu pembahasan dan jangan menghilangkan materi dari dosen. Hasil akhir harus menggunakan format Markdown dan siap dimasukkan ke dalam README.md GitHub.

**Bagian yang disesuaikan dari keluaran prompt ada pada:**

1. Meringkas penjelasan agar lebih padat dan sesuai dengan materi presentasi dosen.
2. Memperbaiki susunan kalimat agar lebih mudah dipahami.
3. Menyesuaikan istilah teknis dengan konsep yang disampaikan dalam perkuliahan.
4. Memisahkan setiap agenda pembahasan agar lebih terstruktur.

---

# 1. ARTI PENTING SISTEM TERDISTRIBUSI DAN TERDESENTRALISASI

## 1.1 Pengertian Umum

Sistem terdistribusi dan terdesentralisasi merupakan konsep penting dalam perkembangan teknologi informasi modern. Kedua konsep ini memungkinkan sistem komputer bekerja dengan melibatkan banyak perangkat, komponen, atau node yang saling terhubung melalui jaringan untuk mendukung pemrosesan data dan penyediaan layanan.

Perkembangan teknologi digital menyebabkan peningkatan jumlah pengguna, volume data, serta kebutuhan terhadap layanan berbasis internet. Sistem komputer dengan pengelolaan terpusat dan sumber daya terbatas dapat mengalami kendala ketika harus menangani permintaan dalam jumlah besar. Oleh karena itu, diperlukan pendekatan sistem terdistribusi dan terdesentralisasi agar pengelolaan sumber daya, pemrosesan data, serta pengendalian sistem dapat dilakukan secara lebih efektif.

Kedua konsep tersebut menjadi fondasi bagi berbagai teknologi modern, seperti cloud computing, media sosial, platform streaming, penyimpanan data berskala besar, dan blockchain.

## 1.2 Faktor yang Menyebabkan Sistem Terdistribusi dan Terdesentralisasi Menjadi Penting

### A. Pertumbuhan Data dan Pengguna yang Sangat Besar

Perkembangan internet dan teknologi digital menyebabkan peningkatan jumlah pengguna serta volume data yang dihasilkan setiap harinya. Berbagai platform digital harus mampu menangani aktivitas pengguna secara bersamaan, mulai dari mengakses informasi, mengunggah file, melakukan transaksi, hingga berkomunikasi secara daring.

Apabila seluruh pemrosesan data hanya bergantung pada satu komputer atau server, sistem berpotensi mengalami kelebihan beban atau overload. Kondisi tersebut dapat menyebabkan penurunan kinerja, keterlambatan pemrosesan, bahkan kegagalan layanan.

Sistem terdistribusi membantu mengatasi permasalahan tersebut dengan membagi pemrosesan dan penyimpanan data ke beberapa komputer atau server yang saling terhubung.

**Contoh penerapan:**
- Google menangani permintaan pencarian dari pengguna dalam jumlah sangat besar.
- Netflix menyediakan layanan streaming video kepada banyak pengguna secara bersamaan.
- Media sosial mengelola data pengguna, unggahan, komentar, dan interaksi dalam jumlah besar.

### B. Kebutuhan terhadap Skalabilitas (Scalability)

Skalabilitas merupakan kemampuan suatu sistem, jaringan, proses, atau organisasi untuk berkembang dan menangani peningkatan beban kerja, jumlah pengguna, maupun permintaan tanpa mengorbankan kinerja atau kualitas layanan.

Dalam sistem terdistribusi, skalabilitas menjadi salah satu aspek penting karena kebutuhan sumber daya dapat meningkat seiring bertambahnya jumlah pengguna dan aktivitas sistem.

Terdapat dua pendekatan utama dalam meningkatkan skalabilitas:

1. **Vertical Scaling (Scale Up)**

   Vertical scaling merupakan metode peningkatan kapasitas sistem dengan memperbesar kemampuan perangkat yang sudah digunakan. Contohnya adalah meningkatkan kapasitas RAM, prosesor, atau media penyimpanan pada sebuah server.

2. **Horizontal Scaling (Scale Out)**

   Horizontal scaling merupakan metode peningkatan kapasitas sistem dengan menambahkan lebih banyak komputer atau server ke dalam jaringan. Beban kerja kemudian dapat dibagi ke beberapa perangkat tersebut.

**Contoh penerapan:**

Sebuah platform e-commerce mengalami peningkatan jumlah pengunjung ketika berlangsungnya promosi besar. Untuk mengatasi peningkatan permintaan, pengelola sistem dapat menambahkan beberapa server agar permintaan pengguna dapat diproses secara bersamaan.

### C. Kebutuhan terhadap Fault Tolerance

Fault tolerance merupakan kemampuan suatu sistem untuk tetap beroperasi meskipun terjadi kegagalan atau malfungsi pada sebagian komponennya, baik perangkat keras (hardware) maupun perangkat lunak (software).

Dalam sistem komputer, kegagalan dapat terjadi akibat kerusakan server, gangguan jaringan, kesalahan aplikasi, atau masalah pada media penyimpanan.

Sistem terdistribusi dapat menerapkan mekanisme toleransi kesalahan dengan menyediakan beberapa komponen yang memiliki fungsi serupa, melakukan replikasi data, serta menyediakan mekanisme pemulihan ketika salah satu komponen mengalami gangguan.

Dengan adanya mekanisme tersebut, kegagalan pada satu komponen tidak selalu menyebabkan keseluruhan sistem berhenti beroperasi.

**Contoh penerapan:**

Pada layanan penyimpanan data, sebuah file dapat disimpan dalam beberapa salinan pada server yang berbeda. Apabila salah satu server mengalami kerusakan, salinan data pada server lain masih dapat digunakan sehingga layanan tetap tersedia.

### D. Kebutuhan terhadap Performa dan Ketersediaan Layanan 24/7

Layanan digital modern dituntut untuk memiliki performa yang baik serta ketersediaan layanan selama 24 jam sehari dan 7 hari dalam seminggu.

Pengguna mengharapkan layanan dapat diakses kapan saja tanpa harus mengalami gangguan yang berkepanjangan. Hal ini menjadi penting terutama bagi layanan perbankan digital, perdagangan elektronik, media sosial, dan platform streaming.

Sistem terdistribusi mendukung kebutuhan tersebut melalui pembagian beban kerja, penggunaan beberapa server, serta mekanisme pengelolaan sumber daya secara bersama.

Selain itu, sistem terdesentralisasi dapat mengurangi ketergantungan terhadap satu titik pengendalian sehingga kegagalan pada satu pihak atau komponen tidak selalu menghentikan seluruh aktivitas jaringan.

**Contoh penerapan:**
- Layanan perbankan digital harus dapat melayani transaksi pengguna setiap saat.
- Netflix harus mampu menyediakan layanan streaming kepada pengguna di berbagai wilayah.
- Platform media sosial harus tetap dapat diakses meskipun terjadi peningkatan aktivitas pengguna.

### E. Mendukung Teknologi Modern

Sistem terdistribusi dan terdesentralisasi merupakan fondasi penting dalam pembangunan berbagai teknologi modern.

Tanpa penerapan sistem distribusi dan desentralisasi, teknologi seperti Google, Netflix, dan blockchain tidak dapat dikembangkan dengan kemampuan layanan seperti yang dikenal saat ini.

Hal tersebut dikarenakan teknologi modern membutuhkan kemampuan untuk mengelola data dalam jumlah besar, membagi beban pemrosesan, meningkatkan ketersediaan layanan, serta mengatur komunikasi antarkomponen yang saling terhubung.

Beberapa contoh penerapannya adalah:

1. **Google**

   Google menggunakan pendekatan komputasi terdistribusi untuk mendukung pengolahan data, pencarian informasi, serta penyediaan berbagai layanan digital kepada pengguna dalam jumlah besar.

2. **Netflix**

   Netflix memanfaatkan infrastruktur terdistribusi untuk mendukung penyediaan dan distribusi konten video kepada pengguna di berbagai wilayah.

3. **Blockchain**

   Blockchain menerapkan konsep jaringan terdesentralisasi yang memungkinkan beberapa node berpartisipasi dalam penyimpanan dan validasi transaksi tanpa bergantung pada satu pengendali pusat.

## 1.3 Hubungan Sistem Terdistribusi dengan Sistem Terdesentralisasi

Sistem terdistribusi dan sistem terdesentralisasi memiliki hubungan yang erat, tetapi keduanya mempunyai fokus yang berbeda.

Sistem terdistribusi lebih menekankan pada pembagian beban kerja, pemrosesan data, dan sumber daya komputasi ke beberapa perangkat yang saling terhubung.

Sementara itu, sistem terdesentralisasi lebih menekankan pada pembagian kendali atau wewenang pengambilan keputusan kepada beberapa pihak atau node sehingga tidak seluruh pengendalian bergantung pada satu pusat.

Keduanya dapat diterapkan secara bersamaan untuk membangun sistem yang mampu menangani beban kerja besar sekaligus mengurangi ketergantungan terhadap satu pihak pengendali.

## 1.4 Kesimpulan

Sistem terdistribusi dan terdesentralisasi memiliki peranan penting dalam perkembangan teknologi informasi modern. Peningkatan jumlah pengguna dan volume data menuntut sistem komputer agar mampu menangani beban kerja yang semakin besar, mempertahankan performa, serta menyediakan layanan dengan tingkat ketersediaan yang tinggi.

Melalui sistem terdistribusi, beban kerja dapat dibagi ke beberapa komputer atau server sehingga sistem lebih mudah dikembangkan dan mampu menangani peningkatan permintaan. Sementara itu, sistem terdesentralisasi memungkinkan pembagian kendali kepada beberapa node sehingga ketergantungan terhadap satu titik pengendalian dapat dikurangi.

---

# 2. PENGERTIAN SISTEM TERDISTRIBUSI

## 2.1 Definisi Sistem Terdistribusi

Sistem terdistribusi (Distributed System) merupakan sekumpulan komputer independen yang saling terhubung dan bekerja sama melalui jaringan sehingga bagi penggunanya terlihat sebagai satu kesatuan sistem yang utuh.

Menurut Andrew S. Tanenbaum dan Maarten van Steen (2007), sistem terdistribusi adalah:

"A collection of independent computers that appears to its users as a single coherent system."

Artinya, sistem terdistribusi terdiri atas beberapa komputer yang berdiri sendiri, tetapi mampu bekerja sama sehingga pengguna dapat mengaksesnya seolah-olah menggunakan satu sistem terpadu.

Dalam sistem terdistribusi, setiap komputer atau node mempunyai sumber daya dan kemampuan pemrosesan masing-masing. Komponen-komponen tersebut saling berkomunikasi melalui jaringan untuk bertukar informasi, mengirim permintaan, dan menjalankan tugas tertentu.

## 2.2 Komponen Utama Sistem Terdistribusi

### A. Node atau Komputer

Node merupakan perangkat komputasi yang menjadi bagian dari sistem terdistribusi. Node dapat berupa komputer, server, perangkat mobile, atau mesin virtual.

Setiap node dapat menjalankan proses tertentu dan berkomunikasi dengan node lainnya melalui jaringan.

### B. Jaringan Komunikasi

Jaringan komunikasi merupakan media yang menghubungkan setiap node agar dapat bertukar data dan informasi.

Komunikasi dapat dilakukan menggunakan berbagai protokol jaringan, seperti TCP/IP, HTTP, dan REST API.

### C. Middleware

Middleware merupakan perangkat lunak perantara yang membantu komunikasi dan koordinasi antarkomponen dalam sistem terdistribusi.

Middleware dapat menyediakan layanan seperti pertukaran pesan, autentikasi, pengelolaan koneksi, dan komunikasi antaraplikasi.

### D. Data dan Penyimpanan

Data merupakan informasi yang diproses dan dikelola oleh sistem. Dalam sistem terdistribusi, data dapat disimpan pada beberapa server atau lokasi yang berbeda.

Penyimpanan data dapat menggunakan mekanisme replikasi maupun pembagian data agar pengelolaan informasi menjadi lebih efisien.

### E. Proses dan Layanan

Proses merupakan program yang dijalankan pada node tertentu untuk melaksanakan tugas. Sementara itu, layanan menyediakan fungsi yang dapat digunakan oleh komponen atau pengguna lainnya.

## 2.3 Karakteristik Dasar Sistem Terdistribusi

Berdasarkan materi perkuliahan, sistem terdistribusi mempunyai beberapa karakteristik penting.

1. **Komponen independen:** setiap komputer dapat bekerja secara mandiri.
2. **Komunikasi melalui jaringan:** setiap komponen berkomunikasi menggunakan jaringan komputer.
3. **Transparansi lokasi:** pengguna tidak harus mengetahui lokasi fisik sumber daya.
4. **Transparansi akses:** perbedaan cara mengakses sumber daya disembunyikan dari pengguna.
5. **Transparansi replikasi:** pengguna tidak harus mengetahui bahwa suatu data memiliki beberapa salinan.
6. **Transparansi kegagalan:** sistem berusaha menyembunyikan atau menangani kegagalan komponen agar layanan tetap dapat digunakan.

## 2.4 Contoh Sistem Terdistribusi

Salah satu contoh sistem terdistribusi adalah aplikasi layanan digital yang memiliki beberapa layanan terpisah.

Misalnya, sebuah aplikasi belanja online mempunyai:

- Account Service untuk mengelola akun pengguna.
- Inventory Service untuk mengelola persediaan barang.
- Shipping Service untuk mengelola pengiriman.
- Account Database untuk menyimpan data akun.
- Inventory Database untuk menyimpan data persediaan.
- Shipping Database untuk menyimpan data pengiriman.

Pengguna dapat mengakses aplikasi melalui perangkat mobile atau browser. Permintaan kemudian diteruskan melalui API Gateway menuju layanan yang sesuai.

Setiap layanan menjalankan fungsi tertentu dan dapat berkomunikasi dengan layanan lainnya melalui jaringan.

## 2.5 Kesimpulan

Sistem terdistribusi merupakan sistem yang terdiri atas beberapa komputer independen yang saling bekerja sama melalui jaringan untuk menyediakan layanan terpadu. Setiap komponen memiliki fungsi masing-masing, tetapi tetap dapat berkomunikasi dan bertukar informasi.

Konsep ini memungkinkan pengembangan sistem yang mampu menangani pekerjaan dalam jumlah besar, mendukung pembagian sumber daya, dan meningkatkan kemampuan layanan digital.

---

# 3. ARSITEKTUR SISTEM DASAR

## 3.1 Pengertian Arsitektur Sistem

Arsitektur sistem merupakan rancangan atau struktur yang menggambarkan bagaimana komponen-komponen dalam suatu sistem disusun, saling terhubung, dan berkomunikasi untuk menjalankan fungsi tertentu.

Dalam sistem terdistribusi, arsitektur sistem menjelaskan hubungan antara komputer, server, client, dan komponen lainnya yang bekerja sama melalui jaringan.

Berdasarkan materi perkuliahan, terdapat tiga bentuk arsitektur dasar yang dibahas, yaitu Client-Server, Peer-to-Peer (P2P), dan Hybrid.

## 3.2 Arsitektur Client-Server

### A. Pengertian

Client-Server merupakan arsitektur jaringan komputer yang membagi peran antara client dan server.

Client merupakan perangkat atau aplikasi yang mengirimkan permintaan layanan, sedangkan server merupakan perangkat yang menerima permintaan, memprosesnya, dan mengirimkan hasil kepada client.

Komunikasi antara client dan server biasanya dilakukan melalui jaringan komputer atau internet.

### B. Cara Kerja

Proses kerja arsitektur Client-Server adalah sebagai berikut:

1. Client mengirimkan permintaan kepada server.
2. Server menerima permintaan yang dikirimkan client.
3. Server memproses permintaan tersebut.
4. Jika diperlukan, server mengambil atau mengolah data dari database.
5. Server mengirimkan hasil pemrosesan kepada client.
6. Client menampilkan hasil yang diterima kepada pengguna.

### C. Contoh Penerapan

- Website yang diakses melalui browser.
- Aplikasi perbankan yang berkomunikasi dengan server bank.
- Sistem akademik yang mengambil data mahasiswa dari server.
- Aplikasi email yang mengakses layanan penyimpanan pesan.

### D. Kelebihan

1. Pengelolaan data dan layanan dapat dilakukan secara terpusat.
2. Pengaturan keamanan lebih mudah dikoordinasikan.
3. Pemeliharaan sistem dapat dilakukan melalui server.
4. Client tidak harus memiliki seluruh sumber daya pemrosesan.

### E. Kekurangan

1. Server dapat menjadi titik kegagalan jika tidak memiliki redundansi.
2. Beban server dapat meningkat ketika jumlah client bertambah.
3. Ketergantungan terhadap server cukup tinggi.
4. Gangguan jaringan dapat menghambat komunikasi client dan server.

## 3.3 Arsitektur Peer-to-Peer (P2P)

### A. Pengertian

Peer-to-Peer atau P2P merupakan arsitektur jaringan yang memungkinkan setiap perangkat atau peer berkomunikasi dan berbagi sumber daya secara langsung dengan perangkat lainnya.

Dalam arsitektur ini, setiap peer dapat berperan sebagai client sekaligus server. Artinya, perangkat dapat meminta sumber daya dari peer lain sekaligus menyediakan sumber daya untuk digunakan oleh perangkat lain.

Tidak semua komunikasi harus melalui server pusat.

### B. Cara Kerja

1. Setiap perangkat bergabung ke dalam jaringan P2P.
2. Perangkat melakukan proses pencarian peer lain.
3. Peer saling bertukar informasi mengenai sumber daya yang tersedia.
4. Ketika membutuhkan data, sebuah peer dapat meminta data dari peer lain.
5. Peer yang memiliki data akan mengirimkannya secara langsung.
6. Proses pertukaran sumber daya dapat berlangsung antara banyak peer.

### C. Contoh Penerapan

**BitTorrent**

BitTorrent merupakan teknologi berbagi file yang menggunakan jaringan P2P. File dibagi menjadi beberapa bagian sehingga pengguna dapat mengunduh bagian-bagian file dari beberapa peer secara bersamaan.

**Blockchain**

Jaringan blockchain menggunakan komunikasi antarnode untuk menyebarkan transaksi dan informasi blok. Setiap node dapat berpartisipasi sesuai aturan jaringan.

### D. Kelebihan

1. Tidak selalu bergantung pada satu server pusat.
2. Sumber daya dapat dibagikan secara langsung.
3. Kapasitas jaringan dapat meningkat seiring bertambahnya peer yang berpartisipasi.
4. Dapat mengurangi beban pada server pusat.

### E. Kekurangan

1. Pengelolaan jaringan lebih kompleks.
2. Ketersediaan sumber daya bergantung pada peer yang aktif.
3. Keamanan dan kepercayaan antarpeer menjadi tantangan.
4. Kinerja dapat berubah sesuai jumlah dan kondisi peer.

## 3.4 Arsitektur Hybrid

### A. Pengertian

Arsitektur Hybrid merupakan kombinasi antara pendekatan Client-Server dan Peer-to-Peer.

Dalam arsitektur ini, sebagian fungsi sistem masih menggunakan server pusat, sementara komunikasi atau pertukaran sumber daya tertentu dapat dilakukan secara langsung antarpengguna atau peer.

Arsitektur hybrid berusaha menggabungkan kemudahan pengelolaan dari Client-Server dengan kemampuan berbagi sumber daya dari P2P.

### B. Cara Kerja

1. Pengguna terhubung dengan server atau node pengelola.
2. Server membantu proses pencarian, pengaturan, atau koordinasi antarpeer.
3. Setelah peer ditemukan, komunikasi atau pertukaran data dapat dilakukan secara langsung.
4. Server tetap dapat digunakan untuk fungsi tertentu seperti autentikasi dan pengelolaan informasi.
5. Peer saling berbagi sumber daya sesuai kebutuhan sistem.

### C. Contoh Penerapan

Materi perkuliahan menampilkan ilustrasi sistem hybrid yang menggabungkan koneksi Client-Server dengan koneksi Peer-to-Peer.

Contoh penerapan pendekatan hybrid dapat ditemukan pada sistem komunikasi dan berbagi file yang menggunakan server untuk koordinasi, tetapi memanfaatkan koneksi langsung antarpengguna untuk pertukaran data tertentu.

### D. Kelebihan

1. Menggabungkan keunggulan arsitektur Client-Server dan P2P.
2. Dapat meningkatkan efisiensi pertukaran sumber daya.
3. Pengelolaan dan koordinasi dapat dibantu oleh server.
4. Sebagian aktivitas dapat dilakukan secara langsung antarnode.

### E. Kekurangan

1. Desain sistem lebih kompleks.
2. Membutuhkan pengelolaan komunikasi yang baik.
3. Ketergantungan terhadap server masih ada pada fungsi tertentu.
4. Pengaturan keamanan dan koordinasi membutuhkan perhatian khusus.

## 3.5 Perbandingan Arsitektur Dasar

| Aspek | Client-Server | Peer-to-Peer | Hybrid |
|---|---|---|---|
| Struktur | Client dan server | Peer saling terhubung | Gabungan keduanya |
| Pengendalian | Server | Antarpeer | Server dan peer |
| Komunikasi | Melalui server | Langsung antarpihak | Melalui server dan langsung |
| Ketergantungan server | Tinggi | Tidak selalu ada | Sebagian |
| Pengelolaan | Relatif terpusat | Lebih tersebar | Kombinasi |
| Contoh | Website | BitTorrent | Sistem berbagi data hybrid |

## 3.6 Kesimpulan

Arsitektur sistem merupakan dasar dalam merancang sistem terdistribusi. Client-Server mengutamakan pembagian peran antara client dan server, Peer-to-Peer memungkinkan perangkat saling berbagi sumber daya secara langsung, sedangkan Hybrid menggabungkan kedua pendekatan tersebut.

Pemilihan arsitektur harus disesuaikan dengan kebutuhan sistem, jumlah pengguna, karakteristik komunikasi, keamanan, serta pengelolaan sumber daya.

---

# 4. KARAKTERISTIK SISTEM TERDISTRIBUSI

## 4.1 Pengertian

Karakteristik sistem terdistribusi merupakan sifat atau kemampuan yang membedakannya dari sistem komputer biasa. Karakteristik tersebut memungkinkan beberapa komputer bekerja sama melalui jaringan untuk menyediakan layanan yang terlihat sebagai satu kesatuan.

Berdasarkan materi perkuliahan, terdapat lima karakteristik utama sistem terdistribusi, yaitu transparansi lokasi, skalabilitas, fault tolerance, kinerja tinggi, dan heterogenitas.

## 4.2 Transparansi Lokasi (Location Transparency)

Transparansi lokasi merupakan kemampuan sistem untuk menyembunyikan lokasi fisik suatu sumber daya dari pengguna.

Dalam sistem terdistribusi, data atau layanan dapat berada pada server yang berbeda lokasi. Namun, pengguna tetap dapat mengaksesnya tanpa harus mengetahui lokasi penyimpanan atau pemrosesannya.

**Contoh:**

Ketika seseorang membuka layanan penyimpanan cloud, pengguna hanya perlu mengakses akun dan file yang tersedia tanpa harus mengetahui server fisik tempat file tersebut disimpan.

**Manfaat:**

1. Mempermudah akses terhadap sumber daya.
2. Mengurangi ketergantungan pengguna terhadap lokasi fisik server.
3. Memberikan pengalaman penggunaan yang lebih sederhana.

## 4.3 Skalabilitas (Scalability)

Skalabilitas merupakan kemampuan sistem untuk meningkatkan kapasitas dalam menghadapi pertumbuhan jumlah pengguna, data, dan beban kerja.

Sistem terdistribusi dapat meningkatkan kapasitas dengan menambahkan sumber daya komputasi atau memperbesar kemampuan perangkat yang sudah digunakan.

**Contoh:**

Sebuah platform pembelajaran online menambahkan beberapa server ketika jumlah mahasiswa yang mengakses sistem meningkat pada saat ujian berlangsung.

**Manfaat:**

1. Mendukung pertumbuhan pengguna.
2. Mengurangi risiko kelebihan beban.
3. Mempermudah pengembangan kapasitas sistem.
4. Mendukung kebutuhan layanan dalam skala besar.

## 4.4 Fault Tolerance

Fault tolerance merupakan kemampuan sistem untuk tetap beroperasi meskipun sebagian komponen mengalami kegagalan.

Kegagalan dapat terjadi pada server, jaringan, aplikasi, maupun media penyimpanan.

Sistem dapat menerapkan replikasi, redundansi, dan mekanisme pemulihan untuk mengurangi dampak kegagalan tersebut.

**Contoh:**

Apabila sebuah server penyimpanan mengalami kerusakan, sistem dapat menggunakan salinan data yang tersedia pada server lain.

**Manfaat:**

1. Meningkatkan keandalan sistem.
2. Mengurangi dampak kegagalan komponen.
3. Menjaga ketersediaan layanan.
4. Mendukung keberlangsungan operasional.

## 4.5 Kinerja Tinggi (High Performance)

Kinerja tinggi merupakan kemampuan sistem dalam memproses permintaan dan menyelesaikan pekerjaan secara efisien.

Dalam sistem terdistribusi, beberapa komputer dapat bekerja secara bersamaan untuk membagi beban pemrosesan.

Pendekatan tersebut dapat meningkatkan kapasitas pemrosesan dibandingkan jika seluruh pekerjaan hanya ditangani oleh satu komputer.

**Contoh:**

Sistem pengolahan data berskala besar membagi proses komputasi ke beberapa server agar pekerjaan dapat dilakukan secara paralel.

**Manfaat:**

1. Meningkatkan kemampuan pemrosesan.
2. Mempercepat penyelesaian pekerjaan tertentu.
3. Membantu menangani permintaan dalam jumlah besar.

## 4.6 Heterogenitas (Heterogeneity)

Heterogenitas merupakan kondisi ketika sistem terdistribusi terdiri atas berbagai jenis perangkat keras, perangkat lunak, sistem operasi, jaringan, dan teknologi yang berbeda.

Komponen-komponen tersebut tetap harus mampu berkomunikasi dan bekerja sama meskipun memiliki karakteristik yang tidak sama.

**Contoh:**

Sebuah aplikasi dapat diakses melalui perangkat Android, iOS, dan komputer Windows. Meskipun perangkat menggunakan sistem operasi yang berbeda, aplikasi tetap dapat berkomunikasi dengan layanan server yang sama.

**Manfaat:**

1. Memungkinkan integrasi berbagai teknologi.
2. Memberikan fleksibilitas dalam pemilihan perangkat.
3. Mendukung penggunaan berbagai platform.
4. Mempermudah pengembangan sistem lintas lingkungan.

## 4.7 Kesimpulan

Sistem terdistribusi memiliki karakteristik yang mendukung pengoperasian sistem dalam lingkungan jaringan yang kompleks. Transparansi lokasi mempermudah akses sumber daya, skalabilitas memungkinkan peningkatan kapasitas, fault tolerance menjaga sistem ketika terjadi kegagalan, kinerja tinggi mendukung pemrosesan yang efisien, dan heterogenitas memungkinkan berbagai perangkat serta teknologi bekerja sama.

Kelima karakteristik tersebut menjadi dasar dalam membangun sistem yang andal, fleksibel, dan mampu memenuhi kebutuhan teknologi modern.

---

# 5. PENGERTIAN SISTEM TERDESENTRALISASI

## 5.1 Definisi Sistem Terdesentralisasi

Sistem terdesentralisasi (Decentralized System) merupakan sistem yang pengendalian, pengelolaan, atau pengambilan keputusannya didistribusikan kepada beberapa pihak atau node, bukan hanya bergantung pada satu pusat kendali.

Dalam sistem terdesentralisasi, beberapa node dapat berpartisipasi dalam pengelolaan jaringan dan pengambilan keputusan berdasarkan aturan yang telah disepakati.

Konsep ini bertujuan mengurangi ketergantungan terhadap satu pihak atau satu titik pengendalian sehingga sistem menjadi lebih tersebar.

## 5.2 Perbedaan Sentralisasi dan Desentralisasi

### A. Sistem Sentralisasi (Centralized System)

Sistem sentralisasi merupakan sistem yang pengendalian dan pengambilan keputusan utamanya berada pada satu pusat atau otoritas tertentu.

Pusat tersebut memiliki wewenang untuk mengatur aktivitas sistem dan mengelola sumber daya yang digunakan.

**Contoh:**

Sistem penyimpanan data yang seluruh pengelolaannya bergantung pada satu server pusat.

**Karakteristik:**

1. Memiliki satu pusat pengendalian.
2. Pengambilan keputusan dilakukan oleh otoritas pusat.
3. Pengelolaan sistem relatif lebih terpusat.
4. Memiliki risiko single point of failure apabila tidak tersedia mekanisme cadangan.

### B. Sistem Terdesentralisasi (Decentralized System)

Sistem terdesentralisasi membagi kendali kepada beberapa node atau pihak yang berpartisipasi dalam jaringan.

Keputusan dapat dilakukan melalui mekanisme koordinasi atau konsensus sesuai aturan yang berlaku.

**Karakteristik:**

1. Tidak bergantung pada satu pusat pengendalian.
2. Kendali dibagikan kepada beberapa node.
3. Keputusan dapat melibatkan beberapa pihak.
4. Mengurangi ketergantungan terhadap satu titik kegagalan.
5. Membutuhkan mekanisme koordinasi dan kesepakatan.

## 5.3 Konsep Single Point of Failure

Single Point of Failure (SPOF) merupakan kondisi ketika satu komponen menjadi titik kritis yang apabila mengalami kegagalan dapat menyebabkan seluruh atau sebagian besar sistem berhenti beroperasi.

Dalam sistem yang sangat terpusat, server pusat dapat menjadi SPOF apabila tidak dilengkapi dengan sistem cadangan.

Sistem terdesentralisasi berusaha mengurangi risiko tersebut dengan membagikan kendali dan fungsi kepada beberapa node.

Namun, desentralisasi tidak secara otomatis menghilangkan seluruh kemungkinan kegagalan. Sistem tetap membutuhkan mekanisme keamanan, koordinasi, dan pemulihan.

## 5.4 Keputusan Kolektif melalui Konsensus

Konsensus merupakan mekanisme yang digunakan oleh beberapa node untuk mencapai kesepakatan mengenai suatu kondisi atau keputusan dalam jaringan.

Pada sistem terdesentralisasi, konsensus menjadi penting karena tidak terdapat satu otoritas pusat yang selalu menentukan seluruh keputusan.

Sebagai contoh, dalam jaringan blockchain, node tertentu berpartisipasi dalam proses validasi transaksi dan penyepakatan kondisi blockchain berdasarkan protokol konsensus yang digunakan.

Beberapa mekanisme konsensus yang dikenal antara lain:

1. **Proof of Work (PoW)**

   Mekanisme konsensus yang melibatkan proses komputasi untuk membuktikan bahwa suatu pekerjaan telah dilakukan sesuai ketentuan jaringan.

2. **Proof of Stake (PoS)**

   Mekanisme konsensus yang menggunakan kepemilikan atau penguncian aset tertentu sebagai salah satu dasar partisipasi dalam proses validasi.

Kedua mekanisme tersebut memiliki cara kerja dan kebutuhan sumber daya yang berbeda.

## 5.5 Contoh Sistem Terdesentralisasi

Berdasarkan materi perkuliahan, contoh sistem terdesentralisasi meliputi:

1. Blockchain.
2. DNS (Domain Name System).
3. BitTorrent.

Ketiga contoh tersebut menunjukkan penerapan pembagian fungsi dan pengelolaan dalam jaringan yang melibatkan banyak komponen.

## 5.6 Kesimpulan

Sistem terdesentralisasi merupakan sistem yang membagi pengendalian kepada beberapa pihak atau node sehingga tidak seluruh keputusan bergantung pada satu pusat.

Konsep ini mendukung pembagian wewenang, partisipasi kolektif, dan pengurangan risiko ketergantungan terhadap satu titik pengendalian.

---

# 6. SISTEM TERDISTRIBUSI VS SISTEM TERDESENTRALISASI

## 6.1 Pengertian Perbedaan Keduanya

Sistem terdistribusi dan sistem terdesentralisasi merupakan dua konsep yang saling berkaitan, tetapi memiliki fokus yang berbeda.

Sistem terdistribusi menekankan pada pembagian beban kerja, pemrosesan data, dan sumber daya ke beberapa komputer yang saling terhubung.

Sementara itu, sistem terdesentralisasi menekankan pada pembagian kendali, wewenang, dan pengambilan keputusan kepada beberapa pihak atau node.

Dengan demikian, suatu sistem dapat memiliki komponen yang tersebar secara fisik, tetapi pengendaliannya masih berada pada satu pusat. Sebaliknya, sistem terdesentralisasi dapat membagikan pengendalian kepada banyak pihak.

## 6.2 Perbedaan Utama

| Aspek | Sistem Terdistribusi | Sistem Terdesentralisasi |
|---|---|---|
| Fokus utama | Pembagian beban kerja | Pembagian kendali |
| Tujuan | Efisiensi pemrosesan dan sumber daya | Mengurangi ketergantungan pada pusat |
| Struktur | Beberapa komputer atau node | Beberapa pihak atau node pengendali |
| Pengelolaan | Dapat tetap terpusat | Kendali dibagikan |
| Komunikasi | Melalui jaringan | Melalui jaringan dan koordinasi |
| Pengambilan keputusan | Dapat diatur oleh pusat | Dapat dilakukan secara kolektif |
| Contoh | Google File System, MinIO | Blockchain |

## 6.3 Sistem Terdistribusi

Sistem terdistribusi berfokus pada bagaimana pekerjaan dibagi ke beberapa komputer atau server.

Contohnya adalah Google File System (GFS) yang dirancang untuk mendukung penyimpanan dan pengelolaan data dalam skala besar.

Dalam pendekatan tersebut, data dan proses pengelolaannya dapat melibatkan beberapa komputer sehingga tidak seluruh pekerjaan harus ditangani oleh satu perangkat.

Materi perkuliahan juga menyebutkan MinIO Object Storage sebagai contoh sistem yang berkaitan dengan distribusi penyimpanan objek.

## 6.4 Sistem Terdesentralisasi

Sistem terdesentralisasi berfokus pada pembagian kontrol atau pengendalian kepada beberapa node.

Contoh utamanya adalah blockchain. Dalam jaringan blockchain, transaksi dan informasi blok dapat divalidasi oleh node berdasarkan aturan protokol yang digunakan.

Tidak seluruh proses pengambilan keputusan harus bergantung pada satu otoritas pusat.

## 6.5 Hubungan antara Keduanya

Sistem terdistribusi dan terdesentralisasi dapat diterapkan secara bersamaan.

Sebuah jaringan blockchain, misalnya, memiliki banyak node yang tersebar dan saling berkomunikasi. Hal tersebut menunjukkan karakteristik distribusi sekaligus pembagian kendali melalui mekanisme konsensus.

Namun, perlu dipahami bahwa tidak semua sistem terdistribusi bersifat terdesentralisasi. Sebuah aplikasi dapat menggunakan banyak server yang tersebar, tetapi tetap dikendalikan oleh satu organisasi.

## 6.6 Kesimpulan

Perbedaan mendasar antara sistem terdistribusi dan sistem terdesentralisasi terletak pada fokus penerapannya. Sistem terdistribusi menekankan pembagian beban kerja, sedangkan sistem terdesentralisasi menekankan pembagian kontrol.

Keduanya dapat saling melengkapi dalam pembangunan infrastruktur teknologi modern.

---

# 7. STUDI KASUS SISTEM TERDISTRIBUSI

## 7.1 Pengertian

Studi kasus sistem terdistribusi merupakan pembahasan mengenai penerapan konsep distribusi pada teknologi atau layanan nyata.

Sistem terdistribusi digunakan untuk mendukung pemrosesan data, penyimpanan informasi, pertukaran pesan, dan penyediaan layanan kepada banyak pengguna.

Berdasarkan materi perkuliahan, beberapa contoh penerapannya adalah Google File System, HDFS, Apache Kafka, Apache Pulsar, Netflix, Twitch, YouTube, Instagram, Threads, Facebook, dan TikTok.

## 7.2 Google File System (GFS) dan HDFS

Google File System (GFS) merupakan sistem file terdistribusi yang dirancang untuk mengelola penyimpanan data dalam skala besar.

Hadoop Distributed File System (HDFS) merupakan sistem file terdistribusi yang menjadi bagian dari ekosistem Apache Hadoop.

Keduanya mendukung penyimpanan data dengan melibatkan beberapa mesin atau node.

### Cara Kerja Secara Umum

1. Data yang akan disimpan dibagi menjadi beberapa bagian.
2. Bagian data ditempatkan pada beberapa node penyimpanan.
3. Sistem mengelola lokasi dan informasi data.
4. Pengguna atau aplikasi mengakses data melalui mekanisme yang disediakan.
5. Data dapat direplikasi untuk mendukung toleransi terhadap kegagalan.

### Manfaat

- Mendukung penyimpanan data berskala besar.
- Membagi penyimpanan ke beberapa perangkat.
- Mendukung pengolahan data terdistribusi.
- Mengurangi ketergantungan terhadap satu media penyimpanan.

## 7.3 Apache Kafka dan Apache Pulsar

Apache Kafka dan Apache Pulsar merupakan teknologi yang digunakan untuk mendukung messaging dan data streaming.

Messaging merupakan mekanisme pertukaran pesan antarkomponen sistem, sedangkan streaming merupakan proses pengiriman dan pemrosesan data secara berkelanjutan.

### Cara Kerja Secara Umum

1. Aplikasi pengirim menghasilkan pesan atau data.
2. Pesan dikirimkan ke sistem messaging.
3. Sistem mengelola penyimpanan dan distribusi pesan.
4. Aplikasi penerima mengambil atau memproses pesan.
5. Data dapat digunakan untuk analisis atau pemrosesan lanjutan.

### Contoh Penerapan

Pada aplikasi e-commerce, ketika pengguna melakukan pembelian, sistem dapat menghasilkan beberapa peristiwa seperti pembayaran, pembaruan stok, dan pengiriman.

Pesan-pesan tersebut dapat diproses oleh layanan yang berbeda melalui sistem messaging.

### Manfaat

- Mendukung komunikasi antarlayanan.
- Memungkinkan pemrosesan data secara berkelanjutan.
- Membantu pemisahan tugas antarbagian aplikasi.
- Mendukung sistem yang memiliki banyak komponen.

## 7.4 Netflix dan Twitch

Netflix dan Twitch merupakan contoh layanan digital yang membutuhkan infrastruktur terdistribusi untuk mendukung akses pengguna dalam jumlah besar.

Netflix menyediakan layanan streaming film dan serial, sedangkan Twitch menyediakan layanan streaming konten video secara langsung.

### Penerapan Sistem Terdistribusi

Kedua layanan tersebut membutuhkan kemampuan untuk:

1. Menyediakan konten kepada banyak pengguna.
2. Mengelola permintaan secara bersamaan.
3. Mengirimkan data melalui jaringan.
4. Menangani perbedaan kondisi jaringan pengguna.
5. Menjaga ketersediaan layanan.

Sistem terdistribusi membantu layanan tersebut dalam pengelolaan sumber daya dan penyediaan konten pada skala besar.

## 7.5 YouTube

YouTube merupakan platform berbagi video yang melibatkan penyimpanan, pemrosesan, dan distribusi konten kepada pengguna di berbagai wilayah.

Ketika pengguna mengunggah video, sistem harus menangani proses penyimpanan, pemrosesan video, pengelolaan informasi, dan penyediaan konten kepada pengguna lainnya.

### Penerapan Sistem Terdistribusi

- Penyimpanan video dalam infrastruktur berskala besar.
- Pemrosesan dan pengelolaan konten.
- Distribusi video kepada pengguna.
- Pengelolaan permintaan akses secara bersamaan.

## 7.6 Instagram, Threads, Facebook, dan TikTok

Platform media sosial tersebut melayani aktivitas pengguna dalam jumlah besar, seperti mengunggah konten, memberikan komentar, menyukai postingan, mengirim pesan, dan mengikuti akun lainnya.

Aktivitas tersebut membutuhkan sistem yang mampu mengelola data dan permintaan secara bersamaan.

### Penerapan Sistem Terdistribusi

1. Pengelolaan akun pengguna.
2. Penyimpanan foto dan video.
3. Pemrosesan interaksi pengguna.
4. Pengiriman notifikasi.
5. Penyediaan konten berdasarkan permintaan pengguna.

## 7.7 Kesimpulan

Berbagai layanan digital modern menggunakan pendekatan sistem terdistribusi untuk mengelola data dan memberikan layanan kepada pengguna dalam skala besar.

Google File System dan HDFS berfokus pada penyimpanan data, Kafka dan Pulsar mendukung messaging serta streaming, sedangkan Netflix, Twitch, YouTube, dan berbagai media sosial memanfaatkan infrastruktur terdistribusi untuk menyediakan layanan digital.

---

# 8. STUDI KASUS SISTEM TERDESENTRALISASI

## 8.1 Pengertian

Studi kasus sistem terdesentralisasi membahas penerapan pembagian kendali dan pengelolaan jaringan kepada beberapa node atau pihak.

Dalam sistem ini, pengendalian tidak sepenuhnya bergantung pada satu pusat. Beberapa node dapat berpartisipasi sesuai aturan dan mekanisme yang berlaku.

Berdasarkan materi perkuliahan, contoh sistem terdesentralisasi meliputi blockchain, DNS, dan BitTorrent.

## 8.2 Blockchain

Blockchain merupakan teknologi pencatatan data digital yang disusun dalam bentuk blok dan saling terhubung menggunakan mekanisme kriptografi.

Dalam jaringan blockchain, beberapa node dapat menyimpan salinan data transaksi dan berpartisipasi dalam proses validasi berdasarkan protokol yang digunakan.

### Cara Kerja Secara Umum

1. Pengguna membuat transaksi.
2. Transaksi disebarkan ke jaringan.
3. Node melakukan pemeriksaan dan validasi sesuai aturan protokol.
4. Transaksi yang memenuhi ketentuan diproses melalui mekanisme konsensus.
5. Data transaksi dimasukkan ke dalam blok.
6. Blok yang diterima menjadi bagian dari rangkaian blockchain.

### Contoh Blockchain

Beberapa blockchain yang disebutkan dalam materi perkuliahan adalah:

- Bitcoin.
- Ethereum.
- Algorand.
- Sui.
- Near.
- Aptos.

### Kelebihan

1. Pembagian kendali kepada beberapa node.
2. Memiliki mekanisme validasi transaksi.
3. Transparansi data sesuai karakteristik jaringan.
4. Mengurangi ketergantungan terhadap satu otoritas pusat.

### Tantangan

1. Membutuhkan mekanisme konsensus.
2. Menghadapi tantangan skalabilitas.
3. Memerlukan perlindungan terhadap serangan jaringan.
4. Membutuhkan tata kelola protokol yang baik.

## 8.3 DNS (Domain Name System)

DNS merupakan sistem yang digunakan untuk menerjemahkan nama domain menjadi alamat IP agar perangkat dapat menemukan server tujuan di jaringan internet.

Contohnya, ketika pengguna mengetik nama domain suatu website, DNS membantu menemukan alamat IP yang sesuai.

### Cara Kerja Secara Umum

1. Pengguna memasukkan nama domain pada browser.
2. Perangkat melakukan permintaan pencarian DNS.
3. Resolver mencari informasi alamat IP yang sesuai.
4. Jika diperlukan, resolver melakukan pencarian melalui server DNS lainnya.
5. Alamat IP dikembalikan kepada perangkat pengguna.
6. Browser menggunakan alamat tersebut untuk menghubungi server tujuan.

### Hubungan dengan Desentralisasi

DNS memiliki struktur pengelolaan informasi yang bersifat hierarkis dan melibatkan berbagai server serta pihak pengelola.

Dengan demikian, pengelolaan sistem nama domain tidak dilakukan hanya oleh satu komputer pusat, melainkan melibatkan beberapa komponen dalam hierarki DNS.

## 8.4 BitTorrent

BitTorrent merupakan protokol berbagi file yang menggunakan pendekatan Peer-to-Peer.

Pengguna dapat mengunduh bagian-bagian file dari beberapa peer yang memiliki bagian data tersebut.

### Cara Kerja

1. Pengguna membuka file torrent atau menggunakan magnet link.
2. Aplikasi BitTorrent mencari peer yang menyediakan bagian file.
3. File dibagi menjadi beberapa bagian atau pieces.
4. Pengguna mengunduh bagian file dari peer yang berbeda.
5. Bagian yang berhasil diunduh diperiksa dan digabungkan.
6. Setelah lengkap, file dapat digunakan oleh pengguna.
7. Pengguna juga dapat membagikan bagian file kepada peer lainnya.

### Kelebihan

- Mengurangi ketergantungan pada satu server.
- Memungkinkan pertukaran file secara langsung.
- Beban distribusi file dapat dibagi kepada banyak peer.
- Efisien untuk distribusi file berukuran besar.

### Kekurangan

- Kecepatan bergantung pada ketersediaan peer.
- Kualitas koneksi jaringan memengaruhi proses transfer.
- Pengguna harus memperhatikan keamanan dan keaslian file.
- Pengelolaan jaringan dapat menjadi kompleks.

## 8.5 Perbandingan Contoh Sistem Terdesentralisasi

| Sistem | Fungsi Utama | Karakteristik |
|---|---|---|
| Blockchain | Pencatatan dan validasi transaksi | Melibatkan node dan konsensus |
| DNS | Penerjemahan nama domain | Pengelolaan hierarkis dan tersebar |
| BitTorrent | Berbagi file | Pertukaran data antarpengguna |

## 8.6 Kesimpulan

Blockchain, DNS, dan BitTorrent merupakan contoh teknologi yang memperlihatkan pengelolaan jaringan dengan melibatkan beberapa komponen atau pihak.

Blockchain menggunakan mekanisme konsensus untuk validasi transaksi, DNS melibatkan hierarki server dalam pengelolaan nama domain, sedangkan BitTorrent memungkinkan pertukaran file secara langsung antarpengguna.

Ketiga contoh tersebut menunjukkan bahwa pembagian fungsi dan pengelolaan jaringan dapat dilakukan melalui berbagai pendekatan.

---

# 9. CAP THEOREM

## 9.1 Pengertian CAP Theorem

CAP Theorem merupakan teori dalam sistem terdistribusi yang menjelaskan hubungan antara tiga karakteristik utama sistem penyimpanan data terdistribusi, yaitu Consistency, Availability, dan Partition Tolerance.

CAP Theorem sering disebut sebagai Brewer's Theorem dan diperkenalkan oleh Eric Brewer pada tahun 2000.

Teori ini menjelaskan bahwa ketika terjadi network partition, sebuah sistem penyimpanan data terdistribusi harus menghadapi pilihan antara mempertahankan konsistensi data atau tetap memberikan ketersediaan layanan.

Ketiga komponen CAP adalah:

1. Consistency.
2. Availability.
3. Partition Tolerance.

## 9.2 Consistency (Konsistensi)

Consistency merupakan kondisi ketika setiap operasi pembacaan data mengembalikan hasil penulisan terbaru atau menghasilkan error.

Artinya, sistem berusaha memastikan bahwa pengguna mendapatkan informasi yang konsisten meskipun data dikelola oleh beberapa node.

**Contoh:**

Pada sistem perbankan, ketika saldo rekening mengalami perubahan akibat transaksi, sistem harus menjaga agar pembacaan saldo tidak menghasilkan informasi yang bertentangan dengan transaksi yang sudah dikonfirmasi.

## 9.3 Availability (Ketersediaan)

Availability merupakan kemampuan sistem untuk memberikan respons terhadap setiap permintaan yang diterima oleh node yang tidak mengalami kegagalan.

Respons tersebut harus berupa hasil yang tidak error, meskipun data yang dikembalikan belum tentu merupakan data paling terbaru.

**Contoh:**

Pada layanan media sosial, pengguna tetap dapat membuka halaman dan melihat informasi meskipun sebagian pembaruan data belum tersinkronisasi ke seluruh server.

## 9.4 Partition Tolerance (Toleransi Partisi)

Partition Tolerance merupakan kemampuan sistem untuk tetap beroperasi meskipun komunikasi antar-node mengalami gangguan, terputus, atau terfragmentasi.

Network partition terjadi ketika sebagian node tidak dapat berkomunikasi dengan node lainnya akibat gangguan jaringan.

**Contoh:**

Sebuah sistem memiliki beberapa server di lokasi yang berbeda. Ketika koneksi jaringan antara dua lokasi terputus, sistem harus menentukan bagaimana permintaan pengguna akan ditangani.

## 9.5 Hubungan Ketiga Komponen CAP

Ketiga komponen CAP memiliki hubungan yang saling berkaitan.

Dalam kondisi normal, sistem dapat beroperasi dengan menjaga konsistensi dan ketersediaan. Namun, ketika terjadi network partition, sistem harus menentukan prioritas antara Consistency dan Availability.

Dengan kata lain, pada kondisi partisi jaringan, sistem tidak dapat menjamin Consistency dan Availability secara penuh pada saat yang bersamaan.

## 9.6 Pilihan AP dan CP

### A. AP (Availability + Partition Tolerance)

AP merupakan pendekatan yang mengutamakan ketersediaan layanan dan toleransi terhadap partisi jaringan.

Ketika terjadi gangguan komunikasi antarnode, sistem tetap berusaha memberikan respons terhadap permintaan pengguna.

Konsekuensinya, data yang diterima pengguna mungkin belum sepenuhnya sinkron dengan data pada node lainnya.

**Karakteristik:**

1. Tetap memberikan respons ketika terjadi partisi jaringan.
2. Mengutamakan ketersediaan layanan.
3. Memungkinkan perbedaan data sementara.
4. Dapat melakukan sinkronisasi setelah koneksi pulih.

### B. CP (Consistency + Partition Tolerance)

CP merupakan pendekatan yang mengutamakan konsistensi data dan toleransi terhadap partisi jaringan.

Ketika terjadi gangguan komunikasi, sistem dapat menolak atau menunda permintaan tertentu apabila konsistensi tidak dapat dijamin.

**Karakteristik:**

1. Mengutamakan konsistensi data.
2. Tetap mempertimbangkan toleransi terhadap partisi.
3. Dapat membatasi permintaan ketika terjadi gangguan jaringan.
4. Mengurangi risiko memberikan data yang tidak konsisten.

### C. Perbandingan AP dan CP

| Aspek | AP | CP |
|---|---|---|
| Prioritas | Availability | Consistency |
| Toleransi partisi | Ya | Ya |
| Respons saat partisi | Tetap berusaha melayani | Dapat menolak atau menunda permintaan |
| Risiko | Data sementara tidak sinkron | Layanan sementara tidak tersedia |
| Fokus | Ketersediaan | Konsistensi |

Materi perkuliahan mencantumkan MongoDB sebagai contoh AP dan Apache Cassandra sebagai contoh CP. Klasifikasi tersebut perlu dipahami sebagai ilustrasi dalam materi dosen; perilaku CAP produk database dapat bergantung pada konfigurasi dan mekanisme operasional yang digunakan.

## 9.7 Kesimpulan

CAP Theorem menjelaskan bahwa sistem penyimpanan data terdistribusi menghadapi trade-off antara konsistensi dan ketersediaan ketika terjadi partisi jaringan.

Perancang sistem perlu menentukan prioritas berdasarkan kebutuhan aplikasi. Sistem yang mengutamakan konsistensi dapat membatasi layanan ketika terjadi gangguan, sedangkan sistem yang mengutamakan ketersediaan dapat menerima kemungkinan ketidaksinkronan data sementara.

---

# 10. KONSISTENSI DATA

## 10.1 Pengertian Konsistensi Data

Konsistensi data merupakan kondisi ketika informasi yang disimpan dan diakses dalam suatu sistem sesuai dengan aturan serta keadaan data yang diharapkan.

Dalam sistem terdistribusi, data dapat disimpan pada beberapa node atau server yang berbeda. Kondisi tersebut menimbulkan tantangan dalam menjaga agar perubahan data dapat diketahui dan diterapkan secara tepat pada seluruh bagian sistem.

Konsistensi data menjadi penting karena pengguna dapat mengakses informasi melalui node yang berbeda pada waktu yang hampir bersamaan.

## 10.2 Strong Consistency

Strong Consistency merupakan model konsistensi yang memastikan bahwa operasi pembacaan data memperoleh hasil sesuai penulisan terbaru yang telah berhasil dilakukan.

Dengan model ini, pengguna diharapkan memperoleh informasi yang sama dan konsisten meskipun mengakses sistem melalui node yang berbeda.

### Karakteristik

1. Menjaga konsistensi informasi.
2. Operasi pembacaan mencerminkan penulisan terbaru yang sudah dikonfirmasi.
3. Memerlukan koordinasi yang tepat antarbagian sistem.
4. Dapat memengaruhi ketersediaan atau waktu respons ketika terjadi gangguan jaringan.

### Contoh Penerapan

Sistem perbankan membutuhkan konsistensi data yang kuat agar saldo rekening dan transaksi tidak menampilkan informasi yang saling bertentangan.

Misalnya, setelah transaksi berhasil dilakukan, saldo yang ditampilkan harus sesuai dengan hasil transaksi tersebut.

## 10.3 Eventual Consistency

Eventual Consistency merupakan model konsistensi yang memungkinkan data pada beberapa node berbeda untuk sementara waktu tidak sama, tetapi akan menjadi konsisten apabila tidak ada pembaruan baru dan proses sinkronisasi berhasil diselesaikan.

Model ini sering digunakan pada sistem yang mengutamakan ketersediaan layanan dan kemampuan distribusi data.

### Karakteristik

1. Perubahan data tidak selalu langsung diterapkan pada seluruh node.
2. Perbedaan data dapat terjadi untuk sementara waktu.
3. Sistem melakukan proses sinkronisasi.
4. Data akan mencapai keadaan konsisten setelah proses penyelarasan selesai.

### Contoh Penerapan

Pada media sosial, seseorang mengunggah sebuah foto. Informasi unggahan tersebut mungkin tidak langsung terlihat pada seluruh server atau perangkat pengguna dalam waktu yang sama.

Setelah proses sinkronisasi berlangsung, informasi tersebut akan tersedia secara konsisten pada bagian sistem yang terkait.

## 10.4 Perbandingan Strong Consistency dan Eventual Consistency

| Aspek | Strong Consistency | Eventual Consistency |
|---|---|---|
| Konsistensi | Dijaga secara kuat | Dicapai secara bertahap |
| Pembaruan data | Harus mencerminkan penulisan terbaru | Dapat mengalami keterlambatan sinkronisasi |
| Perbedaan data | Tidak diharapkan setelah operasi berhasil sesuai model | Dapat terjadi sementara |
| Fokus | Ketepatan dan keseragaman data | Ketersediaan dan sinkronisasi |
| Contoh | Sistem perbankan | Media sosial |

## 10.5 Pentingnya Pemilihan Model Konsistensi

Pemilihan model konsistensi harus mempertimbangkan kebutuhan aplikasi.

Aplikasi yang mengelola transaksi keuangan membutuhkan konsistensi yang kuat karena kesalahan informasi dapat menimbulkan dampak serius.

Sebaliknya, aplikasi media sosial dapat menggunakan eventual consistency untuk beberapa jenis informasi karena keterlambatan sinkronisasi dalam waktu singkat biasanya masih dapat diterima.

## 10.6 Kesimpulan

Konsistensi data merupakan aspek penting dalam sistem terdistribusi karena data dapat disimpan dan diakses melalui beberapa node.

Strong Consistency mengutamakan kesesuaian data dengan penulisan terbaru, sedangkan Eventual Consistency memungkinkan perbedaan data sementara sebelum seluruh node mencapai keadaan konsisten.

Pemilihan model konsistensi harus disesuaikan dengan kebutuhan, karakteristik, dan tingkat ketepatan data yang dibutuhkan oleh aplikasi.

---

# 11. TANTANGAN SISTEM TERDISTRIBUSI DAN TERDESENTRALISASI

## 11.1 Pengertian

Sistem terdistribusi dan terdesentralisasi memiliki berbagai keunggulan dalam pengelolaan sumber daya dan layanan digital. Namun, penerapannya juga menghadapi tantangan teknis maupun nonteknis.

Berdasarkan materi perkuliahan, tantangan utama yang dibahas meliputi latency dan throughput, keamanan, kompleksitas manajemen node, serta governance.

## 11.2 Latency dan Throughput

### A. Latency

Latency merupakan waktu yang dibutuhkan sejak suatu permintaan dikirimkan hingga sistem memberikan respons atau menyelesaikan pemrosesan tertentu.

Semakin tinggi latency, semakin lama pengguna harus menunggu hasil dari sistem.

Dalam sistem terdistribusi, latency dapat dipengaruhi oleh jarak antarnode, kualitas jaringan, jumlah komunikasi, dan beban pemrosesan.

**Contoh:**

Ketika pengguna membuka aplikasi yang servernya berada di lokasi geografis sangat jauh, waktu respons dapat meningkat akibat perjalanan data melalui jaringan.

### B. Throughput

Throughput merupakan jumlah pekerjaan, permintaan, atau data yang dapat diproses oleh sistem dalam periode waktu tertentu.

Throughput menunjukkan kemampuan sistem dalam menangani beban kerja secara keseluruhan.

**Contoh:**

Sebuah server mampu memproses 1.000 permintaan dalam satu detik. Nilai tersebut dapat digunakan untuk menggambarkan throughput sistem pada kondisi pengujian tertentu.

### C. Perbedaan Latency dan Throughput

| Aspek | Latency | Throughput |
|---|---|---|
| Pengertian | Waktu yang dibutuhkan untuk memproses permintaan | Jumlah pekerjaan yang diproses dalam periode tertentu |
| Fokus | Kecepatan respons | Kapasitas pemrosesan |
| Satuan umum | Milidetik atau detik | Request per second atau data per second |
| Tujuan | Mengurangi waktu tunggu | Meningkatkan jumlah pemrosesan |

## 11.3 Keamanan Sistem

Keamanan merupakan tantangan penting karena sistem terdistribusi dan terdesentralisasi melibatkan banyak perangkat, node, dan jalur komunikasi.

Semakin banyak komponen yang terhubung, semakin banyak pula aspek keamanan yang perlu diperhatikan.

Materi perkuliahan menyoroti dua jenis ancaman, yaitu DDoS dan Sybil Attack.

### A. Distributed Denial of Service (DDoS)

DDoS merupakan serangan yang dilakukan dengan membanjiri suatu layanan atau server menggunakan lalu lintas permintaan dalam jumlah besar dari berbagai sumber.

Serangan tersebut bertujuan membuat layanan tidak mampu menangani permintaan yang masuk sehingga pengguna yang sah mengalami kesulitan mengakses sistem.

**Dampak:**

1. Layanan menjadi lambat.
2. Server mengalami kelebihan beban.
3. Pengguna kesulitan mengakses sistem.
4. Ketersediaan layanan dapat terganggu.

### B. Sybil Attack

Sybil Attack merupakan jenis serangan siber yang dilakukan dengan membuat banyak identitas palsu, seperti akun, node, atau pseudonim secara bersamaan untuk mendominasi pengaruh, suara, atau reputasi dalam jaringan.

Serangan ini dapat terjadi pada sistem Peer-to-Peer maupun blockchain.

Penyerang menyamar sebagai banyak pengguna yang seolah-olah sah untuk memanipulasi sistem dan memperoleh pengaruh yang tidak semestinya.

**Dampak:**

1. Mengganggu integritas jaringan.
2. Memanipulasi mekanisme pengambilan keputusan.
3. Mengganggu proses konsensus.
4. Mengurangi kepercayaan terhadap sistem.

**Upaya pencegahan:**

- Menggunakan mekanisme identitas dan autentikasi yang sesuai.
- Menerapkan mekanisme konsensus yang tahan terhadap serangan.
- Melakukan pembatasan dan pemantauan aktivitas mencurigakan.
- Menggunakan mekanisme reputasi atau verifikasi sesuai kebutuhan sistem.

## 11.4 Kompleksitas Manajemen Node

Node merupakan komponen penting dalam sistem terdistribusi dan terdesentralisasi.

Ketika jumlah node bertambah, pengelolaan sistem menjadi semakin kompleks karena setiap node harus dapat berkomunikasi, berkoordinasi, dan menjalankan tugas sesuai aturan sistem.

Tantangan pengelolaan node meliputi:

1. Pemantauan kondisi setiap node.
2. Pengelolaan konfigurasi perangkat.
3. Penanganan node yang mengalami kegagalan.
4. Pengelolaan komunikasi antarperangkat.
5. Sinkronisasi data.
6. Pengaturan keamanan setiap node.

**Contoh:**

Sebuah sistem memiliki puluhan server yang tersebar di beberapa wilayah. Administrator harus memastikan setiap server berjalan dengan baik dan dapat berkomunikasi dengan server lainnya.

## 11.5 Governance (Tata Kelola)

Governance merupakan proses pengaturan, pengambilan keputusan, dan pengelolaan suatu sistem agar berjalan sesuai aturan yang telah disepakati.

Dalam sistem terdesentralisasi, governance menjadi tantangan karena keputusan tidak sepenuhnya berada pada satu pihak.

Beberapa pihak yang berpartisipasi harus memiliki mekanisme untuk menentukan perubahan aturan, pengembangan sistem, serta penyelesaian permasalahan.

**Tantangan governance:**

1. Menentukan pihak yang memiliki hak pengambilan keputusan.
2. Menyepakati perubahan sistem.
3. Mengelola perbedaan kepentingan antarpartisipan.
4. Menjaga transparansi keputusan.
5. Memastikan aturan diterapkan secara konsisten.

## 11.6 Kesimpulan

Sistem terdistribusi dan terdesentralisasi menghadapi berbagai tantangan dalam penerapannya. Latency dan throughput berpengaruh terhadap performa, keamanan menjadi aspek penting untuk melindungi jaringan, kompleksitas manajemen node membutuhkan pengelolaan yang baik, sedangkan governance diperlukan untuk menjaga tata kelola sistem.

Oleh karena itu, pengembangan sistem harus mempertimbangkan aspek performa, keamanan, koordinasi, dan pengelolaan secara menyeluruh.

---

# 12. TREN MASA DEPAN

## 12.1 Pengertian

Perkembangan teknologi informasi terus mendorong munculnya pendekatan baru dalam pembangunan sistem terdistribusi dan terdesentralisasi.

Kebutuhan terhadap komputasi yang lebih fleksibel, pemrosesan data yang cepat, keamanan, dan pengelolaan sumber daya mendorong berkembangnya berbagai teknologi baru.

Berdasarkan materi perkuliahan, terdapat empat tren masa depan yang dibahas, yaitu Cloud-Native, Edge dan Fog Computing, Web3 dan DeFi, serta Federated Data-Learning.

## 12.2 Cloud-Native

Cloud-Native merupakan pendekatan pembangunan dan pengoperasian aplikasi yang dirancang agar dapat memanfaatkan lingkungan cloud secara optimal.

Pendekatan ini memungkinkan aplikasi dibangun menggunakan komponen yang lebih fleksibel, mudah dikembangkan, dan dapat dikelola secara dinamis.

Materi perkuliahan memberikan contoh teknologi Cloud-Native berupa Docker dan Kubernetes.

### A. Docker

Docker merupakan platform yang digunakan untuk mengemas aplikasi beserta dependensinya ke dalam container.

Container memungkinkan aplikasi berjalan secara konsisten pada lingkungan yang berbeda selama lingkungan tersebut mendukung teknologi container.

**Manfaat:**

1. Mempermudah proses deployment aplikasi.
2. Membantu menjaga konsistensi lingkungan.
3. Memudahkan pengelolaan dependensi.
4. Mendukung pengembangan aplikasi berbasis layanan.

### B. Kubernetes

Kubernetes merupakan platform orkestrasi container yang digunakan untuk mengelola aplikasi berbasis container.

Kubernetes membantu pengelolaan deployment, penskalaan, dan pemulihan aplikasi yang berjalan pada kumpulan mesin.

**Manfaat:**

1. Mengelola banyak container.
2. Mendukung penskalaan aplikasi.
3. Membantu pemulihan layanan.
4. Mempermudah pengelolaan aplikasi berskala besar.

## 12.3 Edge dan Fog Computing

### A. Edge Computing

Edge Computing merupakan pendekatan komputasi yang melakukan pemrosesan data lebih dekat dengan sumber data atau perangkat yang menghasilkan data.

Pendekatan ini bertujuan mengurangi kebutuhan pengiriman seluruh data ke pusat data yang jauh.

**Contoh:**

Kamera pengawas yang melakukan analisis awal terhadap gambar secara langsung pada perangkat atau komputer yang berada dekat dengan kamera.

**Manfaat:**

1. Mengurangi latency.
2. Mengurangi lalu lintas pengiriman data.
3. Mendukung respons secara cepat.
4. Membantu pengolahan data secara lokal.

### B. Fog Computing

Fog Computing merupakan pendekatan komputasi yang menyediakan lapisan pemrosesan antara perangkat edge dan pusat cloud.

Fog Computing memungkinkan data diproses melalui perangkat perantara yang berada lebih dekat dengan sumber data dibandingkan pusat cloud.

**Contoh:**

Pada sistem Internet of Things (IoT), beberapa perangkat sensor mengirimkan data ke gateway lokal untuk diproses sebelum informasi tertentu diteruskan ke cloud.

### C. Perbedaan Edge dan Fog Computing

| Aspek | Edge Computing | Fog Computing |
|---|---|---|
| Lokasi pemrosesan | Dekat sumber data atau perangkat | Lapisan perantara antara edge dan cloud |
| Fokus | Pemrosesan dekat perangkat | Koordinasi dan pemrosesan pada lapisan perantara |
| Tujuan | Mengurangi latency | Mengurangi ketergantungan pada cloud pusat |
| Contoh | Pemrosesan pada kamera pintar | Gateway IoT |

## 12.4 Web3 dan DeFi

### A. Web3

Web3 merupakan konsep perkembangan teknologi web yang berkaitan dengan penggunaan teknologi blockchain dan jaringan terdesentralisasi.

Web3 bertujuan memberikan model interaksi digital yang memungkinkan pengguna berpartisipasi dalam jaringan tanpa seluruh aktivitas bergantung pada satu pengendali pusat.

Konsep Web3 sering dikaitkan dengan identitas digital, aset digital, smart contract, dan aplikasi terdesentralisasi.

### B. DeFi (Decentralized Finance)

DeFi merupakan singkatan dari Decentralized Finance, yaitu pendekatan layanan keuangan yang memanfaatkan teknologi blockchain dan smart contract untuk menjalankan berbagai fungsi keuangan secara terdesentralisasi.

Beberapa fungsi yang dapat ditemukan dalam ekosistem DeFi meliputi pertukaran aset digital, peminjaman, dan pengelolaan aset berbasis protokol.

### C. Hubungan Web3 dan DeFi

Web3 merupakan konsep ekosistem teknologi web yang lebih luas, sedangkan DeFi merupakan salah satu penerapan teknologi tersebut dalam bidang keuangan.

Keduanya memanfaatkan teknologi blockchain dan mekanisme otomatisasi untuk mendukung layanan berbasis jaringan terdesentralisasi.

## 12.5 Federated Data-Learning (AI Terdistribusi)

Federated Learning merupakan pendekatan pembelajaran mesin yang memungkinkan beberapa perangkat atau pihak berpartisipasi dalam pelatihan model tanpa harus mengirimkan seluruh data mentah ke satu pusat pengumpulan data.

Dalam pendekatan ini, proses pelatihan dapat dilakukan secara lokal pada perangkat atau organisasi masing-masing. Hasil pembaruan model kemudian dikirimkan untuk digabungkan sesuai mekanisme yang digunakan.

### Cara Kerja Secara Umum

1. Model awal diberikan kepada beberapa perangkat atau pihak.
2. Setiap pihak melakukan pelatihan menggunakan data lokal.
3. Hasil pembaruan model dikirimkan ke proses agregasi.
4. Pembaruan dari berbagai pihak digabungkan.
5. Model hasil pembaruan dapat didistribusikan kembali.
6. Proses pelatihan dapat diulang hingga model mencapai hasil yang diharapkan.

### Manfaat

1. Mengurangi kebutuhan pemindahan data mentah.
2. Mendukung kolaborasi pelatihan model.
3. Membantu menjaga privasi data.
4. Mendukung pengembangan AI terdistribusi.

Federated Learning tetap memerlukan mekanisme keamanan karena pembaruan model yang dikirimkan juga dapat menghadirkan risiko tertentu.

## 12.6 Kesimpulan

Tren masa depan sistem terdistribusi dan terdesentralisasi menunjukkan perkembangan menuju infrastruktur yang lebih fleksibel, efisien, dan mampu mengelola data dalam skala besar.

Cloud-Native mendukung pengembangan aplikasi berbasis cloud, Edge dan Fog Computing mendekatkan pemrosesan data ke sumbernya, Web3 dan DeFi mengembangkan layanan berbasis desentralisasi, sedangkan Federated Learning mendukung pelatihan AI dengan melibatkan berbagai pihak.

---

**AKHIR MODUL 01**
