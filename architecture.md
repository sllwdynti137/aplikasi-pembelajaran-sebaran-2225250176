# Arsitektur

## Gambaran
Aplikasi web satu halaman (single-page) tanpa build. Seluruh kode ada di `index.html`.

```
Browser Android
 |-- UI (HTML + CSS)              -> tampilan, tema pink-krem, animasi CSS
 |-- Logika (JavaScript)
 |     |-- statistik: st(), med(), mi()
 |     |-- materi: mat(), box()
 |     |-- kuis: quiz(), qz(), chk(), fin(), gen(), litQ()
 |     |-- progres: sv(), ld() -> localStorage
 |-- 3D (Three.js r128 via CDN)   -> balok data, bola melayang
 |-- Audio (WebAudio API)         -> musik latar dibangkitkan kode
 `-- (Rencana) Supabase           -> tabel students dan scores
```

## Teknologi
| Bagian | Pilihan | Alasan |
|---|---|---|
| Bahasa | JavaScript, HTML, CSS | Sesuai syarat tugas; ringan di HP |
| 3D | Three.js | Pelengkap ilustrasi 3D |
| Musik | WebAudio | Tidak perlu berkas lagu (bebas hak cipta) |
| Penyimpanan | localStorage (sekarang), Supabase (rencana) | Sederhana dulu, server menyusul |
| Hosting | GitHub / layanan hosting statis gratis | Gratis sementara |

## Alur data
1. Siswa memasukkan nama -> `masuk()` memuat progres dari localStorage (`sebaran:<nama>`).
2. Materi memanggil `st(data)` untuk menghitung R, Q1, Q2, Q3, lalu menggambar 3D dan diagram kotak-garis.
3. Kuis membuat soal (`gen`, `litQ`), menilai jawaban, memperbarui `P.ok`, `P.tot`, `P.lit`, lalu `sv()`.

## Rencana Supabase
Tabel `students(id, name, created_at)` dan `scores(id, student_id, kind, score, total, created_at)`. Detail ada di `api.md`.

## Keputusan
- Satu berkas agar mudah diunggah ke GitHub dan dipresentasikan.
- Soal dibangkitkan acak oleh kode, jawaban benar dihitung dari data sehingga selalu konsisten.
- Dependensi luar hanya Three.js dan Google Fonts; jika offline, tulisan memakai font cadangan.

## Keamanan dan privasi
Hanya nama panggilan yang disimpan. Tidak ada kata sandi atau data sensitif. Saat Supabase dipakai, aktifkan Row Level Security.
