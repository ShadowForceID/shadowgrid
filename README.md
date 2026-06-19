# 🛡️ SHADOWGRID

<div align="center">

![Shadowgrid Banner](https://img.shields.io/badge/SHADOWGRID-Platform%20Keamanan%20Digital-080c10?style=for-the-badge&logoColor=white)

**Platform Keamanan Digital oleh ShadowForce**

[![Live Platform](https://img.shields.io/badge/🌐%20Live-shadowgrid.shadowforce.id-blue?style=flat-square)](cooming-soon)
[![Authorized Use Only](https://img.shields.io/badge/⚠️%20Authorized-Use%20Only-red?style=flat-square)](#)
[![Blue Team](https://img.shields.io/badge/🔵%20Blue-Team%20Ready-1e90ff?style=flat-square)](#)
[![Modules](https://img.shields.io/badge/🧩%20Modules-22%2B%20Tools-green?style=flat-square)](#-detail-fitur)
[![Researchers](https://img.shields.io/badge/👥%20Researchers-2%20Security%20Experts-purple?style=flat-square)](#)

> *Kenali domain sebelum orang lain.*

</div>

---

## 📌 Tentang SHADOWGRID

**SHADOWGRID** adalah platform keamanan digital yang dikembangkan oleh **ShadowForce** untuk membantu pemilik domain dan tim keamanan memahami postur keamanan aset digital mereka secara menyeluruh.

Platform ini mengintegrasikan **domain reconnaissance** dan **web application testing** ke dalam satu antarmuka terpadu — menghasilkan laporan terstruktur yang mencakup integrity score, findings per severity, rekomendasi perbaikan, dan analisis AI mendalam.

> ⚠️ **Hanya untuk penggunaan yang diotorisasi.** Platform ini dirancang untuk pemilik domain yang ingin menganalisis aset mereka sendiri. Penggunaan tanpa otorisasi dilarang keras.

---

## 🚀 Cara Kerja

```
01. Buat Akun
    └── Daftar gratis, tanpa kartu kredit.
        Akses langsung ke semua tools yang tersedia.

02. Input Domain Target
    └── Masukkan domain yang Anda miliki otorisasi untuk dianalisis.
        Konfirmasi persetujuan penggunaan, lalu jalankan pemindaian.

03. Baca Laporan
    └── Lihat integrity score, findings per severity,
        rekomendasi konkret, dan analisis AI mendalam.
        Unduh: HTML · TXT · JSON · PDF · ZIP Bundle
```

---

## 🔍 Detail Fitur

### 🌐 DNS Records & Mail Security

Modul ini memetakan keseluruhan **DNS posture** sebuah domain secara komprehensif, termasuk konfigurasi mail security yang sering menjadi celah masuk serangan phishing dan spoofing.

| Record | Fungsi |
|---|---|
| **A / AAAA** | Resolusi IPv4 dan IPv6 domain |
| **MX** | Identifikasi mail server dan prioritasnya |
| **NS** | Nameserver yang bertanggung jawab atas domain |
| **TXT** | Data teks arbitrari, termasuk verifikasi domain |
| **SPF** | Validasi apakah server pengirim email diotorisasi |
| **DMARC** | Kebijakan autentikasi email dan pelaporan |
| **DKIM** | Deteksi konfigurasi tanda tangan digital email |
| **CAA** | Certificate Authority yang diizinkan menerbitkan sertifikat |

Temuan yang dihasilkan mencakup konfigurasi yang hilang, salah konfigurasi SPF/DMARC yang memungkinkan email spoofing, serta tidak adanya record CAA yang membuka risiko misissuance sertifikat.

---

### 🔒 TLS / SSL Assessment

Modul ini melakukan validasi menyeluruh terhadap implementasi HTTPS domain target — mulai dari proses handshake hingga kepercayaan rantai sertifikat.

- **Handshake Validation** — Memastikan koneksi TLS berhasil dibangun dan tidak terdapat error negosiasi.
- **Trust Chain** — Memverifikasi bahwa sertifikat dikeluarkan oleh CA yang terpercaya dan rantai sertifikat tidak terputus.
- **Certificate Expiry** — Mendeteksi sertifikat yang sudah kedaluwarsa atau akan segera habis masa berlakunya.
- **Protocol Version** — Mengidentifikasi penggunaan protokol lawas yang tidak aman seperti SSLv3, TLS 1.0, dan TLS 1.1.
- **Cipher Suite** — Menganalisis kekuatan cipher yang didukung server dan menandai cipher yang lemah atau deprecated.
- **SSLyze Integration** — Pemindaian mendalam cipher suites, protocol negotiation, dan validasi cert chain menggunakan SSLyze.

---

### 📋 HTTP Security Headers

Pemeriksaan lengkap terhadap header keamanan HTTP yang dikirimkan server. Setiap header yang hilang atau salah konfigurasi menghasilkan finding dengan tingkat severity yang sesuai dan rekomendasi implementasi konkret.

| Header | Perlindungan |
|---|---|
| **HSTS** | Memaksa koneksi HTTPS, mencegah downgrade ke HTTP |
| **Content-Security-Policy (CSP)** | Membatasi sumber daya yang boleh dimuat, mitigasi XSS |
| **X-Frame-Options** | Mencegah clickjacking via iframe embedding |
| **X-Content-Type-Options (nosniff)** | Mencegah MIME-type sniffing oleh browser |
| **Referrer-Policy** | Mengontrol informasi referrer yang dikirim ke pihak ketiga |
| **Permissions-Policy** | Membatasi akses fitur browser seperti kamera, mikrofon, geolokasi |

---

### 🔍 Port Exposure Analysis

Modul ini memetakan **attack surface jaringan** dengan mendeteksi port-port yang aktif dan layanan yang berjalan di baliknya — membantu mengidentifikasi service yang mungkin terekspos secara tidak terduga.

- **TCP Connect Scan** — Koneksi langsung ke port-port umum untuk memverifikasi keterbukaan.
- **Common Ports** — Pemindaian mencakup port-port standar seperti 21 (FTP), 22 (SSH), 23 (Telnet), 25 (SMTP), 80 (HTTP), 443 (HTTPS), 3306 (MySQL), 8080, dan lainnya.
- **Service Mapping** — Mengidentifikasi service dan versinya melalui banner grabbing.
- **Exposure Report** — Laporan ringkas port mana yang seharusnya tidak publik namun terdeteksi terbuka.

---

### 🕷️ XSS Scanner

Modul pemindaian **Cross-Site Scripting (XSS)** yang menguji parameter input pada aplikasi web target terhadap berbagai vektor injeksi skrip berbahaya.

- **Reflected XSS** — Menguji apakah input yang dikirim langsung dikembalikan ke halaman tanpa sanitasi yang memadai.
- **Stored XSS** — Mendeteksi kemungkinan penyimpanan payload berbahaya di server yang akan dieksekusi saat halaman dimuat.
- **WAF Bypass** — Menggunakan teknik encoding dan obfuscation untuk menguji apakah Web Application Firewall dapat dilewati.

---

### 💉 SQL Injection Scanner

Modul pengujian **SQL Injection** yang mencoba mengeksploitasi parameter input untuk berinteraksi langsung dengan database backend.

- **Error-based** — Memancing pesan error database yang mengungkap struktur query internal.
- **Boolean-based Blind** — Mengirim kondisi true/false untuk menyimpulkan data dari respons yang berbeda.
- **GET / POST Parameter** — Pengujian dilakukan pada parameter URL (GET) maupun body form (POST).

---

### 📁 Directory Bruteforce

Modul penemuan direktori dan file tersembunyi yang tidak terdaftar secara publik pada aplikasi web target.

- **Built-in Wordlist** — Menggunakan daftar kata yang dikurasi berisi path umum seperti `/admin`, `/backup`, `/config`, `.env`, dan lainnya.
- **Custom 404 Handling** — Mendeteksi implementasi halaman 404 kustom agar tidak menghasilkan false positive berlebih.
- **Path Discovery** — Mengidentifikasi endpoint yang tidak sengaja terbuka seperti panel admin, file backup, atau dokumentasi internal.

---

### 🔑 Admin Finder

Modul deteksi panel administrasi dan login yang terekspos secara publik pada aplikasi web.

- **Login Panel Detection** — Mencari keberadaan halaman login admin di path-path umum.
- **CMS Detection** — Mengidentifikasi Content Management System (CMS) yang digunakan seperti WordPress, Joomla, Drupal, dan lainnya untuk mempersempit pencarian panel admin spesifik CMS tersebut.

---

### 🌍 CORS Scanner

Modul analisis konfigurasi **Cross-Origin Resource Sharing (CORS)** yang salah konfigurasi dapat memungkinkan domain berbahaya mengakses data sensitif API.

- **Origin Reflection** — Mendeteksi apakah server memantulkan Origin header apa pun tanpa validasi.
- **Wildcard (`*`)** — Mengidentifikasi penggunaan wildcard CORS yang memperbolehkan semua origin mengakses resource.
- **Null Origin** — Menguji apakah request dengan `Origin: null` diterima, yang dapat dieksploitasi dari sandbox atau file lokal.

---

### 🧬 CVE Check

Modul pencocokan terhadap **kerentanan yang telah diketahui dan terdokumentasi** (Common Vulnerabilities and Exposures) berdasarkan layanan dan versi yang terdeteksi.

- **Log4Shell (CVE-2021-44228)** — Salah satu kerentanan paling kritis, memungkinkan Remote Code Execution via logging Apache Log4j.
- **Spring4Shell (CVE-2022-22965)** — RCE pada Spring Framework melalui data binding yang tidak aman.
- **Known CVEs** — Pencocokan terhadap database CVE untuk layanan dan versi software yang teridentifikasi selama pemindaian.

---

### ⚛️ Nuclei Scan

Pemindaian berbasis **template Nuclei** — framework open-source untuk deteksi kerentanan, misconfiguration, dan exposed panels secara cepat dan fleksibel.

- **Template-based** — Menggunakan ribuan template komunitas yang terus diperbarui untuk mendeteksi pola kerentanan spesifik.
- **CVE Templates** — Template khusus untuk CVE yang baru diterbitkan.
- **Misconfiguration Detection** — Mendeteksi konfigurasi server yang salah, exposed sensitive files, dan panel yang tidak seharusnya publik.

---

### 🔬 Nessus Scan

Pemindaian kerentanan menggunakan **Nessus** via integrasi HostedScan API — salah satu scanner kerentanan enterprise paling komprehensif di industri.

- **Plugin-based** — Nessus memiliki ribuan plugin yang menguji berbagai aspek keamanan secara otomatis.
- **Vulnerability Detection** — Mengidentifikasi kerentanan pada layanan, OS, dan aplikasi yang berjalan di host target.
- **CVE Matching** — Mencocokkan temuan dengan entri CVE resmi beserta skor CVSS-nya.

---

### 🦠 OpenVAS Scan

Pemindaian menggunakan **OpenVAS** (Open Vulnerability Assessment System) via HostedScan API — scanner kerentanan open-source berbasis NVT (Network Vulnerability Tests).

- **NVT-based** — Menggunakan ribuan Network Vulnerability Test yang diperbarui secara rutin.
- **Comprehensive Coverage** — Mencakup pengujian jaringan, layanan, dan aplikasi secara mendalam.
- **HostedScan API** — Dijalankan melalui infrastruktur HostedScan untuk hasil yang konsisten dan andal.

---

### 🕵️ OWASP ZAP (Passive & Active)

Integrasi dengan **OWASP Zed Attack Proxy (ZAP)** — salah satu tool pengujian keamanan aplikasi web paling populer di dunia.

**Passive Mode:**
- Menganalisis header HTTP response dan struktur halaman tanpa mengirim payload berbahaya.
- Mendeteksi misconfiguration keamanan yang terlihat dari respons normal server.

**Active Mode:**
- Melakukan simulasi serangan aktif termasuk injeksi payload berbahaya ke parameter input.
- Menguji kerentanan injeksi, autentikasi yang lemah, dan logika aplikasi yang rentan.

---

### 🗺️ NMAP TCP & UDP

Pemetaan jaringan mendalam menggunakan **NMAP** via HostedScan API untuk menemukan port dan layanan yang aktif.

**NMAP TCP:**
- Penemuan port TCP aktif menggunakan metode TCP Connect dan SYN scan.
- Identifikasi layanan dan versinya melalui banner grabbing.

**NMAP UDP:**
- Penemuan port UDP yang sering terlewat oleh scanner TCP biasa.
- Mengidentifikasi layanan tersembunyi seperti DNS (53), SNMP (161), NTP (123), dan lainnya.

---

### 🌿 Subdomain Enumeration

Modul enumerasi **subdomain** untuk menemukan aset tersembunyi atau terlupakan yang terhubung ke domain utama.

- **DNS Lookup** — Resolusi aktif terhadap kandidat subdomain menggunakan DNS query.
- **Wordlist Enumeration** — Menggunakan daftar kata yang dikurasi untuk menebak subdomain umum seperti `dev.`, `staging.`, `api.`, `admin.`, dan sebagainya.

---

### 🕸️ ParamSpider (URL Mining)

Modul pengumpulan **parameter URL** dari arsip web untuk menemukan endpoint lama yang mungkin masih aktif dan rentan.

- **Wayback Archive** — Mengekstrak URL historis dari Wayback Machine (Internet Archive) untuk menemukan parameter yang pernah digunakan.
- **URL Mining** — Mengumpulkan dan menganalisis pola parameter dari berbagai sumber untuk memperluas attack surface yang diuji.

---

### 🖼️ CMS Fingerprint

Modul identifikasi **Content Management System** dan teknologi web yang digunakan oleh domain target.

- **Framework Detection** — Mengidentifikasi framework web seperti WordPress, Laravel, Django, dan lainnya.
- **Server Fingerprinting** — Mendeteksi web server (Apache, Nginx, IIS) dan versinya.
- **Version Detection** — Mengidentifikasi versi spesifik CMS untuk mencocokkan dengan kerentanan yang diketahui.

---

### 📦 JS Bundle Audit

Modul analisis **file JavaScript** yang di-bundle dan dikirim ke browser untuk menemukan informasi sensitif yang tidak sengaja terekspos.

- **API Key Detection** — Mendeteksi API key, token, dan credential yang ter-hardcode dalam kode JavaScript publik.
- **Secret Scanning** — Menemukan secret seperti password, private key, dan JWT secret yang tidak seharusnya ada di client-side code.
- **Debug Comments** — Mengidentifikasi komentar debug, endpoint internal, dan informasi sensitif lain yang tertinggal di production build.

---

### 🐙 GitHub Leak Intelligence

Modul intelijen untuk mendeteksi **kebocoran informasi sensitif** pada repository GitHub publik yang terkait dengan domain atau organisasi target.

- **Public Repository Scan** — Menelusuri repository publik yang terhubung dengan domain atau nama organisasi target.
- **Credential Detection** — Mencari password, API key, token, dan credential lain yang tidak sengaja di-commit.
- **Configuration Leak** — Mendeteksi file konfigurasi sensitif seperti `.env`, `database.yml`, `config.json`, dan sejenisnya yang ter-push ke repository publik.

---

## 📄 Format Laporan

Setiap hasil analisis dapat diekspor dalam berbagai format sesuai kebutuhan:

```
📦 ZIP Bundle     → Paket lengkap semua format dalam satu unduhan
📄 HTML Report    → Tampilan visual interaktif dengan navigasi per modul
📋 TXT Report     → Plain text ringkas untuk integrasi pipeline & scripting
🔢 JSON Export    → Machine-readable, cocok untuk SIEM, dashboard, atau automation
📑 PDF Report     → Format profesional siap cetak untuk dokumentasi & presentasi
```

Setiap laporan menyertakan:
- **Integrity Score** — Skor keamanan keseluruhan domain
- **Findings per Severity** — Temuan dikelompokkan berdasarkan tingkat keparahan (Critical, High, Medium, Low, Info)
- **Rekomendasi** — Langkah perbaikan konkret untuk setiap temuan
- **AI Analysis** — Analisis mendalam berbasis AI yang merangkum postur keamanan secara naratif

---

## 🛠️ Tech Stack & Integrasi

- **Scanning Engine** — Nuclei · Nessus · OpenVAS · NMAP · OWASP ZAP · SSLyze
- **API Integration** — HostedScan API untuk NMAP TCP/UDP, Nessus, dan OpenVAS
- **Recon Tools** — ParamSpider · Wayback Machine API · GitHub Public API
- **AI Analysis** — Analisis mendalam berbasis AI untuk setiap laporan
- **Export Formats** — HTML · JSON · TXT · PDF · ZIP Bundle

---

## 📊 Platform Stats

| Metrik | Nilai |
|---|---|
| 🧩 Check Modules | 22+ tools aktif |
| 👥 Security Researchers | 13 anggota tim |
| 📋 Report Format | HTML, TXT, JSON, PDF, ZIP |
| 🎯 Pendekatan | Blue Team · Defensive · Non-Intrusive |
| 💰 Akses Dasar | Gratis |

---

## 🔐 Prinsip Keamanan

1. **Analisis Terstruktur** — Setiap pemeriksaan dirancang untuk memberikan gambaran menyeluruh terhadap konfigurasi domain tanpa mengganggu sistem target.

2. **Authorized Use Only** — Platform ini hanya untuk pemilik domain yang ingin memahami postur keamanan aset mereka sendiri.

3. **Findings yang Actionable** — Setiap temuan disertai penjelasan dan rekomendasi konkret — tujuannya perbaikan, bukan ketakutan.

4. **Responsible Disclosure** — Seluruh aktivitas platform berpegang pada prinsip ethical security research.

---

## 🌐 Akses Platform

| Link | Keterangan |
|---|---|
| 🔗 [shadowgrid.shadowforce.id](https://shadowgrid.shadowforce.id) | Platform utama |
| 🔑 [/login](https://shadowgrid.shadowforce.id/login) | Masuk / Buat akun gratis 
| 🏠 [shadowforce.id](https://shadowforce.id) | ShadowForce |

---

## ⚠️ Disclaimer

> Platform ini **hanya boleh digunakan untuk domain yang Anda miliki atau memiliki otorisasi eksplisit untuk dianalisis**. Penggunaan SHADOWGRID untuk memindai domain pihak ketiga tanpa izin merupakan pelanggaran hukum dan melanggar **Ketentuan Penggunaan** platform ini.
>
> ShadowForce tidak bertanggung jawab atas penyalahgunaan platform. Semua aktivitas pemindaian dicatat dan dimonitoring.

---

## 👥 Tim

Dikembangkan dengan ❤️ oleh **ShadowForce** — tim yang terdiri dari 2 security researchers berdedikasi membangun alat keamanan yang berguna, etis, dan actionable.

---

<div align="center">

**Mode pasif/defensif · Gunakan hanya untuk aset yang Anda miliki**

© 2026 ShadowForce · [shadowforce.id](https://shadowforce.id)

</div>
