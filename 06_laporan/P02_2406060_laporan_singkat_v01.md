# LAPORAN PRAKTIKUM ADBO
## PERTEMUAN 2: UNIFIED MODELLING LANGUAGE (UML)

- **Nama:** Syakila Nurul Ijati
- **NIM:** 2406060
- **Mata Kuliah:** Praktikum Analisis dan Desain Berorientasi Objek (ADBO)
- **Program Studi:** S1 Teknik Informatika (Semester 5)

---

## A. TUJUAN PRAKTIKUM

Mengacu pada *Jobsheet* Praktikum Pertemuan 2, target capaian yang ingin diraih dalam sesi ini meliputi:

1. Memahami penerapan simbol-simbol fundamental UML, terutama pada *Use Case Diagram*.
2. Meletakkan komponen aktor, *use case*, garis asosiasi, serta batas sistem secara tepat mengikuti kaidah pemodelan UML.
3. Menyusun diagram berdasarkan spesifikasi kebutuhan dan skenario kasus yang ditetapkan.
4. Melengkapi metadata artefak dengan memanfaatkan templat baku yang telah disediakan.
5. Mengevaluasi serta mengoreksi kekeliruan notasi maupun dokumentasi pada diagram.

---

## B. DASAR TEORI

### 1. Pengertian UML

*Unified Modelling Language* (UML) adalah standar bahasa pemodelan visual yang dimanfaatkan untuk memvisualisasikan, merancang, dan mendokumentasikan arsitektur suatu sistem. Penggunaan UML mempermudah tim pengembang dalam memetakan struktur sekaligus perilaku sistem lewat beragam jenis diagram. Melalui representasi visual ini, spesifikasi kebutuhan perangkat lunak dapat dikomunikasikan secara lebih presisi sehingga menunjang kelancaran tahap analisis dan perancangan.

### 2. Konsep Dasar UML

Terdapat tiga pilar utama yang membentuk kerangka pemodelan di dalam UML, yaitu:

1. **Things**, yakni entitas atau elemen dasar penyusun model UML.
2. **Relationships**, yakni relasi yang mengaitkan satu elemen dengan elemen lain di dalam model.
3. **Diagrams**, yakni representasi visual gabungan dari berbagai elemen dan relasi untuk mendeskripsikan cara kerja sistem.

### 3. Jenis Hubungan dalam UML

Beragam relasi yang umum diterapkan dalam pemodelan UML mencakup:

1. **Dependency**, menggambarkan relasi kebergantungan di mana perubahan pada satu elemen memengaruhi elemen lainnya.
2. **Association**, menggambarkan jalur komunikasi atau interaksi langsung antara aktor dan layanan (*use case*).
3. **Generalization**, menggambarkan relasi pewarisan sifat dari entitas umum (*general*) ke entitas khusus (*specialized*).
4. **Realization**, menggambarkan relasi perwujudan atau implementasi antara satu elemen dengan elemen lainnya.

### 4. Notasi Use Case Diagram

Pelaksanaan praktikum Pertemuan 2 menitikberatkan penggunaan empat komponen inti *Use Case Diagram*, yakni:

1. **Actor**, merepresentasikan entitas eksternal yang berinteraksi dengan sistem dan wajib diposisikan di luar batas sistem.
2. **Use Case**, merepresentasikan fitur atau fungsionalitas yang disediakan oleh sistem dalam bentuk simbol elips (oval).
3. **Association**, berupa garis lurus penghubung antara aktor dan *use case* yang menandakan adanya interaksi.
4. **System Boundary**, berupa kotak persegi panjang yang membatasi ruang lingkup fungsionalitas internal sistem.

### 5. Prinsip Penyusunan Use Case Diagram

Perancangan *Use Case Diagram* harus mematuhi sejumlah kaidah pemodelan. Seluruh aktor wajib berada di luar kotak batas sistem, sedangkan setiap *use case* diletakkan di dalamnya. Penamaan judul pada kotak batas sistem harus selaras dengan konteks skenario studi kasus, dan setiap tarikan garis relasi wajib merujuk pada daftar kebutuhan fungsional yang valid.

Lebih lanjut, garis asosiasi semata-mata merepresentasikan hubungan interaksi pengguna dengan fitur, bukan urutan alur kerja (*workflow*). Pada latihan dasar pertemuan ini, relasi lanjutan seperti *include*, *extend*, maupun *generalization* belum diterapkan.

---

## C. HASIL PRAKTIKUM

### 1. Latihan Notasi Use Case Diagram LAB

Pada sesi latihan pertama, studi kasus yang diangkat adalah *Sistem Informasi Peminjaman dan Pengembalian Peralatan Laboratorium Kampus*. Kasus ini menjadi sarana latihan awal untuk memetakan relasi antara pengguna dan fitur sistem.

Berdasarkan skenario yang ditetapkan, dirumuskan dua kebutuhan fungsional utama berikut:

| ID Kebutuhan | Aktor | Fungsi Sistem |
| :--- | :--- | :--- |
| **LAB-R01** | Mahasiswa | Lihat ketersediaan peralatan |
| **LAB-R02** | Petugas laboratorium | Kelola data peralatan |

Mengacu pada tabel kebutuhan tersebut, diagram disusun dengan memosisikan aktor *Mahasiswa* serta *Petugas Laboratorium* di area luar batas sistem, sementara layanan *Lihat Ketersediaan Peralatan* dan *Kelola Data Peralatan* ditempatkan di dalam kotak sistem.

- **Nama sistem:** Sistem Informasi Peminjaman dan Pengembalian Peralatan Laboratorium Kampus.
- **Berkas yang digunakan:**
  - `01_skenario/P02_LAB_skenario_v01.md`
  - `03_latihan_tools/P02/LAB/P02_2406060_LAB_notasi_usecase_v01.drawio`
  - `03_latihan_tools/P02/LAB/P02_2406060_LAB_notasi_usecase_v01.png`
- **Metadata artefak:**
  - **ID Artefak:** LAB-P02-UC
  - **Judul:** Latihan Notasi Fungsi Laboratorium
  - **Pertemuan:** 02
  - **Sumber Kebutuhan:** LAB-R01 dan LAB-R02
  - **Jenis Artefak:** Use Case Diagram
  - **Status:** LATIHAN NOTASI

### 2. Latihan Perbaikan Notasi Use Case Diagram SIA

Pada sesi latihan kedua, studi kasus beralih ke *Sistem Informasi Akademik (SIA)*. Mahasiswa diberikan sebuah draf diagram awal yang mengandung sejumlah kekeliruan notasi untuk kemudian dianalisis dan dikoreksi agar mematuhi standar *Use Case Diagram*.

Spesifikasi kebutuhan sistem yang dijadikan acuan adalah:

| ID Kebutuhan | Aktor | Fungsi Sistem |
| :--- | :--- | :--- |
| **SIA-R01** | Mahasiswa | Lihat jadwal kuliah |
| **SIA-R02** | Admin akademik | Kelola jadwal kuliah |

**Daftar temuan kesalahan pada diagram awal beserta langkah koreksinya:**

| No. | Temuan Kesalahan | Langkah Perbaikan |
| :---: | :--- | :--- |
| **1** | Simbol aktor *Mahasiswa* berada di dalam area batas sistem. | Memindahkan posisi aktor *Mahasiswa* keluar dari batas sistem. |
| **2** | Fitur *Lihat Jadwal Kuliah* digambarkan memakai bentuk persegi panjang. | Mengganti bentuknya menjadi elips agar sesuai dengan standar notasi *Use Case*. |
| **3** | Terdapat garis asosiasi antara aktor *Mahasiswa* dan fitur *Kelola Jadwal Kuliah*. | Menghapus garis relasi yang keliru tersebut agar selaras dengan spesifikasi kebutuhan. |
| **4** | Judul pada batas sistem masih mencantumkan nama sistem laboratorium. | Mengubah judul batas sistem menjadi *Sistem Informasi Akademik*. |

Pasca-perbaikan, diagram final memuat dua aktor dan dua layanan utama: aktor *Mahasiswa* terhubung dengan *Lihat Jadwal Kuliah*, sedangkan *Admin Akademik* terhubung dengan *Kelola Jadwal Kuliah* di dalam ruang lingkup *Sistem Informasi Akademik*.

- **Berkas yang digunakan:**
  - `01_skenario/P02_SIA_skenario_v01.md`
  - `03_latihan_tools/P02/SIA/P02_2406060_SIA_perbaikan_notasi_v01.drawio`
  - `03_latihan_tools/P02/SIA/P02_2406060_SIA_notasi_v01.drawio`
  - `03_latihan_tools/P02/SIA/P02_2406060_SIA_notasi_v01.png`

### 3. Pemeriksaan Hasil Praktikum

Tahap verifikasi dilakukan guna memastikan seluruh rancangan diagram telah memenuhi kriteria penilaian pada *jobsheet*. Aspek yang ditinjau mencakup ketepatan penamaan sistem, letak aktor, bentuk simbol *use case*, ketepatan garis asosiasi, serta keselarasan label fitur dengan tabel kebutuhan.

Di samping itu, dilakukan pula pengecekan berkas sumber `.drawio` agar dipastikan tetap bisa dimuat ulang dan disunting di aplikasi *draw.io*, serta memastikan gambar ekspor `.png` tampil identik dengan rancangan aslinya.

---

## D. ANALISIS

Berdasarkan rangkaian latihan yang dikerjakan, pemodelan UML—khususnya *Use Case Diagram*—terbukti efektif dalam memetakan batas interaksi antara pengguna dan fungsionalitas sistem. Pada kasus LAB, terlihat jelas bahwa setiap aktor hanya dikaitkan dengan hak akses fitur yang relevan berdasarkan daftar kebutuhan: *Mahasiswa* hanya mengakses informasi ketersediaan alat, sementara *Petugas Laboratorium* menangani pengelolaan datanya.

Selanjutnya, pada kasus SIA, identifikasi dan perbaikan kesalahan (seperti aktor yang masuk ke dalam kotak sistem, simbol *use case* berbentuk kotak, relasi ilegal antar-elemen, serta kesalahan judul sistem) menegaskan pentingnya ketelitian terhadap sintaks visual UML. Pelanggaran terhadap aturan dasar notasi dapat memicu ambiguitas dan salah tafsir pada tahap pengembangan berikutnya.

Secara keseluruhan, kedua latihan ini memperkuat pemahaman bahwa garis asosiasi dalam *Use Case Diagram* sekadar menyatakan keterlibatan interaksi, bukan urutan eksekusi langkah. Oleh karena itu, setiap relasi harus dibangun murni berdasarkan dokumen kebutuhan tanpa asumsi tambahan. Disiplin dalam penamaan berkas, pengisian metadata, serta sinkronisasi format `.drawio` dan `.png` turut berperan menjaga keterlacakan dokumen proyek.

---

## E. KESIMPULAN

Pelaksanaan Praktikum Analisis dan Desain Berorientasi Objek Pertemuan 2 memperlihatkan peran krusial UML sebagai bahasa pemodelan visual untuk mendefinisikan kebutuhan fungsional dan interaksi sistem. Melalui *Use Case Diagram*, relasi antara pengguna dan layanan sistem dapat dipresentasikan secara terstruktur menggunakan empat notasi fundamental: *Actor*, *Use Case*, *Association*, dan *System Boundary*.

Kegiatan ini juga menekankan bahwa kepatuhan terhadap aturan baku notasi UML sangat menentukan kualitas dan keterbacaan diagram. Kesalahan penempatan elemen maupun relasi harus segera dikoreksi agar selaras dengan skenario kebutuhan.

Selain aspek pemodelan, mahasiswa turut terlatih dalam menerapkan manajemen artefak yang tertib—mulai dari penyuntingan di *draw.io*, pencatatan metadata, hingga pendokumentasian berbasis Markdown—sehingga seluruh luaran praktikum tersimpan rapi, konsisten, dan siap ditinjau kembali.

---

## F. REFERENSI

1. Institut Teknologi Garut. *Jobsheet Praktikum Analisis dan Desain Berorientasi Objek (ADBO) Pertemuan 2*.
2. Object Management Group (OMG). *Unified Modeling Language (UML) Version 2.5.1*.
3. diagrams.net. *Dokumentasi Penggunaan draw.io*. Tersedia di: https://www.drawio.com/
4. Repository Praktikum ADBO: https://github.com/syakila2406060/IFRWP5149_2406060_LabAlat
