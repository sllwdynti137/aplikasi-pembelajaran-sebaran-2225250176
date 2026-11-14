# API dan Data

## A. Saat ini (tanpa server)
Penyimpanan di `localStorage`, kunci `sebaran:<nama huruf kecil>`:
```json
{ "ok": 12, "tot": 20, "lit": 5 }
```
- `ok`: jumlah soal latihan benar, `tot`: jumlah soal latihan dijawab, `lit`: skor literasi terbaik (0 sampai 6).
- Kunci `sebaran:last` menyimpan nama terakhir.

### Fungsi inti (JavaScript)
| Fungsi | Masukan | Keluaran |
|---|---|---|
| `st(d)` | larik angka | `{s, n, min, max, R, q1, q2, q3, lo, up}` |
| `gen(lv)` | tingkat 0, 1, 2 | satu soal pilihan ganda |
| `quiz(o)` | `{title, qs, again, onAns, onEnd}` | memulai kuis satu soal per layar |
| `sv()` / `ld()` | - | simpan / muat progres |

## B. Rencana Supabase
### Tabel
```sql
create table students (
  id uuid primary key default gen_random_uuid(),
  name text not null unique,
  created_at timestamptz default now()
);
create table scores (
  id uuid primary key default gen_random_uuid(),
  student_id uuid references students(id),
  kind text check (kind in ('latihan','literasi')),
  score int not null,
  total int not null,
  created_at timestamptz default now()
);
alter table students enable row level security;
alter table scores enable row level security;
```
### Contoh pemanggilan (supabase-js)
```js
const { createClient } = supabase;
const db = createClient(SUPABASE_URL, SUPABASE_ANON_KEY);

// masuk atau daftar dengan nama
let { data } = await db.from('students').select('id').eq('name', nama).maybeSingle();
if (!data) ({ data } = await db.from('students').insert({ name: nama }).select('id').single());

// simpan skor
await db.from('scores').insert({ student_id: data.id, kind: 'literasi', score: 5, total: 6 });

// ambil skor terbaik
const { data: best } = await db.from('scores').select('score').eq('student_id', data.id)
  .eq('kind', 'literasi').order('score', { ascending: false }).limit(1);
```
### Catatan
Kunci anon boleh ada di klien; kunci service tidak boleh. Buat kebijakan RLS yang membatasi akses sesuai kebutuhan (misalnya insert dan select untuk anon).
