# Lembar Soal Ujian Mahasiswa
## Pertemuan 02: Evolusi Teknologi — Dari Sistem Terdistribusi ke Komputasi Awan

- **Mata Kuliah:** Komputasi Awan (*Cloud Computing*)
- **Kode MK / Bobot:** TI433946 / 3 SKS
- **Materi Rujukan:** `Pertemuan_02_Evolusi_Sistem_Terdistribusi_ke_Cloud.md`
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
**Karakteristik:** Menguji memori faktual, nama tokoh/sejarah, akronim, dan definisi dasar. Jawaban singkat dan padat dalam 1 menit.  
**Alokasi Waktu:** 1 Menit per Soal (Total: 6 Menit)

#### Soal 2.1 (Level 1 - 1 Menit)
Siapakah ilmuwan komputer yang pada tahun 1961 memprediksi bahwa komputasi suatu saat nanti akan diorganisir sebagai utilitas publik seperti telepon dan listrik?

#### Soal 2.2 (Level 1 - 1 Menit)
Sebutkan tiga pilar yang membentuk singkatan Teorema CAP!

#### Soal 2.3 (Level 1 - 1 Menit)
Apa singkatan dari model transaksi data ACID pada sistem basis data relasional tradisional?

#### Soal 2.4 (Level 1 - 1 Menit)
Sebutkan kepanjangan dari akronim BASE pada sistem data cloud modern!

#### Soal 2.5 (Level 1 - 1 Menit)
Sebutkan satu contoh proyek komputasi ilmiah nyata berskala global yang memanfaatkan arsitektur *Grid Computing*!

#### Soal 2.6 (Level 1 - 1 Menit)
Dalam Teorema PACELC, apa kepanjangan dari huruf P-A-C dan E-L-C?

---

### BAGIAN II: TINGKAT KESULITAN LEVEL 2
**Karakteristik:** Menguji pemahaman konsep, membedakan karakteristik komputasi, dan penjelasan ringkas dalam 2-3 kalimat.  
**Alokasi Waktu:** 2 Menit per Soal (Total: 12 Menit)

#### Soal 2.7 (Level 2 - 2 Menit)
Jelaskan konsep inovasi *Time-Sharing* pada era komputer Mainframe tahun 1960-an!

#### Soal 2.8 (Level 2 - 2 Menit)
Jelaskan perbedaan mendasar antara *Cluster Computing* dan *Grid Computing* dari segi lokasi fisik node-nya!

#### Soal 2.9 (Level 2 - 2 Menit)
Mengapa homogenitas perangkat keras pada *Cluster Computing* berbeda dengan *Grid Computing*?

#### Soal 2.10 (Level 2 - 2 Menit)
Jelaskan apa yang dimaksud dengan sifat *Eventual Consistency* pada model data BASE!

#### Soal 2.11 (Level 2 - 2 Menit)
Mengapa sistem terdistribusi di dunia nyata tidak mungkin memilih kombinasi CA (*Consistency + Availability*) tanpa *Partition Tolerance (P)*?

#### Soal 2.12 (Level 2 - 2 Menit)
Sebutkan tiga faktor teknologi pendukung yang memicu kelahiran *Cloud Computing* di pertengahan era 2000-an!

---

### BAGIAN III: TINGKAT KESULITAN LEVEL 3
**Karakteristik:** Penerapan prinsip teoritis pada mekanisme sistem dan penjelasan komparasi arsitektural terstruktur.  
**Alokasi Waktu:** 3 Menit per Soal (Total: 18 Menit)

#### Soal 2.13 (Level 3 - 3 Menit)
Jelaskan apa yang terjadi pada sistem bertipe **CP (Consistency + Partition Tolerance)** ketika terjadi pemisahan jaringan (*network partition*) antar-node!

#### Soal 2.14 (Level 3 - 3 Menit)
Jelaskan apa yang terjadi pada sistem bertipe **AP (Availability + Partition Tolerance)** ketika terjadi pemisahan jaringan antar-node!

#### Soal 2.15 (Level 3 - 3 Menit)
Mengapa kelemahan model antrean batch (*job queue*) pada Grid Computing diperbaiki oleh model *On-Demand Self-Service* pada Cloud Computing?

#### Soal 2.16 (Level 3 - 3 Menit)
Uraikan arti dari sifat *Soft-State* pada model konsistensi BASE dan bandingkan dengan model ACID!

#### Soal 2.17 (Level 3 - 3 Menit)
Jelaskan bagaimana Teorema PACELC menjelaskan karakteristik basis data Amazon DynamoDB sebagai sistem **PA/EL**!

#### Soal 2.18 (Level 3 - 3 Menit)
Bandingkan mekanisme isolasi beban kerja (*workload isolation*) antara Cluster Computing konvensional dengan Cloud Computing modern!

---

### BAGIAN IV: TINGKAT KESULITAN LEVEL 4
**Karakteristik:** Analisis mendalam trade-off, evaluasi kasus pemilihan basis data terdistribusi, dan pemecahan dilema teknis.  
**Alokasi Waktu:** 4 Menit per Soal (Total: 24 Menit)

#### Soal 2.19 (Level 4 - 4 Menit)
Sebuah bank digital sedang merancang sistem buku besar saldo (*ledger balance*) nasabah. Analisis mengapa arsitek cloud bank tersebut WAJIB memilih model **CP** (atau ACID) dan tidak boleh mengadopsi model **AP** (atau BASE)!

#### Soal 2.20 (Level 4 - 4 Menit)
Sebaliknya, analisislah mengapa platform media sosial (seperti Twitter/X atau Instagram) memilih model **AP** dengan konsistensi *BASE* untuk fitur umpan kiriman (*news feed*) dan tombol suka (*likes*)!

#### Soal 2.21 (Level 4 - 4 Menit)
Analisis fenomena *Split-Brain* pada sistem klaster terdistribusi yang mengalami partisi jaringan, dan bagaimana algoritma konsensus kuorum (seperti Raft atau Paxos) mencegah terjadinya kerusakan data!

#### Soal 2.22 (Level 4 - 4 Menit)
Bandingkan arsitektur Client-Server pada era 1990-an dengan arsitektur Cloud Computing modern dalam hal skalabilitas dan penanganan kegagalan (*fault tolerance*)!

#### Soal 2.23 (Level 4 - 4 Menit)
Mengapa protokol dan middleware Grid Computing (seperti Globus Toolkit) pada akhirnya gagal diadopsi secara masif oleh sektor industri komersial dan kalah telak oleh model Cloud Computing?

#### Soal 2.24 (Level 4 - 4 Menit)
Pada Teorema PACELC, analisislah kompromi yang terjadi pada sistem yang memilih opsi **PC/EC** (seperti Google Cloud Spanner atau PostgreSQL terdistribusi)!

---

### BAGIAN V: TINGKAT KESULITAN LEVEL 5
**Karakteristik:** Evaluasi strategis kasus arsitektur microservices tingkat lanjut, perancangan skema konsistensi data terdistribusi, dan pemecahan kasus sistem perbankan/e-commerce.  
**Alokasi Waktu:** 5 Menit per Soal (Total: 30 Menit)

#### Soal 2.25 (Level 5 - 5 Menit)
**Kasus Perancangan Microservices E-Commerce Terdistribusi:**  
Sebuah platform belanja daring berskala nasional sedang merancang ulang dua layanan mikro:  
1. *Layanan Keranjang Belanja & Riwayat Produk yang Dilihat*  
2. *Layanan Pemotongan Saldo Dompet Digital & Eksekusi Pembayaran*  
Rancanglah strategi klasifikasi teorema CAP (apakah memilih **AP** atau **CP**) untuk masing-masing layanan di atas! Uraikan justifikasi arsitektural dan dampak teknis yang akan terjadi jika Anda salah membalikkan pilihan tersebut!

#### Soal 2.26 (Level 5 - 5 Menit)
Evaluasilah mengapa aplikasi cloud modern berskala global (seperti Netflix atau Uber) cenderung beralih dari model arsitektur database monolitik ACID ke pola arsitektur *Event-Driven Architecture* dengan prinsip BASE dan *Saga Pattern*!

#### Soal 2.27 (Level 5 - 5 Menit)
Rancang sebuah skenario pengujian ketahanan arsitektur (*Chaos Engineering*) untuk menguji apakah sistem basis data cloud Anda benar-benar memenuhi kriteria *Partition Tolerance* saat terjadi pemutusan kabel fiber optik antar-data center!

#### Soal 2.28 (Level 5 - 5 Menit)
Analisis secara kritis bagaimana Teorema CAP berevolusi menjadi Teorema PACELC oleh Daniel Abadi, dan jelaskan mengapa Teorema CAP dianggap tidak lengkap dalam menggambarkan kinerja operasional sistem cloud harian!

#### Soal 2.29 (Level 5 - 5 Menit)
Rancanglah arsitektur sinkronisasi data untuk aplikasi mobile perbankan mikro di pedesaan dengan kondisi sinyal internet sangat tidak stabil (*Offline-First*), dengan mengintegrasikan prinsip *Eventual Consistency* dan algoritma resolusi konflik (*Conflict-Free Replicated Data Types / CRDTs*)!

#### Soal 2.30 (Level 5 - 5 Menit)
Nilai dan kritiklah argumen berikut: *"Dengan teknologi jaringan 5G dan interkoneksi serat optik berkecepatan terabit di data center modern, kegagalan partisi jaringan sudah punah sehingga kita tidak perlu lagi memikirkan Teorema CAP."* Buktikan ketidakbenaran argumen tersebut secara teknis!
