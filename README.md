# Template Skripsi FT UR untuk Agen AI

Template untuk menyusun proposal dan skripsi S1 Fakultas Teknik Universitas Riau dengan agen AI pemrograman: Claude Code, Codex, Gemini CLI, Cursor, GitHub Copilot, OpenCode, dan agen lain yang membaca `AGENTS.md`. Template ini berisi aturan kerja, pedoman format fakultas, struktur proposal acuan prodi, dan alat bantu bahasa. Isi skripsi tidak disertakan.

## Isi

| Berkas | Fungsi |
|---|---|
| `AGENTS.md` | **Satu-satunya file aturan kerja**: kejujuran sitasi, bahasa, format, alur Word dan `.md`. Isi bagian `[ISI: …]` dulu. |
| `CLAUDE.md`, `GEMINI.md`, `.github/copilot-instructions.md` | Penghubung ke `AGENTS.md` untuk agen yang tidak membacanya langsung. Jangan diisi aturan sendiri. |
| `skills-lock.json` | Daftar skill yang dipakai (naskah-id dan bahasa-skills) |
| `.mcp.json`, `.cursor/mcp.json`, `.vscode/mcp.json`, `.gemini/settings.json` | Server MCP Playwright untuk Claude Code, Cursor, Copilot di VS Code, dan Gemini CLI |
| `docs/pedoman-penulisan-skripsi.md` | Pedoman Penulisan Skripsi FT UR 2020 |
| `docs/struktur-proposal-acuan.md` | Struktur dan format proposal yang sudah lulus di prodi, termasuk format Tabel 2.1 |
| `naskah/` | Tempat draf bab dalam Markdown |
| `referensi/` | Salinan PDF setiap sumber yang dikutip, beserta indeksnya |

## Persiapan

1. Pasang agen pilihan Anda, Git, Python 3, dan Node.js 18 atau lebih baru.
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
4. Pasang kedua skill dari folder proyek. Perintah ini menanyakan agen mana yang dipasangi; pilih agen yang Anda pakai (boleh lebih dari satu):
   ```bash
   npx skills add nothinx/naskah-id
   npx skills add alvinindra/bahasa-skills
   ```

   | Skill | Isi | Dipakai untuk |
   |---|---|---|
   | `naskah-id` ([nothinx/naskah-id](https://github.com/nothinx/naskah-id)) | Penyuntingan EYD V/KBBI, skrip `periksa.py` dan `openalex.py` | Memeriksa setiap bab, mengecek rujukan |
   | `bahasa-skills` ([alvinindra/bahasa-skills](https://github.com/alvinindra/bahasa-skills)) | Pemandu yang mengarahkan ke `bahasa-inti` dan `bahasa-peneliti` | Menulis dan menyunting teks skripsi |

   Skill terpasang di `.agents/skills/` (Codex, Cursor, Gemini CLI, Copilot, OpenCode) atau `.claude/skills/` (Claude Code). Kedua folder itu tidak ikut di-commit.
5. Aktifkan server MCP Playwright, yang dipakai untuk mengunduh PDF rujukan bila `curl` gagal:

   | Agen | Konfigurasi |
   |---|---|
   | Claude Code | `.mcp.json` sudah tersedia; setujui saat Claude Code menanyakannya |
   | Cursor | `.cursor/mcp.json` sudah tersedia |
   | GitHub Copilot (VS Code) | `.vscode/mcp.json` sudah tersedia |
   | Gemini CLI | `.gemini/settings.json` sudah tersedia |
   | Codex | Jalankan `codex mcp add playwright -- npx @playwright/mcp@latest` |
   | Agen lain | Daftarkan server dengan perintah `npx @playwright/mcp@latest` sesuai dokumentasi agen |

6. Isi semua bagian `[ISI: …]` di `AGENTS.md`, terutama identitas, judul, dan keputusan penelitian.
7. Simpan repo di GitHub sebagai repo **privat** supaya punya cadangan.

## Alur Kerja

### Menyusun bab

1. Minta agen menyusun kerangka bab dari `docs/struktur-proposal-acuan.md`, lalu isi per subbab.
2. Setiap rujukan diunduh ke `referensi/` dan dicatat di `referensi/README.md`. Klaim dicek ke **teks penuh**, bukan abstrak saja.
3. Klaim yang belum punya sumber ditandai `[PERLU RUJUKAN: …]`; jangan dibiarkan tanpa tanda.

### Memeriksa bab

1. Minta agen memeriksa bab dengan skill `naskah-id`, misalnya: "cek bab 2 pakai naskah-id".
2. Agen menjalankan `periksa.py` untuk ejaan dan gaya, lalu `--banding` untuk memastikan tidak ada angka atau sitasi yang berubah tanpa disengaja.
3. Tidak semua temuan `periksa.py` benar. Salah tandai yang sering muncul: "makro/mikro" pada "F1 makro", nama model (BERTopic, DeBERTa), simbol rumus, dan singkatan di daftar pustaka.

### Menyamakan Word dan `.md`

Bila Anda menulis di Word:

1. Tempelkan teks Word ke agen dan minta disamakan dengan `.md`. Agen membandingkan per kata dan melaporkan perbedaannya.
2. Setiap suntingan agen dilaporkan sebagai daftar **sebelum → sesudah**; pindahkan ke Word satu per satu.
3. Commit setelah setiap putaran suntingan yang disetujui.

## Pelajaran dari Pemakaian

1. **Format acuan diukur dari PDF, bukan ditebak.** Teks hasil ekstraksi biasa kehilangan format miring dan tebal; agen memakai PyMuPDF untuk membacanya.
2. **Nama penulis di tabel diambil dari PDF artikel.** Daftar pustaka hanya memuat inisial, dan nama satu kata (misalnya "Saikin") mudah salah ditulis sebagai "Saikin, S.".
3. **Penelitian terdahulu bisa mengubah klaim celah.** Setiap kali studi baru ditambahkan, periksa ulang paragraf celah penelitian.
4. **Kalimat penyambung dari AI cenderung berlebihan.** Periksa "tersebut", "juga", dan "selain itu" yang berulang.
5. **Isi skripsi dan transkrip wawancara jangan dibagikan.** Bagikan template ini saja.
