# Lembar Konsep Bimbingan Pertama

**Program Studi:** S1 Teknik Informatika, Universitas Muhammadiyah Gresik  
**Nama / NIM:** M. Dicky Andrean / 230602070  
**Kelas:** B-PG 23  
**Status:** Draf untuk bimbingan awal  

## 1. Topik dan Judul Kerja

**Rancang Bangun Sistem Informasi Manajemen Supermatch dan Pemeringkatan Atlet Panco Menggunakan Metode Elo Rating Berbasis Web**  
*(Studi Kasus: Komunitas Panco ISPF Chapter Surabaya dan Sidoarjo)*

Uji coba difokuskan pada Surabaya–Sidoarjo; chapter lain dapat ditambahkan kelak.

## 2. Masalah Lapangan dan Solusi yang Diusulkan

Peneliti adalah anggota aktif ISPF. *Sparring* ialah latihan tanding untuk mencoba teknik dan tidak masuk rating. Supermatch berwasit dapat terjadi pada sesi rutin atau event khusus.

Menurut pengamatan peneliti, hasil supermatch belum direkap terstruktur: anggota mengingat hasil dan video di grup WhatsApp sulit dicari. Belum ditemukan leaderboard dari hasil terverifikasi. Perkiraan **30+ pertandingan per bulan** di Surabaya–Sidoarjo **belum diverifikasi**.

Web responsif diusulkan untuk mencatat atlet, supermatch, bukti, riwayat, dan **leaderboard per tangan serta kelas `-65`, `-75`, `+75 kg`**. Rating hanya berubah dari hasil akhir supermatch yang diwasiti admin terdaftar sebagai wasit sistem.

## 3. Contoh Cara Kerja Elo

Elo menghitung `rating baru = rating lama + K × (hasil − skor harapan)`. **Contoh:** A berating 1000 melawan B berating 1200, K=32. Jika A menang, A naik **24,3 poin** dan B turun **24,3 poin**. Jika B menang, B naik **7,7 poin** dan A turun **7,7 poin**. Kemenangan atas lawan berating lebih tinggi bernilai lebih besar.

## 4. Hal yang Belum Pasti dan Rencana Pengujian

**Belum pasti:** izin uji coba, jumlah pertandingan layak catat, rating awal, K, dan aturan laga lintas kelas. Level awal per tangan didasarkan pada gelar juara 1: pemula 0, semi-pro 1–2, pro ≥3. Angka `1000/1200/1400`, K=32 konstan, dan K=40 lalu 32 masih **kandidat**.

Izin pengurus dan kesediaan wasit **belum diperoleh**. Data baru akan dicatat setelah izin ada. Pengujian: cocokkan hitungan sistem dengan hitungan manual; periksa hak akses dan pengesahan ganda; bandingkan dampak beberapa K pada poin dan peringkat. Data nyata dipakai jika memadai; simulasi tidak membuktikan K terbaik.

## 5. Pertanyaan untuk Dosen Pembimbing

1. Apakah masalah, judul kerja, dan cakupan Surabaya–Sidoarjo layak untuk skripsi S1?
2. Bagaimana batas minimum pengujian Elo yang diharapkan jika data historis belum terstruktur?
3. Kebijakan rating lintas kelas dan skema parameter mana yang sebaiknya diperdalam dalam proposal?

*Dokumen pendukung internal: [CATATAN_SKRIPSI.md](CATATAN_SKRIPSI.md) dan [CELAH_RENCANA_SKRIPSI.md](CELAH_RENCANA_SKRIPSI.md).*
