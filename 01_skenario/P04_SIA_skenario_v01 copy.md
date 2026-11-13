# Skenario Use Case (Pertemuan 4)

## 1. SIA-UC07: Lihat Kalender Akademik
* **Aktor:** Civitas Akademika (diwarisi oleh Mahasiswa dan Dosen)
* **Prakondisi:** Pengguna telah berhasil melakukan autentikasi (*login*) ke dalam sistem.
* **Alur Utama:**
  1. Pengguna memilih menu **Kalender Akademik**.
  2. Sistem mengambil data agenda resmi institusi yang aktif pada tahun akademik berjalan.
  3. Sistem menampilkan rincian jadwal agenda (awal kuliah, batas KRS, masa ujian, dll.).
* **Pascakondisi:** Informasi kalender akademik berhasil ditampilkan kepada pengguna.

---

## 2. SIA-UC08: Input Nilai Mata Kuliah (Realisasi: SIA-CO01)
* **Aktor:** Dosen
* **Prakondisi:** Dosen telah terautentikasi, tercatat sebagai dosen pengampu resmi mata kuliah terkait, dan masa perkuliahan telah berakhir.
* **Alur Utama:**
  1. Dosen membuka menu **Input Nilai** dan memilih kelas mata kuliah yang diampu.
  2. Sistem memvalidasi hak akses pengampu dan menampilkan daftar mahasiswa peserta kelas.
  3. Dosen memasukkan skor atau nilai akhir setiap mahasiswa, lalu menekan tombol **Simpan**.
  4. Sistem menyimpan data nilai dengan status default **Belum Dipublikasikan** dan menampilkan pesan konfirmasi berhasil.
* **Alur Alternatif:**
  * *2a. Dosen bukan pengampu mata kuliah:* Sistem menolak akses dan menampilkan pesan peringatan bahwa pengguna tidak memiliki otorisasi pada kelas tersebut.
* **Pascakondisi:** Data nilai tersimpan di dalam sistem namun belum dapat diakses melalui KHS mahasiswa sebelum dipublikasikan secara resmi.

---

## 3. SIA-UC09: Lihat KHS (Realisasi: SIA-CO02)
* **Aktor:** Mahasiswa
* **Prakondisi:** Mahasiswa telah terautentikasi dan memiliki riwayat pengambilan mata kuliah pada semester terkait.
* **Alur Utama:**
  1. Mahasiswa membuka menu **Kartu Hasil Studi (KHS)** dan memilih periode semester.
  2. Sistem memfilter dan mengambil daftar nilai mahasiswa yang berstatus **Sudah Dipublikasikan**.
  3. Sistem menghitung Indeks Prestasi Semester (IPS) dan menampilkan rincian KHS di layar.
* **Alur Alternatif:**
  * *2a. Nilai semester belum dipublikasikan:* Sistem tidak menampilkan nilai yang masih berstatus draf dan memberikan keterangan bahwa nilai resmi belum diterbitkan.
* **Pascakondisi:** Mahasiswa dapat melihat rincian hasil studi resmi pada semester yang dipilih.

---

## 4. SIA-UC10 s.d. SIA-UC13: Kelola Data Mahasiswa (Tambah, Ubah, Hapus)
* **Aktor:** Admin Akademik
* **Prakondisi:** Admin Akademik telah terautentikasi pada sistem.
* **Alur Utama (General - SIA-UC10):**
  1. Admin Akademik membuka menu **Manajemen Data Mahasiswa**.
  2. Admin memilih salah satu bentuk pengelolaan khusus:
     * **Tambah Data (SIA-UC11):** Admin mengisi formulir biodata mahasiswa baru, sistem memvalidasi kelengkapan NIM/data, lalu menyimpan record baru.
     * **Ubah Data (SIA-UC12):** Admin mencari data mahasiswa, memperbarui informasi yang diperlukan, lalu menyimpan perubahan.
     * **Hapus Data (SIA-UC13):** Admin memilih data mahasiswa untuk dihapus; sistem memeriksa status riwayat akademik mahasiswa sebelum mengeksekusi penghapusan permanen.
* **Alur Alternatif:**
  * *2c.1. Mahasiswa masih memiliki data akademik aktif (pada SIA-UC13):* Sistem membatalkan proses penghapusan dan menampilkan pesan bahwa data mahasiswa aktif tidak dapat dihapus.
* **Pascakondisi:** Perubahan data master mahasiswa (penambahan, pembaruan, atau penghapusan yang valid) tersimpan secara konsisten di sistem.