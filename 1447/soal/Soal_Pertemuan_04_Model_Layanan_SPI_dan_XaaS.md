# Lembar Soal Ujian Mahasiswa
## Pertemuan 04: Model Layanan Komputasi Awan (SPI & XaaS)

- **Mata Kuliah:** Komputasi Awan (*Cloud Computing*)
- **Kode MK / Bobot:** TI433946 / 3 SKS
- **Materi Rujukan:** `Pertemuan_04_Model_Layanan_SPI_dan_XaaS.md`
- **Bentuk Evaluasi:** Uraian / Essay (Analisis Mandiri)
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
**Karakteristik:** Menguji kepanjangan akronim SPI, identifikasi model layanan, dan contoh produk cloud.  
**Alokasi Waktu:** 1 Menit per Soal (Total: 6 Menit)

#### Soal 4.1 (Level 1 - 1 Menit)
Apa kepanjangan dari model klasik SPI dalam arsitektur komputasi awan?

#### Soal 4.2 (Level 1 - 1 Menit)
Sebutkan dua contoh layanan komersial terkemuka di dunia yang termasuk dalam kategori *Infrastructure as a Service (IaaS)*!

#### Soal 4.3 (Level 1 - 1 Menit)
Sebutkan dua contoh platform yang mewakili kategori *Platform as a Service (PaaS)*!

#### Soal 4.4 (Level 1 - 1 Menit)
Sebutkan dua contoh aplikasi perangkat lunak yang termasuk dalam model *Software as a Service (SaaS)*!

#### Soal 4.5 (Level 1 - 1 Menit)
Apa kepanjangan dari istilah CaaS dan DBaaS dalam lanskap komputasi awan modern XaaS?

#### Soal 4.6 (Level 1 - 1 Menit)
Dalam model analogi populer *"Pizza as a Service"*, model layanan cloud manakah yang dianalogikan dengan "Makan di Restoran (*Dine Out*)"?

---

### BAGIAN II: TINGKAT KESULITAN LEVEL 2
**Karakteristik:** Membedakan batas tanggung jawab, menjelaskan fokus pengguna, dan komparasi kontrol teknis.  
**Alokasi Waktu:** 2 Menit per Soal (Total: 12 Menit)

#### Soal 4.7 (Level 2 - 2 Menit)
Jelaskan perbedaan fokus pengguna utama (*Target Persona*) antara model layanan IaaS, PaaS, dan SaaS!

#### Soal 4.8 (Level 2 - 2 Menit)
Pada model layanan IaaS, pihak manakah yang bertanggung jawab melakukan penambalan celah keamanan (*patching*) pada Sistem Operasi (OS) mesin virtual? Jelaskan alasannya!

#### Soal 4.9 (Level 2 - 2 Menit)
Jelaskan mengapa pengembang aplikasi (*developer*) tidak memiliki akses langsung ke kernel atau konfigurasi sistem operasi pada model layanan PaaS!

#### Soal 4.10 (Level 2 - 2 Menit)
Dalam analogi *"Pizza as a Service"*, mengapa IaaS dianalogikan seperti "Membeli Pizza Beku (*Take & Bake*)"?

#### Soal 4.11 (Level 2 - 2 Menit)
Apa perbedaan esensial antara layanan basis data tradisional yang diinstal di dalam VM IaaS dengan layanan *Database as a Service (DBaaS)* seperti Amazon RDS atau Cloud Spanner?

#### Soal 4.12 (Level 2 - 2 Menit)
Jelaskan apa yang dimaksud dengan model layanan *Function as a Service (FaaS)* atau *Serverless*!

---

### BAGIAN III: TINGKAT KESULITAN LEVEL 3
**Karakteristik:** Penerapan dekonstruksi 9 lapis stack komputasi, evaluasi skenario pemilihan model layanan, dan trade-off operasional.  
**Alokasi Waktu:** 3 Menit per Soal (Total: 18 Menit)

#### Soal 4.13 (Level 3 - 3 Menit)
Uraikan dekonstruksi 9 lapisan komputasi (*Compute Stack*) dan jelaskan lapisan mana saja yang dikelola oleh konsumen pada model **PaaS**!

#### Soal 4.14 (Level 3 - 3 Menit)
Jelaskan keuntungan dan kerugian operasional yang dihadapi tim developer ketika memilih migrasi dari IaaS ke PaaS!

#### Soal 4.15 (Level 3 - 3 Menit)
Uraikan bagaimana model layanan *Containers as a Service (CaaS)* seperti Google Kubernetes Engine (GKE) memosisikan dirinya di antara spektrum fleksibilitas IaaS dan kemudahan PaaS!

#### Soal 4.16 (Level 3 - 3 Menit)
Jelaskan peran model *AI as a Service (AIaaS)* (seperti OpenAI API atau Google Vertex AI) dalam menurunkan hambatan adopsi kecerdasan buatan bagi perusahaan rintisan (*startup*)!

#### Soal 4.17 (Level 3 - 3 Menit)
Bandingkan tanggung jawab pencadangan data (*data backup*) dan retensi antara model IaaS, PaaS, dan SaaS!

#### Soal 4.18 (Level 3 - 3 Menit)
Kapan sebuah perusahaan perangkat lunak wajib memilih IaaS dibandingkan PaaS atau SaaS untuk arsitektur produk barunya? Sebutkan minimal 3 kriteria penentu!

---

### BAGIAN IV: TINGKAT KESULITAN LEVEL 4
**Karakteristik:** Analisis mendalam trade-off arsitektural, investigasi kegagalan sistem, dan evaluasi matriks keputusan bisnis.  
**Alokasi Waktu:** 4 Menit per Soal (Total: 24 Menit)

#### Soal 4.19 (Level 4 - 4 Menit)
Sebuah perusahaan e-commerce mengalami kebocoran data nasabah akibat basis data MongoDB mereka yang berjalan di instans AWS EC2 (IaaS) tidak diberi kata sandi dan port 27017 terbuka ke internet publik. Analisis batas tanggung jawab insiden ini berdasarkan dekonstruksi model IaaS!

#### Soal 4.20 (Level 4 - 4 Menit)
Bandingkan implikasi biaya jangka panjang (*Total Cost of Ownership / TCO*) antara membangun aplikasi web menggunakan arsitektur PaaS (misal Heroku) versus mengelolanya sendiri di VM IaaS murah (misal DigitalOcean Droplets) untuk tim teknis berjumlah 2 orang!

#### Soal 4.21 (Level 4 - 4 Menit)
Analisis fenomena *Vendor Lock-in* pada model PaaS dan SaaS, dan bagaimana strategi arsitektur perangkat lunak modern memitigasi risiko tersebut!

#### Soal 4.22 (Level 4 - 4 Menit)
Analisis perbedaan mendasar antara model layanan *Serverless / Function as a Service (FaaS)* dengan *Platform as a Service (PaaS)* konvensional dalam aspek siklus hidup instans (*instance lifecycle*) dan penagihan!

#### Soal 4.23 (Level 4 - 4 Menit)
Mengapa organisasi korporasi besar sering mengadopsi model SaaS untuk operasional penunjang (seperti email dan penggajian/payroll), namun tetap mempertahankan model IaaS atau Private Cloud untuk sistem inti bisnis mereka (*Core Competency*)? Analisis alasan strategisnya!

#### Soal 4.24 (Level 4 - 4 Menit)
Evaluasilah transisi dari arsitektur *Monolithic on IaaS* ke arsitektur *Microservices on CaaS*: Kendala operasional dan keterampilan apa saja yang harus diantisipasi oleh organisasi?

---

### BAGIAN V: TINGKAT KESULITAN LEVEL 5
**Karakteristik:** Studi kasus multi-dimensi perancangan arsitektur sistem startup telemedicine, justifikasi pemilihan SPI & XaaS, dan efisiensi anggaran.  
**Alokasi Waktu:** 5 Menit per Soal (Total: 30 Menit)

#### Soal 4.25 (Level 5 - 5 Menit)
**Kasus Perancangan Startup Telemedicine "SehatCepat":**  
Sebuah startup klinik telemedicine baru memiliki tim teknis yang sangat ramping: 3 programmer backend/frontend dan 1 desainer UI/UX (tanpa adanya insinyur SysAdmin/DevOps). Mereka harus meluncurkan tiga modul sistem utama:  
1. *Layanan Email Perusahaan dan Manajemen Dokumen Internal Tim.*  
2. *Aplikasi Mobile Pasien untuk Konsultasi Chat/Video dengan Dokter (Backend API).*  
3. *Modul Pemrosesan Analitik Citra Medis Rontgen Menggunakan Model Deep Learning Berbasis Akselerator GPU CUDA Khusus.*  
Rancang dan tentukan model layanan cloud yang paling tepat (**SaaS, PaaS, IaaS, atau XaaS**) untuk masing-masing dari ketiga kebutuhan modul di atas! Sertakan argumentasi teknis mendalam dan pertimbangan efisiensi anggaran tim!

#### Soal 4.26 (Level 5 - 5 Menit)
Evaluasilah perdebatan arsitektural: *"Apakah konsep arsitektur IaaS murni akan punah dalam 10 tahun ke depan dan digantikan seluruhnya oleh FaaS (Serverless) dan CaaS (Kubernetes)?"* Berikan analisis kritis Anda disertai argumen teknis pendukung dan sanggahannya!

#### Soal 4.27 (Level 5 - 5 Menit)
Rancanglah sebuah cetak biru arsitektur modern yang mengintegrasikan berbagai model XaaS (**DBaaS, FaaS, Storage-as-a-Service, dan AIaaS**) untuk sistem koreksi esai otomatis pada aplikasi ujian daring universitas!

#### Soal 4.28 (Level 5 - 5 Menit)
Analisis secara komprehensif risiko kepatuhan hukum dan keamanan data rekam medis pasien klinik telemedicine (berdasarkan UU PDP No. 27/2022 di Indonesia) jika modul analitik citra rontgen menggunakan layanan publik AIaaS pihak ketiga di luar negeri!

#### Soal 4.29 (Level 5 - 5 Menit)
Susunlah matriks keputusan formal (*Decision Matrix*) dengan parameter pembobotan kuantitatif untuk membantu dewan direksi perusahaan memilih antara model IaaS versus PaaS saat meremajakan sistem ERP perusahaan!

#### Soal 4.30 (Level 5 - 5 Menit)
Bagaimana integrasi etika tanggung jawab profesional seorang Software Engineer diwujudkan ketika memilih model layanan cloud? Analisis kasus di mana insinyur sengaja memilih arsitektur IaaS yang rumit demi mempertahankan posisinya di perusahaan (*job security*) versus memilih SaaS/PaaS yang efisien bagi organisasi!
