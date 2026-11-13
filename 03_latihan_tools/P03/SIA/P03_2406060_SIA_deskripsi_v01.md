<!-- Tulis use case description utama -->

| Elemen | SIA-UC03 — Ajukan KRS |
| :--- | :--- |
| **Tujuan** | Menghasilkan data pengajuan KRS yang tersimpan dengan status menunggu persetujuan dosen wali |
| **Aktor utama** | Mahasiswa |
| **Sumber kebutuhan** | SIA-R03, SIA-R04, dan SIA-R05 |
| **Pemicu** | Mahasiswa mengakses fitur atau menu pengajuan KRS |
| **Prasyarat** | Mahasiswa sudah masuk ke sistem (terautentikasi); data mata kuliah, prasyarat, serta jadwal perkuliahan telah tersedia |
| **Pascakondisi berhasil** | Data pengajuan KRS terekam dengan status *Menunggu persetujuan* |
| **Pascakondisi gagal** | Tidak ada data pengajuan KRS yang tercatat atau tersimpan di sistem |
| **Include** | SIA-UC04 — Validasi KRS |
| **Extension point** | Konfirmasi penyimpanan tampil, tepat pada langkah ke-5 |
| **Extend** | SIA-UC05 apabila [mahasiswa memutuskan untuk mengunduh bukti pengajuan] |

**Alur utama:**

| Langkah | Tindakan Mahasiswa | Respons Sistem |
| :---: | :--- | :--- |
| **1** | Mengakses menu pengajuan KRS | Menyajikan halaman formulir pemilihan mata kuliah |
| **2** | Menentukan mata kuliah yang hendak diambil | Merekam sementara daftar mata kuliah pilihan mahasiswa |
| **3** | Menekan tombol kirim pengajuan KRS | Mengeksekusi SIA-UC04 Validasi KRS (mengecek kelengkapan isian, pemenuhan prasyarat, dan konflik jadwal) |
| **4** | — | Apabila proses validasi lolos, sistem merekam pengajuan dengan status *Menunggu persetujuan* |
| **5** | Mengecek notifikasi konfirmasi penyimpanan | Memunculkan status pengajuan terbaru; sistem mencapai titik *extension point* |
| **6** | Menyelesaikan sesi pengajuan | Mengakhiri rangkaian proses pengajuan KRS |