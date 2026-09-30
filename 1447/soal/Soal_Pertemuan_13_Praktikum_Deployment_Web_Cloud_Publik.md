# Lembar Soal Ujian Mahasiswa
## Pertemuan 13: Praktikum Deployment Layanan Web di Cloud Publik

- **Mata Kuliah:** Komputasi Awan (*Cloud Computing*)
- **Kode MK / Bobot:** TI433946 / 3 SKS
- **Materi Rujukan:** `Pertemuan_13_Praktikum_Deployment_Web_Cloud_Publik.md`
- **Bentuk Evaluasi:** Uraian / Essay (Analisis Praktikum & Rekayasa Operasional Cloud)
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
**Karakteristik:** Menguji perintah CLI dasar, izin berkas kunci SSH, nomor port standar, dan komponen cloud storage.  
**Alokasi Waktu:** 1 Menit per Soal (Total: 6 Menit)

#### Soal 13.1 (Level 1 - 1 Menit)
Perintah Linux apa yang wajib dijalankan untuk mengubah hak akses berkas kunci privat SSH (`.pem`) agar hanya dapat dibaca oleh pemiliknya saja?

#### Soal 13.2 (Level 1 - 1 Menit)
Nomor port protokol TCP berapakah yang digunakan untuk lalu lintas web standar HTTP dan HTTPS pada konfigurasi Security Group?

#### Soal 13.3 (Level 1 - 1 Menit)
Perintah baris perintah AWS CLI apa yang digunakan untuk mengatur kredensial awal (Access Key, Secret Key, dan Default Region) di terminal lokal?

#### Soal 13.4 (Level 1 - 1 Menit)
Di manakah lokasi direktori default tempat berkas `index.html` disimpan pada web server Nginx di Ubuntu Server?

#### Soal 13.5 (Level 1 - 1 Menit)
Apa nama tipe instans mesin virtual di AWS dan GCP yang bertanda *"Free Tier Eligible"* dan umum digunakan untuk praktikum mahasiswa?

#### Soal 13.6 (Level 1 - 1 Menit)
Mengapa nama wadah penyimpanan (*Bucket*) pada layanan Cloud Object Storage (seperti AWS S3) diwajibkan unik secara global di seluruh dunia?

---

### BAGIAN II: TINGKAT KESULITAN LEVEL 2
**Karakteristik:** Menguji pemahaman konsep perbedaan web statis di S3 vs web server VM, aturan firewall inbound, dan FinOps clean-up.  
**Alokasi Waktu:** 2 Menit per Soal (Total: 12 Menit)

#### Soal 13.7 (Level 2 - 2 Menit)
Jelaskan perbedaan mendasar antara meng-hosting situs web statis di *Cloud Object Storage (S3)* dibandingkan men-deploy-nya di dalam *Mesin Virtual IaaS (EC2)*!

#### Soal 13.8 (Level 2 - 2 Menit)
Mengapa aturan lalu lintas masuk (*Inbound Rule*) untuk port SSH (port 22) pada Security Group disarankan dibatasi hanya ke `My IP` dan bukan `0.0.0.0/0`?

#### Soal 13.9 (Level 2 - 2 Menit)
Jelaskan mengapa mahasiswa diingatkan untuk selalu menghentikan (*Stop*) atau menghapus (*Terminate*) instans VM praktikum setelah selesai digunakan!

#### Soal 13.10 (Level 2 - 2 Menit)
Jelaskan fungsi dari perintah `sudo systemctl status nginx` setelah proses instalasi web server selesai di terminal server!

#### Soal 13.11 (Level 2 - 2 Menit)
Apa yang dimaksud dengan platform PaaS tanpa kartu kredit (seperti Render, Railway, atau Fly.io) dan apa keuntungannya bagi mahasiswa dalam praktikum cloud?

#### Soal 13.12 (Level 2 - 2 Menit)
Apa fungsi dari berkas `error.html` pada konfigurasi hosting situs web statis di Cloud Object Storage?

---

### BAGIAN III: TINGKAT KESULITAN LEVEL 3
**Karakteristik:** Penerapan sintaks baris perintah AWS CLI, analisis berkas kebijakan Bucket Policy JSON, dan prosedur koneksi SSH.  
**Alokasi Waktu:** 3 Menit per Soal (Total: 18 Menit)

#### Soal 13.13 (Level 3 - 3 Menit)
Perhatikan perintah peluncuran instans AWS CLI berikut:
```bash
aws ec2 run-instances \
    --image-id ami-043e33039f1a50a56 \
    --count 1 \
    --instance-type t2.micro \
    --key-name kunci-cloud \
    --security-group-ids sg-0123456789abcdef
```
Uraikan arti teknis dari masing-masing parameter flag pada baris perintah di atas!

#### Soal 13.14 (Level 3 - 3 Menit)
Perhatikan berkas kebijakan Bucket Policy publik berikut:
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::web-praktikum-1447/*"
    }
  ]
}
```
Jelaskan mengapa kebijakan di atas aman untuk situs web statis publik, namun SANGAT BERBAHAYA jika diterapkan pada bucket penyimpanan dokumen skripsi mahasiswa!

#### Soal 13.15 (Level 3 - 3 Menit)
Saat mencoba melakukan koneksi SSH dengan perintah:
```bash
ssh -i "kunci-cloud.pem" ubuntu@203.0.113.25
```
Terminal menampilkan pesan kesalahan:
`Permissions 0644 for 'kunci-cloud.pem' are too open. It is required that your private key files are NOT accessible by others.`  
Jelaskan mengapa OpenSSH menolak koneksi tersebut dan bagaimana langkah teknis memperbaikinya di terminal Linux dan PowerShell Windows!

#### Soal 13.16 (Level 3 - 3 Menit)
Uraikan langkah-langkah mengonfigurasi fitur **Static Website Hosting** pada konsol Cloud Object Storage agar bucket dapat diakses sebagai situs web fungsional melalui browser!

#### Soal 13.17 (Level 3 - 3 Menit)
Jelaskan perbedaan fungsi antara **Alamat IP Publik (*Public IP*)** yang bersifat dinamis (*ephemeral*) dengan **IP Elastis (*Elastic IP / Static Public IP*)** pada instans cloud!

#### Soal 13.18 (Level 3 - 3 Menit)
Uraikan bagaimana skrip **User Data (Cloud-Init)** digunakan untuk mengotomatiskan instalasi web server Nginx secara instan pada saat pertama kali mesin virtual diluncurkan (*at launch time*) tanpa perlu melakukan login SSH manual!

---

### BAGIAN IV: TINGKAT KESULITAN LEVEL 4
**Karakteristik:** Analisis mendalam pemecahan masalah deployment web, audit keamanan firewall berlapis, dan otomatisasi infrastruktur via CLI.  
**Alokasi Waktu:** 4 Menit per Soal (Total: 24 Menit)

#### Soal 13.19 (Level 4 - 4 Menit)
Seorang mahasiswa telah berhasil menginstal Nginx di dalam instans AWS EC2 dan layanan Nginx terbukti aktif (`systemctl status` running). Namun, saat alamat IP Publik VM tersebut dibuka di peramban browser laptop mahasiswa, halaman web mengalami waktu tunggu habis (*Connection Timed Out*). Analisis 3 kemungkinan penyebab teknis kegagalan tersebut pada konfigurasi cloud dan jaringan lokal!

#### Soal 13.20 (Level 4 - 4 Menit)
Bandingkan efisiensi operasional dan skalabilitas antara mengelola 10 instans server web secara manual melalui antarmuka grafis (**Web Management Console**) versus menggunakan skrip otomasi **AWS CLI / Bash Scripting**!

#### Soal 13.21 (Level 4 - 4 Menit)
Analisis langkah-langkah mengonfigurasi nama domain kustom (misal: `kuliah-awan.unida.ac.id`) agar mengarah ke situs web statis di Cloud Object Storage menggunakan layanan DNS manajemen (seperti Amazon Route 53 atau Cloudflare) dan pengaktifan sertifikat enkripsi SSL gratis!

#### Soal 13.22 (Level 4 - 4 Menit)
Analisis perbedaan perilaku teknis antara menghentikan instans (**Instance Stop**) versus memusnahkan instans (**Instance Terminate**) pada layanan komputasi awan IaaS ditinjau dari aspek integritas data pada volume penyimpanan (*Root EBS Volume*) dan penagihan biaya (*Billing*)!

#### Soal 13.23 (Level 4 - 4 Menit)
Sebuah server web IaaS berbasis Nginx tiba-tiba melayani konten halaman web default Nginx lama alih-alih menampilkan berkas HTML kustom yang baru saja diunggah oleh mahasiswa ke `/var/www/html/index.html`. Analisis kemungkinan akar masalah teknis pada izin berkas (*permissions*) atau cache browser!

#### Soal 13.24 (Level 4 - 4 Menit)
Analisis perbandingan biaya dan performa antara menjalankan arsitektur web aplikasi sederhana (Node.js + PostgreSQL) pada sebuah instans VM tunggal (Single All-in-One EC2) versus memisahkan keduanya menjadi arsitektur terkelola (**PaaS Web Service + DBaaS Managed Database**)!

---

### BAGIAN V: TINGKAT KESULITAN LEVEL 5
**Karakteristik:** Desain arsitektur deployment produksi cloud publik, integrasi CI/CD otomatis, penegakan prinsip FinOps, dan tanggung jawab rekayasa digital.  
**Alokasi Waktu:** 5 Menit per Soal (Total: 30 Menit)

#### Soal 13.25 (Level 5 - 5 Menit)
**Kasus Perancangan Pipeline Deployment Otomatis (GitOps / CI/CD):**  
Rancanglah sebuah arsitektur otomatisasi deployment lengkap dari awal hingga akhir: saat seorang mahasiswa melakukan `git push` kode web terbarunya ke repositori GitHub, kode tersebut secara otomatis diuji, dibangun, dan langsung di-deploy ke instans web server cloud publik tanpa perlu login SSH manual!

#### Soal 13.26 (Level 5 - 5 Menit)
Susunlah sebuah skrip Bash otomasi komprehensif yang mengintegrasikan AWS CLI untuk secara otomatis: (1) Membuat Security Group dengan aturan port 80 dan 443, (2) Meluncurkan 1 instans EC2 Ubuntu dengan skrip User Data instalasi web server Nginx, dan (3) Mencetak alamat IP Publik instans yang siap diakses ke layar terminal!

#### Soal 13.27 (Level 5 - 5 Menit)
Rancang sebuah arsitektur situs web hibrida berperforma tinggi dan berbiaya ultra-hemat: menggabungkan **Cloud Object Storage (Static Content Hosting)**, **Content Delivery Network (CDN)**, dan **Serverless Backend API (FaaS)** untuk menangani 1 juta pengunjung harian dengan biaya kurang dari \$10 per bulan!

#### Soal 13.28 (Level 5 - 5 Menit)
Evaluasilah risiko keamanan dari praktik "Menonaktifkan Fitur *Block Public Access*" pada bucket S3 saat praktikum static web hosting: Bagaimana seorang arsitek cloud menyeimbangkan kebutuhan agar web dapat diakses publik tanpa membuka risiko berkas internal lainnya ikut terunduh oleh peretas?

#### Soal 13.29 (Level 5 - 5 Menit)
Rancang sebuah prosedur pengujian penerimaan sistem (**User Acceptance Testing / Deployment Verification Plan**) setelah peluncuran web server di cloud publik, mencakup uji fungsionalitas HTTP, uji beban konkurensi dasar, verifikasi sertifikat SSL/TLS, dan uji keamanan port scanning!

#### Soal 13.30 (Level 5 - 5 Menit)
Integrasikan nilai tanggung jawab profesional dan etika keilmuan mahasiswa informatika: Jelaskan mengapa kebiasaan membiarkan instans cloud menyala tanpa digunakan (*orphaned running instances*) bertentangan dengan prinsip **Amanah, Keadilan Finansial, dan Kepedulian Lingkungan (Green Computing)**!
