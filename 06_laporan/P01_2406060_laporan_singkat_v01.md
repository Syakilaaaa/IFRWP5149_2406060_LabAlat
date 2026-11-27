# LAPORAN PRAKTIKUM ADBO
## PERTEMUAN 1: PENGENALAN LINGKUNGAN PRAKTIKUM DAN KAKAS PEMODELAN UML

- **Nama:** Syakila Nurul Ijati
- **NIM:** 2406060
- **Mata Kuliah:** Praktikum Analisis dan Desain Berorientasi Objek (ADBO)
- **Program Studi:** S1 Teknik Informatika (Semester 5)

---

### A. TUJUAN PRAKTIKUM
Mengacu pada ketentuan praktikum (Sub-CPMK terkait), capaian pembelajaran dari Pertemuan 1 ini adalah agar mahasiswa mampu:
1. Menginisialisasi ruang kerja (*workspace*) serta susunan direktori proyek repository berdasarkan Standar Operasional Prosedur (SOP) yang berlaku.
2. Mengoperasikan fitur-fitur fundamental pada kakas pemodelan UML (seperti *draw.io*) untuk membuat lembar kerja baru, menyusun elemen latihan, merangkai konektornya, hingga menyimpan berkas sumber.
3. Melakukan uji buka ulang (*reopen test*) terhadap berkas sumber (`.drawio`) guna memastikan diagram masih dapat diedit kembali tanpa kendala.
4. Melengkapi logbook ringkas beserta templat metadata artefak untuk mendokumentasikan langkah kerja, hasil verifikasi, hambatan, serta rencana tindak lanjut mandiri.

---

### B. DASAR TEORI
1. **Pengenalan Lingkungan & Workspace UML**
   Praktikum Analisis dan Desain Berorientasi Objek (ADBO) berfokus pada studi kasus utama berupa *Sistem Informasi Peminjaman dan Pengembalian Peralatan Laboratorium Kampus*. Pada sesi perdana (Pertemuan 1), kegiatan dititikberatkan pada adaptasi lingkungan kerja, penataan struktur folder proyek secara sistematis, serta penguasaan dasar editor diagram. Diagram yang disusun pada tahap ini bersifat sebagai **uji operasional kakas** (*tool training*) dan belum merupakan dokumen spesifikasi analisis kebutuhan akhir.
2. **Standard Operating Procedure (SOP) Penataan Direktori**
   Demi menjamin keteraturan dan kemudahan pelacakan artefak, ruang kerja harus dibuat di dalam direktori induk berformat `IFRWP5149_<NIM>_LabAlat` yang terdiri atas subdirektori berikut:
   - `00_administrasi/` (Catatan logbook kegiatan)
   - `01_skenario/` (Dokumen skenario orientasi `S-ORI-01`)
   - `02_template/` (Templat metadata artefak)
   - `03_latihan_tools/` (Direktori penyimpanan berkas latihan/uji coba kakas)
   - `04_model_analisis/` & `05_model_desain/` (Disediakan kosong untuk kebutuhan pertemuan berikutnya)
   - `06_laporan/` (Dokumen laporan ringkas progres)
3. **Aturan Penomoran Versi Artefak**
   Kaidah penamaan berkas menerapkan format standar `P<dua_digit>_<NIM>_<jenis_artefak>_v<dua_digit>.<ekstensi>` (diawali dari `v01`), dengan ketentuan bahwa nomor versi antara berkas sumber (`.drawio`) dan berkas gambar hasil ekspor (`.png`) wajib selalu selaras.

---

### C. HASIL PRAKTIKUM
1. **Setup Workspace & Berkas Administrasi**
   - Berhasil membentuk susunan direktori repository lokal `IFRWP5149_2406060_LabAlat` yang dilengkapi dengan berkas `README.md` berisi identitas mahasiswa, informasi kakas yang digunakan, serta status pengerjaan.
   - Berhasil menyusun logbook awal pada direktori `00_administrasi/P01_2406060_logbook_v01.md` beserta templat metadata di dalam subfolder `02_template/`.
2. **Skenario Orientasi (`S-ORI-01`)**
   - Mendokumentasikan draf awal skenario orientasi pada berkas `01_skenario/S-ORI-01_orientasi_kasus_v01.md` yang menguraikan gambaran alur peminjaman alat dan batasan sistem informasi laboratorium.
3. **Latihan Diagram Aktivitas Sederhana**
   - Menyusun diagram aktivitas sebagai uji coba kakas pada direktori `03_latihan_tools/` dengan penamaan berkas sumber **`P01_2406060_latihan_activity_v01.drawio`** serta hasil ekspor gambar **`P01_2406060_latihan_activity_v01.png`**.
   - Diagram tersebut memuat tepat **4 komponen berurutan** sebagaimana ketentuan pada *jobsheet*:
     1. *Initial Node* (Titik mulai)
     2. Aktivitas: *"Buka daftar peralatan"*
     3. Aktivitas: *"Lihat informasi ketersediaan"*
     4. *Activity Final Node* (Titik selesai)

---

### D. ANALISIS
1. **Analisis Struktur Workspace:** Pemisahan direktori antara ruang uji coba (`03_latihan_tools`) dan ruang model analisis tervalidasi (`04_model_analisis`) sangat membantu mencegah tercampurnya berkas latihan kakas dengan artefak perancangan sistem utama pada sesi-sesi mendatang.
2. **Analisis Pengoperasian Kakas & Konsistensi Versi:** Pelaksanaan uji buka ulang (*reopen test*) pada berkas `.drawio` membuktikan bahwa file sumber dapat dibuka kembali, diatur ulang tata letaknya, serta diekspor kembali menjadi PNG tanpa kehilangan struktur maupun kerusakan data. Hal ini menjamin kelayakan pemeliharaan dokumen proyek dalam jangka panjang.
3. **Keterbatasan Tahap Awal:** Diagram aktivitas yang dibuat pada sesi ini semata-mata ditujukan sebagai latihan fitur dasar editor (penambahan simbol, pemberian label teks, dan penarikan garis penghubung), sehingga belum mencerminkan aturan bisnis secara rinci—yang baru akan dirancang secara bertahap pada pertemuan analisis berikutnya.

---

### E. KESIMPULAN
1. Seluruh rangkaian Praktikum Pertemuan 1 telah tuntas dilaksanakan dan memenuhi semua indikator Sub-CPMK, khususnya dalam hal penyiapan ruang kerja proyek dan pengoperasian fitur dasar kakas UML.
2. Seluruh artefak praktikum mulai dari *README.md*, logbook, templat metadata, skenario orientasi `S-ORI-01`, sampai berkas latihan diagram aktivitas (`.drawio` dan `.png`) telah tersusun sistematis mengikuti SOP penomoran versi `v01` pada repository GitHub pribadi **`syakila2406060/IFRWP5149_2406060_LabAlat`**.