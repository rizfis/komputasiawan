# Lembar Soal Ujian Mahasiswa
## Pertemuan 03: Arsitektur Komputasi Awan

- **Mata Kuliah:** Komputasi Awan (*Cloud Computing*)
- **Kode MK / Bobot:** TI433946 / 3 SKS
- **Materi Rujukan:** `Pertemuan_03_Arsitektur_Cloud_Computing.md`
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
**Karakteristik:** Menguji definisi aktor, komponen dasar front-end/back-end, dan terminologi topologi cloud.  
**Alokasi Waktu:** 1 Menit per Soal (Total: 6 Menit)

#### Soal 3.1 (Level 1 - 1 Menit)
Sebutkan 5 aktor utama dalam arsitektur referensi komputasi awan berdasarkan standar NIST SP 500-292!

#### Soal 3.2 (Level 1 - 1 Menit)
Apa fungsi utama entitas *Cloud Auditor* dalam ekosistem komputasi awan menurut NIST?

#### Soal 3.3 (Level 1 - 1 Menit)
Sebutkan dua komponen antarmuka yang berada pada domain *Front-End* komputasi awan di sisi konsumen!

#### Soal 3.4 (Level 1 - 1 Menit)
Apa yang dimaksud dengan *Availability Zone (AZ)* dalam hierarki infrastruktur fisik cloud provider?

#### Soal 3.5 (Level 1 - 1 Menit)
Apa peran utama dari *Edge Locations* atau *Points of Presence (PoP)* pada jaringan cloud global?

#### Soal 3.6 (Level 1 - 1 Menit)
Apa istilah yang digunakan untuk menggambarkan satu instans infrastruktur server fisik yang hanya melayani satu pelanggan tunggal tanpa berbagi sumber daya?

---

### BAGIAN II: TINGKAT KESULITAN LEVEL 2
**Karakteristik:** Menguji pemahaman konsep peran, perbedaan single-tenant vs multi-tenant, dan karakteristik topologi.  
**Alokasi Waktu:** 2 Menit per Soal (Total: 12 Menit)

#### Soal 3.7 (Level 2 - 2 Menit)
Jelaskan perbedaan peran antara *Cloud Broker* dan *Cloud Carrier* berdasarkan dokumen NIST SP 500-292!

#### Soal 3.8 (Level 2 - 2 Menit)
Jelaskan apa yang dimaksud dengan masalah *Noisy Neighbor* (*tetangga berisik*) dalam lingkungan Multi-Tenancy!

#### Soal 3.9 (Level 2 - 2 Menit)
Mengapa pusat data yang berada dalam satu Region yang sama dibagi menjadi beberapa *Availability Zone* yang terpisah jarak fisiknya?

#### Soal 3.10 (Level 2 - 2 Menit)
Jelaskan fungsi komponen *API Gateway* yang berdiri di antara domain Front-End dan Back-End cloud provider!

#### Soal 3.11 (Level 3.11 / Level 2 - 2 Menit)
Jelaskan kelebihan dan kekurangan arsitektur *Single-Tenant* dibandingkan dengan arsitektur *Multi-Tenant*!

#### Soal 3.12 (Level 2 - 2 Menit)
Bagaimana teknologi *Software-Defined Networking (SDN)* seperti enkapsulasi VXLAN menjaga isolasi paket data antar-pelanggan pada back-end cloud?

---

### BAGIAN III: TINGKAT KESULITAN LEVEL 3
**Karakteristik:** Penerapan alur orkestrasi internal, mekanisme penanganan noisy neighbor, dan strategi Multi-AZ.  
**Alokasi Waktu:** 3 Menit per Soal (Total: 18 Menit)

#### Soal 3.13 (Level 3 - 3 Menit)
Uraikan peran dan cara kerja komponen *Cloud Controller* (seperti Nova pada OpenStack atau Borg pada Google) dalam merespons perintah pembuatan mesin virtual baru!

#### Soal 3.14 (Level 3 - 3 Menit)
Jelaskan mekanisme teknik *CPU & Memory Pinning* dalam mengisolasi sumber daya pada server multi-tenant untuk menghindari fluktuasi kinerja!

#### Soal 3.15 (Level 3 - 3 Menit)
Bagaimana mekanisme *cgroups (Control Groups)* pada kernel sistem operasi digunakan oleh cloud provider untuk mencegah monopoli I/O disk dan jaringan oleh salah satu tenant?

#### Soal 3.16 (Level 3 - 3 Menit)
Jelaskan perbedaan karakteristik teknis dan kompromi arsitektural antara *Replikasi Sinkron (Synchronous)* dan *Replikasi Asinkron (Asynchronous)* antar-Availability Zone!

#### Soal 3.17 (Level 3 - 3 Menit)
Uraikan bagaimana arsitektur *Edge Locations (PoP)* bekerja mempercepat pengiriman konten situs web statis dan dinamis ke pengguna di seluruh dunia!

#### Soal 3.18 (Level 3 - 3 Menit)
Jelaskan kapan sebuah organisasi bisnis disarankan memilih opsi *Dedicated Instances / Dedicated Hosts* di cloud daripada instans multi-tenant standar!

---

### BAGIAN IV: TINGKAT KESULITAN LEVEL 4
**Karakteristik:** Analisis mendalam skenario kegagalan, komparasi ketahanan arsitektur, dan evaluasi kompromi latensi multi-region.  
**Alokasi Waktu:** 4 Menit per Soal (Total: 24 Menit)

#### Soal 3.19 (Level 4 - 4 Menit)
Sebuah arsitektur aplikasi e-commerce menempatkan dua server web di AZ-A dan satu server basis data tunggal juga di AZ-A. Analisis titik kegagalan tunggal (*Single Point of Failure / SPoF*) dari topologi ini dan bagaimana arsitektur Multi-AZ yang tepat memperbaikinya!

#### Soal 3.20 (Level 4 - 4 Menit)
Analisis kompromi hukum dan latensi ketika sebuah aplikasi perbankan nasional memutuskan untuk mengadopsi arsitektur **Multi-Region Deployment** antara Region Jakarta (`ap-southeast-3`) dan Region Tokyo (`ap-northeast-1`)!

#### Soal 3.21 (Level 4 - 4 Menit)
Pada lapisan penyimpanan back-end cloud (seperti AWS S3 atau Ceph), bagaimana mekanisme *Erasure Coding* menggantikan sistem replikasi *Three-Way Mirroring* tradisional untuk efisiensi biaya dan ketahanan disk?

#### Soal 3.22 (Level 4 - 4 Menit)
Analisis peran standar NIST SP 500-292 dalam membantu tim tata kelola perusahaan (*Enterprise Governance*) menyusun kontrak hukum dan *Service Level Agreement (SLA)* dengan Cloud Provider dan Cloud Carrier!

#### Soal 3.23 (Level 4 - 4 Menit)
Bandingkan mekanisme proteksi serangan Distributed Denial of Service (DDoS) yang dijalankan pada lapisan *Edge Locations / PoP* versus proteksi yang dijalankan langsung pada server instans asal (*Origin Server*)!

#### Soal 3.24 (Level 4 - 4 Menit)
Sebuah perusahaan teknologi finansial mengalami penurunan drastis pada metrik I/O aplikasi basis datanya setiap pukul 02.00 pagi akibat proses backup otomatis oleh tenant lain di host fisik yang sama. Analisis opsi teknis apa saja yang dapat diambil oleh perusahaan tersebut kepada cloud provider untuk menjamin kestabilan I/O!

---

### BAGIAN V: TINGKAT KESULITAN LEVEL 5
**Karakteristik:** Desain arsitektur ketersediaan tinggi (HA) dengan toleransi bencana (DR), kepatuhan perbankan, dan kalkulasi latensi RPO/RTO.  
**Alokasi Waktu:** 5 Menit per Soal (Total: 30 Menit)

#### Soal 3.25 (Level 5 - 5 Menit)
**Kasus Desain Arsitektur Perbankan Digital Nasional:**  
Sistem Perbankan Digital Nasional mewajibkan tingkat ketersediaan (*uptime*) minimal **99.99%** dan data transaksi tabungan tidak boleh hilang sedikit pun (**Zero Data Loss / RPO = 0**) meskipun satu data center fisik meledak atau mengalami pemadaman total. Rancanglah cetak biru (*blueprint*) arsitektur sistem komputasi awan yang memanfaatkan konsep *Regions*, *Availability Zones*, *Load Balancer*, dan replikasi basis data untuk memenuhi mandat tersebut!

#### Soal 3.26 (Level 5 - 5 Menit)
Evaluasilah dilema arsitektur: Kapan sebuah perusahaan rintisan (*startup*) unicorn harus beralih dari model arsitektur *Multi-AZ dalam satu Region* menuju arsitektur *Active-Active Multi-Region*, serta kompromi biaya dan kompleksitas data apa yang harus mereka bayar?

#### Soal 3.27 (Level 5 - 5 Menit)
Rancanglah sebuah diagram teks arsitektur dan alur komunikasi lengkap dari hulu ke hilir saat seorang pengguna di ponsel pintar membuka aplikasi mobile hingga instruksinya dieksekusi di database cloud back-end, dengan mencakup seluruh komponen NIST SP 500-292 dan domain Front-End/Back-End!

#### Soal 3.28 (Level 5 - 5 Menit)
Analisis strategi isolasi keamanan dan isolasi performa pada penyedia cloud publik: Bagaimana penyedia cloud menjamin bahwa eksploitasi celah keamanan *hardware-level* (seperti serangan CPU cache *Spectre* dan *Meltdown*) tidak memungkinkan satu tenant mencuri kunci kriptografis tenant lain pada CPU fisik yang sama?

#### Soal 3.29 (Level 5 - 5 Menit)
Sebuah institusi pertahanan negara merencanakan pembangunan pusat komputasi awan mandiri (*Private Cloud Sovereign*). Susunlah rancangan pembagian zona topologi fisik (termasuk kriteria pasokan energi, pendingin, dan interkoneksi jaringan) yang mengadopsi standar Availability Zone dan Region cloud komersial untuk menjamin kedaulatan informasi militer!

#### Soal 3.30 (Level 5 - 5 Menit)
Nilai efektivitas peran *Cloud Broker* dalam skenario perusahaan multinasional yang mengadopsi strategi *Hybrid dan Multi-Cloud* (menggabungkan data center privat lokal, AWS, Azure, dan Alibaba Cloud). Jelaskan 3 fungsi nilai tambah utama yang dihadirkan oleh Cloud Broker tersebut!
