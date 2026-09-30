# Lembar Soal Ujian Mahasiswa
## Pertemuan 11: Keamanan Komputasi Awan (IAM, Enkripsi, dan Isolasi Jaringan)

- **Mata Kuliah:** Komputasi Awan (*Cloud Computing*)
- **Kode MK / Bobot:** TI433946 / 3 SKS
- **Materi Rujukan:** `Pertemuan_11_Keamanan_Cloud_IAM_dan_Enkripsi.md`
- **Bentuk Evaluasi:** Uraian / Essay (Analisis Mandiri & Keamanan Sistem)
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
**Karakteristik:** Menguji definisi dasar keamanan cloud, akronim IAM/NACL/KMS, dan terminologi enkripsi.  
**Alokasi Waktu:** 1 Menit per Soal (Total: 6 Menit)

#### Soal 11.1 (Level 1 - 1 Menit)
Apa kepanjangan dari akronim IAM dalam administrasi keamanan komputasi awan?

#### Soal 11.2 (Level 1 - 1 Menit)
Dalam *Shared Responsibility Model*, apakah keamanan fisik gedung pusat data (*physical security*) menjadi tanggung jawab Penyedia Cloud atau Pelanggan?

#### Soal 11.3 (Level 1 - 1 Menit)
Sebutkan tiga kondisi siklus hidup data (*Data Lifecycle States*) dalam mekanisme perlindungan enkripsi data!

#### Soal 11.4 (Level 1 - 1 Menit)
Standar algoritma enkripsi simetris apa yang menjadi standar industri global untuk mengamankan *Data-at-Rest* pada media penyimpanan cloud?

#### Soal 11.5 (Level 1 - 1 Menit)
Apa kepanjangan dari akronim NACL dalam arsitektur jaringan Virtual Private Cloud (VPC)?

#### Soal 11.6 (Level 1 - 1 Menit)
Sebutkan prinsip keamanan dasar yang menyatakan bahwa pengguna atau sistem hanya boleh diberikan hak akses minimum absolut yang dibutuhkan untuk tugasnya!

---

### BAGIAN II: TINGKAT KESULITAN LEVEL 2
**Karakteristik:** Membedakan Security OF vs IN the Cloud, Stateful SG vs Stateless NACL, dan konsep Confidential Computing.  
**Alokasi Waktu:** 2 Menit per Soal (Total: 12 Menit)

#### Soal 11.7 (Level 2 - 2 Menit)
Jelaskan perbedaan mendasar antara konsep **Security OF the Cloud** dan **Security IN the Cloud** pada *Shared Responsibility Model*!

#### Soal 11.8 (Level 2 - 2 Menit)
Jelaskan mengapa Security Group (SG) disebut bersifat **Stateful** sedangkan NACL disebut bersifat **Stateless**!

#### Soal 11.9 (Level 2 - 2 Menit)
Pada tingkat hierarki infrastruktur manakah Security Group dan NACL masing-masing diterapkan di dalam Virtual Private Cloud (VPC)?

#### Soal 11.10 (Level 2 - 2 Menit)
Apa yang dimaksud dengan teknologi *Confidential Computing* dalam pengamanan *Data-in-Use*?

#### Soal 11.11 (Level 2 - 2 Menit)
Sebutkan 4 elemen kunci yang selalu terdapat dalam blok pernyataan (*Statement*) berkas kebijakan IAM format JSON!

#### Soal 11.12 (Level 2 - 2 Menit)
Mengapa menggunakan akun Administrator tingkat tertinggi (*Root Account*) untuk operasional harian di cloud dianggap sebagai pelanggaran berat praktik keamanan?

---

### BAGIAN III: TINGKAT KESULITAN LEVEL 3
**Karakteristik:** Penerapan kebijakan IAM JSON, mekanisme Envelope Encryption, dan perancangan aturan firewall berlapis.  
**Alokasi Waktu:** 3 Menit per Soal (Total: 18 Menit)

#### Soal 11.13 (Level 3 - 3 Menit)
Perhatikan kebijakan IAM JSON berikut:
```json
{
  "Effect": "Allow",
  "Action": ["s3:GetObject"],
  "Resource": "arn:aws:s3:::berkas-ujian-unida/*",
  "Condition": {
    "IpAddress": {
      "aws:SourceIp": "10.14.0.0/16"
    }
  }
}
```
Uraikan secara detail hak akses apa yang diberikan oleh kebijakan di atas, siapa yang boleh melakukannya, dan apa syarat kondisinya!

#### Soal 11.14 (Level 3 - 3 Menit)
Uraikan mekanisme kerja teknik **Enkripsi Amplop (*Envelope Encryption*)** yang menggunakan *Customer Master Key (CMK)* dan *Data Encryption Key (DEK)* pada layanan Key Management Service (KMS)!

#### Soal 11.15 (Level 3 - 3 Menit)
Jelaskan urutan evaluasi aturan (*Evaluation Order*) pada NACL dan apa fungsi dari nomor urut aturan (*Rule Number*)!

#### Soal 11.16 (Level 3 - 3 Menit)
Bandingkan tanggung jawab keamanan pada lapisan Sistem Operasi (OS) mesin virtual antara model **IaaS** dan **PaaS** berdasarkan *Shared Responsibility Model*!

#### Soal 11.17 (Level 3 - 3 Menit)
Uraikan mengapa protokol **TLS 1.3** lebih aman dan lebih cepat dalam mengamankan *Data-in-Transit* dibandingkan protokol TLS versi sebelumnya (TLS 1.2)!

#### Soal 11.18 (Level 3 - 3 Menit)
Jelaskan peran fitur **Multi-Factor Authentication (MFA)** dalam menggagalkan serangan pencurian kata sandi berbasis *Phishing* atau *Credential Stuffing* pada akun konsol cloud!

---

### BAGIAN IV: TINGKAT KESULITAN LEVEL 4
**Karakteristik:** Analisis mendalam investigasi insiden kebocoran data S3, trade-off evaluasi kebijakan IAM kompleks, dan pertahanan jaringan berlapis.  
**Alokasi Waktu:** 4 Menit per Soal (Total: 24 Menit)

#### Soal 11.19 (Level 4 - 4 Menit)
**Kasus Investigasi Kebocoran Object Storage:**  
Sebuah perusahaan asuransi menyimpan jutaan riwayat klaim medis nasabah di layanan AWS S3. Suatu hari data tersebut bocor dan dapat diunduh bebas di internet. Investigasi forensik membuktikan bahwa: (1) Data center fisik penyedia cloud tidak pernah disusupi, dan (2) Karyawan IT junior mematikan opsi *"Block Public Access"* pada bucket dan menetapkan izin `Principal: "*"` serta `Action: "s3:GetObject"`.  
Analisis secara hukum dan etika: Pihak manakah yang memikul tanggung jawab penuh atas insiden tersebut berdasarkan *Shared Responsibility Model*? Berikan argumentasi hukum teknisnya!

#### Soal 11.20 (Level 4 - 4 Menit)
Analisis konflik logika evaluasi kebijakan IAM: Jika seorang pengguna cloud diikat oleh dua kebijakan, di mana Kebijakan A menyatakan `Effect: Allow` pada `Action: "ec2:*"` dan Kebijakan B menyatakan `Effect: Deny` pada `Action: "ec2:TerminateInstances"`, apakah pengguna tersebut dapat menghapus instans EC2? Uraikan hukum evaluasi logika IAM!

#### Soal 11.21 (Level 4 - 4 Menit)
Analisis perbandingan strategi pertahanan mendalam (*Defense in Depth*) pada arsitektur jaringan Virtual Private Cloud (VPC) yang mengombinasikan **Public Subnet**, **Private Subnet**, **NACL**, dan **Security Group**!

#### Soal 11.22 (Level 4 - 4 Menit)
Bandingkan mekanisme manajemen kunci enkripsi antara **KMS dengan Kunci Dikelola Cloud (AWS-Managed Key)** versus **KMS dengan Kunci Dikelola Pelanggan (Customer-Managed Key / CMK)** ditinjau dari kontrol audit dan biaya!

#### Soal 11.23 (Level 4 - 4 Menit)
Analisis bahaya penggunaan kredensial akses jangka panjang (*Long-Lived Access Keys*) yang disematkan (*hardcoded*) di dalam kode aplikasi, dan bagaimana fitur **IAM Roles / Service Accounts** memberikan solusi yang jauh lebih aman!

#### Soal 11.24 (Level 4 - 4 Menit)
Sebuah perusahaan multinasional mewajibkan seluruh data cadangan yang tersimpan di cloud dienkripsi secara *Client-Side Encryption* sebelum diunggah ke penyedia cloud. Analisis kelebihan dan kerugian teknis pendekatan ini dibandingkan *Server-Side Encryption*!

---

### BAGIAN V: TINGKAT KESULITAN LEVEL 5
**Karakteristik:** Desain arsitektur keamanan Zero Trust enterprise, tata kelola IAM skala korporasi, mitigasi ancaman ransomware, dan etika privasi data.  
**Alokasi Waktu:** 5 Menit per Soal (Total: 30 Menit)

#### Soal 11.25 (Level 5 - 5 Menit)
**Kasus Perancangan Arsitektur Keamanan Perbankan Zero Trust:**  
Rancanglah sebuah cetak biru arsitektur keamanan komprehensif berbasis filosofi **Zero Trust (*Never Trust, Always Verify*)** untuk aplikasi transaksi perbankan digital di cloud publik yang memproses data finansial nasabah, mencakup pilar Identitas (IAM), Jaringan (VPC/Firewall), Data (Enkripsi KMS), dan Audit Log!

#### Soal 11.26 (Level 5 - 5 Menit)
Rancang sebuah kebijakan pencegahan dan mitigasi bencana serangan **Ransomware** yang mengunci seluruh data di Object Storage cloud publik, memanfaatkan fitur **S3 Object Lock (WORM)**, **Versioning**, dan **Replikasi Lintas Akun (*Cross-Account Replication*)**!

#### Soal 11.27 (Level 5 - 5 Menit)
Susunlah kebijakan pengawasan tata kelola IAM otomatis (*Policy-as-Code*) menggunakan kerangka kerja *Service Control Policies (SCPs)* pada tingkat organisasi korporasi (AWS Organizations) untuk menegakkan standar kepatuhan keamanan pada ratusan akun pengembang!

#### Soal 11.28 (Level 5 - 5 Menit)
Analisis secara kritis risiko keamanan dalam integrasi CI/CD modern: Bagaimana sebuah pipeline GitHub Actions dapat dieksploitasi untuk mencuri peran akses ke cloud AWS, dan bagaimana arsitektur autentikasi berbasis **OpenID Connect (OIDC)** menghilangkan penggunaan kredensial statis secara elegan?

#### Soal 11.29 (Level 5 - 5 Menit)
Rancang sebuah rencana tanggap darurat insiden keamanan (*Security Incident Response Plan*) langkah-demi-langkah saat sistem deteksi cloud (seperti GuardDuty) mendeteksi bahwa sebuah instans EC2 telah terinfeksi malware dan sedang melakukan komunikasi ke server pengendali peretas (*Command & Control / C2*)!

#### Soal 11.30 (Level 5 - 5 Menit)
Evaluasilah dimensi etika ilmu pengetahuan dan tanggung jawab moral (CPL02) seorang insinyur keamanan cloud terkait transparansi penanganan insiden: Mengapa menyembunyikan insiden kebocoran data dari regulator dan publik merupakan kejahatan etis dan hukum yang merusak ekosistem digital nasional?
