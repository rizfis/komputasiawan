# Lembar Soal Ujian Mahasiswa
## Pertemuan 06: Teknologi Virtualisasi, Hypervisor, dan Praktikum VM

- **Mata Kuliah:** Komputasi Awan (*Cloud Computing*)
- **Kode MK / Bobot:** TI433946 / 3 SKS
- **Materi Rujukan:** `Pertemuan_06_Virtualisasi_Hypervisor_dan_Praktikum_VM.md`
- **Bentuk Evaluasi:** Uraian / Essay (Analisis Mandiri & Praktikum)
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
**Karakteristik:** Menguji definisi dasar hypervisor, istilah mode jaringan VM, dan perintah dasar Linux terminal.  
**Alokasi Waktu:** 1 Menit per Soal (Total: 6 Menit)

#### Soal 6.1 (Level 1 - 1 Menit)
Apa sebutan teknis untuk komputer fisik induk (*Host*) dan sistem operasi virtual yang berjalan di atasnya (*Guest*) dalam teknologi virtualisasi?

#### Soal 6.2 (Level 1 - 1 Menit)
Sebutkan dua contoh perangkat lunak yang termasuk dalam kategori **Hypervisor Tipe 1 (Bare-Metal)**!

#### Soal 6.3 (Level 1 - 1 Menit)
Sebutkan dua contoh perangkat lunak yang termasuk dalam kategori **Hypervisor Tipe 2 (Hosted)**!

#### Soal 6.4 (Level 1 - 1 Menit)
Apa nama fitur perangkat keras pada prosesor Intel dan AMD yang mendukung virtualisasi berbantuan hardware (*Hardware-Assisted Virtualization*)?

#### Soal 6.5 (Level 1 - 1 Menit)
Perintah terminal Linux apa yang digunakan untuk memeriksa konfigurasi antarmuka dan alamat IP pada Ubuntu Server modern?

#### Soal 6.6 (Level 1 - 1 Menit)
Dalam konfigurasi jaringan VirtualBox, mode adapter manakah yang memberikan mesin virtual alamat IP privat terpisah yang berada dalam satu subnet yang sama dengan komputer host di jaringan LAN fisik?

---

### BAGIAN II: TINGKAT KESULITAN LEVEL 2
**Karakteristik:** Menguji pemahaman konsep arsitektur hypervisor tipe 1 vs 2, fungsi mode jaringan, dan utilitas CLI.  
**Alokasi Waktu:** 2 Menit per Soal (Total: 12 Menit)

#### Soal 6.7 (Level 2 - 2 Menit)
Jelaskan perbedaan letak arsitektural antara Hypervisor Tipe 1 dan Hypervisor Tipe 2 terhadap perangkat keras komputer fisik!

#### Soal 6.8 (Level 2 - 2 Menit)
Mengapa Hypervisor Tipe 1 memiliki performa yang jauh lebih tinggi dan latensi I/O yang lebih rendah dibandingkan Hypervisor Tipe 2?

#### Soal 6.9 (Level 2 - 2 Menit)
Jelaskan perbedaan karakteristik aksesibilitas jaringan antara mode **NAT (Network Address Translation)** dan mode **Host-Only** pada mesin virtual!

#### Soal 6.10 (Level 2 - 2 Menit)
Apa fungsi dan kegunaan dari perintah Linux `lscpu` dan `free -h` yang dijalankan di dalam mesin virtual saat praktikum?

#### Soal 6.11 (Level 2 - 2 Menit)
Jelaskan apa yang dimaksud dengan alokasi disk virtual bertipe *Dynamically Allocated* (Alokasi Dinamis) pada VirtualBox dan apa keuntungannya bagi mahasiswa!

#### Soal 6.12 (Level 2 - 2 Menit)
Mengapa seluruh penyedia layanan komputasi awan publik komersial (seperti AWS, Google Cloud, dan Azure) menggunakan Hypervisor Tipe 1 untuk infrastruktur IaaS mereka?

---

### BAGIAN III: TINGKAT KESULITAN LEVEL 3
**Karakteristik:** Penerapan mekanisme perangkat keras virtualisasi CPU/RAM, penyelesaian masalah jaringan lab kampus, dan prosedur koneksi SSH.  
**Alokasi Waktu:** 3 Menit per Soal (Total: 18 Menit)

#### Soal 6.13 (Level 3 - 3 Menit)
Jelaskan dilema hierarki cincin perlindungan CPU (*CPU Protection Rings*) pada prosesor x86 arsitektur lama dan bagaimana instruksi *Intel VT-x / AMD-V* menyelesaikannya!

#### Soal 6.14 (Level 3 - 3 Menit)
Uraikan mekanisme kerja teknologi *Extended Page Tables (EPT)* / *Nested Page Tables (NPT)* dalam mempercepat virtualisasi memori RAM!

#### Soal 6.15 (Level 3 - 3 Menit)
Saat praktikum di jaringan Wi-Fi kampus, mahasiswa sering kali gagal melakukan koneksi SSH ke VM yang menggunakan mode *Bridged Adapter*. Jelaskan penyebab teknis masalah tersebut dan uraikan solusinya menggunakan kombinasi dua adapter!

#### Soal 6.16 (Level 3 - 3 Menit)
Uraikan langkah-langkah teknis untuk mengamankan dan mengonfigurasi berkas kunci privat SSH (`.pem` atau `id_rsa`) di sistem operasi Linux/macOS sebelum digunakan untuk remote server!

#### Soal 6.17 (Level 3 - 3 Menit)
Jelaskan perbedaan mendasar antara *Full Virtualization* (Virtualisasi Penuh) dan *Paravirtualization* (Paravirtualisasi)!

#### Soal 6.18 (Level 3 - 3 Menit)
Uraikan fungsi dan manfaat dari paket *Guest Additions* (pada VirtualBox) atau *VMware Tools* setelah instalasi sistem operasi Guest OS selesai!

---

### BAGIAN IV: TINGKAT KESULITAN LEVEL 4
**Karakteristik:** Analisis mendalam teorema virtualisasi Popek-Goldberg, isolasi hypervisor, dan evaluasi performa bare-metal vs hosted.  
**Alokasi Waktu:** 4 Menit per Soal (Total: 24 Menit)

#### Soal 6.19 (Level 4 - 4 Menit)
Jelaskan prinsip dasar **Teorema Virtualisasi Popek-Goldberg (*Popek-Goldberg Virtualization Requirements*)** dan jelaskan mengapa arsitektur CPU x86 generasi awal (sebelum tahun 2005) dianggap secara teoritis "tidak dapat divirtualisasikan secara murni" (*unvirtualizable*)!

#### Soal 6.20 (Level 4 - 4 Menit)
Analisis secara kritis perbandingan antara mengelola server cloud melalui antarmuka baris perintah (*CLI / SSH*) versus antarmuka grafis (*GUI / Remote Desktop*) ditinjau dari aspek konsumsi bandwidth, jejak memori sistem (*system footprint*), dan otomasi operasional!

#### Soal 6.21 (Level 4 - 4 Menit)
Analisis mekanisme teknik *Memory Overcommitment* dan *Memory Ballooning* yang diterapkan oleh hypervisor kelas data center (seperti VMware ESXi atau KVM) dalam memaksimalkan utilisasi RAM fisik!

#### Soal 6.22 (Level 4 - 4 Menit)
Analisis risiko keamanan kerentanan pelarian mesin virtual (*Virtual Machine Escape / VM Escape*) dan bagaimana peretas dapat melompat dari sistem operasi Guest untuk mengendalikan server fisik Host!

#### Soal 6.23 (Level 4 - 4 Menit)
Bandingkan mekanisme I/O jaringan virtual berbasis emulasi perangkat lunak (*Emulated E1000*) versus virtualisasi I/O paravirtual (*VirtIO / SR-IOV*) pada mesin virtual Linux Server!

#### Soal 6.24 (Level 4 - 4 Menit)
Sebuah server host Proxmox VE mengalami kehabisan ruang disk fisik pada partisi *Storage Pool*, sementara beberapa VM di dalamnya telah dialokasikan disk berukuran besar namun utilisasi data internalnya sebenarnya masih sedikit. Analisis penggunaan perintah `fstrim` / SCSI Unmap untuk mereklamasi ruang penyimpanan fisik tersebut!

---

### BAGIAN V: TINGKAT KESULITAN LEVEL 5
**Karakteristik:** Desain arsitektur virtualisasi data center enterprise, skenario migrasi hidup (Live Migration), dan mitigasi bencana bare-metal.  
**Alokasi Waktu:** 5 Menit per Soal (Total: 30 Menit)

#### Soal 6.25 (Level 5 - 5 Menit)
**Kasus Perancangan Klaster Virtualisasi Data Center Kampus:**  
Pusat Data Universitas merencanakan konsolidasi 40 unit server fisik lama yang boros listrik menjadi sebuah klaster virtualisasi privat berbasis **Hypervisor Tipe 1 (KVM/Proxmox VE)** dengan 3 unit server server fisik baru berspesifikasi tinggi (*High-Density Compute Nodes*). Klaster ini harus mendukung fitur **Live Migration** (memindahkan VM yang sedang menyala dari Server 1 ke Server 2 tanpa henti layanan saat pemeliharaan hardware) dan **High Availability (HA)** otomatis.  
Rancanglah arsitektur fisik dan logis klaster tersebut, mencakup kebutuhan topologi komputasi, jaringan manajemen/migrasi, dan sistem penyimpanan bersama (*Shared Storage*)!

#### Soal 6.26 (Level 5 - 5 Menit)
Uraikan secara presisi tahapan algoritma internal yang terjadi pada saat proses **Live Migration (Pre-Copy Memory Algorithm)** berlangsung pada hypervisor (seperti KVM / QEMU) dari Host Sumber ke Host Tujuan!

#### Soal 6.27 (Level 5 - 5 Menit)
Evaluasilah perdebatan teknis: Mengapa teknologi virtualisasi perangkat keras (Hypervisor) tetap menjadi fondasi yang tidak tergantikan dalam ekosistem komputasi awan modern, meskipun teknologi kontainerisasi (seperti Docker dan Kubernetes) menawarkan efisiensi komputasi yang jauh lebih ringan dan cepat?

#### Soal 6.28 (Level 5 - 5 Menit)
Rancang sebuah prosedur operasional standar (*Standard Operating Procedure / SOP*) pengerasan keamanan (*Hardening*) untuk server mesin virtual Linux Ubuntu Server 22.04 LTS baru sebelum server tersebut dihubungkan ke internet publik!

#### Soal 6.29 (Level 5 - 5 Menit)
Analisis mendalam fenomena *Nested Virtualization* (Virtualisasi Bersarang): Bagaimana mekanisme teknis hypervisor di dalam mesin virtual bekerja, dan apa use-case industri nyata yang mengharuskan penggunaan teknologi ini di cloud publik?

#### Soal 6.30 (Level 5 - 5 Menit)
Evaluasilah prinsip etika keilmuan dan tanggung jawab seorang Systems Administrator (*SysAdmin*) dalam mengelola hak akses root mesin virtual pada lingkungan komputasi bersama di universitas atau korporasi!
