<!-- Usecase deskripsi -->
1. SIA-UC07 — Lihat Kalender Akademik
| Elemen                    | SIA-UC07 — Lihat Kalender Akademik                                    |
|---------------------------|-----------------------------------------------------------------------|
|   ID dan nama             | SIA-UC07: Lihat Kalender Akademik                                     |
|   Sumber kebutuhan        | SIA-R07                                                               |
|   Tujuan                  | Menyediakan informasi agenda dan jadwal kegiatan akademik institusi   |
|   Aktor utama             | Civitas Akademika (Mahasiswa dan Dosen)                               |
|   Pemicu                  | Pengguna memilih menu kalender akademik                               |
|   Prasyarat               | Pengguna telah terautentikasi ke dalam sistem                         |
|   Pascakondisi berhasil   | Informasi kalender akademik semester aktif ditampilkan secara lengkap |
|   Pascakondisi gagal      | Informasi kalender akademik tidak berhasil ditampilkan                |
|   Include                 | —                                                                     |
|   Extension point         | —                                                                     |
|   Extend                  | —                                                                     |
|   Collaboration           | —                                                                     |

Alur utama:
| Langkah | Tindakan civitas akademika                | Respons sistem                                                         |
|---------|-------------------------------------------|------------------------------------------------------------------------|
|   1     | Membuka halaman kalender akademik         | Menampilkan pilihan semester/tahun akademik                            |
|   2     | Memilih semester aktif yang ingin dilihat | Menyaring data kegiatan dan agenda resmi institusi                     |
|   3     | Melihat daftar agenda akademik            | Menampilkan jadwal agenda (awal semester, perkuliahan, UTS, UAS, dll.) |

Alur alternatif atau pengecualian:
| Langkah | Kondisi / Variasi                        | Tindakan sistem                                                                          |
|---------|------------------------------------------|------------------------------------------------------------------------------------------|
|   2a    | Data kalender akademik belum diterbitkan | Menampilkan pesan pemberitahuan bahwa kalender akademik semester terpilih belum tersedia |


2. SIA-UC08 — Input Nilai Mata Kuliah
| Elemen                | SIA-UC08 — Input Nilai Mata Kuliah                                                    |
|-----------------------|---------------------------------------------------------------------------------------|
| ID dan Nama           | SIA-UC08: Input Nilai Mata Kuliah                                                     |
| Sumber Kebutuhan      | SIA-R08 dan SIA-R12                                                                   |
| Tujuan                | Menyimpan dan mempublikasikan nilai akhir mahasiswa pada mata kuliah yang diampu      |
| Aktor Utama           | Dosen                                                                                 |
| Pemicu                | Dosen memilih menu penginputan nilai setelah perkuliahan berakhir                     |
| Prasyarat             | Dosen telah terautentikasi dan merupakan pengampu resmi mata kuliah terpilih          |
| Pascakondisi Berhasil | Nilai mata kuliah tersimpan di sistem dan terkonfirmasi untuk dipublikasikan pada KHS |
| Pascakondisi Gagal    | Tidak ada nilai baru yang tersimpan atau diubah di dalam sistem                       |
| Include / Extend      | —                                                                                     |
| Collaboration         | SIA-CO01: Input Nilai Mata Kuliah                                                     |

Alur Utama:
| Langkah | Tindakan dosen                             | Respons sistem                                                                  |
|---------|--------------------------------------------|---------------------------------------------------------------------------------|
|   1     | Membuka halaman penginputan nilai          | Menampilkan daftar mata kuliah yang diampu dosen                                |
|   2     | Memilih mata kuliah dan kelas              | Menampilkan daftar mahasiswa beserta form pengisian nilai                       |
|   3     | Mengisikan nilai untuk tiap mahasiswa      | Menampung isian nilai                                                           |
|   4     | Mengirimkan dan mengonfirmasi simpan nilai | Memeriksa validitas rentang nilai yang diinputkan                               |
|   5     | —                                          | Menyimpan data nilai ke sistem dan mengubah status nilai menjadi Dipublikasikan |
|   6     | Melihat konfirmasi simpan                  | Menampilkan ringkasan status keberhasilan simpan nilai                          |

Alur Alternatif/Pengecualian:
| Langkah | Kondisi / Variasi                             | Tindakan sistem                                                                                                         |
|---------|-----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------|
|   1a    | Dosen bukan pengampu mata kuliah              | Menolak akses penginputan nilai dan menampilkan pesan peringatan. Use case berakhir dalam status gagal                  |
|   4a    | Nilai di luar rentang sah (bukan A-E / 0-100) | Menolak penyimpanan, menandai kolom nilai yang tidak valid, dan meminta dosen mengoreksi isian sebelum disimpan kembali |


3. SIA-UC09 — Lihat KHS
| Elemen                    | SIA-UC09 — Lihat KHS                                                      |
|---------------------------|---------------------------------------------------------------------------|
|   ID dan Nama             | SIA-UC09: Lihat KHS                                                       |
|   Sumber Kebutuhan        | SIA-R09 dan SIA-R12                                                       |
|   Tujuan                  | Menampilkan Kartu Hasil Studi (KHS) mahasiswa untuk semester tertentu     |
|   Aktor Utama             | Mahasiswa                                                                 |
|   Pemicu                  | Mahasiswa memilih menu KHS dan menentukan semester                        |
|   Prasyarat               | Mahasiswa telah terautentikasi                                            |
|   Pascakondisi Berhasil   | Tampilan KHS menampilkan daftar nilai yang sudah berstatus dipublikasikan |
|   Pascakondisi Gagal      | KHS tidak ditampilkan atau menampilkan pesan nilai belum dipublikasikan   |
|   Collaboration           | SIA-CO02: Lihat KHS                                                       |

Alur utama:
| Langkah | Tindakan mahasiswa                  | Respons sistem                                                                |
|---------|-------------------------------------|-------------------------------------------------------------------------------|
|   1     | Membuka halaman KHS                 | Menampilkan pilihan semester                                                  |
|   2     | Memilih semester yang ingin dilihat | Menyaring dan menyusun data nilai mahasiswa untuk semester terpilih           |
|   3     | Melihat tampilan KHS                | Menampilkan rincian mata kuliah dan nilai yang sudah berstatus Dipublikasikan |

Alur alternatif atau pengecualian:
| Langkah | Kondisi / Variasi                            | Tindakan sistem                                                                                 |
|---------|----------------------------------------------|-------------------------------------------------------------------------------------------------|
|   2a    | Nilai semester terpilih belum dipublikasikan | Menampilkan pemberitahuan bahwa nilai untuk semester tersebut belum dipublikasikan secara resmi |


4. SIA-UC10 — Kelola Data Mahasiswa (Use Case Umum)
| Elemen                    | SIA-UC10 — Kelola Data Mahasiswa                                             |
|---------------------------|------------------------------------------------------------------------------|
|   ID dan nama             | SIA-UC10: Kelola Data Mahasiswa                                              |
|   Sumber kebutuhan        | SIA-R10 dan SIA-R11                                                          |
|   Tujuan                  | Mengelola data induk dan profil mahasiswa di dalam sistem                    |
|   Aktor utama             | Admin Akademik                                                               |
|   Pemicu                  | Admin Akademik memilih menu pengelolaan data mahasiswa                       |
|   Prasyarat               | Admin Akademik telah terautentikasi                                          |
|   Pascakondisi berhasil   | Data mahasiswa berhasil terkelola (tertambah, terubah, atau terhapus)        |
|   Pascakondisi gagal      | Data mahasiswa tidak mengalami perubahan                                     |
|   Include                 | —                                                                            |
|   Extension point         | —                                                                            |
|   Extend                  | —                                                                            |
|   Generalization          | Use case umum untuk SIA-UC11 (Tambah), SIA-UC12 (Ubah), dan SIA-UC13 (Hapus) |

Alur utama:
| Langkah | Tindakan admin akademik                    | Respons sistem                                                                                   |
|---------|--------------------------------------------|--------------------------------------------------------------------------------------------------|
|   1     | Membuka halaman pengelolaan data mahasiswa | Menampilkan opsi pengelolaan (Tambah, Ubah, Hapus) beserta daftar mahasiswa                      |
|   2     | Memilih jenis tindakan pengelolaan         | Memanggil dan menjalankan alur spesifik dari use case khusus (SIA-UC11, SIA-UC12, atau SIA-UC13) |
|   3     | Selesai melakukan pengelolaan              | Menampilkan konfirmasi keberhasilan pengelolaan data                                             |


5. SIA-UC11 — Tambah Data Mahasiswa
| Elemen                    | SIA-UC11 — Tambah Data Mahasiswa                         |
|---------------------------|----------------------------------------------------------|
|   ID dan nama             | SIA-UC11: Tambah Data Mahasiswa                          |
|   Sumber kebutuhan        | SIA-R11                                                  |
|   Tujuan                  | Mendaftarkan record data mahasiswa baru ke dalam sistem  |
|   Aktor utama             | Admin Akademik                                           |
|   Pemicu                  | Admin Akademik memilih tombol tambah mahasiswa baru      |
|   Prasyarat               | Admin Akademik telah terautentikasi                      |
|   Pascakondisi berhasil   | Data mahasiswa baru tersimpan dan teregistrasi di sistem |
|   ascakondisi gagal       | Data mahasiswa baru tidak tersimpan                      |
|   Include                 | —                                                        |
|   Extension point         | —                                                        |
|   Extend                  | —                                                        |
|   Generalization          | Use case khusus dari SIA-UC10: Kelola Data Mahasiswa     |

Alur utama:
| Langkah | Tindakan admin akademik                                      | Respons sistem                                            |
|---------|--------------------------------------------------------------|-----------------------------------------------------------|
|   1     | Membuka form tambah mahasiswa                                | Menampilkan formulir isian data mahasiswa baru            |
|   2     | Mengisi data identitas dan akademik (NIM, Nama, Prodi, dll.) | Menampung isian data                                      |
|   3     | Menyimpan data mahasiswa baru                                | Memeriksa kelengkapan dan keunikan NIM                    |
|   4     | —                                                            | Menyimpan data mahasiswa baru ke database                 |
|   5     | Melihat konfirmasi simpan                                    | Menampilkan pesan keberhasilan pendaftaran mahasiswa baru |

Alur alternatif atau pengecualian:
| Langkah | Kondisi / Variasi                        | Tindakan sistem                                                                       |
|---------|------------------------------------------|---------------------------------------------------------------------------------------|
|   3a    | NIM sudah terdaftar / data tidak lengkap | Menolak penyimpanan, menampilkan pesan kesalahan, dan meminta admin memperbarui isian |


6. SIA-UC12 — Ubah Data Mahasiswa
| Elemen                    | SIA-UC12 — Ubah Data Mahasiswa                                            |
|---------------------------|---------------------------------------------------------------------------|
|   ID dan nama             | SIA-UC12: Ubah Data Mahasiswa                                             |
|   Sumber kebutuhan        | SIA-R11                                                                   |
|   Tujuan                  | Memperbarui informasi data mahasiswa yang sudah terdaftar                 |
|   Aktor utama             | Admin Akademik                                                            |
|   Pemicu                  | Admin Akademik memilih opsi ubah pada data mahasiswa terpilih             |
|   Prasyarat               | Admin telah terautentikasi dan data mahasiswa terpilih tersedia di sistem |
|   Pascakondisi berhasil   | Data mahasiswa berhasil diperbarui di sistem                              |
|   Pascakondisi gagal      | Perubahan data mahasiswa tidak tersimpan                                  |
|   Include                 | —                                                                         |
|   Extension point         | —                                                                         |
|   Extend                  | —                                                                         |
|   Generalization          | Use case khusus dari SIA-UC10: Kelola Data Mahasiswa                      |

Alur utama (SIA-UC12 — Ubah Data Mahasiswa):
| Langkah | Tindakan admin akademik | Respons sistem |
| --- | --- | --- |
|   1   | Memilih mahasiswa dari daftar dan menekan Edit/Ubah | Menampilkan form ubah data berisi informasi mahasiswa terpilih |
|   2   | Mengubah informasi data yang diperlukan | Menampung perubahan data |
|   3   | Menyimpan perubahan data | Memeriksa validitas data yang diubah |
|   4   | — | Memperbarui record data mahasiswa pada database |
|   5   | Melihat konfirmasi pembaruan | Menampilkan pesan keberhasilan update data |

Alur alternatif atau pengecualian:
| Langkah | Kondisi / Variasi        | Tindakan sistem                                                   |
|---------|--------------------------|-------------------------------------------------------------------|
|   3a    | Format data tidak sesuai | Menolak pembaruan data dan menampilkan pesan peringatan perbaikan |


7. SIA-UC13 — Hapus Data Mahasiswa
| Elemen                    | SIA-UC13 — Hapus Data Mahasiswa                                                        |
|---------------------------|----------------------------------------------------------------------------------------|
|   ID dan nama             | SIA-UC13: Hapus Data Mahasiswa                                                         |
|   Sumber kebutuhan        | SIA-R11                                                                                |
|   Tujuan                  | Menghapus data mahasiswa yang tidak lagi aktif dan tidak memiliki rekam akademik aktif |
|   Aktor utama             | Admin Akademik                                                                         |
|   Pemicu                  | Admin Akademik memilih opsi hapus pada data mahasiswa terpilih                         |
|   Prasyarat               | Admin telah terautentikasi; data mahasiswa terpilih tidak memiliki data akademik aktif |
|   Pascakondisi berhasil   | Data mahasiswa terhapus dari sistem                                                    |
|   Pascakondisi gagal      | Data mahasiswa tetap tersimpan dan tidak terhapus                                      |
|   Include                 | —                                                                                      |
|   Extension point         | —                                                                                      |
|   Extend                  | —                                                                                      |
|   Generalization          | Use case khusus dari SIA-UC10: Kelola Data Mahasiswa                                   |

Alur utama:
| Langkah | Tindakan admin akademik                    | Respons sistem                                                |
|---------|--------------------------------------------|---------------------------------------------------------------|
|   1     | Membuka daftar data mahasiswa              | Menampilkan daftar seluruh mahasiswa                          |
|   2     | Memilih mahasiswa dan menekan tombol Hapus | Menampilkan konfirmasi penghapusan data                       |
|   3     | Mengonfirmasi penghapusan                  | Memeriksa apakah mahasiswa masih memiliki data akademik aktif |
|   4     | —                                          | Menghapus record data mahasiswa dari database                 |
|   5     | Melihat konfirmasi                         | Menampilkan pesan bahwa data mahasiswa berhasil dihapus       |

Alur alternatif atau pengecualian:
| Langkah | Kondisi / Variasi                            | Tindakan sistem                                                                                                                       |
|---------|----------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|
|   3a    | Mahasiswa masih memiliki data akademik aktif | Menolak penghapusan, menampilkan pesan error bahwa data terikat aturan integritas sistem, lalu mengakhiri use case dalam status gagal |