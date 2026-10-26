# Diary App - Praktikum 04: Props dan State

Pengembangan lanjutan dari aplikasi Diary App menggunakan antarmuka interaktif yang dikelola melalui konsep pengelolaan State dan pengiriman data (Props) antar komponen pada React Native.

## Identitas Mahasiswa
- **Nama:** Afdhal Tsany Nurrizki
- **NIM:** 2430511078
- **Semester/Kelas:** Semester 5 / Kelas B

---

## Penjelasan Penggunaan Props dan State

Berdasarkan implementasi kode pada Pertemuan 4 ini, berikut adalah rincian penggunaan State dan Props:

### 1. Penggunaan State (Manajemen Data)
State digunakan untuk menyimpan data yang dapat berubah dan memicu pembaruan antarmuka secara otomatis tanpa me-reload aplikasi.
- **Local State (State Komponen Independen):** 
  Digunakan pada komponen `SearchBar` (`queryText` untuk menyimpan teks pencarian) dan `EntryForm` (`title`, `date`, `preview` untuk menyimpan input isian pengguna sebelum disubmit).
- **Parent State / Lifting State Up:** 
  Dikelola terpusat di `DiaryListScreen` sebagai sumber data utama. State yang dikelola meliputi daftar catatan (`entries`), teks pencarian global (`query`), kumpulan ID catatan yang disukai (`likedIds`), dan data modal yang sedang dibuka (`selected`).

### 2. Penggunaan Props (Pengiriman Data & Fungsi)
Props digunakan untuk mengalirkan data statis maupun fungsi (callback) dari komponen induk (Parent) ke komponen anak (Child).
- **Data Props:** `DiaryListScreen` mengirimkan data seperti `title`, `date`, `preview`, `moodImage`, dan status `liked` ke `DiaryCard` agar dapat dirender secara dinamis sebagai *presentational component*.
- **Callback Props:** Fungsi dikirimkan sebagai props agar komponen anak dapat memicu perubahan pada state induk. Contohnya: fungsi `onToggleLike` dan `onPress` dikirim ke `DiaryCard`, `onChange` dikirim ke `SearchBar`, dan `onSubmit` dikirim ke `EntryForm`.

---

## Fitur Aplikasi
- **Daftar Catatan:** Menampilkan daftar buku harian menggunakan gambar lokal dari `assets/moods`.
- **Interaksi Like:** Mengubah status "suka" secara instan menggunakan ikon hati (🤍/❤️) tanpa reload aplikasi.
- **Pencarian Dinamis:** Menyaring daftar buku harian secara real-time berdasarkan teks yang diketik (menggunakan *derived state*).
- **Tambah Entri:** Menginput catatan baru melalui form terkontrol (*controlled form*) yang akan langsung muncul di urutan teratas daftar.

---