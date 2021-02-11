# Pembuatan Versi

Versi API dibuat dengan versi string yang ditentukan dalam URL dasar yang dapat ditambahkan secara terpisah dari API lain.

Dianjurkan untuk menggunakan API terbaru yang tersedia.

Perubahan yang dianggap kompatibel dengan versi sebelumnya dan tidak memerlukan string versi untuk ditambahkan, diantaranya:

* Menambahkan properti ke objek JSON
* Menambahkan parameter baru
* Mengubah jumlah item yang dihasilkan dalam satu permintaan pencatatan
* Struktur atau panjang pengenal yang dihasilkan oleh API
* Mengubah pesan kesalahan

Perubahan yang dianggap tidak kompatibel dengan versi sebelumnya dan akan membutuhkan versi string untuk ditambahkan, diantaranya:

* Menghapus properti dari objek JSON
* Mengubah struktur URL API

Versi saat ini adalah v1

