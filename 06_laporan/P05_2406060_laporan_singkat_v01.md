# LAPORAN PRAKTIKUM ADBO
## PERTEMUAN 5: SKENARIO USE CASE - DARI DIAGRAM KE LANGKAH KEGIATAN

- **Nama:** Syakila Nurul Ijati
- **NIM:** 2406060
- **Mata Kuliah:** Praktikum Analisis dan Desain Berorientasi Objek (ADBO)
- **Program Studi:** S1 Teknik Informatika (Semester 5)

---

## A. TUJUAN PRAKTIKUM

Mengacu pada *Jobsheet* Praktikum Pertemuan 5, capaian pembelajaran yang diharapkan adalah agar mahasiswa mampu:

1. Menyusun tabel skenario untuk suatu *use case* dengan komponen lengkap, mulai dari nama *use case*, aktor, tujuan, deskripsi, kegiatan, respons sistem, skenario normal, skenario alternatif, hingga skenario akhir.
2. Merumuskan tahapan skenario secara kronologis dengan memuat tepat satu aksi tunggal pada setiap langkah.
3. Memisahkan tindakan aktor ke dalam kolom **Kegiatan** dan reaksi sistem ke dalam kolom **Respon Sistem**.
4. Mengonversi relasi *include* menjadi tahapan wajib di dalam skenario normal serta relasi *extend* menjadi percabangan bersyarat di dalam skenario alternatif.
5. Mengimplementasikan konsep *generalization* aktor dan *generalization use case* dalam penyusunan tabel skenario.
6. Memverifikasi keselarasan tabel skenario terhadap diagram kumulatif Pertemuan 4, meliputi kesamaan nama, kode ID, aktor, serta relasi antar-*use case*.

---

## B. DASAR TEORI

### 1. Pengertian Skenario Use Case

Skenario *use case* adalah penjabaran langkah demi langkah mengenai dialog interaksi antara aktor dan sistem saat mengeksekusi suatu layanan. Dokumen ini menguraikan tindakan spesifik yang diambil pengguna, reaksi yang diberikan sistem, titik munculnya kondisi penyimpangan (alternatif), hingga status akhir penyelesaian proses.

Penyajian skenario umumnya dituangkan dalam format tabel yang bertumpu pada dua kolom utama, yakni **Kegiatan** dan **Respon Sistem**. Kolom *Kegiatan* merekam aksi yang dijalankan aktor, sementara kolom *Respon Sistem* mendokumentasikan umpan balik atau pemrosesan yang dilakukan sistem.

### 2. Perbedaan Use Case Diagram, Use Case Description, dan Skenario Use Case

Ketiga artefak analisis ini saling berkaitan erat namun memiliki tingkat kedalaman penyajian yang berbeda:

1. **Use Case Diagram**, memvisualisasikan peta layanan fungsional yang disediakan sistem beserta relasi interaksinya dengan pihak eksternal (aktor).
2. **Use Case Description**, menguraikan ringkasan spesifikasi fungsi seperti tujuan, pemicu, prasyarat, alur utama, alur alternatif, dan pascakondisi.
3. **Skenario Use Case**, merinci alur interaksi aktor dan sistem ke dalam urutan langkah aksi-reaksi yang granular dan terstruktur.

Dengan demikian, skenario *use case* merupakan elaborasi lebih mendalam dari *use case description* yang berpedoman pada diagram sebagai kerangka acuan. Ketiganya wajib dijaga konsistensinya agar tidak timbul kesenjangan antara pemodelan visual dan spesifikasi alur prosesnya.

### 3. Struktur Tabel Skenario Use Case

Kerangka standar tabel skenario *use case* memuat sejumlah elemen berikut:

1. **Nama Use Case**, identitas serta nama fungsionalitas yang sedang dijabarkan.
2. **Aktor**, peran pengguna yang berinteraksi langsung menjalankan fungsi tersebut.
3. **Tujuan**, sasaran akhir yang ingin dicapai aktor melalui eksekusi *use case*.
4. **Deskripsi**, ringkasan singkat mengenai konteks dan alur utama proses.
5. **Kegiatan**, rincian aksi yang dikerjakan oleh aktor.
6. **Respon Sistem**, rincian tanggapan atau eksekusi logika oleh sistem atas aksi aktor.
7. **Skenario Normal**, urutan langkah ideal ketika transaksi berjalan lancar tanpa kendala.
8. **Skenario Alternatif**, alur percabangan apabila terjadi pengecualian, kesalahan input, atau kondisi opsional.
9. **Skenario Akhir**, kondisi penutup yang menggambarkan keadaan akhir sistem saat proses berakhir sukses maupun gagal.

### 4. Kaidah Penulisan Langkah Skenario

Setiap butir langkah dalam tabel skenario harus merepresentasikan satu aksi yang spesifik agar mudah ditelusuri dan diuji. Kolom *Kegiatan* dikhususkan bagi tindakan aktor, sedangkan kolom *Respon Sistem* dikhususkan bagi reaksi sistem.

Penyusunan kalimat menggunakan ragam aktif dengan kata kerja operasional yang lugas—seperti *memilih*, *mengisi*, *mengirim*, *menampilkan*, *memeriksa*, *menyimpan*, dan *menolak*. Elemen data yang terlibat juga perlu disebutkan secara eksplisit, termasuk nama kolom (*field*), nilai masukan, maupun perubahan status.

Selain itu, penomoran langkah pada bagian **Skenario Alternatif** wajib melanjutkan urutan nomor dari **Skenario Normal** (tidak mengulang dari angka 1), disertai rujukan langkah asal tempat percabangan tersebut bermula.

### 5. Pemetaan Relasi Include

Relasi `<<include>>` pada diagram dipetakan sebagai langkah wajib di dalam bagian **Skenario Normal**, mengingat *use case* yang disertakan selalu dieksekusi sebagai bagian tak terpisahkan dari alur utama.

Pada studi kasus laboratorium, **LAB-UC03 Ajukan Peminjaman** menyertakan **LAB-UC04 Periksa Ketersediaan**. Oleh sebab itu, tahapan pengecekan stok alat dicantumkan dalam skenario normal pengajuan peminjaman cukup berupa rujukan ke tabel skenario **LAB-UC04** tanpa menyalin ulang seluruh rincian langkahnya.

### 6. Pemetaan Relasi Extend

Relasi `<<extend>>` dipetakan sebagai jalur percabangan bersyarat di dalam bagian **Skenario Alternatif**, karena perilaku tambahan tersebut hanya berjalan apabila syarat perluasannya terpenuhi.

Sebagai contoh pada **LAB-UC03 Ajukan Peminjaman**, fitur **Cetak Bukti Pengajuan** hanya dijalankan jika mahasiswa memilih opsi cetak. Maka, langkah tersebut ditempatkan pada cabang alternatif dengan menyertakan informasi *condition* dan *extension point* yang selaras dengan diagram Pertemuan 4.

### 7. Penerapan Generalization Aktor

*Generalization* aktor dimanfaatkan ketika beberapa aktor khusus mewarisi fungsi yang identik dari satu aktor induk. Dalam penyusunan skenario, alur langkah yang sama cukup dituliskan satu kali menggunakan nama aktor umum, sedangkan perbedaan perilaku pada aktor turunan dicantumkan sebagai catatan atau cabang khusus pada tabel yang sama—seperti aktor **Peminjam** yang menaungi *Mahasiswa* dan *Dosen* pada sistem laboratorium.

### 8. Penerapan Generalization Use Case

*Generalization* pada *use case* diterapkan apabila beberapa *use case* khusus berbagi perilaku dasar dari satu *use case* umum. Skenario pada *use case* induk mendokumentasikan alur langkah bersama, sementara masing-masing *use case* turunan memiliki tabel terpisah yang berfokus pada perilaku pembedanya dan merujuk ke tabel induk untuk langkah-langkah umumnya.

### 9. Collaboration dan Realization

Elemen *collaboration* berfungsi memvisualisasikan realisasi internal dari suatu *use case*. Dalam penyusunan skenario Pertemuan 5, *collaboration* tidak dibuatkan tabel skenario tersendiri maupun rincian langkah kegiatan, melainkan cukup dicantumkan pada kolom keterangan tabel *use case* yang direalisasikannya. Detail pertukaran pesan di dalamnya akan dimodelkan pada diagram interaksi di pertemuan selanjutnya.

---

## C. HASIL PRAKTIKUM

### 1. Studi Kasus Sistem Informasi Peminjaman dan Pengembalian Peralatan Laboratorium Kampus

Latihan pertama mengangkat studi kasus *Sistem Informasi Peminjaman dan Pengembalian Peralatan Laboratorium Kampus* dengan berpedoman pada diagram kumulatif Pertemuan 4.

Pada sesi ini tidak ada penambahan kebutuhan maupun *use case* baru; seluruh kebutuhan (**LAB-R01** s.d. **LAB-R11**) serta relasinya tetap merujuk pada *Jobsheet* Pertemuan 4. Fokus kegiatan mahasiswa adalah mengaudit dan menelaah 12 tabel skenario yang telah tersedia pada *Jobsheet* Pertemuan 5.

Daftar 12 *use case* yang ditelaah meliputi:

| No. | ID Use Case | Nama Use Case |
| :---: | :--- | :--- |
| **1** | LAB-UC01 | Lihat Ketersediaan Peralatan |
| **2** | LAB-UC02 | Kelola Data Peralatan |
| **3** | LAB-UC03 | Ajukan Peminjaman |
| **4** | LAB-UC04 | Periksa Ketersediaan |
| **5** | LAB-UC05 | Cetak Bukti Pengajuan |
| **6** | LAB-UC06 | Proses Keputusan Peminjaman |
| **7** | LAB-UC07 | Lihat Laporan Peminjaman |
| **8** | LAB-UC08 | Tambah Data Peralatan |
| **9** | LAB-UC09 | Ubah Data Peralatan |
| **10** | LAB-UC10 | Hapus Data Peralatan |
| **11** | LAB-UC11 | Catat Pengembalian Peralatan |
| **12** | LAB-UC12 | Periksa Kondisi Peralatan |

### 2. Pemeriksaan Skenario LAB

Audit dilakukan dengan membandingkan isi setiap tabel skenario terhadap diagram kumulatif P04—mencakup kesesuaian nama *use case*, ID, aktor, tujuan, serta pola relasi antar-*use case*:

- **a. Relasi Include:** Pada proses pengajuan peminjaman maupun pencatatan pengembalian alat, tahapan pemeriksaan wajib dijalankan sebelum data transaksi disimpan. Hal ini tercermin pada relasi antara **LAB-UC03** dengan **LAB-UC04**, serta **LAB-UC11** dengan **LAB-UC12**.
- **b. Relasi Extend:** Pada skenario pengajuan peminjaman, opsi pencetakan tanda bukti hanya berjalan apabila mahasiswa memilihnya di halaman konfirmasi, sebagaimana dimodelkan pada relasi **LAB-UC03** dengan **LAB-UC05**.
- **c. Generalization Aktor:** Peran **Peminjam** menaungi *Mahasiswa* dan *Dosen*, sehingga skenario peminjaman cukup disusun satu kali atas nama *Peminjam* dengan menyertakan catatan khusus untuk perilaku pembeda.
- **d. Generalization Use Case:** Pengelolaan data alat terbagi atas *use case* induk **LAB-UC02 Kelola Data Peralatan** dan tiga *use case* khusus (**LAB-UC08**, **LAB-UC09**, **LAB-UC10**). Skenario induk memuat langkah umum, sedangkan skenario khusus menjabarkan spesifikasi tambah, ubah, dan hapus data.
- **e. Collaboration:** Tidak dibuatkan tabel skenario terpisah, melainkan sekadar dicantumkan pada metadata/keterangan tabel *use case* terkait, yakni **LAB-CO01** untuk *LAB-UC03* dan **LAB-CO02** untuk *LAB-UC11*.

### 3. Penelusuran Hasil Pemeriksaan Skenario LAB

Hasil verifikasi kesesuaian antar-relasi pada studi kasus LAB dirangkum dalam matriks penelusuran berikut:

| ID Use Case | Relasi yang Ditelusuri | Hasil Pencocokan |
| :--- | :--- | :--- |
| **LAB-UC01** | Asosiasi aktor | Terverifikasi sesuai dengan aktor *Mahasiswa*. |
| **LAB-UC02** | *Generalization use case* | Terverifikasi sebagai induk dari *LAB-UC08*, *LAB-UC09*, dan *LAB-UC10*. |
| **LAB-UC03** | *Include*, *extend*, *generalization* aktor, *collaboration* | Terverifikasi sesuai dengan *LAB-UC04*, *LAB-UC05*, *Peminjam*, dan *LAB-CO01*. |
| **LAB-UC04** | *Include* | Terverifikasi disertakan oleh *LAB-UC03*. |
| **LAB-UC05** | *Extend* | Terverifikasi memperluas *LAB-UC03*. |
| **LAB-UC06** | Asosiasi aktor | Terverifikasi sesuai dengan aktor *Petugas Laboratorium*. |
| **LAB-UC07** | Asosiasi aktor | Terverifikasi sesuai dengan aktor *Kepala Laboratorium*. |
| **LAB-UC08** | *Generalization use case* | Terverifikasi sebagai turunan dari *LAB-UC02*. |
| **LAB-UC09** | *Generalization use case* | Terverifikasi sebagai turunan dari *LAB-UC02*. |
| **LAB-UC10** | *Generalization use case* | Terverifikasi sebagai turunan dari *LAB-UC02*. |
| **LAB-UC11** | *Include* dan *collaboration* | Terverifikasi sesuai dengan *LAB-UC12* dan *LAB-CO02*. |
| **LAB-UC12** | *Include* | Terverifikasi disertakan oleh *LAB-UC11*. |

*(Catatan: Matriks di atas berfungsi sebagai panduan audit berdasarkan relasi pada jobsheet, di mana status akhirnya disesuaikan dengan hasil pemeriksaan aktual terhadap diagram P04).*

### 4. Tugas Sistem Informasi Akademik, Layanan Hasil Studi

Latihan kedua melanjutkan pemodelan *Sistem Informasi Akademik (SIA)* pada modul layanan hasil studi dengan berpedoman pada diagram kumulatif SIA Pertemuan 4 (kebutuhan **SIA-R07** hingga **SIA-R12**).

Mengacu pada daftar tugas pada *Jobsheet* Pertemuan 5, disusun tujuh tabel skenario *use case* berikut:

| No. | ID Use Case | Nama Use Case | Aktor |
| :---: | :--- | :--- | :--- |
| **1** | SIA-UC07 | Lihat Kalender Akademik | Civitas Akademika |
| **2** | SIA-UC08 | Input Nilai Mata Kuliah | Dosen |
| **3** | SIA-UC09 | Lihat KHS | Mahasiswa |
| **4** | SIA-UC10 | Kelola Data Mahasiswa | Admin Akademik |
| **5** | SIA-UC11 | Tambah Data Mahasiswa | Admin Akademik |
| **6** | SIA-UC12 | Ubah Data Mahasiswa | Admin Akademik |
| **7** | SIA-UC13 | Hapus Data Mahasiswa | Admin Akademik |

### 5. Penyusunan Skenario SIA

Seluruh tabel skenario disusun mengikuti format baku contoh *LAB-UC03* yang memuat identitas *use case*, aktor, tujuan, deskripsi, kolom *Kegiatan*, kolom *Respon Sistem*, *Skenario Normal*, *Skenario Alternatif*, dan *Skenario Akhir*:

- **a. SIA-UC07 Lihat Kalender Akademik:** Ditulis satu kali menggunakan aktor umum **Civitas Akademika** yang berlaku otomatis bagi *Mahasiswa* dan *Dosen* sebagai aktor turunannya.
- **b. SIA-UC08 Input Nilai Mata Kuliah:** Menjabarkan langkah dosen pengampu dalam menginput nilai pasca-perkuliahan. Input di luar rentang nilai valid akan ditolak sistem; layanan ini direalisasikan oleh **SIA-CO01 Input Nilai Mata Kuliah**.
- **c. SIA-UC09 Lihat KHS:** Menjabarkan langkah mahasiswa dalam mengakses KHS, di mana sistem hanya menampilkan nilai yang berstatus resmi *dipublikasikan*; layanan ini direalisasikan oleh **SIA-CO02 Lihat KHS**.
- **d. SIA-UC10 Kelola Data Mahasiswa:** Berperan sebagai skenario induk yang mendokumentasikan alur pengelolaan umum bagi ketiga *use case* turunannya.
- **e. SIA-UC11 Tambah Data Mahasiswa:** Berfokus pada perilaku khusus penambahan data mahasiswa baru, sementara langkah umumnya merujuk ke **SIA-UC10**.
- **f. SIA-UC12 Ubah Data Mahasiswa:** Berfokus pada perilaku khusus pembaruan biodata mahasiswa eksisting dengan langkah umum merujuk ke **SIA-UC10**.
- **g. SIA-UC13 Hapus Data Mahasiswa:** Berfokus pada perilaku khusus penghapusan rekaman mahasiswa, dengan aturan bisnis bahwa sistem menolak penghapusan apabila mahasiswa masih memiliki data akademik aktif.

### 6. Penerapan Generalization pada SIA

Dua struktur *generalization* diterapkan secara konsisten pada dokumentasi skenario SIA:

- **Generalization Aktor:** Peran **Civitas Akademika** dipakai sebagai aktor tunggal pada skenario **SIA-UC07** karena *Mahasiswa* dan *Dosen* mewarisi fitur akses kalender akademik darinya.
- **Generalization Use Case:** **SIA-UC10 Kelola Data Mahasiswa** menjadi acuan langkah umum bagi **SIA-UC11**, **SIA-UC12**, dan **SIA-UC13**, sehingga masing-masing skenario khusus cukup menjabarkan perilaku pembedanya.

### 7. Pemeriksaan Konsistensi Skenario SIA

Setelah ketujuh tabel rampung disusun, dilakukan audit konsistensi terhadap diagram P04 dengan memastikan seluruh aturan bisnis berikut terpenuhi:

1. Hak akses *Lihat Kalender Akademik* diwarisi oleh *Mahasiswa* dan *Dosen* dari *Civitas Akademika*.
2. Fitur *Input Nilai Mata Kuliah* terbatas hanya bagi dosen pengampu sah mata kuliah terkait.
3. Halaman *KHS* hanya memuat komponen nilai yang statusnya telah dipublikasikan secara resmi.
4. Operasi *Hapus Data Mahasiswa* hanya diizinkan bagi mahasiswa yang sudah tidak mempunyai data akademik aktif.
5. Elemen *collaboration* hanya dicantumkan pada keterangan tabel *use case* yang direalisasikannya tanpa penjabaran langkah kegiatan tersendiri.
6. Diagram kumulatif SIA Pertemuan 4 tetap dipertahankan utuh karena luaran Pertemuan 5 berfokus pada artefak dokumen skenario.

### 8. Pemeriksaan Struktur dan Penamaan Dokumen

Seluruh luaran praktikum disimpan di dalam direktori `01_skenario` mengikuti konvensi penamaan standar pada *jobsheet*:

- `P05_2406060_LAB_skenario_v01.md` (berisi hasil audit 12 tabel skenario studi kasus LAB)
- `P05_2406060_SIA_skenario_v01.md` (berisi penyusunan 7 tabel skenario tugas SIA)

Berkas diagram P04 tetap dijadikan rujukan tanpa ditimpa, disertai pencatatan progres audit dan penyusunan skenario ke dalam logbook praktikum.

---

## D. ANALISIS

Berdasarkan kegiatan praktikum Pertemuan 5, penyusunan skenario *use case* memainkan peran vital dalam menjembatani pemodelan visual dengan spesifikasi kebutuhan rinci. Apabila *Use Case Diagram* memetakan ruang lingkup fitur dan aktor pada level makro, maka skenario *use case* menguraikan mekanisme operasionalnya melalui dialog aksi-reaksi yang kronologis dan terukur.

Pada studi kasus laboratorium, penelaahan terhadap 12 tabel skenario menegaskan bagaimana aturan pemetaan UML bekerja secara sistematis. Relasi `<<include>>` wajib dituangkan ke dalam jalur utama (*Skenario Normal*) karena merupakan sub-proses mutlak, sedangkan relasi `<<extend>>` ditempatkan pada jalur percabangan (*Skenario Alternatif*) karena bergantung pada kondisi tertentu. Di sisi lain, *generalization* aktor menyederhanakan penulisan dokumentasi karena alur bersama cukup dideskripsikan satu kali melalui aktor induk.

Hal serupa terlihat pada tugas Sistem Informasi Akademik, di mana penerapan *generalization* pada aktor *Civitas Akademika* serta *use case Kel
