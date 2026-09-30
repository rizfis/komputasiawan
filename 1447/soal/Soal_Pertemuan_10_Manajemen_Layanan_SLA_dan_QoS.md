# Lembar Soal Ujian Mahasiswa
## Pertemuan 10: Manajemen Layanan Cloud (SLA, QoS, dan Ketersediaan Tinggi)

- **Mata Kuliah:** Komputasi Awan (*Cloud Computing*)
- **Kode MK / Bobot:** TI433946 / 3 SKS
- **Materi Rujukan:** `Pertemuan_10_Manajemen_Layanan_SLA_dan_QoS.md`
- **Bentuk Evaluasi:** Uraian / Essay (Analisis Mandiri & Perhitungan Matematis)
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
**Karakteristik:** Menguji kepanjangan akronim SLI/SLO/SLA, definisi MTBF/MTTR, dan istilah QoS dasar.  
**Alokasi Waktu:** 1 Menit per Soal (Total: 6 Menit)

#### Soal 10.1 (Level 1 - 1 Menit)
Apa kepanjangan dari akronim SLI, SLO, dan SLA dalam metodologi keandalan layanan cloud?

#### Soal 10.2 (Level 1 - 1 Menit)
Tuliskan rumus matematika sederhana untuk menghitung persentase ketersediaan (*Availability*) berdasarkan nilai MTBF dan MTTR!

#### Soal 10.3 (Level 1 - 1 Menit)
Apa kepanjangan dari parameter MTBF dan MTTR?

#### Soal 10.4 (Level 1 - 1 Menit)
Apa rumus untuk menghitung *Error Budget* (anggaran kesalahan) jika diketahui target SLO sistem?

#### Soal 10.5 (Level 1 - 1 Menit)
Berapa istilah sebutan populer untuk sistem yang memiliki tingkat ketersediaan 99.99% dalam standar industri komputasi awan?

#### Soal 10.6 (Level 1 - 1 Menit)
Sebutkan dua contoh metrik *Quality of Service (QoS)* yang mengukur performa jaringan selain ketersediaan hidup/mati server!

---

### BAGIAN II: TINGKAT KESULITAN LEVEL 2
**Karakteristik:** Menguji pemahaman konsep perbedaan SLI vs SLO vs SLA, aturan error budget, dan definisi metrik QoS.  
**Alokasi Waktu:** 2 Menit per Soal (Total: 12 Menit)

#### Soal 10.7 (Level 2 - 2 Menit)
Jelaskan perbedaan mendasar antara **SLO (*Service Level Objective*)** dan **SLA (*Service Level Agreement*)** dari aspek konsekuensi hukum dan finansialnya!

#### Soal 10.8 (Level 2 - 2 Menit)
Jelaskan bagaimana konsep *Error Budget* mengatur kebijakan rilis fitur baru bagi tim pengembang perangkat lunak!

#### Soal 10.9 (Level 2 - 2 Menit)
Apa yang dimaksud dengan metrik **Jitter** pada Quality of Service (QoS) dan mengapa jitter yang tinggi sangat mengganggu aplikasi telekonferensi video?

#### Soal 10.10 (Level 2 - 2 Menit)
Jelaskan apa yang dimaksud dengan kompensasi finansial berupa **Service Credits** dalam klausul kontrak SLA cloud!

#### Soal 10.11 (Level 2 - 2 Menit)
Mengapa ketersediaan akhir dari dua komponen yang dirangkai secara **Serial** selalu LEBIH RENDAH daripada komponen terlemahnya? Jelaskan secara matematis!

#### Soal 10.12 (Level 2 - 2 Menit)
Jelaskan perbedaan antara *Network Latency* (Round-Trip Time / RTT) dan *Throughput* menggunakan analogi pipa air!

---

### BAGIAN III: TINGKAT KESULITAN LEVEL 3
**Karakteristik:** Penerapan rumus ketersediaan serial dan paralel, kalkulasi downtime matematis, dan perumusan SLI.  
**Alokasi Waktu:** 3 Menit per Soal (Total: 18 Menit)

#### Soal 10.13 (Level 3 - 3 Menit)
Hitunglah toleransi waktu henti (*downtime*) dalam satuan menit dalam kurun waktu satu bulan (diasumsikan 30 hari = 43.200 menit) untuk sebuah layanan cloud dengan jaminan SLA ketersediaan **99.9%**!

#### Soal 10.14 (Level 3 - 3 Menit)
Sebuah sistem web dirancang dengan dua buah server aplikasi identik yang disusun secara **Paralel** di balik load balancer. Masing-masing server memiliki ketersediaan mandiri sebesar **99.0%** ($A_1 = 0.99$ dan $A_2 = 0.99$). Hitung ketersediaan efektif gabungan kedua server tersebut!

#### Soal 10.15 (Level 3 - 3 Menit)
Sebuah server basis data memiliki rata-rata waktu operasional normal sebelum rusak (MTBF) selama 720 jam, dan membutuhkan rata-rata waktu pemulihan tim teknis (MTTR) selama 1.5 jam setiap kali terjadi kerusakan. Hitung persentase ketersediaan (*Availability*) server tersebut!

#### Soal 10.16 (Level 3 - 3 Menit)
Rumuskan sebuah spesifikasi indikator tingkat layanan (**SLI**) dan target (**SLO**) yang terukur secara presisi untuk layanan API pembayaran perbankan digital!

#### Soal 10.17 (Level 3 - 3 Menit)
Uraikan empat komponen penundaan yang membentuk total latensi jaringan (*Total Network Delay*): *Propagation Delay*, *Transmission Delay*, *Queuing Delay*, dan *Processing Delay*!

#### Soal 10.18 (Level 3 - 3 Menit)
Jelaskan mengapa downtime yang direncanakan untuk pemeliharaan rutin (*Scheduled Maintenance Window*) sering kali dikecualikan (*excluded*) dari perhitungan pelanggaran penalti SLA oleh cloud provider!

---

### BAGIAN IV: TINGKAT KESULITAN LEVEL 4
**Karakteristik:** Analisis komparasi trade-off biaya "The Nines", evaluasi kegagalan kaskade, dan audit klausul SLA komersial.  
**Alokasi Waktu:** 4 Menit per Soal (Total: 24 Menit)

#### Soal 10.19 (Level 4 - 4 Menit)
Analisis secara kritis mengapa biaya infrastruktur untuk menaikkan tingkat ketersediaan dari **99.9% (*Three Nines*)** ke **99.999% (*Five Nines*)** meningkat secara eksponensial (bisa mencapai 10x lipat lebih mahal), padahal persentasenya hanya naik kurang dari 0.1%!

#### Soal 10.20 (Level 4 - 4 Menit)
Analisis risiko fenomena kegagalan berantai (*Cascading Failures*) pada sistem cloud terdistribusi saat salah satu layanan mikro (*microservice*) mengalami peningkatan latensi drastis, dan bagaimana penerapan pola arsitektur **Circuit Breaker** memitigasinya!

#### Soal 10.21 (Level 4 - 4 Menit)
Sebuah arsitektur sistem komputasi awan terdiri dari:  
1. *DNS Provider (99.99%)*  
2. *Load Balancer (99.99%)*  
3. *Aplikasi Web Cluster (99.9%)*  
4. *Basis Data Tunggal (99.0%)*  
Keempat komponen tersebut dirangkai secara berurutan (**Serial**). Analisis komponen manakah yang menjadi pembatas utama (*bottleneck*) ketersediaan sistem, dan berapa ketersediaan total dari rantai sistem tersebut?

#### Soal 10.22 (Level 4 - 4 Menit)
Evaluasilah klausul perjanjian SLA tipikal dari penyedia cloud publik komersial: Mengapa penyedia cloud hanya memberikan kompensasi berupa *Service Credits* dan menolak keras bertanggung jawab atas kerugian bisnis riil (seperti hilangnya potensi omzet penjualan miliaran rupiah) yang diderita pelanggan saat terjadi insiden padam (*outage*)?

#### Soal 10.23 (Level 4 - 4 Menit)
Analisis peran teknik pemantauan **Synthetic Monitoring (Probing)** versus **Real User Monitoring (RUM)** dalam mengukur akurasi metrik SLI ketersediaan aplikasi web!

#### Soal 10.24 (Level 4 - 4 Menit)
Bagaimana penerapan strategi **Degradasi Anggun (*Graceful Degradation*)** menjaga kepatuhan SLA saat sistem mengalami beban puncak yang melampaui kapasitas maksimalnya? Berikan contoh konkretnya pada aplikasi e-commerce!

---

### BAGIAN V: TINGKAT KESULITAN LEVEL 5
**Karakteristik:** Perhitungan matematis sistem komposit kompleks multi-tier, perancangan arsitektur perbankan SLA 99.99%, dan audit kompensasi finansial.  
**Alokasi Waktu:** 5 Menit per Soal (Total: 30 Menit)

#### Soal 10.25 (Level 5 - 5 Menit)
**Kasus Perhitungan Matematis Ketersediaan Sistem Komposit Kompleks:**  
Sebuah sistem perbankan daring dirancang dengan topologi arsitektur berjenjang sebagai berikut:  
1. *Satu Load Balancer* dengan SLA ketersediaan **99.99%** ($A_{\text{LB}} = 0.9999$).  
2. *Dua buah Web Server* identik yang dirangkai secara **Paralel**, masing-masing memiliki SLA **99.0%** ($A_{\text{Web1}} = 0.99$ dan $A_{\text{Web2}} = 0.99$).  
3. *Dua buah Database Server* (Master-Standby dengan auto-failover) yang dirangkai secara **Paralel**, masing-masing memiliki SLA **99.5%** ($A_{\text{DB1}} = 0.995$ dan $A_{\text{DB2}} = 0.995$).  
Ketiga tingkatan di atas (Load Balancer, Subsistem Web, dan Subsistem Database) terhubung secara **Serial**.  
```
[ Load Balancer (99.99%) ]
           |
           v
[ 2x Web Server Paralel (99.0% & 99.0%) ]
           |
           v
[ 2x Database Paralel (99.5% & 99.5%) ]
```
**Instruksi Perhitungan Matematis Lengkap:**  
1. Hitung ketersediaan efektif subsistem Web Server paralel ($A_{\text{Web-Total}}$)!  
2. Hitung ketersediaan efektif subsistem Database paralel ($A_{\text{DB-Total}}$)!  
3. Hitung ketersediaan total ($A_{\text{Total-Sistem}}$) dari keseluruhan arsitektur terintegrasi!  
4. Berapa menit toleransi *downtime* sistem ini dalam kurun waktu satu bulan kalender (30 hari = 43.200 menit)?

#### Soal 10.26 (Level 5 - 5 Menit)
Rancang sebuah kebijakan operasional keandalan (*SRE Policy*) berbasis **Error Budget Policy** yang mengikat tim Pengembang Fitur (*Product Development*) dan tim Operasi (*Site Reliability Engineering / SRE*) saat terjadi perselisihan prioritas kerja!

#### Soal 10.27 (Level 5 - 5 Menit)
Analisis dan rancanglah arsitektur peningkatan keandalan untuk mengubah sistem komposit pada Soal 10.25 agar mampu mencapai tingkat ketersediaan minimal **99.995%**! Identifikasi komponen mana yang harus ditingkatkan dan buktikan dengan perhitungan matematisnya!

#### Soal 10.28 (Level 5 - 5 Menit)
Susunlah dokumen template pelaporan analisis pasca-insiden (*Post-Mortem / Incident Review Report*) berbasis budaya tanpa menyalahkan (*Blameless Post-Mortem*) yang wajib diisi oleh tim teknis setelah terjadi pelanggaran SLA!

#### Soal 10.29 (Level 5 - 5 Menit)
Analisis secara kritis bagaimana metrik **User Experience (Apdex - Application Performance Index)** melengkapi keterbatasan metrik teknis ketersediaan server murni (Uptime/Downtime) dalam menilai kualitas layanan aplikasi!

#### Soal 10.30 (Level 5 - 5 Menit)
Bagaimana nilai etika kejujuran dan amanah dijunjung tinggi dalam pelaporan metrik SLA kepada publik? Analisis kasus manipulasi halaman status (*Status Page Gaming*) di mana penyedia layanan secara sengaja mengubah definisi insiden agar tidak perlu membayar penalti kompensasi finansial kepada pelanggan!
