# Rekita

Rekita adalah aplikasi Progressive Web App (PWA) untuk membantu individu atau keluarga mencatat dan memantau keuangan sehari-hari. Aplikasi ini mendukung pencatatan pemasukan dan pengeluaran, statistik bulanan, pengelolaan kategori, serta penggunaan secara offline dengan sinkronisasi ke Supabase.

## Fitur

- Registrasi, login, logout, dan reset password melalui Supabase Auth
- Dashboard dengan saldo, ringkasan bulan berjalan, dan grafik pemasukan serta pengeluaran
- CRUD transaksi pemasukan dan pengeluaran
- Pencarian dan filter transaksi berdasarkan kategori serta rentang waktu
- Pengelolaan kategori pengeluaran
- Statistik keuangan dan perbandingan antarbulan
- Penyimpanan transaksi saat offline melalui IndexedDB
- Sinkronisasi otomatis saat koneksi kembali tersedia
- PWA responsif untuk mobile dan desktop
- Format nominal dalam Rupiah

## Teknologi

- Next.js 15 dan React 19
- TypeScript
- Tailwind CSS
- Supabase Authentication dan PostgreSQL
- Zustand untuk state management
- Recharts untuk visualisasi data
- IndexedDB melalui `idb` untuk dukungan offline
- Vercel untuk deployment frontend

## Prasyarat

- Node.js 18.18 atau versi lebih baru
- npm
- Project Supabase untuk autentikasi dan database

## Instalasi

1. Clone repository dan masuk ke folder proyek.

2. Install dependency:

   ```bash
   npm install
   ```

3. Buat file `.env.local` di root proyek:

   ```env
   NEXT_PUBLIC_SUPABASE_URL=https://your-project.supabase.co
   NEXT_PUBLIC_SUPABASE_ANON_KEY=your-anon-key
   ```

4. Jalankan isi [database-schema.sql](database-schema.sql) di Supabase SQL Editor. Schema tersebut membuat tabel profil pengguna, kategori, transaksi, trigger, dan Row Level Security (RLS).

5. Jalankan server development:

   ```bash
   npm run dev
   ```

6. Buka [http://localhost:3000](http://localhost:3000).

## Struktur Proyek

```text
src/
├── app/            Halaman Next.js App Router
├── components/     Komponen UI yang dapat digunakan ulang
├── hooks/          Custom React hooks
├── lib/            Konfigurasi client dan integrasi library
├── stores/         State management Zustand
├── types/          Definisi tipe TypeScript
└── utils/          Helper, penyimpanan offline, dan sinkronisasi
```

Halaman utama yang tersedia:

- `/auth/login` - Login
- `/auth/register` - Registrasi
- `/auth/reset-password` - Reset password
- `/dashboard` - Ringkasan keuangan
- `/transactions` - Daftar dan filter transaksi
- `/transactions/add` - Tambah transaksi
- `/statistics` - Statistik keuangan
- `/categories` - Kelola kategori
- `/profile` - Profil pengguna