# AGENTS.md: Proyek Skripsi

Repositori ini dipakai untuk penelitian dan penulisan skripsi S1 di **Fakultas Teknik, Universitas Riau**.

> **Cara memakai template ini:** isi semua bagian bertanda `[ISI: …]`, lalu hapus catatan ini. Bagian "Aturan Kerja Agen" berlaku umum dan sebaiknya tidak diubah kecuali ada keputusan pembimbing.
>
> File ini dibaca oleh semua agen AI (Claude Code lewat `CLAUDE.md`, Gemini CLI lewat `GEMINI.md`, Codex, Cursor, GitHub Copilot, OpenCode, dan lainnya secara langsung). Cukup sunting file ini.

## Identitas Penelitian

| Butir | Isi |
|---|---|
| Nama / NIM | [ISI: nama / NIM] |
| Program studi / jurusan | [ISI: misalnya Teknik Informatika S1 / Teknik Elektro], Fakultas Teknik, Universitas Riau |
| Judul (sementara) | [ISI: judul; tulis tanggal setiap kali judul diganti] |
| Pembimbing Utama | [ISI] |
| Pembimbing Pendamping | [ISI] |
| Tahap saat ini | **Proposal** (Bab I–III) untuk Seminar Proposal |

Gambaran penelitian (perinci saat menyusun Bab I dan III):
- **Data**: [ISI: sumber, periode, jumlah, satuan data]
- **Metode**: [ISI]
- **Luaran**: [ISI]

## Keputusan Penelitian

Catat setiap keputusan beserta tanggal dan siapa yang memutuskan (pengguna atau bimbingan). Keputusan baru yang menggantikan keputusan lama ditulis "menggantikan keputusan [tanggal]".

1. [ISI: misalnya "Data hanya X (keputusan bimbingan, 1 Januari 2027)"]

Hal yang belum diputuskan dan tidak boleh diasumsikan (tanyakan pengguna atau tandai `[PERLU DATA: …]`):
- [ISI]

## Dokumen Rujukan

| Berkas | Isi | Baca ketika |
|---|---|---|
| [docs/pedoman-penulisan-skripsi.md](docs/pedoman-penulisan-skripsi.md) | Pedoman Penulisan Skripsi FT UR 2020 (lengkap, termasuk contoh lampiran) | Mengatur format, menyusun bagian awal/akhir, membuat tabel/gambar/rumus, daftar pustaka |
| [docs/struktur-proposal-acuan.md](docs/struktur-proposal-acuan.md) | Struktur dan format proposal yang sudah lulus di prodi (diukur dari PDF) | Menyusun kerangka Bab I–III, Tabel 2.1, dan bagian awal proposal |
| [referensi/README.md](referensi/README.md) | Indeks semua sumber yang dikutip beserta status salinan lokalnya | Menambah atau memeriksa rujukan |
| Skill `bahasa-skills` (bagian `bahasa-peneliti`) | Kaidah bahasa karya ilmiah, kejujuran sitasi, struktur naskah | **Wajib dipakai setiap kali menulis atau menyunting teks skripsi** |
| Skill `naskah-id` | Penyuntingan EYD V/KBBI, pola tulisan AI, `scripts/periksa.py` dan `scripts/openalex.py` di folder skill (misalnya `.agents/skills/naskah-id/` atau `.claude/skills/naskah-id/`, tergantung agen) | Memeriksa setiap bab sebelum dianggap selesai |
| Server MCP Playwright | Peramban otomatis | Mengunduh rujukan yang gagal lewat `curl` dan OpenAlex |

Pedoman fakultas hanya mengatur **format**, bukan sistematika isi. Sistematika isi mengikuti praktik prodi (lihat struktur acuan) dan arahan pembimbing.

## Kerangka Proposal (Bab I–III)

**Proposal yang sudah lulus di prodi adalah acuan utama untuk struktur dan format** ([docs/struktur-proposal-acuan.md](docs/struktur-proposal-acuan.md)). Urutan prioritas jika ada perbedaan: (1) acuan prodi untuk struktur, judul bagian, urutan bagian awal, susunan file, dan format teknis; (2) pedoman fakultas untuk hal yang tidak terlihat di acuan; (3) yang tidak ditiru hanya kekeliruan objektif yang sudah diverifikasi ke PDF aslinya. Sebelum menyebut sesuatu di acuan "keliru", verifikasi ke PDF dengan PyMuPDF: format miring, tebal, dan ukuran huruf hilang di teks ekstraksi biasa.

Bab IV (Hasil dan Pembahasan) dan Bab V (Kesimpulan dan Saran) tidak ditulis pada tahap proposal. Bab III ditulis dalam bentuk rencana ("akan dilakukan" atau pasif netral), bukan hasil.

1. **BAB I PENDAHULUAN**: 1.1 Latar Belakang, 1.2 Perumusan Masalah, 1.3 Tujuan Penelitian (1:1 dengan rumusan), 1.4 Batasan Masalah, 1.5 Manfaat Penelitian, 1.6 Sistematika Penulisan.
2. **BAB II TINJAUAN PUSTAKA**: 2.1 Penelitian Terdahulu (narasi sintesis + Tabel 2.1), lalu landasan teori.
3. **BAB III METODOLOGI PENELITIAN**: diagram alur penelitian, kerangka proses, pengumpulan data, *preprocessing*, pemodelan, evaluasi, dan luaran.

Draf naskah disimpan di `naskah/` (misalnya `naskah/bab1-pendahuluan.md`). Sitasi dalam teks memakai "et al." untuk tiga penulis atau lebih (APA 7). Setiap draf bab memuat daftar pustaka sementara yang semua entrinya sudah diverifikasi.

### Tabel 2.1 Penelitian Terdahulu

Kolom: No | Judul, Penulis, Tahun | Metode Penelitian | Masalah Penelitian | Hasil Penelitian | Perbedaan dengan Penelitian Ini.

1. **Judul, Penulis, Tahun**: judul tegak (tidak miring), nama lengkap penulis pertama dari PDF artikelnya (bukan ditebak dari inisial), "et al." untuk tiga penulis atau lebih, "&" untuk dua penulis. Contoh: "Judul Artikel, Nama Lengkap et al., 2025".
2. **Metode**: frasa benda (metode/model + data, jumlah, tahun + tujuan atau pembanding), tanpa simbol seperti "+" atau "×". Tahun ditulis "tahun 2019–2024", bukan "(2019–2024)" karena terbaca seperti sitasi.
3. **Masalah**: kalimat lengkap (masalah, lalu akibat atau kebutuhannya).
4. **Hasil**: kalimat lengkap yang **melaporkan** angka utama tanpa menafsirkan.
5. **Perbedaan**: "[Penulis] melakukan X, sedangkan penelitian ini melakukan Y."
6. Setiap studi di tabel juga dibahas di narasi 2.1, dan setiap angka di tabel sama dengan angka di narasi.

## Aturan Kerja Agen

### 1. Kejujuran sitasi (aturan paling keras)

1. **Jangan pernah menulis rujukan dari ingatan.** Sitasi hanya boleh berasal dari sumber yang diberikan pengguna atau yang dibuka dan diverifikasi pada sesi itu (penulis, tahun, judul, jurnal, volume/halaman, DOI dibuka).
2. Klaim yang butuh rujukan tetapi belum ada sumbernya ditandai `[PERLU RUJUKAN: <klaim>; cari di <arah pencarian>]`. Data yang belum tersedia ditandai `[PERLU DATA: …]`. Hanya dua penanda ini yang dipakai (sama dengan skill `naskah-id`).
3. Jangan melengkapi detail sitasi (tahun, halaman, DOI, nama penulis) dengan tebakan; tandai untuk diverifikasi.
4. Data/statistik selalu dengan lembaga dan tahun data, misalnya "(BPS, 2025)".
5. Kutip hanya yang teksnya benar-benar dibaca. Sitasi tidak langsung: "A (2019) dalam B (2023)".
6. Sitasi di teks harus 1:1 dengan daftar pustaka.
7. **Kriteria sumber:** terbit **5 tahun terakhir**; jenis yang diutamakan **artikel jurnal yang jelas** (punya ISSN/DOI; jurnal nasional terakreditasi SINTA atau jurnal internasional terindeks Scopus/WoS) dan **buku**. Prosiding, preprint (arXiv), dokumentasi perangkat lunak, dan presentasi konferensi dipakai seminimal mungkin. Pengecualian yang sah: dokumen primer institusi dan karya asal metode yang tidak punya versi jurnal. Setiap pengecualian ditandai di `referensi/README.md`.
8. **Setiap sumber yang dikutip wajib punya salinan lokal di `referensi/`** dan tercatat di `referensi/README.md` (nama file `PenulisPertama_Tahun_KataKunci.pdf`). Urutan cara unduh: `curl` → salinan *open access* via OpenAlex (`https://api.openalex.org/works/doi:<DOI>`, lihat `locations[].pdf_url`; jangan pakai Unpaywall karena mewajibkan email asli, dan email pengguna tidak boleh dikirim) → Playwright. Jika semua gagal, minta pengguna mengunduh dan catat di bagian "Perlu diunduh manual".
9. **Klaim dicek ke teks penuh, bukan hanya abstrak.** Angka dari abstrak sering kehilangan konteks (satuan, jumlah data, kondisi pengujian). Kalimat yang menyimpulkan lebih jauh daripada yang ditulis penulis aslinya dihapus.

### 2. Bahasa (pedoman FT UR + skill `bahasa-skills` + `naskah-id`)

- Ragam **resmi**, bahasa Indonesia baku, ejaan **EYD Edisi V**.
- **Tanpa kata ganti orang pertama/kedua** (saya, kami, kita, Anda). Pakai kalimat pasif dan subjek "penelitian ini". Pengecualian: di prakata, "saya" diganti "penulis".
- Satu kalimat satu gagasan; kalimat di atas ±25 kata dengan dua anak kalimat atau lebih dipecah.
- Subjek tidak boleh berkata depan: "Dalam penelitian ini menunjukkan…" menjadi "Penelitian ini menunjukkan…".
- Tanpa koma sebelum "sehingga" dan "karena" bila anak kalimat mengikuti induk kalimat (EYD V).
- Satu konsep satu istilah sepanjang naskah, termasuk antarbab. Istilah asing dicetak miring; padanan Indonesia diberikan pada kemunculan pertama. Singkatan dijelaskan pada kemunculan pertama di bab itu.
- Bentuk baku: *analisis/menganalisis*, bukan *analisa*. Buang pleonasme (*adalah merupakan*, *agar supaya*, *disebabkan karena*).
- **Dilarang** membuka latar belakang dengan "Di era globalisasi…", "Seiring perkembangan zaman…", "Dewasa ini…".
- Hindari pola tulisan mesin: "tersebut", "hal ini", "selain itu", "oleh karena itu", dan "juga" yang berulang di hampir setiap kalimat. Sebut rujukannya langsung (nama penulis, nama model) atau pakai "itu/ini/-nya".
- Kalimat penyambung antarparagraf boleh ditambahkan, tetapi tidak boleh mengulang isi kalimat sesudahnya atau memutus alur paragraf.
- Dilarang memakai "sangat signifikan" tanpa uji statistik, "banyak penelitian menunjukkan" tanpa rujukan, dan hedging bertumpuk.
- Tinjauan pustaka berupa **sintesis per temuan/aliran**, bukan daftar "Menurut A… Menurut B…".
- Hasil melaporkan tanpa menafsir; pembahasan menafsirkan dan mendialogkan temuan dengan riset terdahulu, lalu keterbatasan.

### 3. Aturan format kunci (rincian di `docs/pedoman-penulisan-skripsi.md`)

| Aspek | Ketentuan |
|---|---|
| Kertas | A4 HVS 70 gsm, cetak satu sisi |
| Huruf | Times New Roman 12 pt di seluruh naskah |
| Margin | Atas 4, kiri 4, bawah 3, kanan 3 cm (halaman pengesahan: kiri 4, lainnya 3 cm) |
| Spasi isi | 1,5; *space before/after* 0 |
| Spasi 1 | Abstrak, daftar isi/tabel/gambar/lampiran, daftar pustaka, isi tabel, judul tabel/gambar lebih dari satu baris |
| Rincian | Wajib **penomoran**, bukan *bullet* |
| Judul bab | KAPITAL, tebal, tengah, tanpa titik |
| Subjudul | Tebal, rata kiri, Huruf Awal Kapital (kecuali kata depan/penghubung) |
| Nomor halaman | Tengah bawah; bagian awal Romawi kecil (i, ii) |
| Tabel | Judul **di atas**, tengah; sumber kiri bawah TNR 10; isi TNR 10–11; nomor per bab (Tabel 2.1) |
| Gambar | Judul **di bawah**, tengah; sumber di bawah judul TNR 10; nomor per bab (Gambar 2.1) |
| Rumus | Tengah, nomor angka Latin dalam kurung per bab, misalnya (3.1) |
| Angka | Desimal **koma** (9,8), ribuan titik (6.000), konsisten termasuk tabel hasil; awal kalimat tidak boleh angka, lambang, rumus, atau singkatan |
| Abstrak | Maksimal 250 kata, satu paragraf, spasi 1; memuat masalah, tujuan, metode, hasil, kesimpulan; kata kunci maksimal 5 |
| Daftar pustaka | APA 7, alfabetis tanpa nomor, spasi 1; judul miring |
| Kutipan langsung | Tanda petik + (Pengarang, tahun, hal. x) |

### 4. Naskah Word dan `.md`

Pengguna mungkin menulis di Word, sedangkan agen menyunting `naskah/*.md`. Agar keduanya tidak berselisih:

1. Bila pengguna menempelkan teks dari Word, bandingkan dulu dengan `.md` per kata dan laporkan perbedaannya sebelum menyamakan.
2. Setiap suntingan agen dilaporkan sebagai daftar **sebelum → sesudah** agar pengguna bisa memindahkannya ke Word.
3. Commit `naskah/` setelah setiap putaran suntingan yang disetujui, dengan pesan yang menjelaskan apa yang berubah.

### 5. Pemeriksaan sebelum menyerahkan teks

1. Semua sitasi bersumber nyata dan punya salinan di `referensi/`; sisanya bertanda `[PERLU RUJUKAN]`.
2. Jalankan `periksa.py` dari skill naskah-id pada bab yang disunting, dan `--banding` terhadap versi sebelum suntingan. Setiap angka atau sitasi yang hilang/bertambah harus bisa dijelaskan.
3. Tidak ada kata ganti orang pertama/kedua (kecuali "penulis" di prakata).
4. Desimal memakai koma; satuan SI tanpa titik.
5. Satu istilah per konsep; istilah asing miring.
6. Rincian memakai penomoran, bukan *bullet*.
7. Latar belakang bebas pembuka klise; kalimat pertama memuat data atau masalah spesifik.

## Pertanyaan Terbuka

1. [ISI]
