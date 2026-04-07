💰 JO Personal Finance - Fullstack Expense Tracker
JO Personal Finance adalah aplikasi manajemen keuangan pribadi berbasis web yang memungkinkan pengguna untuk mencatat pemasukan dan pengeluaran harian secara real-time. Aplikasi ini dibangun dengan arsitektur Fullstack JavaScript menggunakan MySQL sebagai penyimpanan data.

🚀 Fitur Utama
Full CRUD Operations: Tambah, Lihat, Edit, dan Hapus riwayat transaksi.

Real-time Dashboard: Kartu statistik otomatis yang menghitung Total Saldo, Total Pemasukan, dan Total Pengeluaran.

Modern UI/UX: Tampilan bersih dan responsif menggunakan Tailwind CSS dan Font Poppins.

Dynamic Styling: Indikator warna otomatis (Merah untuk pengeluaran, Hijau untuk pemasukan).

Sticky Form: Form input yang tetap terlihat saat melakukan scrolling pada daftar transaksi yang panjang.

🛠️ Tech Stack
Aplikasi ini menggunakan kombinasi teknologi modern:

Frontend
React.js (Vite): Library utama untuk UI.

Tailwind CSS: Framework styling untuk tampilan modern.

Axios: Library untuk melakukan HTTP Request ke API backend.

Lucide React / Emojis: Untuk ikonografi yang menarik.

Backend
Node.js & Express.js: Runtime dan framework untuk server API.

MySQL / MariaDB: Database relasional untuk menyimpan data transaksi.

MySQL2: Driver database dengan dukungan Connection Pool.

Dotenv: Untuk mengelola variabel lingkungan (Environment Variables).

Cors: Untuk mengizinkan akses API dari frontend.

📋 Prasyarat
Sebelum menjalankan proyek ini, pastikan kamu sudah menginstal:

Node.js (Versi 18 ke atas)

XAMPP (Untuk MySQL/MariaDB)

Git

⚙️ Cara Instalasi & Menjalankan

1. Persiapan Database
   Buka phpMyAdmin atau terminal MySQL.

Buat database baru bernama upk_db.

Jalankan query berikut:

SQL
CREATE TABLE transactions (
id INT AUTO_INCREMENT PRIMARY KEY,
description VARCHAR(255) NOT NULL,
amount DECIMAL(15, 2) NOT NULL,
type ENUM('pemasukan', 'pengeluaran') NOT NULL,
category VARCHAR(100),
date DATE NOT NULL,
created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
); 2. Setup Backend
Masuk ke folder backend: cd backend

Instal dependensi: npm install

Buat file .env dan sesuaikan konfigurasinya:

Cuplikan kode
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=
DB_NAME=upk_db
PORT=5000
Jalankan server: npm run dev

3. Setup Frontend
   Buka terminal baru, masuk ke folder frontend: cd frontend

Instal dependensi: npm install

Jalankan aplikasi: npm run dev

Buka browser di: http://localhost:5173

📖 Ringkasan Tutorial Pembuatan
Berikut adalah alur logika yang digunakan dalam membangun proyek ini:

Arsitektur Database: Menggunakan tipe data DECIMAL untuk uang agar presisi dan ENUM untuk kategori tipe agar data konsisten.

API Design: Membangun RESTful API dengan Express.js. Menggunakan Connection Pool di MySQL untuk mencegah error connection closed.

Frontend Logic:

Menggunakan useEffect untuk mengambil data saat aplikasi pertama kali dimuat.

Menggunakan fungsi .reduce() untuk menghitung total saldo secara otomatis dari array transaksi.

Mode Editing menggunakan state isEditing untuk mengubah fungsi tombol "Simpan" menjadi "Update".

Styling: Memanfaatkan utility-first class dari Tailwind untuk membuat layout grid 3-kolom pada dashboard dan 2-kolom pada konten utama.

📂 Struktur Folder
Plaintext
UPK-CRUD/
├── backend/
│ ├── config/ # Konfigurasi DB
│ ├── controllers/ # Logika Bisnis
│ ├── routes/ # Jalur API
│ ├── server.js # Entry Point
│ └── .env # Variabel Rahasia
├── frontend/
│ ├── src/
│ │ ├── api/ # Konfigurasi Axios
│ │ ├── App.jsx # Main Component
│ │ └── main.jsx # Entry Point
└── README.md
👤 Author
Nama zaw - zawindra
