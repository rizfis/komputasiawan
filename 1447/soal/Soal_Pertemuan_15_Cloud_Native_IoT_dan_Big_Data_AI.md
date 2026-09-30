# Lembar Soal Ujian Mahasiswa
## Pertemuan 15: Integrasi Cloud-Native (IoT, Big Data, dan Cloud AI)

- **Mata Kuliah:** Komputasi Awan (*Cloud Computing*)
- **Kode MK / Bobot:** TI433946 / 3 SKS
- **Materi Rujukan:** `Pertemuan_15_Cloud_Native_IoT_dan_Big_Data_AI.md`
- **Bentuk Evaluasi:** Uraian / Essay (Analisis Mandiri & Review Komprehensif Terpadu)
- **Total Soal:** 30 Soal
- **Distribusi Tingkat Kesulitan:**
  - Level 1 (Kemudahan 1 / Sangat Dasar): 6 Soal @ 1 Menit
  - Level 2 (Kemudahan 2 / Dasar-Menengah): 6 Soal @ 2 Menit
  - Level 3 (Kemudahan 3 / Menengah-Aplikatif): 6 Soal @ 3 Menit
  - Level 4 (Kemudahan 4 / Analitis-Tinggi): 6 Soal @ 4 Menit
  - Level 5 (Kemudahan 5 / Evaluasi & Sintesis Desain): 6 Soal @ 5 Menit
- **Estimasi Waktu Pengerjaan Total:** 90 Menit

---

### BAGIAN I: TINGKAT KESULITAN LEVEL 1
**Karakteristik:** Menguji kepanjangan MQTT, tahapan pipa Big Data, istilah Device Shadow, dan komponen hardware GPU AI.  
**Alokasi Waktu:** 1 Menit per Soal (Total: 6 Menit)

#### Soal 15.1 (Level 1 - 1 Menit)
Apa kepanjangan dari akronim protokol komunikasi IoT **MQTT**?

#### Soal 15.2 (Level 1 - 1 Menit)
Sebutkan 4 tahapan berurutan dalam pipa data skala besar (*Big Data Pipeline*) di komputasi awan!

#### Soal 15.3 (Level 1 - 1 Menit)
Apa istilah untuk salinan status virtual terakhir dari sebuah perangkat fisik IoT yang disimpan di memori cloud (*Cloud IoT Core*) meskipun perangkat tersebut sedang offline?

#### Soal 15.4 (Level 1 - 1 Menit)
Berapa ukuran perkiraan header paket data pada protokol MQTT dibandingkan dengan protokol HTTP konvensional?

#### Soal 15.5 (Level 1 - 1 Menit)
Teknologi interkoneksi jaringan ultra-cepat apa yang umum digunakan antar-node server GPU di cloud untuk melatih model AI skala besar (*LLM*) dengan latensi sub-mikrodetik?

#### Soal 15.6 (Level 1 - 1 Menit)
Sebutkan satu contoh layanan mesin pemrosesan analitik data terdistribusi terkelola yang populer di penyedia cloud publik!

---

### BAGIAN II: TINGKAT KESULITAN LEVEL 2
**Karakteristik:** Menguji pemahaman konsep perbedaan Data Lake vs Data Warehouse, keunggulan MQTT, dan GPU-as-a-Service.  
**Alokasi Waktu:** 2 Menit per Soal (Total: 12 Menit)

#### Soal 15.7 (Level 2 - 2 Menit)
Jelaskan perbedaan mendasar antara **Data Lake** dan **Data Warehouse** dari aspek struktur skema data yang disimpannya!

#### Soal 15.8 (Level 2 - 2 Menit)
Mengapa protokol MQTT berbasis pola **Publish-Subscribe** jauh lebih hemat baterai dan bandwidth pada perangkat sensor IoT dibandingkan protokol HTTP **Request-Response**?

#### Soal 15.9 (Level 2 - 2 Menit)
Apa yang dimaksud dengan konsep pemisahan kapasitas penyimpanan dan pemrosesan (**Decoupled Storage and Compute**) pada arsitektur Big Data cloud modern?

#### Soal 15.10 (Level 2 - 2 Menit)
Jelaskan apa yang dimaksud dengan layanan **GPU-as-a-Service** dan mengapa layanan ini sangat revolusioner bagi pengembangan model Deep Learning!

#### Soal 15.11 (Level 2 - 2 Menit)
Jelaskan fungsi dari fitur **Rule Engine** pada platform Cloud IoT Core!

#### Soal 15.12 (Level 2 - 2 Menit)
Apa perbedaan peran antara fase **Pelatihan Model (*Model Training*)** dan fase **Inferensi (*Model Inference*)** pada beban kerja Cloud AI ditinjau dari kebutuhan spesifikasi perangkat keras komputasinya?

---

### BAGIAN III: TINGKAT KESULITAN LEVEL 3
**Karakteristik:** Penerapan alur autentikasi IoT X.509, format kolom Parquet pada Big Data, dan tumpukan arsitektur MLOps.  
**Alokasi Waktu:** 3 Menit per Soal (Total: 18 Menit)

#### Soal 15.13 (Level 3 - 3 Menit)
Uraikan mekanisme autentikasi dan enkripsi keamanan pada koneksi perangkat sensor IoT ke Cloud IoT Core menggunakan **Sertifikat Digital X.509 (Mutual TLS / mTLS)**!

#### Soal 15.14 (Level 3 - 3 Menit)
Jelaskan mengapa format berkas berbasis kolom (**Columnar Storage**, seperti *Apache Parquet*) jauh lebih cepat dan hemat biaya untuk query Big Data analitik di cloud dibandingkan berkas format baris (*Row-Oriented*, seperti CSV atau JSON)!

#### Soal 15.15 (Level 3 - 3 Menit)
Uraikan arsitektur tiga tingkatan (*Three-Tier AI Infrastructure*) pada lanskap komputasi awan modern: **Lapisan Hardware GPU**, **Lapisan MLOps & Managed Cluster**, dan **Lapisan Model-as-a-Service (AIaaS)**!

#### Soal 15.16 (Level 3 - 3 Menit)
Jelaskan cara kerja fitur **Device Shadow** saat seorang pengguna mengirimkan instruksi untuk menyalakan pendingin ruangan (AC) pintar rumahnya melalui aplikasi ponsel saat perangkat AC tersebut sedang mengalami gangguan jaringan internet lokal!

#### Soal 15.17 (Level 3 - 3 Menit)
Uraikan perbedaan fungsi antara penyerapan data secara batch (**Batch Ingestion**) dan penyerapan data secara streaming (**Stream Ingestion**) pada pipa Big Data, beserta contoh teknologi cloud pendukungnya!

#### Soal 15.18 (Level 3 - 3 Menit)
Mengapa arsitektur penyimpanan klaster GPU AI modern membutuhkan sistem file terdistribusi paralel berperforma tinggi (*High-Throughput Parallel Filesystems*, seperti Lustre atau GPFS / Amazon FSx for Lustre)?

---

### BAGIAN IV: TINGKAT KESULITAN LEVEL 4
**Karakteristik:** Analisis mendalam integrasi Lambda vs Kappa Architecture, optimasi biaya pelatihan AI di cloud, dan troubleshooting pipa telemetri IoT.  
**Alokasi Waktu:** 4 Menit per Soal (Total: 24 Menit)

#### Soal 15.19 (Level 4 - 4 Menit)
Analisis perbandingan arsitektural antara **Arsitektur Lambda (*Lambda Architecture*)** dan **Arsitektur Kappa (*Kappa Architecture*)** dalam memproses data terdistribusi skala besar di komputasi awan!

#### Soal 15.20 (Level 4 - 4 Menit)
Analisis strategi optimasi biaya (**FinOps for AI**) saat melatih model kecerdasan buatan berskala besar di cloud publik: Bagaimana memanfaatkan kombinasi **Spot GPU Instances** dan mekanisme **Frequent Checkpointing** untuk memangkas biaya komputasi hingga 70% tanpa risiko kehilangan progres pelatihan!

#### Soal 15.21 (Level 4 - 4 Menit)
Sebuah sistem pemantauan armada logistik berbasis IoT mengalami masalah: saat ribuan truk memasuki area pegunungan yang tidak memiliki sinyal seluler, data pelacakan rute terputus, dan saat truk kembali ke area sinyal, server cloud mengalami kebanjiran paket data mendadak yang merobohkan antrean pesan. Analisis bagaimana teknik **Store-and-Forward** pada node Edge dan mekanisme **Backpressure** pada cloud broker memecahkan dilema ini!

#### Soal 15.22 (Level 4 - 4 Menit)
Bandingkan implikasi privasi, keamanan, dan kepatuhan hukum antara mengadopsi model **Cloud-Hosted Proprietary LLM API (seperti OpenAI ChatGPT API / Anthropic Claude)** versus men-deploy model **Open-Source LLM Mandiri di VPC IaaS Lokal (seperti Meta Llama 3 on Private VPC)** bagi industri perbankan nasional!

#### Soal 15.23 (Level 4 - 4 Menit)
Analisis bagaimana teknik pemangkasan bobot model kecerdasan buatan seperti **Kuantisasi (*Quantization / 4-bit, 8-bit*)** dan **Pruning** memungkinkan model Deep Learning yang awalnya berukuran puluhan gigabyte dapat di-deploy langsung ke perangkat **Edge Computing / Perangkat Seluler**!

#### Soal 15.24 (Level 4 - 4 Menit)
Analisis integrasi holistik semester: Bagaimana konsep dasar dari **Pertemuan 01 (Karakteristik NIST & Elastisitas)**, **Pertemuan 07 (Kontainerisasi Kubernetes)**, dan **Pertemuan 11 (Keamanan IAM & Enkripsi)** saling bertaut membentuk fondasi infrastruktur **Cloud AI Modern** saat ini!

---

### BAGIAN V: TINGKAT KESULITAN LEVEL 5
**Karakteristik:** Desain arsitektur ekosistem terpadu enterprise (Big Data + IoT + AI), evaluasi studi kasus komprehensif akhir semester, dan integrasi etika masa depan komputasi.  
**Alokasi Waktu:** 5 Menit per Soal (Total: 30 Menit)

#### Soal 15.25 (Level 5 - 5 Menit)
**Kasus Desain Arsitektur Terintegrasi Akhir Semester (Smart Agriculture System):**  
Sebuah konsorsium pertanian modern merancang sistem pertanian cerdas (*Smart Greenhouse*) berskala nasional dengan 10.000 perkebunan hidroponik. Sistem harus mengintegrasikan: (1) Jutaan sensor kelembapan tanah dan nutrisi berbasis protokol hemat daya, (2) Pipa Big Data untuk analisis tren panen nasional, dan (3) Model Computer Vision berbasis AI untuk mendeteksi hama penyakit daun tanaman secara otomatis.  
Rancanglah cetak biru arsitektur komprehensif (*End-to-End Architectural Blueprint*) yang mengintegrasikan seluruh domain materi semester ini (**Edge, IoT Core, Big Data Pipeline, Kubernetes Cluster, dan Cloud AI**) secara terpadu!

#### Soal 15.26 (Level 5 - 5 Menit)
**Evaluasi Studi Kasus Perbankan Bank "Artha Aman" (Integrasi Semester):**  
Bank "Artha Aman" mengoperasikan arsitektur Hybrid Cloud: Core Banking berada di On-Premise Private Cloud lokal (mematuhi UU PDP No. 27/2022) dan aplikasi Mobile Banking berada di Public Cloud. Saat jam gajian karyawan nasional setiap tanggal 25, aplikasi mobile mengalami lonjakan transaksi transfer 15 kali lipat.  
Analisis dan rancanglah mekanisme integrasi menyeluruh yang memadukan **Auto-Scaling Group**, **Layer 7 Load Balancer**, **Pemisahan Sesi Stateless (Redis)**, **Interkoneksi Dedicated Direct Connect**, dan **Penyangga Antrean Pesan (Message Queue)** agar sistem Core Banking on-premise lokal yang kapasitasnya terbatas tidak roboh dihantam lonjakan trafik dari Public Cloud!

#### Soal 15.27 (Level 5 - 5 Menit)
Rancang sebuah arsitektur kepatuhan data kecerdasan buatan (**AI Governance & Data Privacy Architecture**) yang menerapkan teknik **Federated Learning (Pembelajaran Terfederasi)** untuk melatih model diagnosis penyakit kanker paru-paru lintas 20 rumah sakit tanpa satu pun data rekam medis pasien keluar dari server internal rumah sakit masing-masing!

#### Soal 15.28 (Level 5 - 5 Menit)
Susunlah peta jalan evaluasi kesiapan arsitektur cloud perusahaan (**Cloud Maturity Model Assessment**) yang mengukur tingkat evolusi teknologi sebuah korporasi dari Tahap 1 (Tradisional) hingga Tahap 4 (Cloud-Native Matang) berdasarkan materi kuliah yang telah dipelajari dari Pertemuan 01 hingga 15!

#### Soal 15.29 (Level 5 - 5 Menit)
Analisis secara kritis paradoks konsumsi energi komputasi awan di era kecerdasan buatan generatif (*The Cloud AI Energy Dilemma*): Bagaimana seorang insinyur komputasi awan menyeimbangkan antara perlombaan melatih model AI raksasa (yang membutuhkan daya listrik ratusan megawatt) dengan komitmen moral terhadap keberlanjutan bumi (**Sustainable Green Computing**)?

#### Soal 15.30 (Level 5 - 5 Menit)
**Sintesis Filosofis dan Etika Keilmuan Akhir Kuliah Komputasi Awan (CPL02):**  
Sebagai calon Sarjana Informatika lulusan Universitas Darussalam Gontor, rumuskan sebuah manifesto etika profesional pribadi yang memadukan **Keunggulan Kompetensi Teknis Komputasi Awan Tingkat Tinggi** dengan **Nilai-Nilai Spiritual Amanah, Keadilan, dan Peradaban Islam** dalam memimpin transformasi digital di masyarakat!
