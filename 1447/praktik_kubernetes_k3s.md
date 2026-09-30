# 📚 MODUL PRAKTIKUM: MEMBANGUN MINI CLUSTER KUBERNETES (K3S)
## Studi Kasus: Deployment Web Sekolah (Apache, MySQL, WordPress) Single-Node

---

| Informasi Modul | Keterangan |
| :--- | :--- |
| **Mata Kuliah** | Komputasi Awan / Sistem Terdistribusi / Administrasi Jaringan |
| **Sasaran Mahasiswa** | S1 Teknik Informatika (Semester 4) |
| **Topik Praktikum** | Mini Cluster Kubernetes K3s All-in-One & Container Orchestration |
| **Estimasi Durasi** | 2 x 170 Menit (2 Sesi Lab) |
| **Sistem Operasi Target** | Ubuntu Server / Desktop (20.04 / 22.04 / 24.04 LTS) |
| **Hasil Akhir (Goal)** | Mini cluster K3s berjalan di 1 VM/PC, menjalankan CMS Web Sekolah (WordPress + Apache + MySQL) dengan akses via domain eksternal tanpa Virtual IP (VIP) |

---

## 🎯 1. Capaian Pembelajaran & Goal Praktikum

### 1.1 Capaian Pembelajaran Praktikum (CLO)
Setelah menyelesaikan modul praktikum ini, mahasiswa diharapkan mampu:
1. **Memahami Arsitektur Kubernetes & K3s:** Menjelaskan perbedaan antara *Control Plane* dan *Worker Node*, serta bagaimana K3s memadatkan keduanya menjadi solusi *lightweight* pada satu mesin fisik/VM.
2. **Melakukan Deployment K3s All-in-One:** Menginstal dan mengonfigurasi cluster Kubernetes single-node di atas OS Ubuntu.
3. **Menerjemahkan Arsitektur Multi-Tier ke Objek Kubernetes:** Mengonfigurasi `Secret`, `PersistentVolumeClaim (PVC)`, `Deployment`, `Service`, dan `Ingress`.
4. **Mengatur Resolusi DNS Eksternal:** Menghubungkan nama domain (`sekolah.local` / `web.sekolah.sch.id`) langsung ke IP address host Kubernetes tanpa dependensi *Virtual IP* (VIP / keepalived).
5. **Memvalidasi *Stateful Persistence* & Troubleshooting:** Membuktikan persistensi data aplikasi database ketika Pod dimatikan (*recreate/reschedule*) serta membaca log kontainer untuk perbaikan kendala.

### 1.2 Ringkasan Skenario Proyek
Sebagai calon sarjana informatika, Anda ditugaskan membangun infrastruktur web portal sekolah modern. Arsitektur lama yang menginstal LAMP (*Linux, Apache, MySQL, PHP*) manual langsung di OS memiliki kelemahan: sulit diisolasi, sulit direplikasi, dan rentan terhadap ketergantungan library OS.

Pada praktikum ini, Anda akan memigrasikan tumpukan LAMP tersebut ke dalam lingkungan kontainer terorkestrasi:
- **Web Server & Application:** WordPress berbasis Apache HTTP Server & PHP (`wordpress:apache`).
- **Database Backend:** Relational Database Management System (`mariadb:10.11` / `mysql:8.0`).
- **Penyimpanan Persisten:** K3s *Local-Path Storage Provisioner*.
- **Pintu Masuk (Traffic Ingress):** K3s Traefik Ingress Controller bawaan pada port 80/443.
- **Infrastruktur:** 1 VM Ubuntu yang merangkap peran *Control Plane* (Master) dan *Worker Node*.

---

## 🏗️ 2. Arsitektur & Topologi Mini Cluster

Dalam produksi berskala besar (*enterprise*), Kubernetes biasanya terdiri dari 3 master node (High Availability) dan puluhan worker node. Namun, untuk kebutuhan lab, riset, edge computing, maupun hosting skala kecil-menengah, arsitektur **All-in-One Single Node** adalah pendekatan yang paling hemat sumber daya (*resource-efficient*).

### 2.1 Diagram Arsitektur Sistem

```
+-----------------------------------------------------------------------------------+
| Komputer Klien / Penguji (Laptop Mahasiswa)                                       |
| Browser: http://sekolah.local                                                     |
| DNS Resolution: sekolah.local -> 192.168.1.50                                      |
+-----------------------------------------+-----------------------------------------+
                                          | HTTP Request (Port 80)
                                          v
+-----------------------------------------------------------------------------------+
| Mesin Virtual / PC Mini Cluster Ubuntu (IP: 192.168.1.50)                          |
|                                                                                   |
|  +-----------------------------------------------------------------------------+  |
|  | K3s Kubernetes Runtime (Control Plane + Worker Node dalam 1 OS)             |
|  |                                                                             |
|  |  [ Traefik Ingress Controller ] <--- Menerima trafik Port 80 host            |
|  |           | (Routing berbasis Host Header: sekolah.local)                   |
|  |           v                                                                 |
|  |  +-----------------------------------------------------------------------+  |
|  |  | Namespace: web-sekolah                                                |  |
|  |  |                                                                       |  |
|  |  |  [ Service: wordpress-svc (Port 80) ]                                 |  |
|  |  |           |                                                           |  |
|  |  |           v                                                           |  |
|  |  |  [ Pod: WordPress (Apache + PHP) ]                                    |  |
|  |  |        |                  |                                           |  |
|  |  |        | Mount: /var/www  +----------> [ Service: mysql-svc (3306) ]  |  |
|  |  |        v                                     |                        |  |
|  |  |   [ PVC: wp-pvc ]                            v                        |  |
|  |  |   (Storage 5Gi)                   [ Pod: MySQL Database ]             |  |
|  |  |                                              |                        |  |
|  |  |                                              | Mount: /var/lib/mysql  |  |
|  |  |                                              v                        |  |
|  |  |                                         [ PVC: mysql-pvc ]            |  |
|  |  |                                         (Storage 5Gi)                 |  |
|  |  +-----------------------------------------------------------------------+  |
|  +-----------------------------------------------------------------------------+  |
|                                                                                   |
|  Storage Fisik Host OS: /var/lib/rancher/k3s/storage/ (Local-Path PV)              |
+-----------------------------------------------------------------------------------+
```

### 2.2 Mengapa Tanpa Virtual IP (VIP)?
Pada kluster *Multi-Master High Availability (HA)*, kita membutuhkan Virtual IP (VIP) dengan protokol VRRP (Keepalived/Kube-VIP) agar ketika Master-1 mati, IP akses dapat otomatis berpindah ke Master-2. 

Pada arsitektur **Single-Node (1 VM/PC)**:
- Tidak ada node master cadangan yang perlu di-failover.
- IP Address kartu jaringan (NIC) Ubuntu sudah bertindak sebagai titik kontak tunggal (*single point of entry*).
- Dengan demikian, DNS dapat **langsung diarahkan ke IP fisik/VM Ubuntu**, membuat arsitektur jauh lebih sederhana, ringan, dan tidak memerlukan konfigurasi ARP broadcast atau modul kernel tambahan.

---

## 💻 3. Kebutuhan Sistem & Prasyarat

### 3.1 Spesifikasi Perangkat Keras Minimum
- **Processor:** 2 vCPU / Cores.
- **RAM:** Minimum 2 GB (Sangat disarankan **3 GB - 4 GB** agar MySQL dan Apache berjalan stabil).
- **Penyimpanan:** 20 GB free disk space.
- **Koneksi Jaringan:** Mode Bridged Adapter (jika menggunakan VirtualBox/VMware) agar VM mendapatkan IP lokal satu subnet dengan laptop penguji.

### 3.2 Spesifikasi Perangkat Lunak
- **Sistem Operasi:** Ubuntu Server atau Ubuntu Desktop 22.04 LTS / 24.04 LTS (64-bit).
- **Akses Pengguna:** User dengan hak `sudo`.
- **Koneksi Internet:** Diperlukan selama instalasi untuk mendownload binary K3s dan image Docker (`wordpress:latest`, `mariadb:10.11`).

---

## 🛠️ 4. Tahap Implementasi Langkah Demi Langkah

---

### TAHAP 1: Persiapan Sistem Operasi Ubuntu

Sebelum memasang Kubernetes, pastikan sistem operasi berada dalam kondisi bersih, terbarui, dan tidak memiliki dependensi yang tumpang tindih.

1. **Buka Terminal di Ubuntu Anda dan lakukan pembaruan repositori:**
   ```bash
   sudo apt update && sudo apt upgrade -y
   ```

2. **Pasang paket utilitas dasar:**
   ```bash
   sudo apt install -y curl wget git net-tools htop
   ```

3. **Periksa dan catat IP Address mesin Ubuntu Anda:**
   ```bash
   hostname -I | awk '{print $1}'
   ```
   > 📌 **Catatan Mahasiswa:** Misalkan IP yang muncul adalah `192.168.1.50`. Catat IP ini, karena akan digunakan sebagai target konfigurasi DNS eksternal.

4. **Konfigurasi Hostname Server:**
   Beri nama server agar mudah diidentifikasi:
   ```bash
   sudo hostnamectl set-hostname node-k3s
   ```

5. **Pengaturan Firewall (UFW):**
   Untuk lingkungan praktikum lab, kita dapat menonaktifkan UFW sementara waktu agar port internal Kubernetes dan Ingress tidak terblokir:
   ```bash
   sudo ufw disable
   ```
   *(Jika Anda ingin membiarkan UFW aktif, pastikan membuka port 80/tcp, 443/tcp, dan 6443/tcp)*.

---

### TAHAP 2: Instalasi Kubernetes K3s (Single-Node Mode)

K3s dibuat oleh Rancher Labs (sekarang SUSE) dan merupakan distribusi Kubernetes resmi yang tersertifikasi CNCF (*Cloud Native Computing Foundation*). K3s menggantikan etcd yang berat dengan SQLite internal serta menyatukan semua komponen k8s ke dalam 1 binary ringan (<100MB).

1. **Jalankan Skrip Instalasi Resmi K3s:**
   ```bash
   curl -sfL https://get.k3s.io | sh -s - --write-kubeconfig-mode 644
   ```
   *Parameter `--write-kubeconfig-mode 644` bertujuan agar konfigurasi k3s dapat dibaca langsung oleh user non-root tanpa harus selalu mengetikkan `sudo`.*

2. **Konfigurasi Akses `kubectl` Pengguna:**
   Secara bawaan K3s menyediakan utilitas `k3s kubectl`. Agar mahasiswa terbiasa dengan standar industri (`kubectl`), buat alias dan symlink:
   ```bash
   mkdir -p ~/.kube
   sudo cp /etc/rancher/k3s/k3s.yaml ~/.kube/config
   sudo chown $(id -u):$(id -g) ~/.kube/config
   export KUBECONFIG=~/.kube/config
   echo "export KUBECONFIG=~/.kube/config" >> ~/.bashrc
   ```

3. **Verifikasi Instalasi K3s:**
   Jalankan perintah pengecekan node:
   ```bash
   kubectl get nodes -o wide
   ```
   **Contoh Output Sukses:**
   ```text
   NAME       STATUS   ROLES                  AGE   VERSION        INTERNAL-IP    EXTERNAL-IP
   node-k3s   Ready    control-plane,master   45s   v1.30.x+k3s1   192.168.1.50   <none>
   ```
   > 💡 **Analisis Mahasiswa:** Perhatikan kolom `ROLES`. Mesin ini berstatus `control-plane,master`. Pada K3s, node master secara otomatis juga bertindak sebagai worker node yang siap menjalankan Pod aplikasi kita.

4. **Periksa Komponen Bawaan K3s:**
   ```bash
   kubectl get pods -n kube-system
   ```
   Anda akan melihat Pod:
   - `coredns-*` (Layanan resolusi nama internal cluster).
   - `local-path-provisioner-*` (Penyedia volume penyimpanan otomatis berbasis folder host).
   - `traefik-*` (Ingress Controller bawaan K3s yang menangani trafik HTTP/HTTPS dari luar).
   - `metrics-server-*` (Pemantau konsumsi RAM/CPU pod).

---

### TAHAP 3: Pembuatan Ruang Kerja (Namespace) & Kredensial (Secret)

Dalam Kubernetes, **Namespace** digunakan untuk mengisolasi resource proyek satu dengan proyek lainnya.

1. **Buat Folder Praktikum:**
   ```bash
   mkdir -p ~/praktik-k8s-sekolah
   cd ~/praktik-k8s-sekolah
   ```

2. **Buat Namespace `web-sekolah`:**
   ```bash
   kubectl create namespace web-sekolah
   ```

3. **Membuat File Manifest Secret (`01-secret.yaml`):**
   *Secret* digunakan untuk menyimpan data sensitif seperti password basis data tanpa menuliskannya secara gamblang (*hardcoded*) di dalam file deployment.

   Buat file `01-secret.yaml` menggunakan editor teks (nano/vim):
   ```bash
   nano 01-secret.yaml
   ```
   Isi dengan konfigurasi berikut:
   ```yaml
   apiVersion: v1
   kind: Secret
   metadata:
     name: mysql-secret
     namespace: web-sekolah
   type: Opaque
   stringData:
     # Password Root MySQL
     mysql-root-password: "PasswordRootSekolah123!"
     # Password User Database
     mysql-password: "UserWebSekolahPass456!"
   ```
   Terapkan manifest:
   ```bash
   kubectl apply -f 01-secret.yaml
   ```

---

### TAHAP 4: Konfigurasi Penyimpanan Persisten (Persistent Volume Claim)

Secara default, kontainer bersifat *ephemeral* (data di dalamnya akan hilang jika kontainer rusak/restart). Untuk web sekolah, artikel, gambar, tema, dan tabel basis data **wajib tersimpan secara permanen**.

K3s telah menyertakan StorageClass bawaan bernama `local-path`. Kita cukup membuat `PersistentVolumeClaim (PVC)`.

1. **Buat File Manifest PVC (`02-pvc.yaml`):**
   ```bash
   nano 02-pvc.yaml
   ```
   Isi dengan konfigurasi berikut:
   ```yaml
   # PVC untuk Data MySQL (/var/lib/mysql)
   apiVersion: v1
   kind: PersistentVolumeClaim
   metadata:
     name: mysql-pvc
     namespace: web-sekolah
   spec:
     accessModes:
       - ReadWriteOnce
     storageClassName: local-path
     resources:
       requests:
         storage: 5Gi
   ---
   # PVC untuk Data WordPress & Media (/var/www/html)
   apiVersion: v1
   kind: PersistentVolumeClaim
   metadata:
     name: wordpress-pvc
     namespace: web-sekolah
   spec:
     accessModes:
       - ReadWriteOnce
     storageClassName: local-path
     resources:
       requests:
         storage: 5Gi
   ```

2. **Terapkan Manifest PVC:**
   ```bash
   kubectl apply -f 02-pvc.yaml
   ```

3. **Cek Status PVC:**
   ```bash
   kubectl get pvc -n web-sekolah
   ```
   *Status awal mungkin `Pending` atau langsung `Bound` (K3s local-path biasanya akan menjadi `Bound` segera setelah Pod yang menggunakannya dijadwalkan).*

---

### TAHAP 5: Deployment & Service Database MySQL (MariaDB)

Kita menggunakan image MariaDB 10.11 yang kompatibel penuh dengan MySQL 8.x dan lebih hemat memori untuk kebutuhan mini cluster.

1. **Buat File Manifest MySQL (`03-mysql.yaml`):**
   ```bash
   nano 03-mysql.yaml
   ```
   Isi dengan konfigurasi berikut:
   ```yaml
   apiVersion: apps/v1
   kind: Deployment
   metadata:
     name: mysql-deployment
     namespace: web-sekolah
     labels:
       app: mysql-sekolah
   spec:
     replicas: 1
     # Strategy Recreate digunakan agar tidak ada 2 pod yang berebut 1 PVC database
     strategy:
       type: Recreate
     selector:
       matchLabels:
         app: mysql-sekolah
     template:
       metadata:
         labels:
           app: mysql-sekolah
       spec:
         containers:
         - name: mariadb
           image: mariadb:10.11
           resources:
             requests:
               memory: "256Mi"
               cpu: "100m"
             limits:
               memory: "512Mi"
               cpu: "500m"
           env:
           - name: MARIADB_ROOT_PASSWORD
             valueFrom:
               secretKeyRef:
                 name: mysql-secret
                 key: mysql-root-password
           - name: MARIADB_DATABASE
             value: "db_sekolah"
           - name: MARIADB_USER
             value: "user_sekolah"
           - name: MARIADB_PASSWORD
             valueFrom:
               secretKeyRef:
                 name: mysql-secret
                 key: mysql-password
           ports:
           - containerPort: 3306
             name: mysql
           volumeMounts:
           - name: mysql-persistent-storage
             mountPath: /var/lib/mysql
         volumes:
         - name: mysql-persistent-storage
           persistentVolumeClaim:
             claimName: mysql-pvc
   ---
   # Service internal agar WordPress dapat menghubungi MySQL via DNS internal
   apiVersion: v1
   kind: Service
   metadata:
     name: mysql-service
     namespace: web-sekolah
   spec:
     type: ClusterIP
     ports:
     - port: 3306
       targetPort: 3306
     selector:
       app: mysql-sekolah
   ```

2. **Terapkan Manifest MySQL:**
   ```bash
   kubectl apply -f 03-mysql.yaml
   ```

3. **Pantau Status Pod MySQL:**
   ```bash
   kubectl get pods -n web-sekolah -w
   ```
   *Tunggu hingga kolom `STATUS` berubah menjadi `Running` (1/1).* Tekan `Ctrl + C` untuk keluar dari watch mode.

---

### TAHAP 6: Deployment & Service WordPress (Apache + PHP)

Image resmi `wordpress:latest` sudah memaketkan Web Server **Apache HTTP Server** dan modul PHP di dalamnya. Kontainer ini akan menerima request web dan berkomunikasi dengan `mysql-service`.

1. **Buat File Manifest WordPress (`04-wordpress.yaml`):**
   ```bash
   nano 04-wordpress.yaml
   ```
   Isi dengan konfigurasi berikut:
   ```yaml
   apiVersion: apps/v1
   kind: Deployment
   metadata:
     name: wordpress-deployment
     namespace: web-sekolah
     labels:
       app: wordpress-sekolah
   spec:
     replicas: 1
     selector:
       matchLabels:
         app: wordpress-sekolah
     template:
       metadata:
         labels:
           app: wordpress-sekolah
       spec:
         containers:
         - name: wordpress
           image: wordpress:latest
           resources:
             requests:
               memory: "256Mi"
               cpu: "150m"
             limits:
               memory: "512Mi"
               cpu: "500m"
           env:
           # Merujuk ke nama Service MySQL di dalam namespace yang sama
           - name: WORDPRESS_DB_HOST
             value: "mysql-service:3306"
           - name: WORDPRESS_DB_NAME
             value: "db_sekolah"
           - name: WORDPRESS_DB_USER
             value: "user_sekolah"
           - name: WORDPRESS_DB_PASSWORD
             valueFrom:
               secretKeyRef:
                 name: mysql-secret
                 key: mysql-password
           ports:
           - containerPort: 80
             name: http
           volumeMounts:
           - name: wordpress-persistent-storage
             mountPath: /var/www/html
         volumes:
         - name: wordpress-persistent-storage
           persistentVolumeClaim:
             claimName: wordpress-pvc
   ---
   # Service ClusterIP untuk menghubungkan Ingress ke WordPress
   apiVersion: v1
   kind: Service
   metadata:
     name: wordpress-service
     namespace: web-sekolah
   spec:
     type: ClusterIP
     ports:
     - port: 80
       targetPort: 80
     selector:
       app: wordpress-sekolah
   ```

2. **Terapkan Manifest WordPress:**
   ```bash
   kubectl apply -f 04-wordpress.yaml
   ```

3. **Verifikasi Status Deployment & Service:**
   ```bash
   kubectl get pods,svc -n web-sekolah
   ```
   Pastikan Pod `wordpress-deployment-*` berada dalam kondisi `Running`.

---

### TAHAP 7: Konfigurasi Ingress Controller (Traefik)

Ingress bertindak sebagai *Reverse Proxy* dan *Load Balancer* layer 7 HTTP. Traefik (bawaan K3s) mendengarkan langsung pada port 80 dan 443 di IP host Ubuntu Anda. Ingress akan membaca header `Host: sekolah.local` dari browser klien dan meneruskannya ke `wordpress-service`.

1. **Buat File Manifest Ingress (`05-ingress.yaml`):**
   ```bash
   nano 05-ingress.yaml
   ```
   Isi dengan konfigurasi berikut:
   ```yaml
   apiVersion: networking.k8s.io/v1
   kind: Ingress
   metadata:
     name: wordpress-ingress
     namespace: web-sekolah
     annotations:
       # Menggunakan Ingress Class bawaan K3s (Traefik)
       traefik.ingress.kubernetes.io/router.entrypoints: web
   spec:
     rules:
     - host: sekolah.local
       http:
         paths:
         - path: /
           pathType: Prefix
           backend:
             service:
               name: wordpress-service
               port:
                 number: 80
   ```
   *(Opsional: Anda juga bisa menambahkan domain lain seperti `web.sekolah.sch.id` di bawah blok `rules`)*.

2. **Terapkan Manifest Ingress:**
   ```bash
   kubectl apply -f 05-ingress.yaml
   ```

3. **Verifikasi Ingress:**
   ```bash
   kubectl get ingress -n web-sekolah
   ```
   **Contoh Output:**
   ```text
   NAME                CLASS    HOSTS           ADDRESS        PORTS   AGE
   wordpress-ingress   <none>   sekolah.local   192.168.1.50   80      30s
   ```

---

## 🌐 5. Konfigurasi DNS Eksternal (Tanpa Virtual IP)

Karena kita tidak menggunakan Virtual IP (VIP), nama domain `sekolah.local` harus dipetakan langsung ke IP address mesin Ubuntu tempat K3s berjalan.

Pilihlah salah satu metode berikut sesuai lingkungan pengujian Anda:

### Opsi A: Konfigurasi `hosts` di Laptop Klien (Paling Mudah & Standar Lab)
Jika mahasiswa mengakses web dari laptop pribadinya (Windows / macOS / Linux) yang berada satu jaringan Wi-Fi/LAN dengan mesin Ubuntu:

#### 1. Jika Klien menggunakan Windows:
1. Buka aplikasi **Notepad** dengan mode **Run as Administrator**.
2. Buka file: `C:\Windows\System32\drivers\etc\hosts`.
3. Tambahkan baris berikut di baris paling bawah (ganti `192.168.1.50` dengan IP VM Ubuntu Anda):
   ```text
   192.168.1.50   sekolah.local
   ```
4. Simpan file (`Ctrl + S`).

#### 2. Jika Klien menggunakan Linux atau macOS:
1. Buka terminal laptop Anda.
2. Edit file `/etc/hosts`:
   ```bash
   sudo nano /etc/hosts
   ```
3. Tambahkan baris:
   ```text
   192.168.1.50   sekolah.local
   ```
4. Simpan dan keluar (`Ctrl + O`, `Enter`, `Ctrl + X`).

---

### Opsi B: Konfigurasi DNS Server Lab (MikroTik / Pi-hole / dnsmasq)
Jika di laboratorium kampus tersedia router (misal MikroTik):
1. Masuk ke Winbox / WebFig MikroTik.
2. Navigasi ke menu **IP** -> **DNS** -> **Static**.
3. Klik tombol **Add (+)**:
   - **Name:** `sekolah.local`
   - **Type:** `A`
   - **Address:** `192.168.1.50` (IP Node K3s)
4. Klik **OK**. Semua komputer yang terhubung ke jaringan lab otomatis dapat mengakses domain tanpa mengubah file hosts masing-masing.

---

### Uji Konektivitas DNS:
Lakukan ping dari laptop klien ke domain tersebut:
```bash
ping sekolah.local
```
Jika membalas (*reply*) dari IP `192.168.1.50`, berarti resolusi DNS eksternal telah berhasil!

---

## 🚀 6. Pengujian & Verifikasi Web Sekolah

### 6.1 Akses Web Installer WordPress
1. Buka browser (Google Chrome / Mozilla Firefox) di laptop klien.
2. Kunjungi alamat: `http://sekolah.local`
3. Anda akan disambut oleh halaman instalasi resmi WordPress:
   - Pilih Bahasa: **Bahasa Indonesia** atau **English**.
   - Judul Situs: **Portal Resmi SMA Negeri 1 Informatika**
   - Nama Pengguna (*Admin Username*): `admin_sekolah`
   - Sandi (*Password*): `BuatPasswordKuat123!`
   - Email Anda: `admin@sekolah.sch.id`
4. Klik tombol **Install WordPress**.
5. Login ke Dashboard WordPress dan buat 1 postingan artikel baru untuk pengujian data (contoh: *"Pengumuman Penerimaan Siswa Baru Tahun 2026"*).

---

### 6.2 Uji Persistensi Data (Simulasi Bencana / Pod Termination)
Tujuan utama orkestrasi kontainer adalah ketahanan sistem. Mari kita uji apakah artikel yang baru dibuat akan hilang jika kontainer Pod WordPress dan Pod MySQL dihapus secara paksa.

1. **Cek nama Pod yang sedang berjalan:**
   ```bash
   kubectl get pods -n web-sekolah
   ```

2. **Hapus Pod MySQL dan Pod WordPress secara bersamaan:**
   ```bash
   kubectl delete pod -l app=mysql-sekolah -n web-sekolah
   kubectl delete pod -l app=wordpress-sekolah -n web-sekolah
   ```

3. **Perhatikan reaksi Kubernetes:**
   ```bash
   kubectl get pods -n web-sekolah -w
   ```
   > 💡 **Analisis Mahasiswa:** *Deployment Controller* mendeteksi bahwa *desired state* adalah `replicas: 1`. Karena pod lama dihapus, Kubernetes secara otomatis langsung melahirkan pod baru dalam hitungan detik.

4. **Buka kembali browser dan refresh halaman:** `http://sekolah.local`
   - Web tetap berjalan normal.
   - Artikel dan gambar yang Anda buat sebelumnya **TIDAK HILANG**.
   - Ini membuktikan bahwa `PersistentVolumeClaim` berhasil mempertahankan data di level host Ubuntu (`/var/lib/rancher/k3s/storage/`).

---

## 🔍 7. Perintah Esensial & Monitoring Mahasiswa

Sebagai calon administrator sistem Kubernetes, mahasiswa wajib menguasai perintah inspeksi terminal berikut:

### 1. Melihat Log Kontainer Secara Real-time
Gunakan perintah ini untuk memantau request web Apache yang masuk:
```bash
kubectl logs -f -l app=wordpress-sekolah -n web-sekolah
```
*(Buka halaman web di browser, perhatikan log akses Apache HTTP Server akan muncul di terminal).*

### 2. Memeriksa Detail & Status Pod (Debugging)
Jika pod mengalami error atau pending, periksa penyebabnya di bagian `Events`:
```bash
kubectl describe pod -l app=wordpress-sekolah -n web-sekolah
```

### 3. Masuk ke Dalam Shell Kontainer (Exec)
Jika Anda ingin mengecek konfigurasi Apache di dalam kontainer:
```bash
kubectl exec -it deployment/wordpress-deployment -n web-sekolah -- /bin/bash
```
Di dalam kontainer, coba cek konfigurasi apache:
```bash
ls -la /var/www/html
cat /etc/apache2/apache2.conf | head -n 20
exit
```

### 4. Mengakses Konsol MySQL Langsung dari Pod
```bash
kubectl exec -it deployment/mysql-deployment -n web-sekolah -- mysql -u user_sekolah -p
```
Masukkan password `UserWebSekolahPass456!`. Kemudian jalankan:
```sql
SHOW DATABASES;
USE db_sekolah;
SHOW TABLES;
SELECT option_name, option_value FROM wp_options WHERE option_name = 'siteurl';
EXIT;
```

---

## 🚑 8. Panduan Masalah Umum & Troubleshooting

| Gejala Kendala | Penyebab Umum | Langkah Solusi |
| :--- | :--- | :--- |
| **Status Pod `ImagePullBackOff` atau `ErrImagePull`** | Gagal mengunduh image dari Docker Hub (koneksi internet lambat / kuota habis). | Jalankan `kubectl describe pod <nama-pod> -n web-sekolah` untuk melihat error jaringan. Pastikan Ubuntu terhubung ke internet. Coba tarik manual via nerdctl/crictl jika perlu. |
| **Status Pod `CrashLoopBackOff` pada MySQL** | Memori (RAM) VM habis terpakai atau permission volume direktori storage bermasalah. | Jalankan `htop` di Ubuntu untuk memeriksa RAM. Tambahkan RAM VM menjadi 3GB/4GB. Periksa log MySQL dengan `kubectl logs -l app=mysql-sekolah -n web-sekolah`. |
| **Error: "Error establishing a database connection" di browser** | Pod WordPress tidak dapat menghubungi Pod MySQL (Service belum siap atau kredensial password di Secret salah). | 1. Pastikan pod MySQL sudah `Running`.<br>2. Cek apakah nama host di WordPress `mysql-service:3306` cocok dengan nama `Service` MySQL.<br>3. Pastikan password di `01-secret.yaml` sama dengan yang diacu oleh MySQL dan WordPress. |
| **Browser: "Site can't be reached" (ERR_NAME_NOT_RESOLVED)** | Resolusi DNS belum berhasil diarahkan ke IP VM Ubuntu. | Cek file hosts di komputer klien. Jalankan `ping sekolah.local` di Command Prompt/Terminal klien untuk memastikan sudah mengarah ke IP Ubuntu. |
| **Browser: 404 Not Found dari Traefik** | Domain yang diakses di browser berbeda dengan konfigurasi `host` di file Ingress. | Pastikan Anda mengetik `http://sekolah.local`, bukan IP langsung atau domain lain. Ingress Traefik mencocokkan header HTTP `Host`. |

---

## 📝 9. Lembar Kerja Mahasiswa (Tugas & Eksplorasi Mandiri)

Untuk menguji pemahaman Anda secara komprehensif, kerjakan tugas berikut dan cantumkan hasilnya dalam Laporan Resmi Praktikum:

### Tugas 1: Resource Scaling (Horizontal Pod Autoscaler Concept)
1. Naikkan replika WordPress menjadi 2 Pod dengan perintah:
   ```bash
   kubectl scale deployment wordpress-deployment --replicas=2 -n web-sekolah
   ```
2. Jalankan `kubectl get pods -n web-sekolah`. Amati apakah kedua Pod berhasil berjalan.
3. *Pertanyaan Analisis:* Apakah aman menaikkan replika WordPress dengan tipe penyimpanan `ReadWriteOnce (RWO)` pada kluster multi-node? Jelaskan perbedaannya dengan `ReadWriteMany (RWX)` seperti NFS atau Longhorn!

### Tugas 2: Resource Quota & Limits
1. Buka kembali file `04-wordpress.yaml`.
2. Ubah `limits.memory` menjadi `128Mi` (sengaja diturunkan).
3. Terapkan perubahan (`kubectl apply -f 04-wordpress.yaml`).
4. Akses web dan unggah file gambar berukuran besar (>5MB). Apa yang terjadi pada Pod? Apakah muncul status `OOMKilled` (Out of Memory)? Catat temuan Anda!

### Tugas 3: Simulasi Pemadaman Mesin (Reboot Test)
1. Lakukan reboot pada VM Ubuntu: `sudo reboot`.
2. Tunggu 2 menit hingga VM menyala kembali.
3. Buka browser dan akses kembali `http://sekolah.local` tanpa menyalakan pod secara manual.
4. *Pertanyaan Analisis:* Mengapa service K3s dan semua kontainer otomatis kembali menyala tanpa intervensi manual administrator? (Petunjuk: pelajari systemd service `k3s.service`).

---

## 📖 10. Referensi & Bacaan Lanjutan
1. Official Documentation K3s: [https://docs.k3s.io/](https://docs.k3s.io/)
2. Kubernetes Official Documentation: [https://kubernetes.io/docs/home/](https://kubernetes.io/docs/home/)
3. Traefik Ingress Controller for Kubernetes: [https://doc.traefik.io/traefik/providers/kubernetes-ingress/](https://doc.traefik.io/traefik/providers/kubernetes-ingress/)
4. Docker Official WordPress Image: [https://hub.docker.com/_/wordpress](https://hub.docker.com/_/wordpress)
5. Docker Official MariaDB Image: [https://hub.docker.com/_/mariadb](https://hub.docker.com/_/mariadb)
