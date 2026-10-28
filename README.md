# Template Skripsi FT UR dengan Claude Code

Template untuk menyusun proposal dan skripsi S1 Fakultas Teknik Universitas Riau dengan Claude Code. Template ini berisi aturan kerja, pedoman format fakultas, struktur proposal acuan prodi, dan alat bantu bahasa. Isi skripsi tidak disertakan.

## Isi

| Berkas | Fungsi |
|---|---|
| `CLAUDE.md` | Aturan kerja Claude: kejujuran sitasi, bahasa, format, alur Word dan `.md`. **Isi bagian `[ISI: …]` dulu.** |
| `.claude/settings.json` | Memasang plugin bahasa-skills, naskah-id, dan Playwright secara otomatis |
| `docs/pedoman-penulisan-skripsi.md` | Pedoman Penulisan Skripsi FT UR 2020 |
| `docs/struktur-proposal-acuan.md` | Struktur dan format proposal yang sudah lulus di prodi, termasuk format Tabel 2.1 |
| `naskah/` | Tempat draf bab dalam Markdown |
| `referensi/` | Salinan PDF setiap sumber yang dikutip, beserta indeksnya |

## Persiapan

1. Pasang [Claude Code](https://claude.com/claude-code), Git, dan Python 3.
2. Pasang PyMuPDF untuk membaca PDF:
   ```bash
   pip install pymupdf
   ```
3. Salin template ini ke folder baru, lalu jadikan repo Git sendiri:
   ```bash
   git init
   git add .
   git commit -m "Mulai dari template skripsi FT UR"
   ```
4. Buka folder itu dengan Claude Code. Claude Code akan menawarkan pemasangan tiga plugin dari `.claude/settings.json`; setujui semuanya:

   | Plugin | Isi | Dipakai untuk |
   |---|---|---|
   | `bahasa-skills` ([alvinindra/bahasa-skills](https://github.com/alvinindra/bahasa-skills)) | Skill `bahasa-peneliti` dan `bahasa-inti` | Menulis dan menyunting teks skripsi |
   | `naskah-id` ([nothinx/naskah-id](https://github.com/nothinx/naskah-id)) | Skill penyuntingan EYD V/KBBI, skrip `periksa.py` dan `openalex.py` | Memeriksa setiap bab, mengecek rujukan |
   | `playwright` (resmi Anthropic) | Peramban otomatis | Mengunduh PDF rujukan yang gagal lewat `curl` |

   Bila tawaran tidak muncul, jalankan `/plugin` di Claude Code dan pasang ketiganya secara manual.
5. Isi semua bagian `[ISI: …]` di `CLAUDE.md`, terutama identitas, judul, dan keputusan penelitian.
6. Simpan repo di GitHub sebagai repo **privat** supaya punya cadangan.

## Alur Kerja

### Menyusun bab

1. Minta Claude menyusun kerangka bab dari `docs/struktur-proposal-acuan.md`, lalu isi per subbab.
2. Setiap rujukan diunduh ke `referensi/` dan dicatat di `referensi/README.md`. Klaim dicek ke **teks penuh**, bukan abstrak saja.
3. Klaim yang belum punya sumber ditandai `[PERLU RUJUKAN: …]`; jangan dibiarkan tanpa tanda.

### Memeriksa bab

1. Minta Claude memeriksa bab dengan skill `naskah-id`, misalnya: "cek bab 2 pakai naskah-id".
2. Claude menjalankan `periksa.py` untuk ejaan dan gaya, lalu `--banding` untuk memastikan tidak ada angka atau sitasi yang berubah tanpa disengaja.
3. Tidak semua temuan `periksa.py` benar. Salah tandai yang sering muncul: "makro/mikro" pada "F1 makro", nama model (BERTopic, DeBERTa), simbol rumus, dan singkatan di daftar pustaka.

### Menyamakan Word dan `.md`

Bila Anda menulis di Word:

1. Tempelkan teks Word ke Claude dan minta disamakan dengan `.md`. Claude membandingkan per kata dan melaporkan perbedaannya.
2. Setiap suntingan Claude dilaporkan sebagai daftar **sebelum → sesudah**; pindahkan ke Word satu per satu.
3. Commit setelah setiap putaran suntingan yang disetujui.

## Pelajaran dari Pemakaian

1. **Format acuan diukur dari PDF, bukan ditebak.** Teks hasil ekstraksi biasa kehilangan format miring dan tebal; Claude memakai PyMuPDF untuk membacanya.
2. **Nama penulis di tabel diambil dari PDF artikel.** Daftar pustaka hanya memuat inisial, dan nama satu kata (misalnya "Saikin") mudah salah ditulis sebagai "Saikin, S.".
3. **Penelitian terdahulu bisa mengubah klaim celah.** Setiap kali studi baru ditambahkan, periksa ulang paragraf celah penelitian.
4. **Kalimat penyambung dari AI cenderung berlebihan.** Periksa "tersebut", "juga", dan "selain itu" yang berulang.
5. **Isi skripsi dan transkrip wawancara jangan dibagikan.** Bagikan template ini saja.
