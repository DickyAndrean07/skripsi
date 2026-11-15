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

---

## 2. Ringkasan Keputusan & Latar Belakang Riset

### 2.1 Objek Penelitian
* **Organisasi Resmi:** **Indonesia Strong Pullers Federation (ISPF)**
* **Tautan Profil Resmi:** [Instagram ISPF @ispf.ipp](https://www.instagram.com/ispf.ipp/)
* **Chapter / Wilayah yang Terlibat:**
  * **Utama:** ISPF Surabaya & Sidoarjo (200+ anggota aktif).
  * **Mitra Sparring & Afiliasi:** ISPF Lamongan (atlet aktif sparring/supermatch lintas wilayah).
* **Latar Belakang Peneliti & Hubungan Antar-Chapter (*Insider Advantage*):**
  * Peneliti merupakan *puller* aktif yang berdomisili asal di Lamongan dan menempuh studi di Gresik.
  * Peneliti aktif mengikuti latihan rutin dan sparring di dua simpul komunitas: ISPF Lamongan (saat berada di domisili asal) dan ISPF Surabaya & Sidoarjo (saat berada di domisili studi Gresik).
  * Terjalin komunikasi langsung dengan ketua dan pengurus/wasit di kedua chapter pasca-pertemuan di turnamen resmi.
  * **Justifikasi Akademis Bab 1:** Membuktikan adanya fenomena **mobilitas atlet lintas wilayah**, di mana atlet membutuhkan sistem pemeringkatan (ELO Rating) terpusat yang adil dan dapat diakses dari mana saja saat bertanding di luar kota asalnya.
* **Masalah Lapangan (Problem Statement):**
  1. Sparring merupakan latihan tanding rutin yang biasanya dilakukan dua kali seminggu dan perlu dibedakan dari supermatch. Hasil menang-kalah sparring tidak mencerminkan kekuatan atlet karena peserta dapat sedang mencoba atau mempelajari teknik.
  2. Supermatch dipimpin oleh wasit, yaitu anggota ISPF yang pernah menjadi wasit resmi atau anggota senior yang memahami aturan. Pencatatan skor, riwayat tanding, foul, dan evaluasi performa masih manual/ingatan.
  3. Belum ada sistem klasemen (*leaderboard*) resmi berbasis data untuk mengukur performa atlet secara objektif per kelas tanding dan tangan (kiri/kanan).

#### Pembedaan Sparring dan Supermatch (Klarifikasi Peneliti, 2026-11-16)

* **Sparring:** latihan tanding panco yang dilakukan rutin, sekitar dua kali seminggu; bukan latihan angkat beban. Pada sesi sparring, peserta bebas memilih lawan tanding.
* **Tujuan sparring:** mempelajari teknik baru atau mencoba teknik yang telah dilatih dalam latihan mandiri. Karena tujuan dan intensitas tiap peserta dapat berbeda, kemenangan dalam sparring tidak otomatis berarti pemenangnya lebih kuat.
* **Supermatch:** pertandingan yang dapat muncul karena seorang atlet menantang atlet lain untuk membuktikan kemampuan atau menguji batasnya; atlet juga dapat dipertemukan untuk menjalani supermatch. Supermatch memiliki wasit: anggota ISPF yang pernah menjadi wasit resmi atau anggota senior yang memahami aturan.
* **Waktu pelaksanaan bukan pembeda:** supermatch dapat berlangsung dalam sesi latihan rutin dua kali seminggu maupun dalam event khusus supermatch. Jadi, supermatch yang berlangsung saat sesi rutin tetap merupakan supermatch, bukan sparring.
* **Aturan input sistem (keputusan peneliti):** hasil supermatch hanya dapat dimasukkan ke sistem jika pertandingan tersebut diwasiti oleh admin yang sudah terdaftar sebagai wasit di sistem. Tidak semua supermatch yang terjadi di lapangan otomatis dapat dicatat di sistem.
* **Implikasi rancangan sementara:** sistem perlu membedakan jenis aktivitas/pertandingan dari jadwal atau event tempat kegiatan berlangsung. Hasil sparring tidak digunakan sebagai dasar pemeringkatan Elo karena bukan ukuran kekuatan yang andal. Sumber hasil supermatch dalam sistem dibatasi oleh aturan wasit terdaftar di atas; tata cara pencatatan dan pengesahan hasil lainnya masih perlu dirinci bersama pengurus/wasit.

### 2.2 Keputusan Metode / Algoritma
* **Metode Terpilih:** **Algoritma ELO Rating**
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

### [2026-11-16] - Klarifikasi Aktivitas Lapangan dan Arah Judul

* **Klarifikasi dari peneliti:** sparring adalah latihan tanding panco, bukan latihan angkat beban, yang rutin dilakukan sekitar dua kali seminggu. Peserta bebas memilih lawan dan memakai sparring untuk mempelajari teknik baru atau mencoba teknik dari latihan mandiri. Hasil menang-kalah sparring tidak dapat langsung dipakai untuk menyimpulkan siapa lebih kuat. Supermatch dapat terjadi karena tantangan untuk membuktikan kemampuan atau menguji batas, atau karena atlet dipertemukan. Supermatch dapat diadakan pada sesi rutin maupun pada event khusus. Supermatch memiliki wasit, yaitu anggota ISPF yang pernah menjadi wasit resmi atau anggota senior yang memahami aturan.
* **Aturan input sistem dari peneliti:** hanya hasil supermatch yang diwasiti oleh admin yang telah terdaftar sebagai wasit di sistem yang dapat dimasukkan ke sistem. Wasit supermatch di lapangan dan wasit yang memenuhi syarat input sistem tidak selalu sama.
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
