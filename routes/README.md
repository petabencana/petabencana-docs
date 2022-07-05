# Open API

API Data PetaBencana menyediakan sejumlah endpoint untuk Anda dapat berinteraksi dengan sistem. Ringkasan di bawah ini adalah detail lengkap dari setiap endpoint dan contoh hasil permintaan dapat ditemukan di halaman berikutnya.

## Ringkasan _Endpoint_

Detail dari setiap endpoint adalah sebagai berikut:

| Endpoint            | Deskripsi                                  | Metode  | Terproteksi |
| ------------------- | ------------------------------------------ | ------- | ----------- |
| /admin              | Batas Administrasi                         | GET     | Tidak       |
| /floodgauges        | <p>Alat Ukur Tinggi</p><p>Muka Air</p>     | GET,PUT | Tidak       |
| /floods             | Genangan Banjir                            | GET     | Sebagian    |
| /floods/archive     | Arsip Genangan Banjir                      | GET     | Tidak       |
| /floods/timeseries  | <p>Time Series </p><p>Genangan Banjir</p>  | GET     | Tidak       |
| /infrastructure     | Infrastruktur                              | GET     | Tidak       |
| /reports            | Laporan Urun-daya                          | GET     | Tidak       |
| /reports/archive    | <p>Arsip Laporan</p><p>Urun-daya</p>       | GET     | Tidak       |
| /reports/timeseries | <p>Time Series Laporan</p><p>Urun-daya</p> | GET     | Tidak       |
| /stats/\*           | Statistik Ringkasan                        | GET     | Tidak       |
