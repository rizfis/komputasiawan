# Lembar Soal Ujian Mahasiswa
## Pertemuan 09: Skalabilitas, Elastisitas, dan Load Balancing

- **Mata Kuliah:** Komputasi Awan (*Cloud Computing*)
- **Kode MK / Bobot:** TI433946 / 3 SKS
- **Materi Rujukan:** `Pertemuan_09_Skalabilitas_Elastisitas_dan_Load_Balancing.md`
- **Bentuk Evaluasi:** Uraian / Essay (Analisis Mandiri & Perancangan Sistem)
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
**Karakteristik:** Menguji definisi dasar skalabilitas vs elastisitas, algoritma load balancing, dan istilah komponen ASG.  
**Alokasi Waktu:** 1 Menit per Soal (Total: 6 Menit)

#### Soal 9.1 (Level 1 - 1 Menit)
Apa istilah untuk jenis skalabilitas yang dilakukan dengan cara menambah spesifikasi hardware (seperti vCPU atau RAM) pada satu mesin server virtual yang sama?

#### Soal 9.2 (Level 1 - 1 Menit)
Apa istilah untuk jenis skalabilitas yang dilakukan dengan cara menambah jumlah instans server baru yang bekerja paralel di balik penyeimbang beban?

#### Soal 9.3 (Level 1 - 1 Menit)
Sebutkan 3 parameter batas jumlah instans yang wajib dikonfigurasi pada sebuah *Auto-Scaling Group (ASG)*!

#### Soal 9.4 (Level 1 - 1 Menit)
Sebutkan dua contoh algoritma distribusi trafik yang umum digunakan pada sebuah *Load Balancer*!

#### Soal 9.5 (Level 1 - 1 Menit)
Pada model referensi OSI, pada lapisan berapakah *Network Load Balancer (NLB)* dan *Application Load Balancer (ALB)* masing-masing beroperasi?

#### Soal 9.6 (Level 1 - 1 Menit)
Apa fungsi dari pengaturan durasi jeda waktu *Cooldown Period* pada Auto-Scaling Group?

---

### BAGIAN II: TINGKAT KESULITAN LEVEL 2
**Karakteristik:** Membedakan konsep skalabilitas vs elastisitas, karakteristik L4 vs L7, dan penjelasan algoritma penyeimbang beban.  
**Alokasi Waktu:** 2 Menit per Soal (Total: 12 Menit)

#### Soal 9.7 (Level 2 - 2 Menit)
Jelaskan perbedaan mendasar antara konsep **Skalabilitas (*Scalability*)** dan **Elastisitas (*Elasticity*)** dalam komputasi awan!

#### Soal 9.8 (Level 2 - 2 Menit)
Jelaskan cara kerja algoritma *Least Connections* dan sebutkan kapan algoritma ini lebih unggul dibandingkan *Round Robin*!

#### Soal 9.9 (Level 2 - 2 Menit)
Mengapa aplikasi yang ingin menerapkan skalabilitas horizontal secara mulus wajib dirancang dengan arsitektur **Stateless**?

#### Soal 9.10 (Level 2 - 2 Menit)
Jelaskan apa yang dimaksud dengan fitur *SSL/TLS Termination (SSL Offloading)* pada Layer 7 Load Balancer dan apa manfaatnya bagi server aplikasi!

#### Soal 9.11 (Level 2 - 2 Menit)
Apa kelemahan utama dari Skalabilitas Vertikal (*Scale-Up*) dibandingkan Skalabilitas Horizontal (*Scale-Out*) saat diterapkan pada server produksi?

#### Soal 9.12 (Level 2 - 2 Menit)
Jelaskan fungsi dari fitur *Sticky Sessions (Session Affinity)* pada penyeimbang beban dan bagaimana cara kerjanya!

---

### BAGIAN III: TINGKAT KESULITAN LEVEL 3
**Karakteristik:** Penerapan konfigurasi load balancing Nginx, mekanisme health checks, dan perancangan metrik pemicu ASG.  
**Alokasi Waktu:** 3 Menit per Soal (Total: 18 Menit)

#### Soal 9.13 (Level 3 - 3 Menit)
Perhatikan cuplikan konfigurasi Nginx penyeimbang beban berikut:
```nginx
upstream backend_nodes {
    least_conn;
    server 10.0.1.10:80 weight=3;
    server 10.0.1.11:80 weight=1;
}
```
Uraikan arti dari direktif `least_conn` dan parameter `weight=3` vs `weight=1` pada konfigurasi di atas!

#### Soal 9.14 (Level 3 - 3 Menit)
Jelaskan alur mekanisme **Health Check** yang dijalankan secara berkala oleh Load Balancer terhadap server target, serta apa yang terjadi jika salah satu server dinyatakan *Unhealthy*!

#### Soal 9.15 (Level 3 - 3 Menit)
Bandingkan kriteria perutean trafik (*Routing Criteria*) antara Layer 4 Load Balancer (NLB) dan Layer 7 Load Balancer (ALB)!

#### Soal 9.16 (Level 3 - 3 Menit)
Uraikan rantai telemetri tertutup (*Closed-Loop Telemetry*) antara metrik performa CloudWatch/Prometheus, alarm ambang batas, dan aksi Auto-Scaling Group!

#### Soal 9.17 (Level 3 - 3 Menit)
Jelaskan bagaimana arsitektur klaster in-memory terdistribusi (seperti Redis atau Memcached) memecahkan masalah dependensi sesi pada arsitektur web yang diskalakan secara horizontal!

#### Soal 9.18 (Level 3 - 3 Menit)
Apa bahaya dari fenomena efek osilasi liar (*Thrashing / Flapping*) pada Auto-Scaling Group jika parameter ambang batas *Scale-Out* dan *Scale-In* dikonfigurasi terlalu berdekatan tanpa adanya *Cooldown Period*?

---

### BAGIAN IV: TINGKAT KESULITAN LEVEL 4
**Karakteristik:** Analisis mendalam pemisahan modul L4 vs L7, pemilihan metrik pemicu penskalaan, dan arsitektur toleransi bencana multi-AZ.  
**Alokasi Waktu:** 4 Menit per Soal (Total: 24 Menit)

#### Soal 9.19 (Level 4 - 4 Menit)
Sebuah portal berita online raksasa mengalami lonjakan pembaca hingga 20 kali lipat saat pemilihan umum. Aplikasi berita tersebut memiliki dua modul:  
1. *Modul Halaman Berita Statis (Teks & Foto)*  
2. *Modul Kolom Komentar Interaktif Real-Time*  
Analisis mengapa memisahkan kedua modul ini ke dalam target group yang berbeda menggunakan **Layer 7 Application Load Balancer (ALB)** jauh lebih efektif dan hemat biaya dibandingkan menggunakan satu penyeimbang beban Layer 4!

#### Soal 9.20 (Level 4 - 4 Menit)
Analisis pemilihan metrik pemicu penskalaan Auto-Scaling (*Scaling Metric Policy*): Mengapa metrik **Request Count per Target** sering kali jauh lebih responsif dan akurat dalam mencegah degradasi aplikasi web dibandingkan hanya mengandalkan metrik **CPU Utilization**?

#### Soal 9.21 (Level 4 - 4 Menit)
Analisis perbandingan arsitektur penyeimbang beban berbasis **Cross-Zone Load Balancing** pada infrastruktur multi-AZ ditinjau dari aspek distribusi beban dan biaya transfer data!

#### Soal 9.22 (Level 4 - 4 Menit)
Bandingkan mekanisme penyeimbang beban perangkat lunak internal (seperti Nginx / HAProxy / Envoy) dengan penyeimbang beban terkelola cloud publik (seperti AWS ALB / GCP Cloud Load Balancing) ditinjau dari ketahanan terhadap serangan DDoS dan perawatan operasional!

#### Soal 9.23 (Level 4 - 4 Menit)
Analisis fenomena *Warm-Up / Pre-Warming* pada Load Balancer cloud publik: Mengapa kampanye diskon kilat (*Flash Sale*) yang lonjakan trafiknya melonjak dari 100 ke 100.000 request dalam 1 detik sering kali gagal jika load balancer tidak di-pre-warm terlebih dahulu?

#### Soal 9.24 (Level 4 - 4 Menit)
Sebuah klaster Auto-Scaling Group diatur untuk melakukan *Scale-In* (mematikan server) saat jam kerja berakhir. Analisis risiko terjadinya pemutusan transaksi pelanggan yang sedang berlangsung (*abrupt termination*) dan bagaimana fitur **Connection Draining / Deregistration Delay** mencegah masalah tersebut!

---

### BAGIAN V: TINGKAT KESULITAN LEVEL 5
**Karakteristik:** Desain komprehensif arsitektur auto-scaling & load balancing multi-AZ, studi kasus e-commerce flash sale, dan justifikasi FinOps.  
**Alokasi Waktu:** 5 Menit per Soal (Total: 30 Menit)

#### Soal 9.25 (Level 5 - 5 Menit)
**Kasus Desain Arsitektur Lonjakan Trafik E-Commerce "CepatBeli":**  
Platform belanja online "CepatBeli" menghadapi lonjakan trafik ekstrem dari 2.000 pengguna aktif harian menjadi 50.000 pengguna serentak saat kampanye promo tanggal kembar. Rancanglah sebuah cetak biru arsitektur komputasi awan terpadu yang memadukan **Layer 7 Application Load Balancer**, **Auto-Scaling Group Multi-AZ**, **Stateless Application Layer**, dan **In-Memory Cache** untuk menjamin ketersediaan sistem 100% tanpa henti layanan!

#### Soal 9.26 (Level 5 - 5 Menit)
Rancang sebuah kebijakan penskalaan prediktif (**Predictive Scaling**) yang dikombinasikan dengan penskalaan dinamis (**Dynamic Step Scaling**) pada platform streaming video langsung saat menyiarkan pertandingan final piala dunia! Jelaskan alasan mengapa *Dynamic Scaling* reaktif saja tidak cukup untuk kasus tersebut!

#### Soal 9.27 (Level 5 - 5 Menit)
Analisis strategi penyeimbangan beban berbasis **Global Server Load Balancing (GSLB)** menggunakan layanan DNS Anycast (seperti AWS Route 53 atau Cloudflare) untuk merutekan pengguna ke dua region cloud yang berbeda (Region Jakarta dan Region Frankfurt)!

#### Soal 9.28 (Level 5 - 5 Menit)
Evaluasilah perdebatan arsitektur: Kapan sebuah organisasi sebaiknya menghentikan penambahan kapasitas horizontal (*Scale-Out*) pada aplikasi dan harus mulai melakukan pemecahan arsitektur (*Decomposition*) menjadi arsitektur Microservices atau Serverless?

#### Soal 9.29 (Level 5 - 5 Menit)
Rancang sebuah arsitektur hibrida hemat biaya (*FinOps Strategy*) yang menggabungkan instans komputasi bertipe **On-Demand Instances** dan **Spot Instances** di dalam sebuah Auto-Scaling Group untuk memangkas biaya server hingga 70%!

#### Soal 9.30 (Level 5 - 5 Menit)
Analisis etika keilmuan dan tanggung jawab mitigasi serangan dalam perancangan Auto-Scaling: Bagaimana seorang arsitek cloud mengonfigurasi batas pengaman (*guardrails*) pada Auto-Scaling Group untuk mencegah serangan eksploitasi finansial (*Economic Denial of Sustainability / EDoS*) oleh peretas yang memanfaatkan sifat elastisitas cloud?
