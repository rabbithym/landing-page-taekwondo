# Garuda Taekwondo Academy — Landing Page

Landing page resmi dan bersih untuk akademi taekwondo, untuk atlet dan orang tua atlet.

**Gaya:** formal, navy-putih-merah, bahasa Indonesia resmi. Dibangun dengan skill Diagram Design + Impeccable (critique, audit, polish).

## Isi

- Hero "Disiplin. Prestasi. Karakter." dan 5 prinsip taekwondo
- 3 program: Anak, Remaja — Teknik & Poomsae, Atlet Prestasi Kyorugi
- Seksi khusus orang tua: laporan 3 bulanan, keamanan, izin bertanding
- Penjelajah jenjang sabuk interaktif (putih sampai hitam)
- Jadwal latihan yang bisa disaring per kelas, biaya transparan, FAQ
- Formulir trial gratis yang menyusun ringkasan pendaftaran untuk disalin / diunduh

## Jalankan

Buka `index.html` langsung, atau jalankan server statis:

```bash
python3 -m http.server 8000
# buka http://localhost:8000
```

Tidak ada build step, tidak ada server, tidak ada database.

## Struktur

```
index.html
assets/
  hero.jpg
  kids.jpg
  poomsae.jpg
  sparring.jpg
  competition.jpg
DESIGN.md
```

`DESIGN.md` mencatat sistem desain hasil polish: warna, tipografi, bentuk, dan komponen.

## Catatan foto

Foto di kartu "Remaja — Teknik & Poomsae" diperbaiki 2026-11-25: foto lama sebenarnya foto pertandingan kyorugi. Foto baru adalah tiga atlet yang menampilkan jurus poomsae di turnamen taekwondo, Kunsan Air Base, Korea, 30 Januari 2005 — foto U.S. Air Force oleh Senior Airman Giang Nguyen, domain publik (Wikimedia Commons, File:Poomsae.jpg), tanpa kewajiban atribusi. Foto pers World Taekwondo dari final Chuncheon 2026 TIDAK dipakai, karena lisensi pakai-ulangnya belum terkonfirmasi.
