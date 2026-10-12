# Panduan deployment dan langkah manual yang tersisa

## 1. Prasyarat
- Node.js 20 atau lebih baru
- Akses ke proyek Supabase `yhcswjsoshlxmeegzxyl`
- Akses pemilik ke proyek Vercel `ujian-sekolah-smk-mandiri`
- API key AI dari penyedia yang disetujui sekolah (hanya jika fitur AI akan diaktifkan)

## 2. Jalankan lokal
```bash
npm install
npm run dev
```

## 3. Deploy ke Vercel
1. Ekstrak folder ini.
2. Masuk ke akun Vercel pemilik proyek `ujian-sekolah-smk-mandiri`.
3. Impor repositori Git atau unggah folder melalui alur deployment yang tersedia.
4. Pilih framework Vite, build command `npm run build`, output `dist`, Node 20+.
5. Tambahkan `OPENAI_API_KEY` sebagai encrypted server-side environment variable (jangan gunakan prefix `VITE_`).
6. Deploy preview dahulu, tes login dan seluruh alur, baru promosikan ke production.

## 4. Blogger
Tambahkan tautan ke URL Vercel yang sudah terverifikasi di halaman portal sekolah. Jangan menaruh service-role key, password, atau kunci jawaban pada template Blogger.

## 5. Verifikasi sebelum ujian nyata
- Uji login dengan akun Supabase Auth yang punya profil aktif.
- Uji peran admin, guru, proktor, dan siswa secara terpisah.
- Uji soal draft/approved, token, batas waktu, autosave, submit ganda, koneksi putus, dan kunci jawaban.
- Uji backup/restore dan ekspor laporan.
- Pastikan domain dan redirect URL Auth di Supabase cocok dengan URL deployment final.

## Hambatan akses yang ditemukan saat sesi implementasi
Akun konektor Vercel saat ini dapat menemukan proyek, tetapi operasi deployment/logs ditolak dengan HTTP 403: scope `offecialsmkswastamandiri-2522` tidak diotorisasi pada sesi konektor. Pemilik perlu mengotorisasi ulang koneksi Vercel untuk scope tersebut atau memberikan akses tim yang tepat sebelum deployment otomatis dapat dilakukan. Proyek belum dinyatakan online.
