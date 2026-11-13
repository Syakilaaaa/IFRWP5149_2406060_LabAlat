# Kebutuhan dan skenario sistem informasi akademik: layanan hasil studi (v01)

## skenario 

dalam tugas kali ini tentang layanan hasil studi, dengan teknik generalization dan
collaboration yang sama seperti studi kasus, tetapi diterapkan pada skenario
baru tanpa contoh jawaban.
Mahasiswa dan dosen merupakan civitas akademik yg dapat melihat kalender  akademik. Dosen menginput nilai mata kuliah yang
diampunya setelah masa perkuliahan berakhir. Mahasiswa melihat Kartu
Hasil Studi (KHS) untuk semester yang nilainya sudah dipublikasikan. Admin
Akademik mengelola data mahasiswa: menambah data mahasiswa baru,
mengubah data mahasiswa, dan menghapus data mahasiswa.

## tabel kebutuhan 

|  ID   |                                          Kebutuhan_tugas                                           |
|-------|----------------------------------------------------------------------------------------------------|
| SIA-R01 s.d. SIA-R02 | Jadwal Kuliah dan Kelola Jadwal Kuliah |
| SIA-R03 s.d. SIA-R06 | Pengajuan KRS, Validasi KRS, Unduh Bukti, Proses Keputusan KRS |
|SIA-R07|          Mahasiswa dan Dosen, sebagai Civitas Akademika, dapat melihat kalender akademik.          |
|SIA-R08|                      Dosen dapat menginput nilai mata kuliah yang diampunya.                       |
|SIA-R09|           Mahasiswa dapat melihat KHS untuk semester yang nilainya sudah dipublikasikan.           |
|SIA-R10|                           Admin Akademik dapat mengelola data mahasiswa.                           |
|SIA-R11|Pengelolaan data mahasiswa terdiri dari tiga bentuk khusus: tambah, ubah, dan hapus data mahasiswa. |
|SIA-R12|     Model menunjukkan collaboration yang merealisasikan Input Nilai Mata Kuliah dan Lihat KHS      |

## asumsi sistem 

* Penomoran kode kebutuhan diawali dari SIA-R07 supaya SIA-R01 dan SIA-R02 (Pertemuan 2) serta SIA-R03 hingga SIA-R06 (Pertemuan 3) tetap memiliki identitas yang terpisah.

* Setiap pengguna diasumsikan sudah terautentikasi dan memperoleh hak akses berdasarkan perannya masing-masing.

* Kalender akademik dalam studi kasus ini merujuk pada jadwal agenda resmi institusi (seperti awal perkuliahan, tenggat KRS, periode ujian, dan sejenisnya); jangan dicampuradukkan dengan jadwal kuliah pada Pertemuan 2.

* Penginputan nilai hanya dapat dilakukan oleh dosen pengampu mata kuliah terkait. Nilai yang baru dimasukkan berstatus belum dipublikasikan sebelum disahkan sesuai aturan tugas ini: KHS hanya memuat nilai-nilai yang telah resmi dipublikasikan.

* Fitur Hapus Data Mahasiswa hanya berlaku bagi mahasiswa yang sudah tidak mempunyai riwayat akademik aktif. Aturan ini bersifat simulasi untuk keperluan latihan.

* Proses pengajuan KRS tetap digambarkan sebagai bagian dari diagram kumulatif Pertemuan 3. Sementara itu, urusan pembayaran serta perancangan basis data berada di luar cakupan tugas ini.

## Identifikasi Aktor (Generalization Aktor)

| Aktor | Kedudukan | Tujuan terhadap Sistem |
| :--- | :--- | :--- |
| **Civitas Akademika** | Umum (*general*), baru di Pertemuan 4 | Peran induk bagi seluruh civitas akademika; menurunkan hak akses melihat kalender akademik kepada Mahasiswa dan Dosen. |
| **Mahasiswa** | Khusus dari Civitas Akademika, tetap dari P2 & P3 | Melakukan pengajuan KRS, mengecek jadwal kuliah, mengunduh bukti KRS, melihat kalender akademik (warisan), serta mengakses KHS. |
| **Dosen** | Khusus dari Civitas Akademika, baru di P4 | Mengakses kalender akademik (diwarisi dari Civitas Akademika) dan melakukan penginputan nilai mata kuliah. |
| **Admin Akademik** | Tetap dari pertemuan sebelumnya | Mengatur data mahasiswa (menambah, memperbarui, dan menghapus). |

---

## Katalog Use Case Gabungan SIA

| ID | Nama Use Case | Peran dalam Model | Sumber Kebutuhan |
| :--- | :--- | :--- | :--- |
| **SIA-UC01** | Lihat Jadwal Kuliah | Tetap dari Pertemuan 2; fungsi mahasiswa | SIA-R01 |
| **SIA-UC02** | Kelola Jadwal Kuliah | Tetap dari Pertemuan 2; fungsi admin | SIA-R02 |
| **SIA-UC03** | Ajukan KRS | Tetap dari Pertemuan 3; fungsi mahasiswa | SIA-R03 |
| **SIA-UC04** | Validasi KRS | Tetap dari Pertemuan 3; disertakan (*include*) pada SIA-UC03 | SIA-R04 |
| **SIA-UC05** | Unduh Bukti Pengajuan KRS | Tetap dari Pertemuan 3; perluasan bersyarat (*extend*) pada SIA-UC03 | SIA-R05 |
| **SIA-UC06** | Proses Keputusan KRS | Tetap dari Pertemuan 3; fungsi dosen wali | SIA-R06 |
| **SIA-UC07** | Lihat Kalender Akademik | Baru di P4; fungsi aktor umum Civitas Akademika | SIA-R07 |
| **SIA-UC08** | Input Nilai Mata Kuliah | Baru di P4; fungsi dosen; direalisasikan oleh SIA-CO01 | SIA-R08 |
| **SIA-UC09** | Lihat KHS | Baru di P4; fungsi mahasiswa; direalisasikan oleh SIA-CO02 | SIA-R09 |
| **SIA-UC10** | Kelola Data Mahasiswa | Baru di P4; *use case* INDUK (umum) untuk SIA-UC11, SIA-UC12, SIA-UC13 | SIA-R10, SIA-R11 |
| **SIA-UC11** | Tambah Data Mahasiswa | Baru di P4; *use case* TURUNAN (khusus) dari SIA-UC10 | SIA-R11 |
| **SIA-UC12** | Ubah Data Mahasiswa | Baru di P4; *use case* TURUNAN (khusus) dari SIA-UC10 | SIA-R11 |
| **SIA-UC13** | Hapus Data Mahasiswa | Baru di P4; *use case* TURUNAN (khusus) dari SIA-UC10 | SIA-R11 |

## uji konsistensi 
* Situasi A: Mahasiswa dapat mengakses kalender akademik meskipun tidak ada garis asosiasi langsung dari aktor Mahasiswa. Hal ini tetap valid secara pemodelan karena Mahasiswa berperan sebagai aktor turunan (specialized) yang mewarisi fitur tersebut dari aktor induk (general) Civitas Akademika melalui relasi generalization.

* Situasi B: Apabila dosen yang bukan pengampu mencoba memasukkan nilai, sistem akan menolak akses tersebut karena prakondisi (precondition) use case mewajibkan pengguna tercatat sebagai dosen pengampu resmi pada mata kuliah yang bersangkutan.

* Situasi C: Tindakan Admin Akademik yang berupaya menghapus data mahasiswa dengan status akademik masih aktif akan dicegah oleh sistem, mengacu pada ketentuan batasan penghapusan data yang telah ditetapkan.


