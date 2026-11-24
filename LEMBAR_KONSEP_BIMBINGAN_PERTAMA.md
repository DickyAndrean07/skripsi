# Lembar Konsep Bimbingan Pertama

**Program Studi:** S1 Teknik Informatika, Universitas Muhammadiyah Gresik  
**Nama / NIM:** M. Dicky Andrean / 230602070  
**Kelas:** B-PG 23  
**Status:** Draf untuk bimbingan awal  

## 1. Topik dan Judul Kerja

**Rancang Bangun Sistem Informasi Manajemen Supermatch dan Pemeringkatan Atlet Panco Menggunakan Metode Elo Rating Berbasis Web**  
*(Studi Kasus: Komunitas Panco ISPF Chapter Surabaya dan Sidoarjo)*

Uji coba difokuskan pada Surabaya–Sidoarjo. Sistem dapat dikembangkan untuk komunitas lain kemudian.

## 2. Masalah Lapangan dan Solusi yang Diusulkan

Peneliti adalah anggota aktif ISPF. *Sparring* adalah latihan tanding untuk mencoba teknik dan tidak dihitung dalam rating. Supermatch berwasit dapat berlangsung pada sesi rutin atau event khusus. Menurut pengamatan peneliti, hasilnya belum direkap terstruktur; video di grup WhatsApp sulit ditelusuri. Perkiraan awal peneliti adalah **30+ partai per bulan** di Surabaya–Sidoarjo; jumlah ini akan dikonfirmasi bersama pengurus dan wasit. Ajakan supermatch dari komunitas Gresik untuk Januari memuat dua calon pasangan beda kelas, tetapi jadwalnya belum dikonfirmasi.

Web responsif diusulkan untuk mencatat atlet, hasil dan bukti supermatch, riwayat, serta **leaderboard per tangan dan kelas `-65`, `-75`, `+75 kg`**. Kategori **Openweight** diusulkan untuk laga lintas kelas. Elo berubah hanya dari hasil akhir supermatch yang diwasiti admin terdaftar sebagai wasit sistem.

## 3. Contoh Cara Kerja Elo

Elo menghitung `rating baru = rating lama + K × (hasil − skor harapan)`. **Contoh dengan K=32:** A (1000) melawan B (1200). Jika A menang, A **+24,3** dan B **−24,3**; jika B menang, B **+7,7** dan A **−7,7**. Kemenangan atas lawan berating lebih tinggi memberi poin lebih besar.

## 4. Usulan Parameter Sistem dan Rencana Pengujian

**Parameter awal:** level per tangan didasarkan pada jumlah gelar juara 1: pemula 0, semi-pro 1–2, pro ≥3. Rating awal Openweight dipilih **1000 per atlet per tangan**, terpisah dari kelas berat. Angka awal kelas berat `1000/1200/1400`, nilai K, dan syarat laga yang mengubah rating masih perlu dibahas.

Pengumpulan data baru direncanakan secara prospektif pada sesi rutin atau event setelah izin dan alur pencatatan disepakati dengan pengurus serta wasit. Ajakan untuk Januari menjadi peluang uji coba jika jadwalnya pasti. Pengujian direncanakan dengan membandingkan hitungan sistem dan manual, memeriksa hak akses serta pengesahan ganda, dan membandingkan dampak beberapa nilai K. Jumlah laga yang layak dicatat akan diperiksa sebelum pengujian dengan data nyata.

## 5. Pertanyaan untuk Dosen Pembimbing

1. Apakah masalah, judul kerja, dan cakupan uji Surabaya–Sidoarjo layak untuk skripsi S1? Perlukah nama ISPF dicantumkan di judul atau cukup dijelaskan sebagai sumber data dan tempat uji?
2. Apakah metode Elo Rating tepat untuk memeringkat atlet dari hasil akhir supermatch? Parameter awal dan pengujian Elo apa yang perlu saya prioritaskan dalam proposal?

*Dokumen pendukung internal: [CATATAN_SKRIPSI.md](CATATAN_SKRIPSI.md) dan [CELAH_RENCANA_SKRIPSI.md](CELAH_RENCANA_SKRIPSI.md).*
