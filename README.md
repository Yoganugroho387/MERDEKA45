# Merdeka45 — Portal Berita Nasional Pro

**Merdeka45** adalah platform web portal berita nasional modern, cepat, dan responsif yang dibangun menggunakan arsitektur **PHP Native MVC**, **Database MySQL (PDO)**, dan **Tailwind CSS**. Sistem ini dirancang untuk menyajikan berita secara berimbang, akurat, dan memiliki antarmuka yang elegan dengan dukungan optimasi perangkat mobile serta panel manajemen berita admin yang lengkap.

---

## Daftar Fitur Utama Platform

### 1. Antarmuka Publik & Pengalaman Pengguna (Frontend)

- **Desain Layout Modern Style**:
  - Layout berita terstruktur dengan grid berita terkini, headline utama, serta widget sidebar populer.
  - Sudut elemen visual dan kartu berita berdesain siku 90 derajat yang tegas dan profesional.

- **Tampilan Khusus Mobile (Default Ringkas / List View)**:
  - Pada layar smartphone/mobile, daftar berita otomatis menyajikan tampilan **Ringkas (List View)** tanpa opsi switcher yang mengganggu.
  - Mengoptimalkan ruang baca dan kecepatan loading di perangkat mobile.

- **Animasi Navigasi Mobile (Cascading Unrolling Curtain)**:
  - Menu navigasi mobile membuka dengan efek gelaran bertahap yang mulus (*staggered entrance*).
  - Peralihan otomatis ikon burger ke tombol penutup (*xmark*).

- **Logo Emblem Sticky Navbar (Smooth Scroll)**:
  - Logo emblem Merdeka45 secara otomatis meluncur dan muncul di navbar atas saat pengunjung meng-scroll halaman ke bawah.

- **Running Text Breaking News (Terkini Ticker)**:
  - Pita berita berjalan di bagian atas halaman untuk menyampaikan berita yang sedang hangat terjadi.

- **Pita Tag Trending Otomatis (Hashtag Bar)**:
  - Menampilkan topik trending dan tagar populer secara otomatis dari kategori berita.

- **Widget Cuaca Real-Time & Kurs Mata Uang (USD/IDR)**:
  - Menampilkan suhu cuaca wilayah Jakarta dan nilai tukar kurs USD ke IDR secara otomatis melalui API publik real-time.

- **Indikator Kemajuan Navigasi (Loading Progress Bar)**:
  - Indikator pita warna di bagian paling atas halaman yang bergerak halus saat pengunjung berpindah antar artikel.

- **Langganan Warta (Newsletter Footer & SMTP Auto-Broadcast)**:
  - Form berlangganan email terintegrasi di footer website via AJAX.
  - Pembaca akan menerima email konfirmasi otomatis serta warta berita setiap kali artikel baru diterbitkan.

- **Halaman Statis & Legalitas**:
  - Menyediakan halaman Kebijakan Privasi, Syarat & Ketentuan, Pedoman Media Siber, Kontak Redaksi, dan Mitra & Partner.

- **Optimasi SEO & Feed Publik**:
  - Generator sitemap XML otomatis (`/sitemap.xml`).
  - Feed RSS publik (`/rss.xml` dan `/feed`) untuk integrasi pembaca berita eksternal.

---

### 2. Panel Manajemen Administrator (Admin Dashboard Pro)

- **Panel Admin Berbasis Shadcn UI Style**:
  - Antarmuka admin bernuansa dark mode profesional dengan sidebar navigasi terorganisir.

- **Manajemen Artikel Berita**:
  - Tambah, edit, dan hapus artikel berita dengan fitur kaya teks (konten rich-text), ringkasan, gambar thumbnail, status headline, dan breaking news.
  - Fitur pengarsipan status berita (*published*, *draft*, *pending*).

- **Alur Pengawasan Berita (Pending Review Workflow)**:
  - Halaman khusus untuk meninjau artikel draf atau kiriman penulis sebelum dipublikasikan ke publik.

- **Integrasi API Berita Eksternal (Currents API Sync)**:
  - Sinkronisasi berita nasional otomatis dari sumber Currents API dengan sekali klik di panel admin.

- **Manajemen Banner Iklan Penutup & Sponsor**:
  - Admin dapat menambah, mengubah, dan mengaktifkan slot banner iklan di berbagai posisi:
    - Banner Leaderboard Header (728x90)
    - Banner Tengah Beranda (728x90)
    - Banner In-Feed Sela Berita
    - Banner Sidebar Kanan (300x250)
    - Banner Penutup Beranda Utama
  - Disertai petunjuk ukuran piksel banner agar pas dipasang.

- **Manajemen Langganan Warta (Subscribers Management)**:
  - Melihat daftar seluruh email pelanggan aktif, tanggal mendaftar, serta opsi pengiriman broadcast email manual maupun hapus subscriber.

- **Pengaturan Server SMTP Email & Uji Coba (Test SMTP)**:
  - Konfigurasi Host SMTP, Port, Username, Password, Nama & Email Pengirim, serta saklar otomatisasi broadcast.
  - Fitur tombol *Test Pengiriman Email* untuk memastikan server SMTP terhubung dengan baik.

- **Manajemen Kategori Berita**:
  - Mengelola data kategori berita, slug URL, dan melihat statistik jumlah artikel per kategori.

- **Manajemen Mitra & Partner**:
  - Mengelola daftar logo dan tautan mitra kerja sama.

- **Manajemen Pengguna Admin (User Management)**:
  - Mengelola akun pengelola website (Admin/Editor).

---

## Teknologi yang Digunakan

- **Bahasa Pemrograman**: PHP (Object-Oriented Programming, MVC Architecture)
- **Database**: MySQL / MariaDB (Koneksi PDO Aman & Prepared Statements)
- **Styling UI**: Tailwind CSS (Utility-First CSS Framework)
- **Ikonografi**: FontAwesome 6 Free Pro Icons
- **Tipografi**: Google Fonts (Open Sans)
- **Klien Email**: Socket Native SMTP Engine PHP
- **Web Server**: Apache / Nginx / LiteSpeed dengan modul Rewrite (`.htaccess`)

---

## Struktur Direktori Proyek

```text
yoportal_berita/
├── app/
│   ├── config/          # Konfigurasi database & variabel aplikasi
│   ├── controllers/     # Logika pengontrol (Frontend & Admin)
│   ├── core/            # Framework inti (App, Controller, Database, Mailer, Helper)
│   ├── models/          # Model database (News, Category, Banner, Subscriber, Partner, Setting, User)
│   └── views/           # Tampilan antarmuka HTML/PHP (Frontend & Admin)
├── public/              # Berkas publik (index.php, .htaccess, aset gambar,CSS, JS)
├── storage/             # Direktori penyimpanan unggahan & skrip pembantu
├── .htaccess            # Aturan routing Apache utama
├── database_merdeka45.sql # File dump database lengkap untuk deployment
└── README.md            # Dokumentasi proyek
```

---

## Panduan Instalasi Lokal (Laragon / XAMPP)

1. **Clone / Ekstrak Proyek**:
   Letakkan folder proyek di direktori `htdocs` (XAMPP) atau `www` (Laragon).

2. **Import Database**:
   - Buka **phpMyAdmin** (`http://localhost/phpmyadmin`).
   - Buat database baru dengan nama `portal_berita`.
   - Import file `database_merdeka45.sql` yang berada di direktori akar proyek.

3. **Konfigurasi Database**:
   Buka file `app/config/config.php`, lalu sesuaikan kredensial MySQL jika diperlukan:
   ```php
   define('DB_HOST', '127.0.0.1');
   define('DB_USER', 'root');
   define('DB_PASS', '');
   define('DB_NAME', 'portal_berita');
   ```

4. **Akses Website**:
   - Beranda Publik: `http://localhost/yoportal_berita`
   - Portal Login Admin: `http://localhost/yoportal_berita/yoportal`

---

## Panduan Deploy ke cPanel Hosting

1. **Upload ZIP Proyek**: Upload file `yoportal_berita_cpanel.zip` ke folder `public_html` di cPanel File Manager, lalu ekstrak.
2. **Import Database**: Buat database MySQL di cPanel, lalu import file `database_merdeka45.sql` melalui phpMyAdmin cPanel.
3. **Edit Konfigurasi**: Sesuaikan `DB_USER`, `DB_PASS`, dan `DB_NAME` pada file `app/config/config.php` dengan data MySQL cPanel Anda.

---

---

*Hak Cipta &copy; 2026 Merdeka45 Portal Berita Pro. Seluruh hak cipta dilindungi undang-undang.*
