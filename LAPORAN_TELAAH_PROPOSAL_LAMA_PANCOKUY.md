# Laporan Telaah Proposal Lama PancoKuy untuk Rencana Skripsi Supermatch–Elo

**Tanggal telaah:** 16 November 2026  
**Sumber:** repositori [`DickyAndrean07/proposal-pancoKuy`](https://github.com/DickyAndrean07/proposal-pancoKuy), cabang `main`, commit [`b59ac202fdcc6f988289559f2b22d31d4b4ccebc`](https://github.com/DickyAndrean07/proposal-pancoKuy/commit/b59ac202fdcc6f988289559f2b22d31d4b4ccebc).  
**Pembanding:** [CATATAN_SKRIPSI.md](CATATAN_SKRIPSI.md) dan [CELAH_RENCANA_SKRIPSI.md](CELAH_RENCANA_SKRIPSI.md).  
**Status:** laporan pemetaan bahan lama; bukan bukti bahwa celah skripsi baru sudah tertutup.

## Kesimpulan utama

**Ada bahan yang berguna, terutama catatan lapangan mentah dan pola perancangan sistem. Namun proposal lama tidak menyediakan data hasil supermatch maupun validasi kebutuhan pemeringkatan Elo.** Fokus proposal mata kuliah adalah platform komunitas PancoKuy dengan rekomendasi lawan **sparring** memakai *Weighted Product* (WP). Fokus skripsi sekarang adalah pencatatan **supermatch** dan rating **Elo**. Karena objek kegiatan, tujuan, algoritma, entitas data, dan pengujiannya berubah, Bab I–III lama tidak dapat dipindahkan begitu saja.

Proposal lama sendiri menempatkan riwayat/ranking supermatch sebagai **fitur pengembangan lanjutan**. Catatan keputusan Juli 2026 menyebut belum ada data riwayat pertandingan saat WP dipilih dan mengusulkan Elo ketika data supermatch sudah cukup. Ini adalah petunjuk riset yang penting, sekaligus alasan untuk **mengaudit ketersediaan data sekarang** sebelum mengunci rancangan pengujian Elo. ([Ringkasan konsep](https://github.com/DickyAndrean07/proposal-pancoKuy/blob/b59ac202fdcc6f988289559f2b22d31d4b4ccebc/05_Catatan/ringkasan_konsep_sistem.md), [catatan observasi](https://github.com/DickyAndrean07/proposal-pancoKuy/blob/b59ac202fdcc6f988289559f2b22d31d4b4ccebc/05_Catatan/catatan_observasi_lapangan.md))

## 1. Informasi yang dapat dipakai sebagai bahan awal

| Temuan dari proposal lama | Kegunaan untuk skripsi sekarang | Batas bukti |
|---|---|---|
| Penulis adalah anggota yang beraktivitas di Lamongan serta Surabaya–Sidoarjo; komunikasi komunitas memakai WhatsApp. | Memudahkan penentuan narasumber, pengamatan alur, dan penjelasan mengapa data atlet lintas wilayah perlu diidentifikasi secara konsisten. | Ini pengalaman penulis, belum membuktikan semua chapter memiliki masalah atau kebutuhan yang sama. |
| Catatan mentah menjelaskan sparring sebagai sarana belajar teknik, mengontrol permainan, dan mencoba *counter*, bukan sekadar mengejar menang. | Menguatkan **alasan konseptual** untuk memisahkan sparring dari pertandingan yang masuk rating. | Penjelasan penulis perlu diuji kepada pengurus/wasit; jangan diubah menjadi statistik komunitas. |
| Supermatch telah muncul dalam catatan lama sebagai kegiatan yang lebih serius dan berbeda dari sparring. | Menjadi jejak awal munculnya topik supermatch sebelum skripsi baru direncanakan. | Redaksi lama menyebut wasit *atau teman penengah*. Klarifikasi terbaru peneliti lebih spesifik: supermatch memiliki wasit, dan **hanya hasil yang diwasiti admin terdaftar sebagai wasit di sistem** yang boleh dimasukkan. Gunakan aturan terbaru sebagai rancangan saat ini. |
| Contoh lokasi dan pola pertemuan: Lamongan pernah dicatat tidak memiliki jadwal tetap; Surabaya pernah dicatat rutin malam Jumat dan ada kegiatan insidental. | Menjadi daftar lokasi serta situasi untuk pengamatan atau wawancara ulang. | Catatan ini bertanggal Juli 2026; jadwal terkini, termasuk keterangan sesi rutin dua kali seminggu, harus dipastikan per chapter. |
| Rancangan lama telah memisahkan akun pengguna, profil atlet, hubungan atlet dengan beberapa basecamp, serta event. | Pola identitas atlet lintas lokasi dan pemisahan kegiatan dari profil dapat dijadikan **sketsa awal** ERD baru. | Skema lama belum memiliki supermatch, wasit terdaftar, ronde, *foul*, hasil sah, kelompok rating, atau mutasi Elo. |
| Proposal lama memiliki tabel skenario *black-box* dan contoh pembandingan hasil algoritma dengan hitungan manual. | Format tabel uji dapat diadaptasi untuk tes otorisasi, alur hasil, transaksi rating, dan unit test Elo. | Pengujian lama hanya merancang WP dengan 5–10 profil simulasi; tidak membuktikan mutu rating atau prediksi Elo. |

Sumber utama tabel: [catatan mentah penulis](https://github.com/DickyAndrean07/proposal-pancoKuy/blob/b59ac202fdcc6f988289559f2b22d31d4b4ccebc/05_Catatan/catatan_mentah_wawancara_penulis.md), [observasi lapangan](https://github.com/DickyAndrean07/proposal-pancoKuy/blob/b59ac202fdcc6f988289559f2b22d31d4b4ccebc/05_Catatan/catatan_observasi_lapangan.md), dan [Bab III lama](https://github.com/DickyAndrean07/proposal-pancoKuy/blob/b59ac202fdcc6f988289559f2b22d31d4b4ccebc/01_Draft_Proposal/BAB3_AnalisisPerancangan.md).

### Nilai khusus catatan mentah

File wawancara/observasi mentah mencatat **jawaban penulis sendiri** atas pertanyaan pada 2–3 Juli 2026. Nilainya adalah jejak yang dapat diaudit: apa yang benar-benar diamati, kapan, dan bagaimana pengamatan itu berubah menjadi masalah penelitian. Namanya mengandung kata “wawancara”, tetapi **jangan menyajikannya sebagai wawancara independen dengan senior atau pengurus**. Untuk Bab I baru, ia lebih tepat disebut **observasi awal atau pengalaman lapangan peneliti**, lalu diperkuat dengan narasumber dan dokumen pertandingan lain. ([Catatan mentah](https://github.com/DickyAndrean07/proposal-pancoKuy/blob/b59ac202fdcc6f988289559f2b22d31d4b4ccebc/05_Catatan/catatan_mentah_wawancara_penulis.md))

## 2. Bagian yang tidak boleh dipindahkan sebagai isi skripsi baru

1. **Problem statement lama.** Masalah utama lama adalah pencarian basecamp, informasi event yang tenggelam di WhatsApp, dan pemilihan lawan sparring. Ini bukan bukti langsung bahwa pencatatan **hasil supermatch** bermasalah. Latar belakang baru memerlukan contoh catatan pertandingan, dampak kesalahan/ketiadaan riwayat, serta kebutuhan pengurus/atlet atas peringkat. ([Bab I lama](https://github.com/DickyAndrean07/proposal-pancoKuy/blob/b59ac202fdcc6f988289559f2b22d31d4b4ccebc/01_Draft_Proposal/BAB1_Pendahuluan.md))
2. **WP dan enam kriteria sparring.** Lokasi, berat, lama aktif, frekuensi, tangan, dan level merupakan masukan pencocokan profil. Elo membutuhkan hasil pertandingan berurutan; bobot dan tabel skor WP tidak dapat diganti nama menjadi parameter Elo. ([Bab III lama](https://github.com/DickyAndrean07/proposal-pancoKuy/blob/b59ac202fdcc6f988289559f2b22d31d4b4ccebc/01_Draft_Proposal/BAB3_AnalisisPerancangan.md))
3. **Fitur dan ERD lama sebagai desain final.** `sparing_requests` menyimpan ajakan sparring, bukan hasil supermatch yang dipimpin wasit. `events` dapat menjadi konteks waktu/tempat, tetapi supermatch bisa terjadi pada sesi rutin maupun event khusus; jenis acara tidak menentukan jenis pertandingan. Butuh desain baru untuk wasit, peserta, ronde, *foul*, hasil, dan riwayat rating.
4. **Klaim manfaat yang belum diuji.** Bab I lama mengaitkan pencocokan lawan dengan keamanan dan pengurangan cedera. Klaim itu tidak menjadi dasar skripsi Elo dan tidak boleh dipakai sebagai manfaat sistem baru tanpa pengujian yang sesuai. Sama halnya, “rating objektif/adil” belum boleh diklaim sebelum cakupan dan mutu data diuji. ([Bab I lama](https://github.com/DickyAndrean07/proposal-pancoKuy/blob/b59ac202fdcc6f988289559f2b22d31d4b4ccebc/01_Draft_Proposal/BAB1_Pendahuluan.md))
5. **Rencana pengujian dummy sebagai bukti akurasi.** Bab III lama secara jujur membatasi tes WP pada kecocokan rumus dengan data simulasi dan menyatakan itu bukan pembuktian efektivitas statistik. Pendekatan hitung manual masih berguna untuk **ketepatan implementasi Elo**, tetapi klaim bahwa Elo berguna memprediksi hasil supermatch membutuhkan pertandingan nyata yang memadai. ([Bab III lama](https://github.com/DickyAndrean07/proposal-pancoKuy/blob/b59ac202fdcc6f988289559f2b22d31d4b4ccebc/01_Draft_Proposal/BAB3_AnalisisPerancangan.md))

## 3. Instrumen dan pustaka yang berpotensi didaur ulang

Repositori memiliki **blueprint Google Form**, bukan hasil survei yang dapat dipakai sebagai angka Bab I. Pertanyaan lama tentang tidak adanya catatan hasil supermatch dan prioritas fitur ranking dapat dijadikan *bahan redaksi awal*. Form baru sebaiknya menanyakan pengalaman **supermatch**, jumlah kejadian dalam periode tertentu, cara wasit mencatat hasil, contoh kehilangan/selisih data, dan kebutuhan riwayat. Pisahkan responden atlet dari pengurus/wasit. Hapus pembuka yang menganggap beberapa fitur platform “sudah pasti ada”, karena itu dapat menggiring jawaban; jangan mengutip pilihan jawaban sebagai hasil penelitian. ([Blueprint formulir](https://github.com/DickyAndrean07/proposal-pancoKuy/blob/b59ac202fdcc6f988289559f2b22d31d4b4ccebc/02_Referensi/referensi_instrumen/Blueprint_GoogleForm_ArmWrestling.md))

Bab II lama memuat pustaka mengenai **aturan panco, konteks olahraga, sistem web, dan pengujian perangkat lunak**. Itu dapat menjadi daftar bacaan awal **setelah sumber aslinya dicek lagi**. Pustaka WP dan perbandingan metode SPK tidak lagi menjadi landasan algoritma utama. Bab II baru memerlukan sumber tentang Elo, asumsi rating berurutan, *cold start*, pemilihan K, evaluasi prediksi, serta aturan supermatch yang benar-benar digunakan di ISPF. Aturan federasi internasional yang dikutip proposal lama tidak otomatis sama dengan aturan komunitas/studi kasus. ([Bab II lama](https://github.com/DickyAndrean07/proposal-pancoKuy/blob/b59ac202fdcc6f988289559f2b22d31d4b4ccebc/01_Draft_Proposal/BAB2_LandasanTeori.md))

Repositori juga menyimpan enam halaman wireframe HTML dan tangkapan layar, menurut [README](https://github.com/DickyAndrean07/proposal-pancoKuy/blob/b59ac202fdcc6f988289559f2b22d31d4b4ccebc/README.md). Aset ini dapat dipakai sebagai inspirasi pola navigasi/profil, **bukan rancangan antarmuka final**. Alur kerja wasit di samping meja, validasi hasil, riwayat, dan leaderboard masih harus dirancang ulang.

## 4. Perbedaan atau ketidakpastian yang harus dijernihkan

| Hal | Proposal lama | Rencana sekarang / keputusan yang dibutuhkan |
|---|---|---|
| Kegiatan utama | Sparring dan pencocokan lawan latih tanding. | Supermatch yang diwasiti dan pencatatan hasilnya; sparring tetap latihan teknik dan tidak memberi hasil Elo. |
| Wasit | Catatan lama menyebut wasit atau teman sebagai penengah untuk sparring yang lebih serius. | Klarifikasi terbaru: supermatch memiliki wasit; hanya pertandingan dengan **admin terdaftar sebagai wasit sistem** yang hasilnya boleh masuk. Perlu definisi operasional dan otorisasi. |
| Ketersediaan data | Pada Juli 2026 dicatat belum ada riwayat pertandingan untuk mendukung Elo. | Audit apakah kini ada catatan historis yang dapat diverifikasi; jumlah anggota/grup WhatsApp bukan jumlah pertandingan layak rating. |
| Jadwal | Lamongan tidak tetap; Surabaya rutin malam Jumat, menurut catatan Juli. | Catatan baru menyebut sesi sparring rutin sekitar dua kali seminggu. Pastikan jadwal terkini **per chapter**; perubahan jadwal tidak mengubah definisi supermatch. |
| Wilayah | Proposal lama membahas komunitas lebih luas dan beberapa kota. | Judul baru membatasi Surabaya–Sidoarjo dengan Lamongan sebagai mitra; tentukan apakah hasil lintas wilayah masuk populasi rating. |

Perbedaan di atas **bukan bukti bahwa satu versi salah**: dokumen lama bertanggal Juli 2026 dan fokusnya berbeda. Namun penguji dapat mempertanyakannya bila kedua naskah dibaca tanpa penjelasan waktu dan ruang lingkup.

## 5. Dampak langsung pada daftar celah skripsi baru

| ID pada daftar celah | Apa yang diberikan proposal lama | Apa yang masih harus diperoleh |
|---|---|---|
| **B1.1 / E2.7 / T4.5** — data layak Elo | Catatan bahwa data riwayat pertandingan dulu belum tersedia; tidak ditemukan dataset hasil supermatch dalam repositori yang ditelaah. | Inventaris hasil historis atau rencana pengumpulan prospektif, termasuk tanggal, atlet, tangan, kelas, dan wasit yang memenuhi aturan. |
| **B1.2** — bukti masalah pencatatan | Pengalaman penulis tentang koordinasi WhatsApp dan kebutuhan ranking sebagai ide pengembangan. | Contoh konkret masalah pencatatan **supermatch**, bukan hanya masalah informasi jadwal atau lawan sparring. |
| **B1.4** — wilayah dan populasi | Gambaran mobilitas penulis dan pola latihan Lamongan–Surabaya. | Aturan pertandingan lintas wilayah dan siapa yang berhak masuk leaderboard studi kasus. |
| **B1.6** — instrumen | Blueprint survei dan contoh wawancara diri sendiri. | Survei terarah yang benar-benar dijalankan, wawancara independen pengurus/wasit, jumlah responden, dan dokumen pertandingan. |
| **E2.1 / D3.1** — hasil dan wasit | Pembedaan awal sparring/supermatch. | Aturan formal hasil akhir, status wasit admin terdaftar, verifikasi, dan otorisasi entri. |
| **D3.3–D3.6 / T4.1–T4.6** — rancangan dan uji | Pola ERD akun/profil/event dan tabel skenario uji. | Desain entitas pertandingan serta mutasi Elo, transaksi dan audit, kasus uji hasil, dan evaluasi data nyata. |

**Tidak ada butir pada [CELAH_RENCANA_SKRIPSI.md](CELAH_RENCANA_SKRIPSI.md) yang otomatis dapat ditandai selesai hanya dari proposal lama.** Proposal itu memberi petunjuk dan instrumen awal, bukan konfirmasi terbaru dari pihak ISPF atau dataset pertandingan.

## Langkah paling bernilai berikutnya

1. Temui pengurus/wasit dan minta **contoh 3–5 catatan supermatch** serta perkiraan total pertandingan yang masih bisa diverifikasi. Identifikasi siapa yang kelak dapat menjadi admin sekaligus wasit terdaftar.
2. Konfirmasi aturan hasil akhir dan data wajib: tangan, kelas, jumlah ronde, *foul*, pembatalan, tanggal, atlet, wasit, dan cara koreksi.
3. Sesuaikan lima pertanyaan pra-riset lama agar khusus menilai masalah **pencatatan supermatch**, lalu catat jumlah dan peran responden.
4. Gunakan temuan terverifikasi untuk menutup butir dalam `CELAH_RENCANA_SKRIPSI.md`; setelah itu barulah pindahkan keputusan dan bukti yang sudah pasti ke `CATATAN_SKRIPSI.md`.

**Penilaian akhir:** proposal lama berharga sebagai arsip proses berpikir, pengetahuan domain awal, dan bahan perancangan. Nilai utamanya untuk skripsi baru adalah **membantu merumuskan pertanyaan lapangan yang tepat**. Ia belum membuktikan bahwa rating Elo dapat dihitung atau diuji dengan data ISPF yang tersedia saat ini.
