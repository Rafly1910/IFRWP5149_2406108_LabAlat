a. Ajukan KRS

|   Elemen                 |   SIA-UC03—AjukanKRS                                                          |
|   Tujuan                 |   Menghasilkan pengajuan KRS yang tersimpan untuk diproses dosen wali         |
|   Aktorutama             |   Mahasiswa                                                                   |
|   Sumber kebutuhan       |   SIA-R03, SIA-R04, dan SIA-R05                                               |
|   Pemicu                 |   Mahasiswa memilih fungsi pengajuan KRS                                      |
|   Prasyarat              |   Mahasiswa telah terautentikasi; data mata kuliah dan jadwal kuliah tersedia |
|   Pascakondisi berhasil  |   Pengajuan KRS tersimpan dengan status Menunggu Persetujuan Dosen Wali       |
|   Pascakondisi gagal     |   Tidak ada pengajuan KRS baru yang berhasil tersimpan                        |
|   Include                |   SIA-UC04 — Validasi KRS                                                     |
|   Extension point        |   Bukti pengajuan KRS tersedia, pada langkah 6                                |
|   Extend                 |   SIA-UC05 jika [mahasiswa memilih unduh]                                     |


Alur Utama :
Langkah     Tindakan mahasiswa                          Respons sistem  
|------------------------------------------------------------------------------------------------------------------------------------------------|
1           Membuka pengajuan KRS                       Menampilkan formulir pengajuan beserta daftar mata kuliah dan jadwal   
2           Memilih mata kuliah yang akan diambil       Menampung pilihan mata kuliah   
3           Mengirim pengajuan KRS                      Memeriksa kelengkapan data isian   
4           —                                           Menjalankan SIA-UC04   
5           —                                           Jika validasi berhasil, menyimpan pengajuan KRS berstatus Menunggu Persetujuan Dosen Wali   
6           Melihat konfirmasi pengajuan                Menampilkan pesan konfirmasi dan status; mencapai extension point   
7           Mengakhiri pengajuan                        Menutup proses pengajuan KRS


b. Validasi KRS

|   Elemen                 |   SIA-UC04 — Validasi KRS                                                                              |
|   Tujuan                 |   Memastikan pengajuan KRS memenuhi kelengkapan, prasyarat mata kuliah, dan tidak ada benturan jadwal  |
|   Aktorutama             |   Sistem (dipanggil oleh SIA-UC03)                                                                     |
|   Sumber kebutuhan       |   SIA-R04                                                                                              |
|   Pemicu                 |   Pemanggilan otomatis saat mahasiswa mengirim pengajuan KRS pada SIA-UC03                             |
|   Prasyarat              |   Data mata kuliah yang dipilih pada pengajuan KRS telah dikirimkan oleh SIA-UC03                      |
|   Pascakondisi berhasil  |   Pengajuan KRS terkonfirmasi valid dan siap disimpan                                                  |
|   Pascakondisi gagal     |   Validasi KRS mengembalikan status gagal beserta rincian alasannya ke SIA-UC03                        |
|   Include                |   -                                                                                                    |
|   Extension point        |   -                                                                                                    |
|   Extend                 |   -                                                                                                    |


Alur Utama :
Langkah     Tindakan aktor          Respons sistem  
|----------------------------------------------------------------------------------------------------------------|
1           -                       Memeriksa kelengkapan isian mata kuliah yang dipilih   
2           -                       Memeriksa status pemenuhan prasyarat untuk tiap mata kuliah yang dipilih   
3           -                       Memeriksa ada atau tidaknya benturan jadwal antar mata kuliah   
4           -                       Mengembalikan respons validasi berhasil ke use case pemanggil (SIA-UC03)   



c. Unduh Bukti pengajuanKRS

|   Elemen                 |   SIA-UC05 — Unduh Bukti Pengajuan KRS                                              |
|   Tujuan                 |   Menyediakan berkas bukti pengajuan KRS bagi mahasiswa                             |
|   Aktorutama             |   Mahasiswa                                                                         |
|   Sumber kebutuhan       |   SIA-R05                                                                           |
|   Pemicu                 |   Mahasiswa memilih opsi unduh bukti pada konfirmasi pengajuan KRS                  |
|   Prasyarat              |   Extension point pada SIA-UC03 tercapai (pengajuan KRS telah berhasil tersimpan)   |
|   Pascakondisi berhasil  |   Berkas bukti pengajuan KRS terunduh ke perangkat mahasiswa                        |
|   Pascakondisi gagal     |   Berkas bukti tidak terunduh, namun status pengajuan KRS tetap tersimpan           |
|   Include                |   -                                                                                 |
|   Extension point        |   -                                                                                 |
|   Extend                 |   -                                                                                 |


Alur Utama :
Langkah     Tindakan Mahasiswa                              Respons sistem
|-------------------------------------------------------------------------------------------------------------------------|  
1           Memilih opsi unduh bukti pengajuan              Menampung permintaan unduh   
2           -                                               Menyusun dan menggenerasi berkas bukti pengajuan KRS   
3           -                                               Mengunduhkan berkas bukti pengajuan KRS ke perangkat mahasiswa   


d. Proses keputusan KRS

|   Elemen                 |   SIA-UC06 — Proses Keputusan KRS                                                                          |
|   Tujuan                 |   Menetapkan status persetujuan atau penolakan pengajuan KRS mahasiswa disertai catatan keputusan          |
|   Aktorutama             |   Dosen Wali                                                                                               |
|   Sumber kebutuhan       |   SIA-R06                                                                                                  |
|   Pemicu                 |   Dosen Wali memilih daftar pengajuan KRS mahasiswa bimbingan                                              |
|   Prasyarat              |   Dosen Wali telah terautentikasi dan terdapat pengajuan KRS berstatus Menunggu Persetujuan                |
|   Pascakondisi berhasil  |   Status pengajuan KRS tersimpan dengan status baru (Disetujui atau Ditolak) beserta catatan keputusan     |
|   Pascakondisi gagal     |   Status pengajuan KRS tidak mengalami perubahan                                                           |
|   Include                |   -                                                                                                        |
|   Extension point        |   -                                                                                                        |
|   Extend                 |   -                                                                                                        |


Alur Utama :
Langkah     Tindakan dosen wali                                     Respons sistem  
|----------------------------------------------------------------------------------------------------------------------------------------------------|
1           Membuka daftar pengajuan KRS mahasiswa bimbingan        Menampilkan daftar pengajuan KRS berstatus Menunggu Persetujuan   
2           Memilih salah satu pengajuan KRS                        Menampilkan detail rincian mata kuliah yang diajukan      
3           Meninjau rincian pengajuan KRS                          -   
4           Memilih opsi Setujui dan memasukkan catatan keputusan   Menampung keputusan dan catatan  
5           —                                                       Memperbarui dan menyimpan status KRS menjadi Disetujui beserta catatan keputusan   
6           Mengakhiri peninjauan                                   Menampilkan konfirmasi status terbaru   
