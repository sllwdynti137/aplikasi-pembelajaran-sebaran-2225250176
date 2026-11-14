# Sebaran: Belajar Jangkauan dan Kuartil

Aplikasi web ramah smartphone (Android) untuk siswa SMP kelas IX, materi statistika: penyebaran data (jangkauan dan kuartil).
Dirancang dari wawancara siswa dengan pengelolaan **cognitive load** untuk meningkatkan **literasi matematis**.

## Fitur
- Masuk dengan nama siswa (contoh: Sela); progres tersimpan di perangkat
- Materi: **Pengertian** (bisa dibaca ulang) dan **Praktik 3D** lima langkah
- Diagram balok 3D (Three.js) dan diagram kotak-garis animasi
- Latihan kuis mudah, sedang, sulit: satu soal per layar, langsung dikoreksi
- Kuis literasi membandingkan dua kelompok (6 tahap, skor maksimum 6)
- Benar: ucapan selamat dan konfeti. Salah: "Tidak boleh menyerah, tetap semangat!" disertai pembahasan
- Animasi anak sekolah belajar, musik ceria (WebAudio), warna pink dan krem dengan tulisan maroon

## Menjalankan
Prasyarat: Node.js dan npm.
```
npm start
```
Atau buka `index.html` di browser.

## Dokumen proyek
| Berkas | Isi |
|---|---|
| [prd.md](prd.md) | Kebutuhan produk dan dasar wawancara |
| [architecture.md](architecture.md) | Arsitektur dan teknologi |
| [design.md](design.md) | Palet, tipografi, animasi, layar |
| [api.md](api.md) | Skema data dan rencana Supabase |
| [agents.md](agents.md) | Panduan untuk AI agent (Claude Code) |
| [task.md](task.md) | Daftar tugas dan jadwal |
| [docs/kisi-kisi-materi.md](docs/kisi-kisi-materi.md) | Kisi-kisi materi dan soal |

## Struktur
```
sebaran-app/
  index.html   aplikasi lengkap
  package.json
  README.md  prd.md  architecture.md  design.md  api.md  agents.md  task.md
  docs/kisi-kisi-materi.md
```

Penulis: Sela Widiyanti (2225250176), Kelas 3F, Algoritma dan Pemrograman.
