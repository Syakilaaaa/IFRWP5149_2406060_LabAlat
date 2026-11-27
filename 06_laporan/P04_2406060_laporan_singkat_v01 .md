# LAPORAN PRAKTIKUM ADBO
## PERTEMUAN 4: USE CASE DIAGRAM LANJUTAN - GENERALIZATION DAN COLLABORATION

- **Nama:** Syakila Nurul Ijati
- **NIM:** 2406060
- **Mata Kuliah:** Praktikum Analisis dan Desain Berorientasi Objek (ADBO)
- **Program Studi:** S1 Teknik Informatika (Semester 5)

---

## A. TUJUAN PRAKTIKUM

Mengacu pada *Jobsheet* Praktikum Pertemuan 4, target capaian pembelajaran yang harus dicapai mahasiswa meliputi kemampuan untuk:

1. Mengklasifikasikan aktor umum (*general*) dan aktor khusus (*specialized*) sesuai skenario, lalu merangkai relasi *generalization* aktor dengan orientasi panah yang tepat.
2. Membangun *generalization* pada *use case* yang terdiri atas satu *use case* induk dan beberapa *use case* turunan beserta penjelasan perilaku yang diwariskan.
3. Memanfaatkan elemen *collaboration* guna memvisualisasikan realisasi suatu *use case* dan mengaitkannya memakai relasi *realization*.
4. Menyusun *Use Case Diagram* kumulatif dengan tetap mempertahankan komponen dari Pertemuan 3 sembari mengintegrasikan fitur-fitur baru Pertemuan 4.
5. Merumuskan dokumentasi *Use Case Description* baru yang memuat pemicu, prasyarat, skenario utama, skenario alternatif, hingga pascakondisi.
6. Membuktikan keterlacakan (*traceability*) setiap komponen baru terhadap spesifikasi kebutuhan serta melakukan evaluasi dan penyempurnaan model pasca-tinjauan (*review*).

---

## B. DASAR TEORI

### 1. Pengertian Use Case Diagram Lanjutan

*Use Case Diagram* adalah representasi visual dalam UML untuk memetakan layanan sistem beserta pola interaksinya dengan pihak eksternal. Pada Pertemuan 4, cakupan pemodelan diperluas melalui penerapan konsep *generalization* dan *collaboration*.

Sesi ini merupakan kelanjutan langsung dari rancangan pada Pertemuan 3. Oleh sebab itu, diagram terdahulu tidak dirombak dari nol, melainkan dipertahankan keutuhannya dan diperkaya dengan elemen baru sesuai kebutuhan skenario. Pendekatan kumulatif ini bertujuan melengkapi cakupan fungsional sistem tanpa mengubah makna kebutuhan yang telah disepakati sebelumnya.

### 2. Generalization Aktor

*Generalization* aktor merupakan relasi pewarisan antara aktor umum dengan aktor khusus. Aktor turunan secara otomatis mewarisi seluruh hak akses atau asosiasi yang dimiliki aktor induknya, sehingga garis interaksi yang identik tidak perlu digambar berulang kali.

Sebagai ilustrasi, pada sistem peminjaman peralatan laboratorium didefinisikan aktor **Peminjam** sebagai peran umum, sementara **Mahasiswa** dan **Dosen** berperan sebagai aktor khusus di bawahnya. Keduanya mewarisi kapabilitas untuk melihat ketersediaan alat dan mengajukan peminjaman.

Notasi panah *generalization* digambarkan dengan garis solid berujung segitiga kosong yang mengarah ke aktor umum. Apabila aktor khusus mempunyai layanan eksklusif yang tidak dimiliki aktor lainnya, garis asosiasinya tetap ditarik langsung dari aktor khusus tersebut.

### 3. Generalization Use Case

*Generalization* pada *use case* menghubungkan suatu *use case* umum dengan beberapa *use case* khusus. *Use case* turunan mewarisi tujuan serta perilaku dasar dari *use case* induknya, lalu menambahkan spesifikasi perilaku unik yang membedakannya.

Contoh penerapannya adalah **Kelola Data Peralatan** sebagai *use case* umum yang diturunkan menjadi tiga variasi khusus: **Tambah Data Peralatan**, **Ubah Data Peralatan**, dan **Hapus Data Peralatan**.

Ketiganya berbagi sasaran umum untuk mengelola data inventaris, namun masing-masing menghasilkan luaran spesifik: *Tambah* menyimpan entri baru, *Ubah* memodifikasi data yang ada, dan *Hapus* menghilangkan rekaman data sesuai ketentuan. Arah panah *generalization* ditarik dari masing-masing *use case* khusus menuju *use case* umum menggunakan garis utuh dengan kepala segitiga kosong.

### 4. Collaboration

*Collaboration* merupakan elemen UML yang merepresentasikan sekumpulan komponen dan peran yang bersinergi untuk mewujudkan suatu fungsionalitas sistem. Elemen ini menggambarkan kolaborasi internal antarbagian sistem dalam merealisasikan layanan tertentu.

Secara visual, *collaboration* digambarkan sebagai bentuk elips bergaris putus-putus dengan label nama yang wajib identik dengan nama *use case* yang direalisasikannya. *Collaboration* bukanlah *use case* baru dan tidak terhubung langsung dengan aktor; dalam praktikum ini, ia berfungsi merealisasikan *use case* inti dari skenario.

### 5. Relasi Realization

*Realization* adalah relasi yang menandakan bahwa suatu elemen mewujudkan atau mengimplementasikan spesifikasi dari elemen lainnya. Pada konteks praktikum ini, *collaboration* bertindak sebagai perwujudan nyata dari sebuah *use case*.

Notasi *realization* berupa garis putus-putus dengan ujung segitiga kosong yang mengarah dari *collaboration* menuju *use case* yang direalisasikan. Sebagai contoh, *collaboration* **Ajukan Peminjaman** merealisasikan *use case* **Ajukan Peminjaman**—keduanya bernama sama persis, namun memiliki peran semantik yang berbeda dalam model.

### 6. Perbedaan Include, Extend, Generalization, dan Realization

Keempat jenis relasi dalam *Use Case Diagram* memiliki makna pemodelan yang berbeda:

1. **Include**, menandakan sub-perilaku dari suatu *use case* yang wajib disertakan setiap kali *use case* utama dieksekusi.
2. **Extend**, menandakan perilaku opsional yang hanya dijalankan apabila kondisi perluasan tertentu terpenuhi.
3. **Generalization**, menandakan hubungan pewarisan sifat dan perilaku dari elemen induk (umum) ke elemen turunan (khusus).
4. **Realization**, menandakan hubungan perwujudan antara elemen pengimplementasi (*collaboration*) dengan elemen fungsional yang direalisasikannya (*use case*).

Pemahaman yang tepat atas keempat relasi ini mencegah kekeliruan arah panah maupun tertukarnya makna semantik antar-elemen diagram.

### 7. Use Case Description Lanjutan

*Use Case Description* menyajikan uraian tekstual yang merinci mekanisme jalannya layanan sistem. Pada Pertemuan 4, struktur dokumen ini mempertahankan kerangka Pertemuan 3 dengan penambahan dua atribut baru, yakni **Generalization** dan **Collaboration**.

Dengan demikian, elemen lengkap di dalamnya mencakup: ID dan nama, sumber kebutuhan, tujuan, aktor utama, aktor pendukung, pemicu, prasyarat, alur utama, alur alternatif/pengecualian, pascakondisi berhasil, pascakondisi gagal, aturan bisnis/asumsi, *generalization*, serta *collaboration*.

---

## C. HASIL PRAKTIKUM

### 1. Studi Kasus Sistem Informasi Peminjaman dan Pengembalian Peralatan Laboratorium Kampus

Latihan pertama mengembangkan model *Sistem Informasi Peminjaman dan Pengembalian Peralatan Laboratorium Kampus* yang telah dirintis pada Pertemuan 3.

Pada sesi ini ditambahkan fitur terkait akses peminjaman bagi dosen, pemecahan manajemen data alat, serta pencatatan pengembalian alat. Konsep *generalization* turut diterapkan untuk menyederhanakan hierarki aktor dan *use case*.

Daftar kebutuhan baru yang ditambahkan pada studi kasus LAB meliputi:

| ID Kebutuhan | Kebutuhan Sistem |
| :--- | :--- |
| **LAB-R07** | Mahasiswa dan Dosen sebagai Peminjam dapat mengecek ketersediaan peralatan serta mengajukan peminjaman. |
| **LAB-R08** | Petugas laboratorium dapat mengelola data peralatan dalam bentuk tambah, ubah, dan hapus data. |
| **LAB-R09** | Petugas laboratorium dapat mencatat pengembalian peralatan untuk transaksi yang berstatus *Dipinjam*. |
| **LAB-R10** | Sistem memverifikasi dan merekam kondisi fisik peralatan sebagai bagian dari proses pencatatan pengembalian. |
| **LAB-R11** | Model menampilkan *collaboration* yang merealisasikan *Ajukan Peminjaman* dan *Catat Pengembalian Peralatan*. |

Sementara itu, spesifikasi **LAB-R01** hingga **LAB-R06** dari Pertemuan 3 tetap dipertahankan tanpa perubahan.

### 2. Generalization Aktor pada Kasus LAB

Diagram kumulatif studi kasus laboratorium melibatkan lima aktor dengan rincian peran berikut:

| Aktor | Kedudukan | Tujuan terhadap Sistem |
| :--- | :--- | :--- |
| **Peminjam** | Aktor umum | Merepresentasikan peran induk bagi seluruh pengguna yang meminjam peralatan. |
| **Mahasiswa** | Aktor khusus | Mengecek ketersediaan alat, mengajukan peminjaman, serta mencetak bukti pengajuan. |
| **Dosen** | Aktor khusus | Mengecek ketersediaan alat dan mengajukan peminjaman. |
| **Petugas Laboratorium** | Aktor tetap | Mengelola inventaris peralatan, memproses keputusan peminjaman, dan mencatat pengembalian. |
| **Kepala Laboratorium** | Aktor tetap | Mengakses laporan rekapitulasi peminjaman. |

Peran **Peminjam** dijadikan aktor induk bagi **Mahasiswa** dan **Dosen** karena keduanya berbagi dua layanan yang sama, yaitu melihat ketersediaan alat dan mengajukan peminjaman. Berkat relasi *generalization*, asosiasi kedua layanan tersebut cukup ditarik satu kali dari aktor *Peminjam*, sedangkan fitur **Cetak Bukti Pengajuan** tetap terhubung khusus ke aktor **Mahasiswa**.

### 3. Generalization Use Case pada Kasus LAB

Pada ranah manajemen inventaris, layanan pengelolaan dibagi menjadi satu *use case* induk dan tiga *use case* turunan:

| ID Use Case | Nama Use Case | Kedudukan |
| :--- | :--- | :--- |
| **LAB-UC02** | Kelola Data Peralatan | *Use case* umum |
| **LAB-UC08** | Tambah Data Peralatan | *Use case* khusus |
| **LAB-UC09** | Ubah Data Peralatan | *Use case* khusus |
| **LAB-UC10** | Hapus Data Peralatan | *Use case* khusus |

Ketiga *use case* turunan tersebut menjabarkan aksi spesifik dari *Kelola Data Peralatan*: menambah rekaman baru, memperbarui data eksisting, serta menghapus data alat sesuai aturan yang berlaku. Panah *generalization* diarahkan dari **LAB-UC08**, **LAB-UC09**, dan **LAB-UC10** menuju **LAB-UC02**.

### 4. Penambahan Use Case Pengembalian Peralatan

Selain manajemen inventaris, ditambahkan pula dua *use case* baru untuk mengakomodasi alur pengembalian alat:

| ID Use Case | Nama Use Case | Peran dalam Model |
| :--- | :--- | :--- |
| **LAB-UC11** | Catat Pengembalian Peralatan | Layanan utama yang dijalankan petugas laboratorium. |
| **LAB-UC12** | Periksa Kondisi Peralatan | Sub-proses wajib yang disertakan saat pencatatan pengembalian. |

**LAB-UC11** berfungsi merekam transaksi pengembalian alat yang berstatus dipinjam, yang di dalamnya selalu mengeksekusi **LAB-UC12** guna memeriksa dan mencatat kondisi peralatan. Oleh sebab itu, keduanya dihubungkan melalui relasi `<<include>>`.

### 5. Collaboration dan Realization pada Kasus LAB

Untuk merealisasikan dua fungsionalitas transaksi inti pada kasus laboratorium, digunakan dua elemen *collaboration*:

| ID Collaboration | Nama Collaboration | Use Case yang Direalisasikan |
| :--- | :--- | :--- |
| **LAB-CO01** | Ajukan Peminjaman | LAB-UC03 Ajukan Peminjaman |
| **LAB-CO02** | Catat Pengembalian Peralatan | LAB-UC11 Catat Pengembalian Peralatan |

Kedua *collaboration* divisualisasikan menggunakan elips bergaris putus-putus dan ditautkan melalui panah *realization* yang mengarah masing-masing ke **LAB-UC03** dan **LAB-UC11**.

### 6. Penyusunan Use Case Description LAB-UC11

Dokumentasi *Use Case Description* disusun secara rinci untuk fitur baru **LAB-UC11 Catat Pengembalian Peralatan** dengan rincian spesifikasi berikut:

| Elemen | Keterangan |
| :--- | :--- |
| **ID dan Nama** | LAB-UC11 Catat Pengembalian Peralatan |
| **Sumber Kebutuhan** | LAB-R09 dan LAB-R10 |
| **Tujuan** | Merekam transaksi pengembalian serta memperbarui status peminjaman dan kondisi peralatan. |
| **Aktor Utama** | Petugas Laboratorium |
| **Pemicu** | Petugas mengakses menu pencatatan pengembalian dan memilih transaksi peminjaman yang akan diselesaikan. |
| **Prasyarat** | Petugas sudah terautentikasi dan transaksi peminjaman yang dipilih berstatus *Dipinjam*. |
| **Pascakondisi Berhasil** | Data pengembalian terekam beserta tanggal kembali dan kondisi alat; status peminjaman berubah menjadi *Selesai*. |
| **Pascakondisi Gagal** | Tidak ada data pengembalian yang tersimpan dan status peminjaman tetap tidak berubah. |
| **Include** | LAB-UC12 Periksa Kondisi Peralatan |
| **Collaboration** | LAB-CO02 Catat Pengembalian Peralatan |

Pada skenario utama, petugas memilih transaksi peminjaman yang akan dikembalikan, lalu sistem menampilkan rincian peminjaman beserta statusnya. Petugas memverifikasi jenis dan jumlah alat yang dikembalikan. Sistem kemudian mengecek keabsahan status *Dipinjam* dan mengeksekusi pemeriksaan kondisi fisik alat. Jika semua validasi lolos, sistem menyimpan tanggal pengembalian dan kondisi alat, mengubah status peminjaman menjadi *Selesai*, serta menampilkan ringkasan konfirmasi.

Pada skenario alternatif, sistem menolak pencatatan apabila status transaksi bukan *Dipinjam*. Jika ditemukan peralatan berstatus *Rusak Ringan* atau *Rusak Berat*, pengembalian tetap diproses dengan mencantumkan catatan kerusakan pada data inventaris. Apabila kuantitas alat yang dikembalikan tidak cocok, sistem meminta petugas mengoreksi input sebelum data disimpan.

### 7. Tugas Sistem Informasi Akademik (SIA), Layanan Hasil Studi

Latihan kedua menerapkan konsep serupa pada studi kasus *Sistem Informasi Akademik (SIA)* dengan topik layanan hasil studi—melanjutkan cakupan jadwal kuliah (Pertemuan 2) dan pengajuan KRS (Pertemuan 3).

Dalam skenario ini, **Mahasiswa** dan **Dosen** tergabung sebagai **Civitas Akademika** yang berhak mengakses kalender akademik. Setelah masa perkuliahan usai, **Dosen** menginput nilai mata kuliah yang diampunya, sedangkan **Mahasiswa** dapat mengakses Kartu Hasil Studi (KHS) untuk semester yang nilainya sudah dipublikasikan. Sementara itu, **Admin Akademik** bertugas mengelola data master mahasiswa.

Daftar kebutuhan baru untuk tugas SIA adalah:

| ID Kebutuhan | Kebutuhan Sistem |
| :--- | :--- |
| **SIA-R07** | Mahasiswa dan Dosen sebagai Civitas Akademika dapat mengakses kalender akademik. |
| **SIA-R08** | Dosen dapat menginput nilai untuk mata kuliah yang diampunya. |
| **SIA-R09** | Mahasiswa dapat melihat KHS pada semester yang nilainya telah resmi dipublikasikan. |
| **SIA-R10** | Admin Akademik dapat mengelola data master mahasiswa. |
| **SIA-R11** | Pengelolaan data mahasiswa mencakup tiga bentuk khusus: tambah, ubah, dan hapus data mahasiswa. |
| **SIA-R12** | Model menampilkan *collaboration* yang merealisasikan *Input Nilai Mata Kuliah* dan *Lihat KHS*. |

Dengan mempertahankan **SIA-R01** sampai **SIA-R06**, diagram SIA Pertemuan 4 berfungsi sebagai model kumulatif yang menyatukan layanan jadwal kuliah, pengajuan KRS, dan layanan hasil studi.

### 8. Generalization Aktor pada Tugas SIA

Pada model SIA, peran **Civitas Akademika** ditetapkan sebagai aktor umum yang membawahi **Mahasiswa** dan **Dosen**:

| Aktor | Kedudukan | Tujuan terhadap Sistem |
| :--- | :--- | :--- |
| **Civitas Akademika** | Aktor umum | Mengakses kalender akademik. |
| **Mahasiswa** | Aktor khusus | Mengakses kalender akademik (warisan) serta melihat KHS. |
| **Dosen** | Aktor khusus | Mengakses kalender akademik (warisan) serta menginput nilai mata kuliah yang diampu. |
| **Admin Akademik** | Aktor tetap | Mengelola data mahasiswa. |
| **Dosen Wali** | Aktor tetap | Memproses keputusan pengajuan KRS (dari pertemuan sebelumnya). |

Karena hak akses kalender akademik diwariskan dari **Civitas Akademika**, garis asosiasinya cukup ditarik satu kali dari aktor umum tersebut, sementara fitur **Lihat KHS** dan **Input Nilai Mata Kuliah** tetap melekat langsung pada aktor khusus masing-masing.

### 9. Generalization Use Case pada Tugas SIA

Manajemen data mahasiswa dimodelkan menggunakan satu *use case* umum dan tiga *use case* khusus:

| ID Use Case | Nama Use Case | Kedudukan |
| :--- | :--- | :--- |
| **SIA-UC10** | Kelola Data Mahasiswa | *Use case* umum |
| **SIA-UC11** | Tambah Data Mahasiswa | *Use case* khusus |
| **SIA-UC12** | Ubah Data Mahasiswa | *Use case* khusus |
| **SIA-UC13** | Hapus Data Mahasiswa | *Use case* khusus |

Masing-masing *use case* turunan menjalankan fungsi spesifik—menambah entri mahasiswa baru, memodifikasi biodata, atau menghapus data mahasiswa yang memenuhi syarat—dengan arah panah *generalization* menuju **SIA-UC10**.

### 10. Collaboration dan Realization pada Tugas SIA

Dua elemen *collaboration* diterapkan untuk merealisasikan fitur utama layanan hasil studi:

| ID Collaboration | Nama Collaboration | Use Case yang Direalisasikan |
| :--- | :--- | :--- |
| **SIA-CO01** | Input Nilai Mata Kuliah | SIA-UC08 Input Nilai Mata Kuliah |
| **SIA-CO02** | Lihat KHS | SIA-UC09 Lihat KHS |

Keduanya ditautkan menggunakan panah *realization* menuju *use case* masing-masing dengan penamaan yang identik.

### 11. Use Case Description pada Tugas SIA

Dokumentasi *Use Case Description* disusun untuk dua fitur layanan hasil studi berikut:

- **Input Nilai Mata Kuliah (SIA-UC08):** Menguraikan prosedur dosen dalam menginput nilai pasca-perkuliahan dengan syarat dosen telah terautentikasi dan tercatat sebagai pengampu mata kuliah terkait. Input nilai di luar rentang valid akan ditolak sistem, sedangkan nilai valid akan disimpan dengan status awal *belum dipublikasikan* hingga disahkan. Fitur ini direalisasikan oleh **SIA-CO01 Input Nilai Mata Kuliah**.
- **Lihat KHS (SIA-UC09):** Menguraikan mekanisme mahasiswa dalam mengakses KHS per semester. Sistem menyaring data sehingga hanya nilai yang sudah berstatus *dipublikasikan* yang ditampilkan kepada mahasiswa. Fitur ini direalisasikan oleh **SIA-CO02 Lihat KHS**.

### 12. Pengujian Konsistensi Model SIA

Verifikasi model dilakukan dengan menguji tiga skenario konsistensi sesuai ketentuan *jobsheet*:

| No. | Kondisi Pengujian | Hasil yang Diharapkan |
| :---: | :--- | :--- |
| **1** | Mahasiswa mengakses kalender akademik tanpa garis asosiasi langsung dari ikon Mahasiswa. | Tetap valid secara pemodelan karena Mahasiswa mewarisi fungsi tersebut dari aktor induk Civitas Akademika. |
| **2** | Dosen yang bukan pengampu mata kuliah mencoba menginput nilai. | Sistem menolak akses karena pengguna tidak memenuhi prasyarat sebagai pengampu sah mata kuliah terkait. |
| **3** | Admin Akademik berupaya menghapus data mahasiswa yang masih memiliki riwayat akademik aktif. | Proses penghapusan dibatalkan oleh sistem sesuai aturan pembatasan penghapusan data. |

Pengujian ini memastikan keselarasan antara struktur *generalization*, otorisasi aktor, aturan bisnis, dan spesifikasi *Use Case Description*.

### 13. Pemeriksaan dan Dokumentasi Artefak

Pada tahap akhir, dilakukan peninjauan menyeluruh atas diagram kumulatif LAB dan SIA untuk menjamin konsistensi antara daftar kebutuhan, katalog *use case*, arah panah *generalization* dan *realization*, penamaan *collaboration*, serta deskripsi *use case*.

Seluruh diagram disimpan dalam format sumber `.drawio` dan hasil ekspor `.png` mengikuti aturan penamaan `P04` beserta NIM dan kode studi kasus. Artefak dari Pertemuan 3 (`P03`) tetap dijaga keutuhannya tanpa ditimpa, dan setiap revisi pasca-tinjauan didokumentasikan pada versi berikutnya (`v02`) yang tercatat di dalam metadata dan logbook.

---

## D. ANALISIS

Berdasarkan pelaksanaan praktikum Pertemuan 4, penerapan relasi *generalization* terbukti efektif dalam mereduksi kerumitan diagram dengan mengelompokkan aktor maupun *use case* yang berbagi karakteristik serupa. Pada kasus laboratorium, penyatuan *Mahasiswa* dan *Dosen* di bawah aktor induk *Peminjam* menghilangkan duplikasi garis asosiasi pada layanan pengecekan alat dan pengajuan peminjaman, sehingga struktur diagram menjadi lebih ringkas dan terbaca jelas.

Hal serupa terlihat pada pemodelan *Kelola Data Peralatan* yang dipecah menjadi tiga *use case* khusus (*Tambah*, *Ubah*, dan *Hapus*). Pendekatan ini memperlihatkan bagaimana satu tujuan umum pengelolaan data dapat diturunkan menjadi operasi spesifik yang memiliki hasil akhir berbeda tanpa kehilangan keterkaitan konseptualnya.

Selanjutnya, pengenalan elemen *collaboration* dan relasi *realization* memperjelas jembatan antara layanan fungsional yang diakses pengguna dengan mekanisme kerja sama internal sistem yang mewujudkannya—seperti pada *Ajukan Peminjaman* dan *Catat Pengembalian Peralatan* (kasus LAB), maupun *Input Nilai Mata Kuliah* dan *Lihat KHS* (kasus SIA). Ketelitian dalam mengarahkan panah *realization* dari *collaboration* menuju *use case* sangat krusial agar tidak rancu dengan relasi *include* maupun *extend*.

Pada kasus SIA, hierarki aktor *Civitas Akademika* dan pemecahan *Kelola Data Mahasiswa* menunjukkan konsistensi pola pemodelan lintas studi kasus. Di samping itu, uji konsistensi terhadap akses dosen non-pengampu serta penghapusan data mahasiswa aktif menegaskan bahwa diagram visual harus selalu ditopang oleh prasyarat dan aturan bisnis yang eksplisit di dalam *Use Case Description*.

Secara keseluruhan, praktikum ini membuktikan pentingnya pendekatan pengembangan model secara inkremental dan kumulatif. Dengan mempertahankan artefak Pertemuan 3 dan menambahkan elemen Pertemuan 4 secara terukur, cakupan fungsional sistem berkembang secara utuh tanpa merusak konsistensi kebutuhan awal.

---

## E. KESIMPULAN

Pelaksanaan Praktikum Analisis dan Desain Berorientasi Objek Pertemuan 4 menunjukkan bahwa *generalization* dan *collaboration* merupakan instrumen penting dalam menyusun *Use Case Diagram* tingkat lanjut. *Generalization* memfasilitasi pemodelan pewarisan hak akses maupun perilaku dari aktor atau *use case* induk kepada elemen turunannya sehingga struktur model lebih efisien.

Sementara itu, *collaboration* beserta relasi *realization* memvisualisasikan bagaimana sebuah *use case* diwujudkan melalui sinergi komponen sistem, yang penerapannya menuntut ketepatan simbol, arah panah, serta kesamaan penamaan.

Selain penguasaan notasi lanjutan, praktikum ini menegaskan urgensi menjaga kesinambungan model antarpertemuan. Penggabungan fitur lama dan baru dalam diagram kumulatif P04—yang didukung oleh katalog kebutuhan, *Use Case Description*, serta uji konsistensi—menghasilkan dokumentasi analisis sistem yang terstruktur, akurat, dan mudah ditelusuri.

---

## F. REFERENSI

1. Institut Teknologi Garut. (2026). *Jobsheet Praktikum Analisis dan Desain Berorientasi Objek (ADBO) Pertemuan 4: Use Case Diagram Lanjutan - Generalization dan Collaboration*.
2. Object Management Group. (2017). *OMG Unified Modeling Language (UML), Version 2.5.1*.
3. Tegarden, D. P., Samuel, B., Lukyanenko, R., Dennis, A., & Wixom, B. H. *Systems Analysis and Design: An Object-Oriented Approach with UML*. Wiley.
4. Fowler, M. *UML Distilled: A Brief Guide to the Standard Object Modeling Language*. Addison-Wesley.
5. Dokumentasi draw.io. *An Introduction to UML Diagrams, Save a Diagram in Various Formats, dan Supported Export Formats*.
6. Repository Praktikum ADBO: https://github.com/syakila2406060/IFRWP5149_2406060_LabAlat