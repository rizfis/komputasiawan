# Lembar Soal Ujian Mahasiswa
## Pertemuan 07: Containerization (Docker), Orkestrasi (Kubernetes), Storage & Networking

- **Mata Kuliah:** Komputasi Awan (*Cloud Computing*)
- **Kode MK / Bobot:** TI433946 / 3 SKS
- **Materi Rujukan:** `Pertemuan_07_Containerization_Docker_dan_Orkestrasi_Kubernetes.md`
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
**Karakteristik:** Menguji terminologi dasar container, komponen Kubernetes, dan perintah praktikum K8s.  
**Alokasi Waktu:** 1 Menit per Soal (Total: 6 Menit)

#### Soal 7.1 (Level 1 - 1 Menit)
Apa unit eksekusi dan penyebaran (*deployment unit*) terkecil dalam arsitektur Kubernetes?

#### Soal 7.2 (Level 1 - 1 Menit)
Sebutkan dua pilar fitur bawaan kernel Linux yang mendasari isolasi dan pembatasan sumber daya pada container Docker!

#### Soal 7.3 (Level 1 - 1 Menit)
Sebutkan 4 komponen inti yang berada di dalam *Control Plane (Master Node)* Kubernetes!

#### Soal 7.4 (Level 1 - 1 Menit)
Komponen agen apa yang berjalan di setiap *Worker Node* Kubernetes untuk memastikan kontainer berjalan sesuai instruksi Control Plane?

#### Soal 7.5 (Level 1 - 1 Menit)
Berapa rentang nomor port statis default yang dibuka pada Worker Node untuk tipe layanan Kubernetes bertipe **NodePort**?

#### Soal 7.6 (Level 1 - 1 Menit)
Perintah baris perintah `kubectl` apa yang digunakan untuk melihat daftar seluruh node aktif beserta status kesiapannya di dalam klaster?

---

### BAGIAN II: TINGKAT KESULITAN LEVEL 2
**Karakteristik:** Menguji pemahaman konsep perbedaan VM vs Container, peran K3s, dan tipe Service Kubernetes.  
**Alokasi Waktu:** 2 Menit per Soal (Total: 12 Menit)

#### Soal 7.7 (Level 2 - 2 Menit)
Jelaskan perbedaan mendasar antara mesin virtual (VM) dan container Docker dari aspek penggunaan kernel sistem operasi!

#### Soal 7.8 (Level 2 - 2 Menit)
Sebutkan tiga jenis *Linux Namespaces* beserta fungsinya masing-masing dalam mengisolasi container!

#### Soal 7.9 (Level 2 - 2 Menit)
Mengapa varian Kubernetes **K3s** (oleh Rancher) sangat ideal digunakan untuk praktikum mahasiswa di laptop berspesifikasi terbatas dibandingkan Kubernetes standar (*K8s vanilla*)?

#### Soal 7.10 (Level 2 - 2 Menit)
Jelaskan perbedaan fungsi antara tipe Service **ClusterIP** dan **LoadBalancer** di Kubernetes!

#### Soal 7.11 (Level 2 - 2 Menit)
Mengapa penyimpanan data di dalam container secara default disebut bersifat **fana (*ephemeral*)**, dan bagaimana cara mengatasinya agar data tidak hilang saat container restart?

#### Soal 7.12 (Level 2 - 2 Menit)
Apa fungsi dan kegunaan dari berkas manifest deklaratif YAML pada Kubernetes dibandingkan menjalankan perintah imperatif secara manual?

---

### BAGIAN III: TINGKAT KESULITAN LEVEL 3
**Karakteristik:** Penerapan siklus hidup Pod, mekanisme rekonsiliasi self-healing, dan interaksi PV/PVC.  
**Alokasi Waktu:** 3 Menit per Soal (Total: 18 Menit)

#### Soal 7.13 (Level 3 - 3 Menit)
Uraikan langkah-langkah kerja komponen Kubernetes Control Plane dari saat pengguna menjalankan `kubectl apply -f deployment.yaml` hingga Pod benar-benar berjalan di Worker Node!

#### Soal 7.14 (Level 3 - 3 Menit)
Jelaskan mekanisme kerja **Loop Rekonsiliasi (*Reconciliation Loop*)** yang memungkinkan Kubernetes melakukan pemulihan mandiri (*Self-Healing*) saat sebuah Pod dihapus paksa!

#### Soal 7.15 (Level 3 - 3 Menit)
Jelaskan alur relasi dan pembagian peran antara **Persistent Volume (PV)**, **Persistent Volume Claim (PVC)**, dan **StorageClass** pada penyimpanan terdistribusi Kubernetes!

#### Soal 7.16 (Level 3 - 3 Menit)
Uraikan perbedaan mekanisme kerja jaringan container antara **kube-proxy** mode *iptables* dan mode *IPVS* pada Worker Node!

#### Soal 7.17 (Level 3 - 3 Menit)
Jelaskan cara kerja sistem file berlapis (*Layered Filesystem / OverlayFS*) pada citra Docker dan bagaimana hal itu menghemat ruang disk host secara signifikan!

#### Soal 7.18 (Level 3 - 3 Menit)
Uraikan proses teknis saat sebuah Worker Node baru bergabung (*join*) ke Master Node K3s menggunakan parameter `K3S_URL` dan `K3S_TOKEN`!

---

### BAGIAN IV: TINGKAT KESULITAN LEVEL 4
**Karakteristik:** Analisis mendalam strategi pembaruan Rolling Update vs Recreate, bedah arsitektur etcd quorum, dan troubleshooting kegagalan Pod.  
**Alokasi Waktu:** 4 Menit per Soal (Total: 24 Menit)

#### Soal 7.19 (Level 4 - 4 Menit)
Analisis perbedaan strategi pembaruan aplikasi pada Kubernetes Deployment antara **RollingUpdate** dan **Recreate** ditinjau dari aspek ketersediaan layanan (*downtime*) dan konsumsi sumber daya komputasi klaster!

#### Soal 7.20 (Level 4 - 4 Menit)
Analisis peran krusial basis data terdistribusi **etcd** pada Kubernetes Control Plane dan mengapa arsitek cloud mewajibkan jumlah node etcd selalu berjumlah GANJIL (3, 5, atau 7 node) pada lingkungan produksi!

#### Soal 7.21 (Level 4 - 4 Menit)
Sebuah Pod mengalami status **CrashLoopBackOff** setelah di-deploy ke klaster Kubernetes. Analisis langkah-langkah investigasi sistematis menggunakan perintah CLI `kubectl` untuk mendiagnosis akar masalahnya!

#### Soal 7.22 (Level 4 - 4 Menit)
Analisis mekanisme kerja pemeriksaan kesehatan container pada Kubernetes melalui **Liveness Probe**, **Readiness Probe**, dan **Startup Probe**!

#### Soal 7.23 (Level 4 - 4 Menit)
Bandingkan model isolasi keamanan jaringan Kubernetes default yang bersifat *"Flat Network & Non-Isolated"* dengan implementasi kebijakan isolasi berbasis **Kubernetes NetworkPolicy**!

#### Soal 7.24 (Level 4 - 4 Menit)
Analisis arsitektur internal **Container Runtime Interface (CRI)** dan jelaskan mengapa Kubernetes mendepresiasi modul *Dockershim* bawaan pada versi 1.24 ke atas demi mendukung runtime langsung seperti **containerd** atau **CRI-O**!

---

### BAGIAN V: TINGKAT KESULITAN LEVEL 5
**Karakteristik:** Desain arsitektur microservices enterprise di Kubernetes, perancangan manifest multi-tier lengkap, penanganan bencana cluster, dan analisis UTS.  
**Alokasi Waktu:** 5 Menit per Soal (Total: 30 Menit)

#### Soal 7.25 (Level 5 - 5 Menit)
**Kasus Desain Arsitektur Modernisasi Aplikasi Perusahaan Logistik:**  
Sebuah perusahaan logistik nasional ingin memodernisasi aplikasi pelacakan resi barang monolitiknya yang selama ini sering down saat jam sibuk menjadi arsitektur berbasis container di atas Kubernetes. Rancanglah sebuah cetak biru manifest deklaratif lengkap yang memuat:  
1. *Deployment Nginx Web Server* dengan 3 replika, batas kuota CPU/RAM (`resources limits & requests`), dan label selektor `app: logistik-web`.  
2. *Service tipe NodePort* pada port `30088` untuk mengekspos aplikasi ke jaringan luar.  
3. Uraikan bagaimana arsitektur ini menjamin ketersediaan tinggi (*Zero Downtime*) saat tim merilis pembaruan versi image dari `v1.0` ke `v2.0`!

#### Soal 7.26 (Level 5 - 5 Menit)
Rancang sebuah skenario penanganan bencana (*Disaster Recovery*) pada klaster Kubernetes produksi jika Master Node (Control Plane) mengalami mati total permanen (*hardware burnout*), sementara seluruh Worker Node masih menyala dan melayani pengguna. Jelaskan apa yang terjadi pada aplikasi yang sedang berjalan dan bagaimana prosedur pemulihan klasternya!

#### Soal 7.27 (Level 5 - 5 Menit)
Evaluasilah perbandingan arsitektural antara penyedia CNI (*Container Network Interface*) berbasis **Overlay Network (seperti Flannel dengan VXLAN)** versus CNI berbasis **Flat Routed Network (seperti AWS VPC CNI atau Calico BGP)** ditinjau dari latensi transmisi paket dan konsumsi CPU!

#### Soal 7.28 (Level 5 - 5 Menit)
Analisis secara kritis risiko keamanan dalam penggunaan citra container publik (*Public Docker Hub Images*): Bagaimana seorang insinyur SecOps menerapkan prinsip keamanan rantai pasok perangkat lunak (*Software Supply Chain Security*) pada pipeline CI/CD Kubernetes?

#### Soal 7.29 (Level 5 - 5 Menit)
Rancanglah sebuah arsitektur terpadu integrasi **Horizontal Pod Autoscaler (HPA)** yang dikombinasikan dengan **Cluster Autoscaler (CA)** pada penyedia cloud publik untuk menangani lonjakan beban kerja yang ekstrem!

#### Soal 7.30 (Level 5 - 5 Menit)
**Integrasi Review Komprehensif Ujian Tengah Semester (UTS):**  
Hubungkan konsep fondasi dari Pertemuan 01 hingga Pertemuan 07: Jelaskan bagaimana evolusi dari *Mainframe* $\to$ *Virtual Machine (Hypervisor)* $\to$ *Container (Docker/Kubernetes)* mencerminkan upaya manusia dalam mengejar prinsip **Amanah Efisiensi Sumber Daya (Anti-Israf)** dan fleksibilitas arsitektur komputasi terdistribusi!
