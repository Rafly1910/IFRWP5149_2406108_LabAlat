Mahasiswa mengajukan KRS dengan memilih mata kuliah. Setiap pengajuan menjalankan validasi KRS yang memeriksa kelengkapan, prasyarat mata kuliah, dan benturan jadwal. Jika validasi berhasil, sistem menyimpan pengajuan berstatus menunggu persetujuan dosen wali. Pada konfirmasi penyimpanan, mahasiswa dapat memilih mengunduh bukti pengajuan. Dosen wali menyetujui atau menolak KRS dan memberikan catatan keputusan.


| ID      | Kebutuhan Tugas                                                           |
| ------- | ------------------------------------------------------------------------- |
| SIA-R01 | Mahasiswa dapat melihat jadwal kuliah                                     |
| SIA-R02 | Admin akademik dapat mengelola jadwal kuliah                              |
| SIA-R03 | Mahasiswa dapat mengajukan KRS                                            |
| SIA-R04 | Sistem memvalidasi KRS sebagai bagian pengajuan                           |
| SIA-R05 | Mahasiswa dapat mengunduh bukti jika memilihnya pada konfirmasi pengajuan |
| SIA-R06 | Dosen wali dapat memproses persetujuan atau penolakan KRS                 |


Batas dan asumsi: 
• Pengguna telah terautentikasi. 
• Data mata kuliah, prasyarat, dan jadwal tersedia. 
• Validasi gagal menyebabkan pengajuan belum berhasil tersimpan. 
• Unduh bukti tidak menjadi syarat keberhasilan pengajuan. 
• KRS tersimpan belum berarti disetujui. 
• Pembayaran, pengisian nilai, dan implementasi basis data berada di luar tugas. 


| Aktor          | Tujuan terhadap sistem                    |
| -------------- | ----------------------------------------- |
| Mahasiswa      | Mengajukan KRS, Mengunduh bukti pengajuan |
| Dosen Wali     | Mengvalidasi KRS dan memberikan catatan   |
| Admin Akademik | mengelola jadwal kuliah                   |


|ID Use Case| Nama Use Case             | Aktor Terkait     |Sumber Kebutuhan   |
|-------------------------------------------------------------------------------|
|SIA-UC01   | Lihat Jadwal Kuliah       | Mahasiswa         |SIA-R01            |
|SIA-UC02   | Kelola Jadwal Kuliah      | Admin Akademik    |SIA-R02            |
|SIA-UC03   | Ajukan KRS                | Mahasiswa         |SIA-R03            |
|SIA-UC04   | Validasi KRS              | (System / Include)|SIA-R04            |
|SIA-UC05   | Unduh Bukti Pengajuan KRS | Mahasiswa         |SIA-R05            |
|SIA-UC06   | Proses Keputusan KRS      | Dosen Wali        |SIA-R06            |  