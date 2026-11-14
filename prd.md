# PRD: Aplikasi Sebaran (Jangkauan dan Kuartil)

## 1. Latar belakang
Hasil wawancara dengan siswa S01 (kelas IX C) menunjukkan jangkauan mudah dikenali, tetapi penentuan kuartil (Q1 dan Q3) menantang: siswa harus mengurutkan data, mencari median, membagi data, lalu mencari median lagi. Kesulitan makin besar pada data genap, data banyak, tabel, dan soal cerita panjang. Tampilan yang ramai membuat siswa sulit fokus.

## 2. Tujuan
- Membantu siswa SMP memahami jangkauan dan kuartil secara bertahap.
- Mengelola *cognitive load* (intrinsic, extraneous, germane) sesuai temuan wawancara.
- Meningkatkan **literasi matematis**: merumuskan, menggunakan, dan menafsirkan matematika dalam konteks (membandingkan dua kelompok data dan memberi alasan).

## 3. Pengguna
Siswa SMP kelas IX, memakai smartphone Android. Masuk dengan nama siswa.

## 4. Masalah dan solusi (dari wawancara)
| Kode | Temuan S01 | Solusi di aplikasi |
|---|---|---|
| IL01-IL05 | Q1 dan Q3 sulit; data genap dan banyak lebih sulit | Praktik 3D lima langkah, data ganjil dan genap, latihan bertingkat |
| EL01, EL05 | Soal panjang membingungkan | Kalimat soal singkat, data ditampilkan terpisah |
| EL02, EL03 | Tampilan ramai mengganggu; penanda warna sederhana membantu | Warna konsisten untuk Q1, Q2, Q3; hiasan dibatasi |
| EL04 | Perlu urutan runtut dan bisa mengulang | Tombol Sebelumnya, Berikutnya, Ulangi; halaman Pengertian |
| GL01-GL03 | Contoh bertahap dan petunjuk membantu | Pembahasan langkah setelah setiap soal |
| GL02 | Memeriksa kembali jawaban | Koreksi langsung dengan jawaban benar |
| DS01-DS03 | Perlu contoh jelas, penanda Q1/Q2/Q3, latihan mudah ke sulit | Semua fitur di atas |

## 5. Kebutuhan fungsional
- FR1 Masuk dengan nama siswa (minimal 2 huruf); sapaan di beranda.
- FR2 Beranda: ringkasan progres dan tombol mulai.
- FR3 Materi - Pengertian: kartu definisi, rumus, contoh; bisa dibaca ulang.
- FR4 Materi - Praktik 3D: lima langkah, data ganjil dan genap, diagram batang 3D dan diagram kotak-garis animasi.
- FR5 Latihan: tiga tingkat, 5 soal acak per ronde, satu soal per layar.
- FR6 Kuis literasi: 6 tahap membandingkan dua kelompok, skor maksimum 6.
- FR7 Koreksi: benar tampil ucapan selamat; salah tampil "Tidak boleh menyerah, tetap semangat!" dan pembahasan.
- FR8 Musik latar ceria dengan tombol nyala/mati.
- FR9 Progres tersimpan per nama.

## 6. Kebutuhan non-fungsional
- Berjalan di browser Android modern; tata letak responsif.
- Kontras teks maroon/krem; fokus keyboard terlihat; animasi dimatikan jika pengguna memilih kurangi gerakan.
- Tidak mengumpulkan data pribadi selain nama panggilan.
- Satu berkas HTML, tanpa proses build.

## 7. Metrik keberhasilan
- Siswa dapat menyelesaikan satu ronde latihan tanpa bantuan.
- Skor kuis literasi meningkat pada percobaan ulang.
- Umpan balik siswa: tampilan tidak membingungkan dan menyenangkan.

## 8. Di luar lingkup (saat ini)
Login dengan kata sandi, papan peringkat, materi selain statistika penyebaran data, penyimpanan di server (rencana, lihat architecture.md dan api.md).

## 9. Asumsi
Metode kuartil: median separuh bawah dan separuh atas tanpa menyertakan median utama, sesuai pembelajaran di kelas. Catatan rapat menyebut materi "bentuk"; aplikasi mengikuti wawancara dan soal (statistika). Dapat disesuaikan jika dosen meminta lain.
