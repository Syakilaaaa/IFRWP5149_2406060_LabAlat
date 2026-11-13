# LAPORAN PRAKTIKUM ADBO
## PERTEMUAN 3: USE CASE DIAGRAM DAN USE CASE DESCRIPTION

- **Nama:** Syakila Nurul Ijati
- **NIM:** 2406060
- **Mata Kuliah:** Praktikum Analisis dan Desain Berorientasi Objek (ADBO)
- **Program Studi:** S1 Teknik Informatika (Semester 5)

---

## A. TUJUAN PRAKTIKUM

Mengacu pada *Jobsheet* Praktikum Pertemuan 3, capaian pembelajaran yang diharapkan dari sesi ini adalah agar mahasiswa mampu:

1. Merumuskan batasan sistem, daftar aktor, kebutuhan fungsional, aturan bisnis, serta asumsi berdasarkan skenario kasus yang diberikan.
2. Mengidentifikasi *use case* yang berorientasi pada tujuan aktor, bukan sekadar nama tombol antarmuka, tabel basis data, atau langkah teknis.
3. Menyusun *Use Case Diagram* yang selaras dengan katalog kebutuhan serta relasi antara aktor dan layanan sistem.
4. Menyusun dokumen *Use Case Description* yang mencakup elemen pemicu, prasyarat, skenario utama, skenario alternatif atau pengecualian, hingga pascakondisi.
5. Memastikan keterlacakan (*traceability*) setiap *use case* terhadap kode kebutuhan yang melatarbelakanginya.
6. Mengevaluasi dan menyempurnakan model berdasarkan hasil tinjauan (*review*) serta mencatat setiap pembaruannya pada versi dokumen berikutnya.

---

## B. DASAR TEORI

### 1. Pengertian Use Case Diagram

*Use Case Diagram* adalah jenis diagram dalam standar UML yang berfungsi memvisualisasikan ragam layanan suatu sistem beserta interaksi antara sistem dengan entitas eksternal. Diagram ini mempermudah pemangku kepentingan dalam memahami kapabilitas fungsional yang disediakan sistem serta pihak-pihak (aktor) yang berhak mengaksesnya.

Secara konseptual, *Use Case Diagram* menyajikan gambaran tingkat tinggi mengenai keterhubungan antara aktor dan fungsionalitas sistem. Diagram ini tidak menjabarkan urutan langkah kerja secara kronologis maupun detail respons sistem, melainkan memetakan ruang lingkup fitur dan pola interaksinya.

### 2. Komponen Use Case Diagram

Penyusunan *Use Case Diagram* melibatkan beberapa elemen utama berikut:

1. **Actor**, yakni pengguna, sistem eksternal, atau entitas lain yang berinteraksi langsung dengan sistem yang dimodelkan.
2. **Use Case**, yakni unit layanan atau fungsi spesifik yang disediakan sistem guna memenuhi tujuan aktor.
3. **Association**, yakni garis penghubung yang merepresentasikan komunikasi atau interaksi antara aktor dengan *use case*.
4. **System Boundary**, yakni kotak pembatas yang mendefinisikan ruang lingkup fungsionalitas internal sistem.
5. **Collaboration**, yakni sinergi antarbeberapa elemen model untuk mewujudkan perilaku sistem yang lebih kompleks.
6. **Include**, yakni relasi ketergantungan yang menandakan bahwa suatu *use case* selalu menyertakan perilaku dari *use case* lainnya.
7. **Extend**, yakni relasi perluasan yang menyisipkan perilaku tambahan ke dalam *use case* dasar apabila syarat tertentu terpenuhi.
8. **Generalization**, yakni relasi pewarisan antara entitas induk (umum) dengan entitas turunan (khusus).

### 3. Relasi Include

Relasi `<<include>>` diterapkan apabila sebuah *use case* mewajibkan eksekusi perilaku dari *use case* lain sebagai bagian tak terpisahkan dari prosesnya. Garis panah putus-putus diarahkan dari *use case* utama menuju *use case* yang disertakan.

Sebagai contoh pada studi kasus laboratorium, fitur *Ajukan Peminjaman* wajib menjalankan pemeriksaan stok alat terlebih dahulu. Dengan demikian, hubungan antara **LAB-UC03 Ajukan Peminjaman** dan **LAB-UC04 Periksa Ketersediaan** dimodelkan menggunakan relasi `<<include>>`.

### 4. Relasi Extend

Relasi `<<extend>>` dipakai untuk memodelkan fitur opsional atau perilaku tambahan yang hanya dieksekusi saat kondisi tertentu tercapai. Tanpa adanya perilaku tambahan tersebut, *use case* dasar tetap dapat diselesaikan secara utuh.

Pada kasus laboratorium, pencetakan tanda bukti merupakan opsi tambahan apabila mahasiswa memilih tombol cetak pada layar konfirmasi. Oleh sebab itu, **LAB-UC05 Cetak Bukti Pengajuan** dihubungkan menggunakan relasi `<<extend>>` mengarah ke **LAB-UC03 Ajukan Peminjaman**.

### 5. Use Case Description

*Use Case Description* merupakan spesifikasi tekstual yang menguraikan secara rinci mekanisme berjalannya suatu fitur melalui dialog interaksi antara aktor dan sistem. Dokumen ini melengkapi aspek detail alur proses yang tidak dapat direpresentasikan secara visual di dalam diagram.

Struktur informasi di dalam *Use Case Description* meliputi:

1. **ID dan Nama**, kode identitas unik beserta nama *use case* yang sinkron dengan diagram.
2. **Sumber Kebutuhan**, referensi kode kebutuhan yang mendasari pembuatan *use case*.
3. **Tujuan**, sasaran akhir yang hendak dicapai aktor saat menjalankan layanan.
4. **Aktor Utama**, entitas yang menginisiasi interaksi untuk mencapai tujuan tersebut.
5. **Aktor Pendukung**, entitas eksternal lain yang turut terlibat dalam proses (bila ada).
6. **Pemicu**, peristiwa awal yang mengawali berjalannya skenario *use case*.
7. **Prasyarat**, keadaan awal yang wajib dipenuhi sebelum *use case* dapat dieksekusi.
8. **Alur Utama**, urutan langkah interaksi normal antara aktor dan sistem hingga tujuan tercapai.
9. **Alur Alternatif atau Pengecualian**, cabang skenario lain maupun penanganan kendala/kegagalan proses.
10. **Pascakondisi**, status atau keadaan akhir sistem setelah proses berakhir sukses maupun gagal.
11. **Aturan Bisnis dan Asumsi**, batasan kebijakan serta asumsi yang mengatur jalannya proses.

---

## C. HASIL PRAKTIKUM

### 1. Studi Kasus Sistem Informasi Peminjaman dan Pengembalian Peralatan Laboratorium Kampus

Latihan pertama mengangkat studi kasus *Sistem Informasi Peminjaman dan Pengembalian Peralatan Laboratorium Kampus*. Sistem ini mencakup alur pengelolaan data alat, pengajuan peminjaman, pengecekan ketersediaan stok, pengambilan keputusan peminjaman, hingga pelaporan peminjaman.

Mengacu pada skenario kasus, dirumuskan enam kebutuhan fungsional utama sebagai landasan pemodelan:

| ID Kebutuhan | Kebutuhan Sistem |
| :--- | :--- |
| **LAB-R01** | Mahasiswa dapat mengecek ketersediaan peralatan laboratorium. |
| **LAB-R02** | Petugas dapat mengelola data master peralatan. |
| **LAB-R03** | Mahasiswa dapat mengajukan peminjaman dan sistem memverifikasi ketersediaan alat sebelum data disimpan. |
| **LAB-R04** | Mahasiswa dapat mencetak tanda bukti pada halaman konfirmasi pengajuan apabila menginginkannya. |
| **LAB-R05** | Petugas dapat memberikan keputusan persetujuan atau penolakan atas pengajuan peminjaman. |
| **LAB-R06** | Kepala laboratorium dapat mengakses laporan rekapitulasi peminjaman. |

Dari daftar kebutuhan tersebut, diidentifikasi tiga aktor yang terlibat langsung dengan sistem:

| Aktor | Tujuan terhadap Sistem |
| :--- | :--- |
| **Mahasiswa** | Mengecek ketersediaan alat, mengajukan peminjaman, serta mencetak bukti pengajuan. |
| **Petugas Laboratorium** | Mengelola inventaris peralatan dan memproses persetujuan/penolakan peminjaman. |
| **Kepala Laboratorium** | Memantau dan melihat laporan peminjaman peralatan. |

Kebutuhan di atas kemudian dipetakan ke dalam tujuh *use case* berikut:

| ID Use Case | Nama Use Case |
| :--- | :--- |
| **LAB-UC01** | Lihat Ketersediaan Peralatan |
| **LAB-UC02** | Kelola Data Peralatan |
| **LAB-UC03** | Ajukan Peminjaman |
| **LAB-UC04** | Periksa Ketersediaan |
| **LAB-UC05** | Cetak Bukti Pengajuan |
| **LAB-UC06** | Proses Keputusan Peminjaman |
| **LAB-UC07** | Lihat Laporan Peminjaman |

### 2. Penentuan Relasi Include dan Extend pada Kasus LAB

Untuk memperjelas ketergantungan fungsional antar-*use case*, diterapkan dua jenis relasi utama:

- **Relasi Include:** **LAB-UC03 Ajukan Peminjaman** terhubung melalui relasi `<<include>>` ke **LAB-UC04 Periksa Ketersediaan**. Hal ini dikarenakan validasi stok ketersediaan peralatan merupakan tahapan wajib sebelum sistem menyimpan transaksi pengajuan.
- **Relasi Extend:** **LAB-UC05 Cetak Bukti Pengajuan** terhubung melalui relasi `<<extend>>` ke **LAB-UC03 Ajukan Peminjaman**. Pencetakan bukti bersifat opsional—hanya berjalan jika mahasiswa memilih fitur cetak di layar konfirmasi—sehingga pengajuan tetap dinyatakan sah meskipun bukti tidak dicetak.

Spesifikasi elemen pada relasi *extend* tersebut dirinci sebagai berikut:
- **Use Case Dasar:** LAB-UC03 Ajukan Peminjaman.
- **Use Case Tambahan:** LAB-UC05 Cetak Bukti Pengajuan.
- **Extension Point:** Bukti pengajuan tersedia.
- **Kondisi:** Mahasiswa memilih opsi cetak.

### 3. Penyusunan Use Case Description LAB-UC03

Salah satu dokumentasi deskripsi yang disusun berdasarkan *jobsheet* adalah **LAB-UC03 Ajukan Peminjaman**, yang berorientasi pada penyimpanan permohonan peminjaman alat ke dalam sistem.

Ringkasan spesifikasi *use case* tersebut tersaji pada tabel berikut:

| Elemen | Keterangan |
| :--- | :--- |
| **ID dan Nama** | LAB-UC03 Ajukan Peminjaman |
| **Tujuan** | Menghasilkan data pengajuan peminjaman peralatan yang tersimpan di sistem. |
| **Aktor Utama** | Mahasiswa |
| **Sumber Kebutuhan** | LAB-R03 dan LAB-R04 |
| **Pemicu** | Mahasiswa mengakses menu pengajuan peminjaman. |
| **Prasyarat** | Mahasiswa sudah login (terautentikasi) dan data peralatan tersedia di sistem. |
| **Pascakondisi Berhasil** | Data pengajuan tercatat dengan nomor registrasi dan status *Menunggu Keputusan*. |
| **Pascakondisi Gagal** | Tidak ada data pengajuan baru yang tersimpan di dalam sistem. |
| **Include** | LAB-UC04 Periksa Ketersediaan. |
| **Extend** | LAB-UC05 Cetak Bukti Pengajuan. |

Skenario utama diawali saat mahasiswa membuka formulir pengajuan, lalu memilih jenis peralatan, kuantitas, durasi peminjaman, dan keperluan peminjaman. Begitu formulir dikirim, sistem memvalidasi kelengkapan isian dan mengeksekusi pemeriksaan stok alat. Jika stok mencukupi, sistem merekam pengajuan beserta nomor registrasinya, lalu menampilkan halaman konfirmasi berisi nomor dan status pengajuan.

Jika mahasiswa menekan tombol cetak bukti, sistem menjalankan skenario perluasan untuk mencetak tanda bukti. Sebaliknya, jika opsi cetak dilewati, transaksi pengajuan tetap dianggap tuntas selama seluruh tahapan validasi berhasil dilalui.

### 4. Tugas Sistem Informasi Akademik (SIA)

Pada latihan kedua, studi kasus beralih ke *Sistem Informasi Akademik (SIA)* dengan fokus pada alur pengajuan Kartu Rencana Studi (KRS). Mahasiswa dapat menentukan mata kuliah dan mengajukan KRS secara daring. Sistem kemudian memverifikasi kelengkapan data, pemenuhan mata kuliah prasyarat, serta potensi benturan jadwal kuliah.

Jika seluruh validasi terpenuhi, pengajuan disimpan dengan status *Menunggu Persetujuan Dosen Wali*. Pada layar konfirmasi, tersedia opsi bagi mahasiswa untuk mengunduh bukti pengajuan KRS. Selanjutnya, dosen wali meninjau pengajuan tersebut untuk menyetujui atau menolaknya disertai catatan keputusan.

Daftar kebutuhan fungsional pada tugas SIA dirumuskan sebagai berikut:

| ID Kebutuhan | Kebutuhan Sistem |
| :--- | :--- |
| **SIA-R01** | Mahasiswa dapat mengecek jadwal perkuliahan. |
| **SIA-R02** | Admin akademik dapat mengelola data jadwal perkuliahan. |
| **SIA-R03** | Mahasiswa dapat melakukan pengajuan KRS. |
| **SIA-R04** | Sistem menjalankan validasi KRS sebagai bagian integral dari proses pengajuan. |
| **SIA-R05** | Mahasiswa dapat mengunduh bukti pengajuan apabila memilihnya di halaman konfirmasi. |
| **SIA-R06** | Dosen wali dapat memproses persetujuan atau penolakan pengajuan KRS. |

Dalam pemodelan ini, kode **SIA-R01** dan **SIA-R02** dipertahankan identitasnya dari Pertemuan 2, sedangkan **SIA-R03** hingga **SIA-R06** ditambahkan untuk mengakomodasi fungsionalitas pengajuan KRS.

### 5. Penyusunan Use Case Description SIA

Mengacu pada skenario kasus SIA, disusun empat dokumen deskripsi *use case* utama, yakni:

1. **Ajukan KRS**, menguraikan langkah mahasiswa dalam memilih mata kuliah hingga mengirimkan formulir pengajuan KRS.
2. **Validasi KRS**, menguraikan mekanisme sistem dalam memeriksa kelengkapan isian, pemenuhan syarat mata kuliah, serta konflik jadwal.
3. **Unduh Bukti Pengajuan KRS**, menguraikan alur pengunduhan berkas bukti ketika mahasiswa memilih opsi unduh di layar konfirmasi.
4. **Proses Keputusan KRS**, menguraikan tindakan dosen wali saat memberikan keputusan persetujuan atau penolakan KRS beserta catatannya.

Karena proses validasi wajib dijalankan setiap kali KRS diajukan, relasi antara *Ajukan KRS* dan *Validasi KRS* dimodelkan dengan `<<include>>`. Di sisi lain, *Unduh Bukti Pengajuan KRS* bersifat opsional dan tidak memengaruhi sahnya penyimpanan KRS, sehingga dihubungkan memakai relasi `<<extend>>`.

### 6. Pengujian Konsistensi Model SIA

Usai menyusun diagram dan deskripsi *use case*, dilakukan uji konsistensi terhadap tiga skenario kondisi yang ditetapkan dalam *jobsheet*:

| No. | Kondisi Pengujian | Hasil yang Diharapkan |
| :---: | :--- | :--- |
| **1** | Proses validasi berhasil dan mahasiswa tidak mengunduh bukti. | Data pengajuan KRS tetap terekam dengan status *Menunggu Persetujuan Dosen Wali*. |
| **2** | Proses validasi gagal. | Data pengajuan KRS ditolak dan tidak tersimpan ke dalam sistem. |
| **3** | Proses validasi berhasil dan mahasiswa memilih mengunduh bukti. | Data pengajuan tersimpan dan berkas bukti pengajuan berhasil diunduh oleh mahasiswa. |

Ketiga skenario uji tersebut membuktikan bahwa penerapan relasi *include* dan *extend* telah selaras dengan logika perilaku sistem pada deskripsi *use case*.

### 7. Pemeriksaan dan Dokumentasi Artefak

Tahap akhir mencakup verifikasi keselarasan antara tabel kebutuhan, katalog *use case*, diagram, serta dokumen deskripsi. Pemeriksaan ini turut meninjau ketepatan arah panah *include* dan *extend*, posisi *extension point*, syarat perluasan, hingga rumusan pascakondisi berhasil dan gagal.

Berkas sumber diagram disimpan dalam ekstensi `.drawio`, sementara hasil ekspor gambarnya disimpan sebagai `.png` mengikuti format penamaan standar `P03_<NIM>_<KASUS>_<ARTEFAK>_v<NN>` guna memisahkan artefak LAB dan SIA. Apabila dilakukan revisi pasca-tinjauan, dokumen disimpan dengan nomor versi baru tanpa menimpa berkas versi sebelumnya.

---

## D. ANALISIS

Berdasarkan rangkaian kegiatan praktikum yang telah dijalankan, *Use Case Diagram* terbukti efektif dalam memetakan batasan layanan sistem serta interaksi setiap aktor. Pada kasus laboratorium, pemisahan peran antara *Mahasiswa*, *Petugas Laboratorium*, dan *Kepala Laboratorium* tergambar secara jelas karena setiap aktor hanya dihubungkan dengan fitur yang relevan dengan kebutuhan fungsionalnya.

Penerapan relasi *include* dan *extend* menjadi aspek krusial dalam memperjelas alur logika antarfitur. Relasi *include* pada pengajuan peminjaman menegaskan bahwa pengecekan ketersediaan stok merupakan prasyarat mutlak sebelum data disimpan. Sebaliknya, relasi *extend* pada pencetakan bukti menandakan fitur opsional yang bergantung pada pilihan pengguna. Perbedaan mendasar ini memperlihatkan bahwa *include* merepresentasikan sub-proses wajib, sedangkan *extend* merepresentasikan perilaku tambahan bersyarat.

Pada studi kasus SIA, pengujian konsistensi terhadap skenario validasi sukses, validasi gagal, serta pengunduhan bukti memastikan bahwa diagram dan *Use Case Description* saling sinkron. Selain itu, status awal pengajuan KRS yang disimpan sebagai *Menunggu Persetujuan Dosen Wali* menjaga aturan bisnis bahwa pengajuan mahasiswa belum otomatis disahkan tanpa persetujuan wali akademik.

Secara keseluruhan, praktikum ini menegaskan sifat saling melengkapi antara *Use Case Diagram* dan *Use Case Description*. Diagram menyajikan peta interaksi secara visual, sementara deskripsi menjabarkan rincian langkah, respons sistem, skenario pengecualian, serta kondisi akhir. Konsistensi penamaan, kode ID, dan keterlacakan kebutuhan di antara keduanya menjadi kunci utama dalam menghasilkan model analisis yang akurat dan mudah dipelihara.

---

## E. KESIMPULAN

Pelaksanaan Praktikum Analisis dan Desain Berorientasi Objek Pertemuan 3 memperlihatkan bahwa *Use Case Diagram* berfungsi memodelkan ruang lingkup fungsionalitas sistem serta keterlibatan aktor di dalamnya. Penyusunan setiap elemen diagram wajib berlandaskan tujuan aktor dan spesifikasi kebutuhan yang tertuang dalam skenario.

Melalui praktikum ini, mahasiswa memahami perbedaan penerapan relasi `<<include>>` untuk sub-fungsi yang wajib dijalankan dalam proses utama dan relasi `<<extend>>` untuk perilaku tambahan yang bersifat kondisional. Pemahaman tersebut dilengkapi dengan penyusunan *Use Case Description* guna mendokumentasikan pemicu, prasyarat, skenario utama, skenario alternatif, serta pascakondisi secara terperinci.

Dengan demikian, pemodelan berorientasi objek tidak hanya bertumpu pada visualisasi diagram, tetapi juga menuntut dokumentasi tekstual yang konsisten dan terlacak agar rancangan sistem mudah dipahami serta siap dilanjutkan ke tahap pengembangan berikutnya.

---

## F. REFERENSI

1. Institut Teknologi Garut. (2026). *Jobsheet Praktikum Analisis dan Desain Berorientasi Objek (ADBO) Pertemuan 3: Use Case Diagram dan Use Case Description*.
2. Object Management Group. (2017). *OMG Unified Modeling Language (UML), Version 2.5.1*.
3. Dokumentasi draw.io. *An Introduction to UML Diagrams, Save a Diagram in Various Formats, dan Supported Export Formats*.
4. Repository Praktikum ADBO: https://github.com/syakila2406060/IFRWP5149_2406060_LabAlat
