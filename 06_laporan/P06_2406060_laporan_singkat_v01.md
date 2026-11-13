# LAPORAN PRAKTIKUM ADBO
## PERTEMUAN 6: ACTIVITY DIAGRAM – DARI SKENARIO KE ALUR AKTIVITAS

- **Nama:** Syakila Nurul Ijati
- **NIM:** 2406060
- **Mata Kuliah:** Praktikum Analisis dan Desain Berorientasi Objek (ADBO)
- **Program Studi:** S1 Teknik Informatika (Semester 5)

---

### A. TUJUAN PRAKTIKUM

Mengacu pada *Jobsheet* Praktikum Pertemuan 6, target capaian yang harus diraih mahasiswa meliputi kemampuan untuk:

1. Membangun alur utama *activity diagram* yang berpedoman pada **Skenario Normal** dalam tabel skenario Pertemuan 5.
2. Mengonversi **Skenario Alternative** menjadi node percabangan *decision* yang dilengkapi kondisi *guard* secara tepat.
3. Menerapkan pasangan elemen *fork* dan *join* untuk memodelkan rangkaian aktivitas yang dieksekusi secara paralel.
4. Mengelompokkan setiap simbol *action* ke dalam jalur *swimlane* yang sesuai dengan aktor atau entitas pelaksananya.
5. Memastikan keterlacakan (*traceability*) setiap *action* pada *activity diagram* terhadap baris langkah di tabel skenario Pertemuan 5.
6. Mengevaluasi kelengkapan dan ketepatan diagram menggunakan daftar periksa (*checklist*) sebelum berkas diserahkan.

### B. DASAR TEORI

1. **Pengertian Activity Diagram**

   *Activity diagram* merupakan jenis diagram dalam UML yang berfungsi memvisualisasikan alur kerja (*workflow*) atau rangkaian aktivitas di dalam suatu proses bisnis maupun sistem. Diagram ini memetakan urutan eksekusi kegiatan, percabangan logika keputusan, aktivitas yang berlangsung bersamaan (paralel), serta pembagian tanggung jawab tiap pelaku yang terlibat. Pada sesi ini, penyusunan *activity diagram* bertumpu langsung pada tabel skenario *use case* hasil Pertemuan 5.

2. **Unsur-Unsur Activity Diagram**

   Penyusunan *activity diagram* melibatkan komponen-komponen utama berikut:

   - **Initial Node:** Titik awal dimulainya alur proses; setiap diagram wajib memiliki tepat satu *initial node*.
   - **Action:** Merepresentasikan langkah kerja atau aktivitas spesifik yang dijalankan oleh aktor maupun sistem.
   - **Control Flow:** Garis berpanah yang menunjukkan arah perpindahan kendali dari satu *action* ke *action* selanjutnya.
   - **Decision:** Simbol belah ketupat yang berfungsi memecah alur menjadi beberapa jalur alternatif berdasarkan evaluasi kondisi tertentu.
   - **Guard:** Ekspresi syarat yang diapit tanda kurung siku (`[...]`) untuk menerangkan kondisi pada setiap jalur keluar dari *decision*.
   - **Merge:** Simbol belah ketupat yang menyatukan kembali jalur-jalur percabangan ke dalam satu aliran utama.
   - **Fork:** Garis tebal (*synchronization bar*) yang memecah satu alur tunggal menjadi dua atau lebih alur paralel yang berjalan serentak.
   - **Join:** Garis tebal yang menyinkronkan dan menggabungkan kembali alur-alur paralel setelah seluruh cabangnya selesai dieksekusi.
   - **Activity Final Node:** Simbol titik akhir yang menandakan berhentinya seluruh rangkaian aktivitas pada diagram.
   - **Swimlane:** Pembatas kolom atau baris yang memetakan tanggung jawab pelaksanaan *action* berdasarkan masing-masing aktor atau sistem.

3. **Pemetaan Skenario ke Activity Diagram**

   Konversi tabel skenario ke *activity diagram* mengikuti kaidah pemetaan yang terstruktur: bagian **Skenario Normal** dituangkan menjadi alur utama diagram, sedangkan **Skenario Alternative** diwujudkan sebagai percabangan *decision*. Sub-proses *include* dimodelkan sebagai *action* wajib di jalur utama, sementara perilaku *extend* dimodelkan sebagai cabang bersyarat. Dari sisi penempatan, setiap aksi pada kolom *Kegiatan* diletakkan di *swimlane* aktor terkait, sedangkan kolom *Respon Sistem* diletakkan di *swimlane* **Sistem**.

4. **Aturan Penggunaan Decision, Fork, dan Join**

   Setiap cabang yang keluar dari node *decision* wajib disertai keterangan *guard* yang eksplisit serta mencakup seluruh kemungkinan logika kondisi (saling melengkapi), dan cabang-cabang yang kembali ke alur utama harus disatukan lewat node *merge*. Di sisi lain, percabangan paralel yang diawali dengan *fork* wajib ditutup kembali menggunakan pasangan *join* sebelum alur proses dilanjutkan ke tahap berikutnya. Penggunaan kedua jenis simbol ini harus disesuaikan secara cermat dengan kebutuhan alur proses.

### C. HASIL PRAKTIKUM

Kegiatan praktikum Pertemuan 6 menitikberatkan pada perancangan *activity diagram* berdasarkan tabel skenario Pertemuan 5 pada dua studi kasus utama, yakni *Sistem Informasi Peminjaman dan Pengembalian Peralatan Laboratorium Kampus* serta *Sistem Informasi Akademik (SIA)*.

**1. Activity Diagram Sistem Laboratorium (LAB)**

Mengacu pada ketentuan *jobsheet*, disusun tujuh buah *activity diagram* utama berikut:

1. **LAB-UC01 – Lihat Ketersediaan Peralatan:** Memvisualisasikan alur ketika peminjam mengakses fitur ketersediaan alat hingga sistem menampilkan daftar peralatan beserta status stoknya.
2. **LAB-UC02 – Kelola Data Peralatan:** Memvisualisasikan alur manajemen inventaris peralatan yang bercabang ke dalam tiga operasi utama, yakni tambah, ubah, dan hapus data.
3. **LAB-UC03 – Ajukan Peminjaman:** Memvisualisasikan rangkaian pengajuan peminjaman mulai dari pengisian formulir, penyimpanan data, pengecekan ketersediaan alat, hingga tahap keputusan peminjaman.
4. **LAB-UC05 – Cetak Bukti Pengajuan:** Memvisualisasikan alur pencetakan tanda bukti apabila mahasiswa memilih opsi cetak pada layar konfirmasi.
5. **LAB-UC06 – Proses Keputusan Peminjaman:** Memvisualisasikan tahapan petugas laboratorium saat meninjau dan menetapkan status pengajuan peminjaman (disetujui atau ditolak).
6. **LAB-UC11 – Catat Pengembalian Peralatan:** Memvisualisasikan prosedur pengembalian alat, inspeksi kondisi fisik barang, serta pembaruan status peminjaman dan inventaris.
7. **LAB-UC07 – Lihat Laporan Peminjaman:** Memvisualisasikan langkah kepala laboratorium dalam menentukan rentang periode dan menampilkan laporan rekapitulasi peminjaman.

Pada pemodelan kasus LAB ini, beberapa *use case* tidak digambarkan sebagai diagram terpisah: **LAB-UC04** dan **LAB-UC12** diintegrasikan langsung sebagai *action* (*include*) di dalam diagram induknya, sedangkan **LAB-UC08**, **LAB-UC09**, dan **LAB-UC10** dimodelkan sebagai cabang opsi tambah, ubah, dan hapus di dalam *Activity Kelola Data Peralatan*.

**2. Activity Diagram Sistem Informasi Akademik (SIA)**

Pada studi kasus SIA, mahasiswa merancang satu *activity diagram* terpadu yang menggambarkan alur **Input Nilai Mata Kuliah** hingga **Lihat KHS**, dengan pembagian empat jalur *swimlane*: **Dosen**, **Sistem**, **Admin Akademik**, dan **Mahasiswa**.

Alur kerja diawali saat dosen menginput nilai mata kuliah dan sistem menyimpannya. Sistem kemudian mengevaluasi kelengkapan data nilai melalui node *decision*: apabila nilai masih belum lengkap, alur diarahkan kembali agar dosen melengkapinya terlebih dahulu; sebaliknya, jika sudah lengkap, proses berlanjut ke tahap verifikasi dan pengesahan oleh Admin Akademik.

Pasca-pengesahan nilai, sistem mempersiapkan publikasi hasil studi. Alur selanjutnya dipecah menggunakan elemen *fork* menjadi dua aktivitas paralel yang berjalan serentak, yaitu memublikasikan KHS pada portal akademik dan mengirimkan notifikasi hasil studi kepada mahasiswa. Kedua cabang paralel tersebut kemudian disinkronkan kembali melalui elemen *join* sebelum diakhiri dengan aktivitas mahasiswa melihat KHS.

**3. Struktur Penyimpanan Hasil Praktikum**

Seluruh berkas luaran praktikum diorganisasikan ke dalam direktori `04_model_analisis/P06/` yang dipisahkan ke subfolder `LAB` dan `SIA`. Masing-masing diagram disimpan dalam format sumber `.drawio` beserta gambar hasil ekspor `.png`.

Penamaan seluruh berkas mengikuti standar konvensi *jobsheet* dengan mencantumkan **NIM 2406060** dan penanda versi `v01`.

### D. ANALISIS

Berdasarkan pelaksanaan praktikum Pertemuan 6, *activity diagram* berperan sebagai jembatan visual yang menerjemahkan rincian tekstual pada tabel skenario Pertemuan 5 menjadi aliran proses yang dinamis. Setiap pasangan aksi aktor dan respons sistem pada tabel skenario dipetakan menjadi elemen *action* yang saling terhubung, sehingga penyusunan diagram harus berpedoman penuh pada urutan skenario sumber tanpa menambah langkah berdasarkan asumsi pribadi.

Penerapan node *decision* beserta kondisi *guard* memegang peranan krusial dalam merepresentasikan logika percabangan alur. Setiap jalur keluar dari *decision* harus terdefinisi jelas agar tidak menimbulkan jalur buntu (*dead-end*), dan cabang yang menyatu kembali ke aliran utama wajib dihubungkan melalui *merge*. Di sisi lain, pasangan *fork* dan *join* dimanfaatkan secara khusus untuk memodelkan eksekusi aktivitas yang bersifat konkuren (paralel)—seperti penerbitan KHS dan pengiriman notifikasi secara bersamaan pada kasus SIA—di mana fungsi kedua simbol ini tidak dapat dipertukarkan.

Selain itu, penggunaan *swimlane* terbukti sangat efektif dalam memetakan batas wewenang dan tanggung jawab antar-entitas (seperti mahasiswa, petugas laboratorium, dosen, admin akademik, maupun sistem). Melalui proses audit akhir menggunakan *checklist*, dipastikan bahwa seluruh *action* terlacak ke langkah skenario asalnya, setiap *decision* dilengkapi *guard*, setiap *fork* tertutup rapi oleh *join*, serta tidak ditemukan aliran kontrol yang terputus.

### E. KESIMPULAN

Pelaksanaan Praktikum Analisis dan Desain Berorientasi Objek Pertemuan 6 memperlihatkan bahwa *activity diagram* berfungsi memodelkan alur aktivitas dinamis suatu proses yang diturunkan dari skenario *use case*. Penyusunan diagram dilakukan dengan memetakan *Skenario Normal* ke jalur utama, *Skenario Alternative* ke percabangan *decision*, serta memanfaatkan *fork* dan *join* untuk aktivitas paralel.

Melalui rangkaian latihan ini, mahasiswa mempraktikkan penerapan komponen inti *activity diagram* UML—meliputi *initial node*, *action*, *control flow*, *decision*, *merge*, *fork*, *join*, *activity final node*, dan *swimlane*—dengan tetap menjaga keterlacakan penuh terhadap tabel skenario Pertemuan 5. Luaran akhir yang dihasilkan berupa tujuh *activity diagram* untuk studi kasus LAB dan satu *activity diagram* untuk studi kasus SIA dalam format `.drawio` beserta hasil ekspor `.png`.

### F. REFERENSI

1. Object Management Group. (2017). *OMG Unified Modeling Language (OMG UML), Version 2.5.1*.
2. Institut Teknologi Garut. (2026). *Jobsheet Praktikum Analisis dan Desain Berorientasi Objek Pertemuan 4*. Institut Teknologi Garut.
3. Institut Teknologi Garut. (2026). *Jobsheet Praktikum Analisis dan Desain Berorientasi Objek Pertemuan 5*. Institut Teknologi Garut.
4. Institut Teknologi Garut. (2026). *Jobsheet Praktikum Analisis dan Desain Berorientasi Objek Pertemuan 6: Activity Diagram – Dari Skenario ke Alur Aktivitas*. Institut Teknologi Garut.
5. Fowler, M. *UML Distilled: A Brief Guide to the Standard Object Modeling Language*. Addison-Wesley.
6. draw.io. *An Introduction to UML Diagrams, Save a Diagram in Various Formats, dan Supported Export Formats*.
