# Panduan untuk AI Agent (Claude Code)

## Konteks
Aplikasi belajar statistika (jangkauan dan kuartil) untuk siswa SMP kelas IX, pengelolaan cognitive load, target literasi matematis. Baca `prd.md`, `design.md`, `architecture.md` sebelum mengubah kode.

## Aturan
1. Bahasa antarmuka: Bahasa Indonesia, kalimat singkat dan ramah.
2. Pertahankan palet dan aturan warna di `design.md`: gambar pink-krem, teks maroon-krem.
3. Jangan menambah hiasan yang tidak berkaitan dengan materi (temuan wawancara EL03, DS03).
4. Metode kuartil: median separuh bawah dan atas tanpa median utama. Jangan diubah tanpa izin dosen.
5. Semua jawaban benar dihitung dari data lewat `st()`, jangan ditulis manual.
6. Hormati `prefers-reduced-motion`.
7. Satu berkas `index.html` tanpa build; Three.js lewat CDN dengan versi tetap.
8. Jangan menyimpan data pribadi selain nama panggilan.
9. Kunci rahasia (service key) tidak boleh masuk kode.

## Perintah
- Menjalankan: `npm start`
- Uji manual: masuk, Pengertian, Praktik 3D ganjil dan genap, kuis benar dan salah, kuis literasi.

## Tugas yang mungkin diminta
- Menyambungkan Supabase sesuai `api.md`.
- Menambah soal literasi atau tingkat kesulitan.
- Menambah materi lain (misalnya bentuk bangun) dengan pola yang sama.

## Definisi selesai
Tanpa galat di konsol, tampilan nyaman di layar 360 px, teks sesuai `design.md`, dokumen terkait ikut diperbarui.
