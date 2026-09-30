# Lembar Soal Ujian Mahasiswa
## Pertemuan 14: Tren Cloud Modern — Serverless, Edge Computing, dan Multi-Cloud

- **Mata Kuliah:** Komputasi Awan (*Cloud Computing*)
- **Kode MK / Bobot:** TI433946 / 3 SKS
- **Materi Rujukan:** `Pertemuan_14_Serverless_Edge_dan_Multi_Cloud.md`
- **Bentuk Evaluasi:** Uraian / Essay (Analisis Mandiri & Desain Arsitektur Modern)
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
**Karakteristik:** Menguji definisi dasar Serverless, akronim FaaS/IaC, batasan waktu eksekusi, dan konsep Edge.  
**Alokasi Waktu:** 1 Menit per Soal (Total: 6 Menit)

#### Soal 14.1 (Level 1 - 1 Menit)
Apa kepanjangan dari akronim FaaS dalam arsitektur komputasi serverless?

#### Soal 14.2 (Level 1 - 1 Menit)
Apa yang dimaksud dengan karakteristik **Scale-to-Zero** pada arsitektur Serverless?

#### Soal 14.3 (Level 1 - 1 Menit)
Berapa batas waktu eksekusi maksimal (*Execution Timeout Limit*) untuk satu fungsi serverless pada layanan AWS Lambda?

#### Soal 14.4 (Level 1 - 1 Menit)
Apa nama alat deklaratif sumber terbuka standar industri yang paling populer untuk mengelola *Infrastructure as Code (IaC)* lintas penyedia cloud?

#### Soal 14.5 (Level 1 - 1 Menit)
Dalam hierarki komputasi terdistribusi, lapisan manakah yang memproses data tepat di lokasi fisik sumber data berada (seperti di kamera atau gateway lokal)?

#### Soal 14.6 (Level 1 - 1 Menit)
Dua argumen parameter default apa yang wajib didefinisikan pada fungsi pengendali utama (*handler function*) Python di AWS Lambda?

---

### BAGIAN II: TINGKAT KESULITAN LEVEL 2
**Karakteristik:** Menguji pemahaman konsep perbedaan Cold Start vs Warm Start, peran Fog Computing, dan keuntungan Multi-Cloud.  
**Alokasi Waktu:** 2 Menit per Soal (Total: 12 Menit)

#### Soal 14.7 (Level 2 - 2 Menit)
Jelaskan fenomena perbedaan antara **Cold Start** dan **Warm Start** pada eksekusi fungsi serverless!

#### Soal 14.8 (Level 2 - 2 Menit)
Mengapa fungsi Serverless (FaaS) diwajibkan bersifat **Stateless**? Di manakah data transaksi seharusnya disimpan?

#### Soal 14.9 (Level 2 - 2 Menit)
Jelaskan peran **Fog Computing** sebagai lapisan perantara antara ribuan perangkat Edge dengan Cloud Terpusat!

#### Soal 14.10 (Level 2 - 2 Menit)
Sebutkan dua motivasi bisnis utama yang mendorong perusahaan mengadopsi strategi **Multi-Cloud**!

#### Soal 14.11 (Level 2 - 2 Menit)
Jelaskan perbedaan model penagihan (*Billing Model*) antara mesin virtual konvensional (IaaS) dengan fungsi Serverless (FaaS)!

#### Soal 14.12 (Level 2 - 2 Menit)
Apa keuntungan menggunakan bahasa deklaratif (HCL) pada Terraform dibandingkan menulis skrip prosedural imperatif (seperti skrip Bash atau Python SDK) untuk membuat infrastruktur cloud?

---

### BAGIAN III: TINGKAT KESULITAN LEVEL 3
**Karakteristik:** Penerapan arsitektur Event-Driven, pemecahan masalah Cold Start, dan skenario mobil otonom Edge Computing.  
**Alokasi Waktu:** 3 Menit per Soal (Total: 18 Menit)

#### Soal 14.13 (Level 3 - 3 Menit)
Uraikan arsitektur pemrosesan berbasis peristiwa (**Event-Driven Architecture**) saat seorang pengguna mengunggah foto profil di aplikasi web menggunakan integrasi S3 Bucket dan Serverless Function!

#### Soal 14.14 (Level 3 - 3 Menit)
Jelaskan mengapa arsitektur sistem kendali darurat rem pada **Kendaraan Otonom (*Self-Driving Car*)** WAJIB mengadopsi Edge Computing dan tidak boleh mengandalkan Cloud Terpusat!

#### Soal 14.15 (Level 3 - 3 Menit)
Uraikan tiga strategi teknis yang dapat diterapkan oleh arsitek perangkat lunak untuk meminimalkan dampak lonjakan latensi **Cold Start** pada fungsi Serverless!

#### Soal 14.16 (Level 3 - 3 Menit)
Perhatikan berkas kode deklaratif Terraform berikut:
```hcl
resource "aws_s3_bucket" "data_primer" {
  bucket = "unida-arsip-utama"
}

resource "google_storage_bucket" "data_cadangan" {
  name     = "unida-arsip-cadangan"
  location = "ASIA-SOUTHEAST2"
}
```
Jelaskan bagaimana kode di atas mendemonstrasikan paradigma *Multi-Cloud Deployment* dan apa manfaat bisnis bagi perguruan tinggi!

#### Soal 14.17 (Level 3 - 3 Menit)
Jelaskan alur interaksi fungsi serverless Python saat membaca parameter dari URL HTTP query string (seperti `?nama=Mahasiswa`) dan mengembalikan respons terformat JSON dengan kode status HTTP 200!

#### Soal 14.18 (Level 3 - 3 Menit)
Kapan sebuah beban kerja pemrosesan data jangka panjang LEBIH TEPAT dijalankan di atas Mesin Virtual (IaaS) atau Container (CaaS) dibandingkan menggunakan Serverless (FaaS)? Berikan minimal dua contoh!

---

### BAGIAN IV: TINGKAT KESULITAN LEVEL 4
**Karakteristik:** Analisis mendalam kalkulasi biaya FinOps FaaS vs VM, mitigasi Concurrency Spike, dan evaluasi arsitektur Edge-to-Cloud.  
**Alokasi Waktu:** 4 Menit per Soal (Total: 24 Menit)

#### Soal 14.19 (Level 4 - 4 Menit)
**Kasus Analisis Biaya FinOps Proyek "Smart City":**  
Pemerintah kota memasang **50.000 sensor suhu** di seluruh penjuru kota. Setiap sensor mengirimkan satu paket data setiap 1 jam secara berkala selama sebulan penuh (30 hari).  
- *Opsi A:* Menjalankan 5 unit Virtual Machine (EC2 `t3.medium`) yang menyala terus-menerus 24 jam sehari selama sebulan penuh (total biaya sewa sekitar \$150/bulan).  
- *Opsi B:* Menggunakan arsitektur Serverless (AWS Lambda + API Gateway) di mana fungsi hanya menyala saat ada paket data masuk (durasi eksekusi rata-rata 100 ms per pemanggilan).  
**Pertanyaan Analisis:**  
1. Hitung total jumlah pemanggilan fungsi serverless per bulan ($50.000 \times 24 \times 30$)!  
2. Analisis perbandingan efisiensi biaya finansial antara Opsi A dan Opsi B, dan mengapa Serverless jauh lebih hemat biaya untuk pola beban kerja sensor tersebut!

#### Soal 14.20 (Level 4 - 4 Menit)
Pada skenario Proyek Smart City di atas, apa risiko arsitektural yang dapat terjadi jika seluruh 50.000 sensor tersebut diprogram mengirimkan data secara serentak persis pada detik yang sama di awal jam (**Concurrency Spike / Thundering Herd Problem**)? Analisis langkah mitigasinya!

#### Soal 14.21 (Level 4 - 4 Menit)
Analisis perbandingan kinerja dan tantangan arsitektur antara pemrosesan analitik citra kamera CCTV lalu lintas berbasis **Edge AI (Pemrosesan di Kamera Pintar)** versus **Cloud AI (Streaming Video ke Data Center Pusat)**!

#### Soal 14.22 (Level 4 - 4 Menit)
Analisis strategi integrasi Multi-Cloud: Mengapa mengimplementasikan arsitektur database terdistribusi lintas penyedia cloud (misal klaster database terbelah antara AWS dan Azure) jauh lebih sulit dan berisiko dibandingkan mengimplementasikan lapisan aplikasi web multi-cloud?

#### Soal 14.23 (Level 4 - 4 Menit)
Bandingkan mekanisme arsitektur komputasi serverless berbasis kontainer (**Serverless Container / CaaS**, seperti Google Cloud Run atau AWS Fargate) versus serverless berbasis fungsi murni (**FaaS**, seperti AWS Lambda)! Kapan arsitek harus memilih Cloud Run dibanding Lambda?

#### Soal 14.24 (Level 4 - 4 Menit)
Analisis bagaimana konsep *Edge Computing* mendukung paradigma **Internet of Medical Things (IoMT)** pada perangkat medis pemantau pasien jantung di rumah sakit!

---

### BAGIAN V: TINGKAT KESULITAN LEVEL 5
**Karakteristik:** Desain arsitektur IoT Smart City skala masif terpadu, perancangan blueprint Multi-Cloud IaC, dan evaluasi strategis komputasi modern.  
**Alokasi Waktu:** 5 Menit per Soal (Total: 30 Menit)

#### Soal 14.25 (Level 5 - 5 Menit)
**Kasus Desain Arsitektur Terintegrasi IoT Smart City:**  
Rancanglah sebuah cetak biru arsitektur komputasi awan modern dari hulu ke hilir untuk mengelola sistem **50.000 sensor pemantau banjir dan kualitas air** di seluruh aliran sungai perkotaan, yang mengintegrasikan lapisan **Edge Computing (Gateway Sensor)**, **Message Broker (MQTT / Event Streaming)**, **Serverless Processing (FaaS)**, dan **Penyimpanan Terdistribusi (Data Lake & Database NoSQL)**!

#### Soal 14.26 (Level 5 - 5 Menit)
Susunlah sebuah cetak biru kode **Terraform (HCL)** modular tingkat lanjut yang merancang arsitektur **Multi-Cloud Disaster Recovery** terpadu: membuat klaster komputasi kontainer primer di AWS (EKS) dan klaster komputasi sekunder di Google Cloud Platform (GKE), lengkap dengan deklarasi variabel dan mekanisme failover!

#### Soal 14.27 (Level 5 - 5 Menit)
Evaluasilah perdebatan arsitektur: *"Apakah adopsi Serverless FaaS menyebabkan tim pengembang mengalami bentuk Vendor Lock-in baru yang jauh lebih berbahaya dan mengikat dibandingkan Vendor Lock-in di era IaaS?"* Berikan analisis kritis mendalam Anda!

#### Soal 14.28 (Level 5 - 5 Menit)
Rancang sebuah arsitektur alur kerja Serverless kompleks (**Serverless Orchestration**) menggunakan pola mesin status (*State Machine*, seperti AWS Step Functions) untuk proses registrasi nasabah bank digital (*Digital Onboarding / KYC*) yang melibatkan penanganan kegagalan (*error retry*), jeda waktu (*wait states*), dan intervensi verifikasi manusia!

#### Soal 14.29 (Level 5 - 5 Menit)
Analisis secara komprehensif bagaimana konvergensi antara **Edge Computing**, **Jaringan 5G (Network Slicing)**, dan **Komputasi Awan Terpusat** memungkinkan implementasi bedah medis jarak jauh (*Telesurgery*) secara aman dan dapat diandalkan!

#### Soal 14.30 (Level 5 - 5 Menit)
Integrasikan etika keilmuan dan filosofi teknologi: Analisis paradoks pergeseran tanggung jawab manusia di era komputasi modern: *"Ketika seluruh pengelolaan infrastruktur diabstraksikan oleh sistem Serverless dan Kecerdasan Buatan otonom, apakah tanggung jawab moral seorang Insinyur Perangkat Lunak berkurang ataukah justru semakin berat?"* Sajikan pandangan kritis beradab Anda!
