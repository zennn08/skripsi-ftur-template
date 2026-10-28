# Struktur Proposal Acuan (Teknik Informatika S1, FT UR)

> Disarikan dari proposal skripsi Teknik Informatika UR yang sudah lulus (2026), diukur dari PDF-nya dengan PyMuPDF. Dokumen ini hanya memuat **struktur dan format**, bukan isi.
> **Acuan utama untuk struktur, judul bagian, dan format.** Bila berbeda dengan pedoman fakultas, ikuti acuan ini, kecuali butir di bagian 8. Bila Anda punya PDF proposal kating sendiri, verifikasi ulang dan perbarui dokumen ini.
> [ISI: lokasi PDF acuan di komputer Anda, bila ada]

## 1. Susunan File (Konvensi Penamaan)

Satu PDF per bagian, diberi nomor urut:

```
1_Cover_NIM_<Nama>.pdf            (sampul, halaman judul, pengesahan, orisinalitas, persetujuan publikasi, prakata)
2_Daftar Isi_<NIM>_<Nama>.pdf     (daftar isi, daftar gambar, daftar tabel)
3_Abstrak_<NIM>_<Nama>.pdf        (abstrak + abstract)
4_BAB 1_<NIM>_<Nama>.pdf
5_BAB 2_<NIM>_<Nama>.pdf
6_BAB 3_<NIM>_<Nama>.pdf
7_BAB 4 ... 8_BAB 5 ...           (khusus skripsi penuh; tidak masuk proposal)
9_Daftar Pustaka_<NIM>_<Nama>.pdf
10_Lampiran_<NIM>_<Nama>.pdf
```

## 2. Bagian Awal (Praktik Prodi)

Urutan di daftar isi: Halaman Judul (i) → Pengesahan (ii) → Pernyataan Orisinalitas (iii) → Prakata (iv) → Persetujuan Publikasi (vi) → Abstrak (vii) → *Abstract* (viii) → Daftar Isi (ix) → Daftar Gambar → Daftar Tabel.

> Urutan ini berbeda dari pedoman fakultas; acuan prodi yang dipakai.

| Bagian | Isi kunci |
|---|---|
| Sampul | SKRIPSI / judul (kapital, piramida terbalik) / Oleh: / Nama / NIM: ... / PROGRAM STUDI TEKNIK INFORMATIKA S1 / JURUSAN TEKNIK ELEKTRO / FAKULTAS TEKNIK / UNIVERSITAS RIAU / PEKANBARU / tahun |
| Halaman judul | Sama dengan sampul + "Diajukan untuk Memenuhi Persyaratan Meraih Gelar Sarjana Teknik Teknik Informatika Fakultas Teknik Universitas Riau" |
| Pengesahan | Pembimbing (nama + NIP) dan Koordinator Prodi Teknik Informatika S1 (nama + NIP). Untuk dua pembimbing: "Pembimbing Utama" dan "Pembimbing Pendamping" (Lampiran E pedoman) |
| Persetujuan publikasi | Judul "HALAMAN PERNYATAAN PERSETUJUAN PUBLIKASI TUGAS AKHIR UNTUK KEPENTINGAN AKADEMIS"; isian Nama, NIM, Program Studi, Jurusan, Fakultas, Jenis Karya; Hak Bebas Royalti Non-Eksklusif |
| Prakata (proposal) | Disebut "Proposal Skripsi ... dalam rangka memenuhi salah satu syarat kelulusan mata kuliah Seminar Proposal"; daftar terima kasih bernomor |
| Abstrak | Judul → Nama → "Program Studi Teknik Informatika, Fakultas Teknik, Universitas Riau" → ABSTRAK → satu paragraf → "Kata Kunci:"; versi Inggris: "Informatics Engineering Department, Faculty of Engineering, University of Riau" → ABSTRACT → "Keywords:" |

## 3. Kerangka BAB I Pendahuluan

1.1 Latar Belakang
1.2 Perumusan Masalah (bernomor, kalimat tanya "Bagaimana ...?")
1.3 Tujuan Penelitian (bernomor, sejajar 1:1 dengan rumusan masalah)
1.4 Batasan Masalah
1.5 Manfaat Penelitian
1.6 Sistematika Penulisan (BAB I–V, masing-masing satu paragraf pendek)

Alur latar belakang yang lazim: objek dan konteks berdata → masalah di lapangan → metode yang sudah ada → kelebihan dan kekurangannya (dengan rujukan) → metode yang dipilih dan masalahnya → solusi → tujuan, ditutup dengan judul penelitian. Penutup yang berorang pertama ("Oleh karena itu, penulis membuat judul …") diganti bentuk impersonal, misalnya "Rancangan penelitian tersebut dirumuskan dalam judul “…”."

## 4. Kerangka BAB II Tinjauan Pustaka

2.1 Penelitian Terdahulu: narasi sintesis per kelompok temuan, ditutup **Tabel 2.1 Tabel Penelitian Terdahulu** dengan kolom:

| No | Judul, Penulis, Tahun | Metode Penelitian | Masalah Penelitian | Hasil Penelitian | Perbedaan (dengan penelitian ini) |
|---|---|---|---|---|---|

Format sel yang terukur dari PDF acuan:

1. **Judul, Penulis, Tahun**: judul tegak (tidak miring), TNR 10, lalu nama lengkap penulis pertama dan tahun, dipisah koma, misalnya "Judul Artikel, Nama Lengkap, dkk., 2025". Dua penulis ditulis keduanya dengan "&". Template ini memakai "et al." agar konsisten dengan sitasi di teks; ganti ke "dkk." bila pembimbing meminta.
2. **Metode Penelitian**: frasa benda yang menyebut model/metode, data, dan tujuan, misalnya "Model X yang dioptimalkan dengan Y untuk mendeteksi Z pada N data."
3. **Masalah, Hasil, Perbedaan**: kalimat lengkap. Hasil memuat angka; Perbedaan membandingkan penelitian terdahulu dengan penelitian sendiri.

2.2 dst.: landasan teori, dari domain kasus → konsep umum → metode inti → *tools* → metrik evaluasi → kerangka proses.

## 5. Kerangka BAB III Metodologi Penelitian

3.1 Metodologi Penelitian: diagram alur penelitian (Gambar 3.1) + narasi tiap tahap + jenis pendekatan
3.2 Penerapan kerangka kerja (misalnya CRISP-DM, gambar dengan sumber)
3.3 dst.: tahap-tahap kerangka kerja (pemahaman masalah, pengumpulan data, *preprocessing*, pemodelan, evaluasi, *deployment*), masing-masing dengan anak subbab yang nomornya mengikuti induk (3.4.1 di bawah 3.4)

## 6. Daftar Pustaka

APA 7 (tanpa kota penerbit, DOI berupa URL `https://doi.org/...`), alfabetis, rata kiri dengan indentasi gantung.

## 7. Format Teknis (Diukur dari PDF Acuan dengan PyMuPDF)

| Aspek | Nilai terukur | Sesuai pedoman? |
|---|---|---|
| Kertas | A4 (21 × 29,7 cm) | Ya |
| Margin teks | Kiri 4,0; atas 4,0; kanan ±2,9–3,0; bawah ±3,0 cm | Ya (4-4-3-3) |
| Huruf isi | Times New Roman 12 pt | Ya |
| Spasi isi | 1,5 (jarak baris ±20,7 pt); antar-subjudul 2 × 1,5 | Ya |
| Judul bab | "BAB I" dan "PENDAHULUAN" dua baris, tebal, tengah | Ya |
| Subjudul | Nomor di 4,0 cm, teks judul di 5,25 cm (tab), tebal, rata kiri | Ya |
| Anak subjudul | Misalnya "3.3.1 Observasi", tebal, rata kiri di 4,0 cm | Ya |
| Istilah asing | Dicetak miring | Ya |
| Sampul | Judul TNR 16 tebal; nama/prodi TNR 14 tebal | Ya |
| Isi tabel | TNR 10 pt | Ya (maks. 11 pt) |
| Rumus | Cambria Math (Equation Editor Word) | Pedoman tidak mengatur |
| Nomor halaman | Bagian awal: romawi kecil, tengah bawah. File BAB pada acuan tidak memuat nomor halaman | Konfirmasi ke pembimbing saat penyusunan akhir |

## 8. Kesalahan yang Sering Muncul (Jangan Ditiru)

1. Nomor anak subbab tidak mengikuti induknya (misalnya 3.3.4 diletakkan di bawah 3.4). Pakai 3.4.1, 3.5.1, dst.
2. Nomor gambar/tabel di teks tidak sinkron dengan keterangan dan daftar gambar. Pakai *cross-reference* otomatis Word.
3. Istilah tidak konsisten antarsubbab (misalnya "Matrik" dan "Matriks").
4. Nama penulis di daftar pustaka tidak dibalik atau masih bergelar. APA: "Riani, A.", tanpa gelar.
5. Wikipedia dipakai sebagai rujukan ilmiah.
6. Tanda desimal campur titik dan koma. Pakai koma (0,991; 93,8%) sesuai pedoman dan EYD V.
7. Orang pertama di isi bab ("penulis membuat …") dan kata berlebihan tanpa ukuran ("sangat krusial", "signifikan" tanpa uji).
