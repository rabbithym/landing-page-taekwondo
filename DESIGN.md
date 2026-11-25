# Garuda Taekwondo Academy — Sistem Desain

Konteks (PRODUCT): landing page untuk atlet dan orang tua atlet. Tujuan utama
pengunjung: mendaftar trial gratis. Gaya: resmi, bersih, seperti dokumen
akademi — bukan template promosi generik.

## Warna
- Navy `#0d1b33` — warna utama (nav, footer, panel ringkasan, sabuk terpilih)
- Merah `#c8102e` — satu-satunya aksen aksi (CTA, penanda seksi, garis atas kartu unggulan)
- Merah teks `--red-text` — `#c8102e` di light, `#ff8fa3` di dark (kontras teks merah di dark: 8,66:1 di `#0b1220`, lolos AA; jangan pakai `--red` untuk teks kecil di dark, rasionya cuma 3,18:1)
- Tinta `#0e1729`, teks sekunder `#2c3a52`, teks muted `#475467` (kontras AA di putih)
- Latar bergantian putih / `#f2f4f8`; mode gelap mengikuti `prefers-color-scheme`

## Tipografi
- Archivo 800 untuk judul (uppercase, letter-spacing -0.015em, line-height 1.08)
- Public Sans untuk isi (line-height 1.6–1.68)
- Source Serif 4 hanya untuk nama lima prinsip taekwondo

## Bentuk & ritme
- Sudut tajam: tombol 3px, kartu 4px, chip/tag 2px — tanpa pill
- Kepala seksi selalu diawali garis atas 2px tinta + label berkotak merah 9px
- Garis atas 3–4px merah/navy dipakai sebagai penanda unggulan, bukan garis samping
- Jarak seksi 84px desktop, 60px mobile; jangkar `scroll-margin-top: 96px`

## Komponen
- Filter jadwal: tombol persegi, status aktif navy + `aria-pressed`
- Penjelajah sabuk: tingkat terpilih = blok navy penuh teks putih, panel detail
  diawali pita warna sabuk yang dipilih
- FAQ: akordeon hairline tanpa kotak, ikon + merah berputar 45° saat terbuka
- Formulir: fokus biru `#175cd3` dengan cincin 3px; ringkasan navy bergaris merah

## Aturan
- Tidak ada gradient, tidak ada bayangan berwarna, tidak ada kicker tanpa garis seksi
- Gerakan hanya transisi ≤0.2s dan dimatikan pada `prefers-reduced-motion`
- Semua fungsi (sabuk, filter jadwal, pilih paket, ringkasan salin/unduh) wajib tetap jalan

## Pengecualian yang disengaja (audit Impeccable 2026-11-25)
Temuan detector di bawah ini BUKAN cacat — sengaja dipertahankan karena bagian
dari identitas akademi. Jangan "diperbaiki" oleh audit/perintah polish berikutnya
tanpa persetujuan pengguna.
- **Kicker di atas heading (7 seksi).** Setiap kepala seksi memakai label
  berkotak merah 9px di atas h2. Detector melarang kicker secara mutlak, tapi
  di sini label itu penanda seksi resmi, selalu dipasangkan dengan garis atas
  2px tinta. Hero eyebrow mengikuti pola yang sama (garis merah 36px, bukan pill).
- **Garis atas di kartu rounded (4 kartu).** `.card` dan `.price-card.featured`
  memakai border-top 3–4px merah/navy dengan radius 4px. Garis itu penanda
  unggulan; radius kecil (4px) membuat benturannya minimal.
- **Cramped-padding (8 temuan, false positive terverifikasi).** Detector membaca
  seksi sebagai nempel ke tepi, padahal `.wrap` = `min(1180px, calc(100% - 40px))`
  memberi inset 20px kiri-kanan di semua lebar, `.section` hanya punya padding
  vertikal (84px 0), dan `.hero-copy` punya padding 64px 48px. Diverifikasi lewat
  CSS 2026-11-25; screenshot render tidak bisa dijalankan di VM (Chrome tidak
  bisa start: Hatch WebGL domain policy). Jangan ubah padding apa pun.
- **Em-dash sebagai pemisah terstruktur.** Em-dash di judul ("Anak — Fondasi &
  Karakter"), definisi lima prinsip ("Kesopanan — hormat…"), dan jam ("Selasa —
  16.30") adalah pemisah, bukan jeda kalimat. Yang dikurangi hanya em-dash jeda
  di paragraf prosa.
