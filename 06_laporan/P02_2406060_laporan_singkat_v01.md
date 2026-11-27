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

Perancangan *Use Case Diagram* harus mematuhi sejumlah kaidah pemodelan. Seluruh aktor wajib berada di luar kotak batas sistem, sedangkan setiap *use case* diletakkan di dalamnya. Penamaan judul pada kotak batas sistem harus selaras dengan konteks skenario studi kasus, dan setiap tarikan garis relasi wajib merujuk pada daftar