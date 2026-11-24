# DOKUMENTASI & LOG PERENCANAAN SKRIPSI

Dokumen ini berfungsi sebagai buku catatan utama (*living document*) untuk merekam seluruh ide, keputusan metodologi, progres bimbingan, dan riwayat diskusi pengerjaan skripsi.

---

## 1. Identitas Skripsi

* **Mahasiswa:** Semester 7 - Teknik Informatika
* **Institusi:** Program Studi Teknik Informatika, Fakultas Teknik, Universitas Muhammadiyah Gresik (UMG)
* **Tahun Akademik:** 2025 / 2026
* **Bidang / Topik:** **Rekayasa Perangkat Lunak (RPL)**
* **Calon Dosen Pembimbing:**
  1. **Pembimbing 1:** Dosen Pengampu Mata Kuliah Rekayasa Perangkat Lunak (RPL)
  2. **Pembimbing 2:** Dosen Pengampu Mata Kuliah Basis Data Lanjut
* **Judul Terpilih:**
  > **"Rancang Bangun Sistem Informasi Manajemen Supermatch dan Pemeringkatan Atlet Panco Menggunakan Algoritma ELO Rating Berbasis Web"**  
  > *(Studi Kasus: Indonesia Strong Pullers Federation / ISPF Surabaya & Sidoarjo)*
* **Cakupan penelitian yang ditegaskan pada 2026-11-16:** pengumpulan data dan uji coba skripsi difokuskan pada ISPF Surabaya dan Sidoarjo. Rancangan data dan hak akses disiapkan agar chapter lain dapat ditambahkan kelak, tetapi keikutsertaan ISPF Lamongan Utara/Selatan, Malang, Kediri, atau chapter lain bukan syarat keberhasilan skripsi dan belum diklaim sebagai lokasi uji coba.

---

## 2. Ringkasan Keputusan & Latar Belakang Riset

### 2.1 Objek Penelitian
* **Organisasi Resmi:** **Indonesia Strong Pullers Federation (ISPF)**
* **Tautan Profil Resmi:** [Instagram ISPF @ispf.ipp](https://www.instagram.com/ispf.ipp/)
* **Chapter / Wilayah yang Terlibat:**
  * **Lokasi penelitian dan uji coba yang direncanakan:** ISPF Surabaya & Sidoarjo (perkiraan 200+ anggota aktif, perlu verifikasi).
  * **Konteks relasi atlet lintas wilayah:** ISPF Lamongan (atlet aktif sparring/supermatch lintas wilayah); tidak menjadi lokasi uji coba wajib pada cakupan saat ini.
* **Pihak yang perlu diajak membahas uji coba sistem (menurut peneliti):** ketua ISPF Surabaya dan Sidoarjo serta para senior. Persetujuan penggunaan sistem dan data supermatch belum diminta atau diperoleh.
* **Latar Belakang Peneliti & Hubungan Antar-Chapter (*Insider Advantage*):**
  * Peneliti merupakan *puller* aktif yang berdomisili asal di Lamongan dan menempuh studi di Gresik.
  * Peneliti aktif mengikuti latihan rutin dan sparring di dua simpul komunitas: ISPF Lamongan (saat berada di domisili asal) dan ISPF Surabaya & Sidoarjo (saat berada di domisili studi Gresik).
  * Terjalin komunikasi langsung dengan ketua dan pengurus/wasit di kedua chapter pasca-pertemuan di turnamen resmi.
  * **Justifikasi Akademis Bab 1:** Membuktikan adanya fenomena **mobilitas atlet lintas wilayah**, di mana atlet membutuhkan sistem pemeringkatan (ELO Rating) terpusat yang adil dan dapat diakses dari mana saja saat bertanding di luar kota asalnya.
* **Masalah Lapangan (Problem Statement):**
  1. Sparring merupakan latihan tanding rutin yang biasanya dilakukan dua kali seminggu dan perlu dibedakan dari supermatch. Hasil menang-kalah sparring tidak mencerminkan kekuatan atlet karena peserta dapat sedang mencoba atau mempelajari teknik.
  2. Supermatch dipimpin oleh wasit, yaitu anggota ISPF yang pernah menjadi wasit resmi atau anggota senior yang memahami aturan. Menurut peneliti, hasil supermatch selama ini tidak dicatat secara terstruktur dan umumnya hanya diingat anggota; pertandingan biasanya direkam dan videonya dikirim ke grup WhatsApp.
  3. Belum ada sistem klasemen (*leaderboard*) resmi berbasis data untuk mengukur performa atlet secara objektif per kelas tanding dan tangan (kiri/kanan).

#### Pembedaan Sparring dan Supermatch (Klarifikasi Peneliti, 2026-11-16)

* **Sparring:** latihan tanding panco yang dilakukan rutin, sekitar dua kali seminggu; bukan latihan angkat beban. Pada sesi sparring, peserta bebas memilih lawan tanding.
* **Tujuan sparring:** mempelajari teknik baru atau mencoba teknik yang telah dilatih dalam latihan mandiri. Karena tujuan dan intensitas tiap peserta dapat berbeda, kemenangan dalam sparring tidak otomatis berarti pemenangnya lebih kuat.
* **Supermatch:** pertandingan yang dapat muncul karena seorang atlet menantang atlet lain untuk membuktikan kemampuan atau menguji batasnya; atlet juga dapat dipertemukan untuk menjalani supermatch. Supermatch memiliki wasit: anggota ISPF yang pernah menjadi wasit resmi atau anggota senior yang memahami aturan.
* **Kelas berat menurut pengalaman peneliti sebagai anggota ISPF:** `-65 kg`, `-75 kg`, dan `+75 kg`. Supermatch lintas kelas dapat terjadi, misalnya ketika atlet kelas lebih ringan ingin menguji batas kemampuannya atau ada persoalan personal antaratlet. Batas tepat untuk berat 65 kg dan 75 kg perlu ditulis secara eksplisit dalam rancangan aturan.
* **Waktu pelaksanaan bukan pembeda:** supermatch dapat berlangsung dalam sesi latihan rutin dua kali seminggu maupun dalam event khusus supermatch. Jadi, supermatch yang berlangsung saat sesi rutin tetap merupakan supermatch, bukan sparring.
* **Aturan input sistem (keputusan peneliti):** hasil supermatch hanya dapat dimasukkan ke sistem jika pertandingan tersebut diwasiti oleh admin yang sudah terdaftar sebagai wasit di sistem. Tidak semua supermatch yang terjadi di lapangan otomatis dapat dicatat di sistem.
* **Gagasan platform lintas komunitas (belum menjadi keputusan aturan):** setiap komunitas dapat memiliki admin atau wasit tepercaya untuk mengelola profil atlet dan mengajukan hasil supermatch. Keabsahan hasil perlu didukung bukti, misalnya video pertandingan, sebelum memengaruhi peringkat. Belum diputuskan apakah admin yang bukan wasit pertandingan boleh memasukkan hasil; ini perlu diselaraskan dengan aturan input sebelumnya.
* **Batas perluasan sistem:** entitas chapter/komunitas dan relasinya dengan atlet, admin, wasit, serta pertandingan dapat dirancang untuk lebih dari dua chapter. Implementasi dan evaluasi skripsi tetap dibatasi pada ISPF Surabaya dan Sidoarjo; penerapan di chapter lain adalah peluang pengembangan setelah penelitian.
* **Kondisi data lama (keterangan peneliti, belum diaudit):** belum ada rekap hasil supermatch yang terstruktur. Video pertandingan biasanya dikirim ke grup WhatsApp, tetapi video lama sulit dicari dan tidak selalu memperlihatkan hasil dengan jelas. Peneliti memperkirakan terjadi sekitar 30 pertandingan supermatch atau lebih per bulan di Surabaya dan Sidoarjo secara gabungan; angka ini menghitung pertandingan, bukan jumlah event, dan belum diverifikasi dengan inventaris.
* **Implikasi rancangan sementara:** sistem perlu membedakan jenis aktivitas/pertandingan dari jadwal atau event tempat kegiatan berlangsung. Hasil sparring tidak digunakan sebagai dasar pemeringkatan Elo karena bukan ukuran kekuatan yang andal. Sumber hasil supermatch dalam sistem dibatasi oleh aturan wasit terdaftar di atas; tata cara pencatatan dan pengesahan hasil lainnya masih perlu dirinci bersama pengurus/wasit.

### 2.2 Keputusan Metode / Algoritma
* **Metode Terpilih:** **Algoritma ELO Rating**
* **Klasifikasi level awal atlet (keputusan peneliti, 2026-11-16):** berdasarkan jumlah gelar **juara 1 turnamen**, dihitung terpisah untuk tangan kanan dan tangan kiri. Pemula = 0 kali juara 1; semi-pro = 1–2 kali; pro = 3 kali atau lebih. Atlet dapat memiliki level awal berbeda pada kedua tangan. Gelar dihitung dari semua turnamen yang menetapkan juara 1, 2, dan 3; *fun match* dikecualikan. Posisi juara 2 dan 3 tidak menambah hitungan gelar untuk klasifikasi ini.
* **Parameter yang belum ditetapkan:** cara memverifikasi riwayat juara 1 dan mengidentifikasi *fun match*, angka rating awal untuk tiap level, serta jarak antarrating. Klasifikasi level belum otomatis menetapkan angka Elo.
* **Kebijakan Elo untuk supermatch lintas kelas belum diputuskan:** pertandingan lintas kelas dapat dicatat sebagai supermatch, tetapi perlu aturan tersendiri apakah hasilnya mengubah rating per kelas, masuk ke kelompok rating terbuka, atau hanya tercatat tanpa perubahan Elo. Jangan menyamakan dua kelompok rating kelas yang terpisah tanpa aturan penghubung yang jelas.
* **Alasan Pemilihan ELO dibanding Metode Lain (misal SPK / Weighted Product):**
  * Panco (*arm wrestling*) adalah olahraga adu fisik satu lawan satu (*head-to-head zero-sum*). Penentu utama kehebatan *puller* adalah *siapa yang berhasil dikalahkan*, bukan sekadar akumulasi nilai kriteria statis.
  * *Weighted Product (WP)* rawan bias jika ada atlet yang memiliki winrate tinggi hanya karena melawan pemula.
  * ELO Rating memberikan nilai bobot kemenangan dinamis: mengalahkan atlet berperingkat tinggi menghasilkan lonjakan poin lebih besar.
  * Meningkatkan keterlibatan (*engagement*) komunitas karena skor rating terasa kompetitif (mirip sistem catur FIDE / rank game kompetitif).
  * Menghindari kejenuhan penguji terhadap topik SPK konvensional.

### 2.3 Strategi Pengumpulan Bukti Masalah (Bab 1)
* Menggunakan **Kuesioner Pra-Riset Singkat (Google Form 4–5 Pertanyaan)** yang disebarkan ke grup WhatsApp ISPF Surabaya-Sidoarjo dan ISPF Lamongan.
* Menyertakan pertanyaan filter demografi wilayah (Surabaya-Sidoarjo vs Lamongan).
* Hasil survei (diagram persentase) akan disajikan di Sub-bab 1.1 Latar Belakang untuk mengunci penilaian "Ketajaman Perumusan Masalah" (bobot 25% UMG).

### 2.4 Keputusan Platform & Arsitektur Antarmuka (PWA vs Mobile Native)
* **Keputusan:** **Web Responsive (Mobile-First) dengan kapabilitas Progressive Web App (PWA)**.
* **Alasan Pemilihan PWA dibanding Mobile Native (Play Store / App Store):**
  * **Fokus Riset S1:** Menghindari beban ganda pembuatan backend terpisah dan frontend mobile native, sehingga waktu fokus dialokasikan ke implementasi & pengujian **Algoritma ELO Rating**.
  * **Aksesibilitas Universal (Cross-Platform):** 200+ anggota ISPF dapat langsung mengakses sistem dari ponsel pintar mereka (baik Android maupun iOS/iPhone) hanya dengan membagikan tautan URL di grup WhatsApp.
  * **Ergonomi Lapangan (Meja Panco):** Antarmuka didesain *mobile-first* agar wasit (*puller* senior) dapat mencatat skor, *round*, dan *foul* secara taktil dan cepat di samping meja tanding.
  * **Bebas Hambatan Distribusi:** Dapat di-*install* langsung ke layar utama ponsel (*Add to Home Screen*) tanpa perlu membayar biaya pendaftaran developer store ($25 Google Play / $99 per tahun Apple) dan terbebas dari antrean regulasi review Google (aturan 20 tester selama 14 hari).

---

## 3. Ketentuan Kunci Berdasarkan Panduan Skripsi UMG 2025

Berdasarkan `BUKU PANDUAN SKRIPSI 2025.pdf`:

1. **Standar Level S1 (Hal. 2):** Wajib memiliki kontribusi *implementation development* dan pengujian metode/algoritma (bukan sekadar CRUD biasa / Level D3).
2. **Sistem Akademik:** Seluruh tahapan (pengajuan Form A1/B1, log bimbingan, pendaftaran sempro, dan sidang) menggunakan sistem **MONTA**.
3. **Standar Format Tulisan:**
   * **Font:** Times New Roman, ukuran 12 pt, spasi 1.5.
   * **Margin:** Atas 4 cm, Kiri 4 cm, Bawah 3 cm, Kanan 3 cm.
   * **Format Penomoran:** Sub-bab menggunakan format *numbering* bertingkat (dilarang menggunakan *bullets*).
   * **Kutipan & Daftar Pustaka:** Menggunakan sistem **Vancouver** (penomoran [1], [2], dst.).
   * **Artikel Ilmiah:** Gaya selingkung jurnal internasional **IEEE**.
4. **Batas Plagiasi:** Maksimal **30%** saat pendaftaran sidang akhir.
5. **Kriteria Penilaian Utama:**
   * **Proposal:** Ketajaman rumusan masalah (25%), kesesuaian metode (30%), penguasaan materi (30%), pustaka (15%).
   * **Sidang Akhir:** Kesesuaian tujuan dengan implementasi (30%), pengujian (30%), penguasaan materi (20%), nilai proposal (20%).

---

## 4. Log Riwayat Diskusi (Changelog)

Format pencatatan berkala untuk diskusi berikutnya:

### [2026-11-24] - Standarisasi Penamaan Kelas Berat, Penanganan Catchweight, dan Alur Wasit

* **Penamaan Divisi untuk Rancangan Web:**
  * Peneliti mengusulkan label berikut untuk antarmuka web dan dokumen skripsi; batas kilogramnya mengikuti kelas yang dipakai dalam studi kasus, bukan standar universal olahraga tarung:
    * `-65 kg` $\rightarrow$ **Lightweight** (Kelas Ringan)
    * `-75 kg` $\rightarrow$ **Middleweight** (Kelas Menengah)
    * `+75 kg` $\rightarrow$ **Heavyweight** (Kelas Berat)
    * Lintas kelas $\rightarrow$ **Openweight** (Kelas Bebas). Istilah *catchweight* dipakai hanya bila batas berat khusus telah disepakati; Openweight bukan sinonim *pound-for-pound*.
* **Rancangan Penanganan Duel Lintas Kelas:**
  * Laga beda kelas (misalnya calon pasangan 84 kg vs 74 kg) diusulkan masuk kategori Openweight dan mengubah rating Openweight jika hasilnya memenuhi syarat; rating divisi kelas berat masing-masing atlet (`-65`, `-75`, `+75 kg`) tidak berubah.
  * **Keputusan peneliti tentang rating awal Openweight (24 November 2026):** setiap atlet memulai dari **1000 Elo Openweight untuk tangan kanan dan 1000 Elo Openweight untuk tangan kiri**, tanpa membedakan kelas berat atau level pemula/semi-pro/pro. Rating Openweight tiap atlet kemudian berubah mengikuti hasil akhir supermatch Openweight yang sah dan rating lawannya; tidak ada tambahan poin otomatis berdasarkan selisih berat badan. Rating Openweight terpisah dari rating divisi kelas berat. Anggapan bahwa peserta Openweight sudah kuat adalah pandangan peneliti, belum bukti untuk menyimpulkan bahwa kekuatan awal semua peserta setara. Nilai *K-factor*, syarat laga yang masuk Openweight, dan syarat tampil di leaderboard masih perlu ditetapkan.
* **Perancangan Alur Wasit Meja Panco (*Mobile-First*):**
  * Wasit login per akun chapter $\rightarrow$ Memilih dua atlet (sistem menandai bila kelas beratnya berbeda; kategori Openweight dikonfirmasi oleh wasit) $\rightarrow$ Memilih tangan (kanan/kiri) dan memasukkan skor ronde $\rightarrow$ Menampilkan *live preview* kalkulasi Elo untuk verifikasi visual $\rightarrow$ Memasukkan tautan bukti video $\rightarrow$ Menekan tombol *"Sahkan Pertandingan"* (eksekusi atomik, status terkunci `verified`, pembaruan mutasi rating instan).
* **Standar Foto Profil Kartu Tanding (*Fight Card*):**
  * Disepakati format foto atlet potret kepala-bahu (*Headshot / Bust Shot*) dengan rasio 1:1 atau 3:4, dilengkapi badge status tingkat keahlian (*Pro, Semi-Pro, Pemula*), serta fitur *auto-crop* dan siluet cadangan (*fallback avatar*) jika foto belum tersedia.

### [2026-11-23] - Informasi Awal Ajakan Supermatch Gresik

* **Sumber dan isi pesan:** peneliti menyampaikan pesan grup tentang orang-orang dari komunitas Gresik yang siap supermatch dengan ISPF Surabaya dan Sidoarjo pada bulan Januari. Pesan memuat 12 nama dalam daftar dan dua calon pasangan yang ditulis dengan `vs`. Tahun, tanggal pasti, tempat, dan afiliasi kedua lawan yang disebut setelah `vs` belum dikonfirmasi.
* **Contoh kebutuhan rancangan:** berat yang tertulis pada dua calon pasangan ialah 84 kg vs 74 kg dan 72 kg vs 80 kg. Berdasarkan kelas kerja `-65`, `-75`, dan `+75 kg`, keduanya berpotensi menjadi pertandingan lintas kelas. Angka tersebut berasal dari pesan, belum merupakan hasil penimbangan atau bukti kesepakatan *catchweight*.
* **Batas kesimpulan:** ajakan ini belum membuktikan bahwa pertandingan telah dijadwalkan secara pasti, terlaksana, memiliki wasit yang memenuhi aturan sistem, atau menghasilkan data untuk Elo. Daftar orang yang siap bertanding tidak dapat dihitung sebagai jumlah partai. Simpan pesan asli beserta tanggal kirimnya jika akan digunakan sebagai bukti pra-riset.
* **Gagasan pengembangan, belum menjadi keputusan skripsi:** platform promotor independen dan pengelolaan admin/wasit per komunitas dapat dibahas kemudian. Gagasan ini tidak otomatis menghapus kebutuhan izin penggunaan data, tidak mengubah aturan saat ini bahwa hasil yang dicatat harus diwasiti admin terdaftar sebagai wasit di sistem, dan tidak memperluas studi kasus yang masih berfokus pada ISPF Surabaya–Sidoarjo. Kewenangan lintas komunitas serta kebijakan Elo lintas kelas tetap terbuka; lihat [CELAH_RENCANA_SKRIPSI.md](CELAH_RENCANA_SKRIPSI.md).

### [2026-11-16] - Klarifikasi Aktivitas Lapangan dan Arah Judul

* **Keputusan cakupan dan judul kerja:** pertahankan judul manajemen supermatch dan pemeringkatan Elo berbasis web dengan studi kasus ISPF Surabaya dan Sidoarjo. Struktur sistem disiapkan untuk kemungkinan chapter lain bergabung kelak, tetapi uji coba lintas banyak chapter tidak menjadi target skripsi saat ini. Sebutan “antar-komunitas” tidak dimasukkan ke judul kerja.
* **Klarifikasi kelas berat dari peneliti:** kelas yang dipakai adalah `-65 kg`, `-75 kg`, dan `+75 kg`. Supermatch lintas kelas mungkin terjadi karena atlet kelas ringan ingin menguji batas atau karena persoalan personal. Ini adalah keterangan langsung peneliti sebagai anggota ISPF; kebijakan dampaknya pada Elo belum ditetapkan.
* **Gagasan platform lintas komunitas dari peneliti:** tiap komunitas memiliki admin atau wasit tepercaya yang dapat mengelola profil atlet dan mengajukan hasil; bukti seperti video diperlukan untuk keabsahan. Rincian hak input, verifikasi bukti, dan pengesahan Elo belum ditetapkan.
* **Klarifikasi level awal Elo:** "juara" berarti **juara 1 turnamen**, bukan seluruh posisi podium. Jumlah gelar dihitung terpisah menurut tangan: pemula 0, semi-pro 1–2, pro 3 atau lebih. Semua turnamen yang menetapkan juara 1, 2, dan 3 dapat menjadi sumber gelar, kecuali *fun match*; hanya posisi juara 1 yang dihitung. Cara pembuktian gelar dan angka rating awal masih terbuka.
* **Klarifikasi dari peneliti:** sparring adalah latihan tanding panco, bukan latihan angkat beban, yang rutin dilakukan sekitar dua kali seminggu. Peserta bebas memilih lawan dan memakai sparring untuk mempelajari teknik baru atau mencoba teknik dari latihan mandiri. Hasil menang-kalah sparring tidak dapat langsung dipakai untuk menyimpulkan siapa lebih kuat. Supermatch dapat terjadi karena tantangan untuk membuktikan kemampuan atau menguji batas, atau karena atlet dipertemukan. Supermatch dapat diadakan pada sesi rutin maupun pada event khusus. Supermatch memiliki wasit, yaitu anggota ISPF yang pernah menjadi wasit resmi atau anggota senior yang memahami aturan.
* **Aturan input sistem dari peneliti:** hanya hasil supermatch yang diwasiti oleh admin yang telah terdaftar sebagai wasit di sistem yang dapat dimasukkan ke sistem. Wasit supermatch di lapangan dan wasit yang memenuhi syarat input sistem tidak selalu sama.
* **Klarifikasi ketersediaan data:** hasil supermatch lama tidak pernah dicatat dalam rekap terstruktur dan biasanya hanya diingat anggota. Pertandingan sering direkam lalu dikirim ke grup WhatsApp, tetapi video sulit ditelusuri dan hasilnya tidak selalu terlihat jelas. Perkiraan awal peneliti: sekitar 30 pertandingan supermatch atau lebih per bulan di Surabaya dan Sidoarjo secara gabungan. Jumlah pertandingan yang memenuhi aturan wasit sistem belum diketahui.
* **Pihak untuk konfirmasi:** menurut peneliti, rencana uji coba pencatatan supermatch perlu dibahas dengan ketua ISPF Surabaya dan Sidoarjo serta para senior; pembicaraan dan persetujuannya belum dilakukan.
* **Keputusan saat ini:** peneliti lebih condong ke Opsi 1, yaitu rancang bangun sistem informasi manajemen supermatch dan pemeringkatan atlet dengan Elo. Opsi 3 (matchmaking) bukan fokus utama judul saat ini; kebutuhan fitur mempertemukan lawan supermatch dapat dikaji kemudian berdasarkan temuan lapangan.
* **Catatan untuk perancangan:** jangan menyamakan sparring dengan supermatch, jangan menggunakan jadwal rutin vs event khusus sebagai penentu jenis pertandingan, jangan memasukkan hasil sparring ke rating Elo, dan batasi input hasil supermatch menurut status admin sekaligus wasit terdaftar di sistem.

### [2026-10-15] - Diskusi Arsitektur Platform & Penguatan Batasan Kasus
* **Topik Dibahas:**
  * Evaluasi kepraktisan penggunaan aplikasi mobile untuk pencatatan wasit di samping meja panco dan pengecekan ranking oleh atlet.
  * Analisis hambatan publikasi ke Play Store (biaya $25 + aturan wajib 20 tester selama 14 hari) dan App Store ($99/tahun + batasan ekosistem iOS/Mac).
  * Klarifikasi ruang lingkup wilayah: Memastikan batasan penelitian tidak melebar ke seluruh Jawa Timur, melainkan terkunci pada **ISPF Surabaya & Sidoarjo** dengan **ISPF Lamongan** sebagai mitra tanding.
  * Pencatatan latar belakang personal peneliti (*insider advantage*): Peneliti merupakan atlet aktif berdomisili asal Lamongan yang menempuh kuliah di Gresik, sehingga rutin mengikuti kegiatan di ISPF Lamongan maupun ISPF Surabaya-Sidoarjo. Fakta ini memperkuat justifikasi fenomena "mobilitas atlet lintas wilayah" untuk Bab 1.
* **Keputusan / Hasil:**
  * Menyepakati arsitektur **Web Mobile-First / Progressive Web App (PWA)**.
  * Judul skripsi tetap mempertahankan frasa *"Berbasis Web"* sesuai dokumen akademik, namun perancangan UI/UX difokuskan ramah layar ponsel (*mobile-first* touch target) dan mendukung instalasi pintasan layar utama (*Add to Home Screen*).
  * Batasan studi kasus terkunci aman tanpa perlu melobi chapter kota lain.

### [2026-10-14] - Diskusi Awal & Penentuan Arah Skripsi
* **Topik Dibahas:**
  * Penjelasan jenis skripsi di Informatika (Rancang Bangun vs Eksperimental Algoritma).
  * Pembedahan buku panduan skripsi UMG 2025 (klausul S1 vs D3 di hal. 2).
  * Eksplorasi objek penelitian: Federasi Panco **Indonesia Strong Pullers Federation (ISPF)**.
  * Diskusi perbandingan metode: Sistem Pakar (Certainty Factor) vs SPK (Weighted Product) vs Algoritma ELO Rating.
  * Analisis realita lapangan: Latihan sparring harian informal vs Supermatch formal dengan wasit.
  * Pemilihan peminatan di form: **RPL (Rekayasa Perangkat Lunak)**.
  * Pemilihan calon dosen pembimbing: Dosen RPL (Pembimbing 1) dan Dosen Basis Data Lanjut (Pembimbing 2).
  * Klarifikasi sumber masalah skripsi: Memilih jalur **Kuesioner Pra-Riset Singkat** yang disebar ke ISPF Surabaya-Sidoarjo dan ISPF Lamongan untuk memperkuat bukti masalah di Bab 1.
* **Keputusan / Hasil:**
  * Menetapkan judul: *Rancang Bangun Sistem Informasi Manajemen Supermatch dan Pemeringkatan Atlet Panco Menggunakan Algoritma ELO Rating Berbasis Web (Studi Kasus: Indonesia Strong Pullers Federation / ISPF Surabaya & Sidoarjo)*.
  * Link Instagram resmi dicatat: `https://www.instagram.com/ispf.ipp/`.

---

## 5. Daftar Pertanyaan & Catatan Terbuka (Open Q&A / Backlog)

1. [ ] Menyusun draf 4–5 pertanyaan kuesioner pra-riset untuk disebar ke grup ISPF.
2. [ ] Merancang arsitektur alur Supermatch (tangan kanan/kiri, kategori berat badan, dan sistem perhitungan ELO).
3. [ ] *(Pertanyaan berikutnya...)*
