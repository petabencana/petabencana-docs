# Kode Eror

Petabencana menggunakan [Kode Status HTTP](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes) standar untuk mengkomunikasikan eror beserta pesan eror berformat json yang memberikan lebih banyak informasi tentang penyebabnya. Kode-kode utama yang digunakan adalah sebagai berikut:

Kode Eror 4xx

Eror yang dimulai dengan angka 4 biasanya menunjukkan masalah dari sisi pengguna yang harus diselesaikan sebelum meminta ulang layanan, diantaranya:

* **400 Bad Request** - biasanya disebabkan oleh parameter kueri yang salah, misalnya `"child \"type\" gagal karena [\"type\"` harus salah satu dari `[floodgates, pumps, waterways]]"`
* **403 Forbidden** - token autentikasi tidak valid
* **404 Not Found** - sumber daya tidak ditemukan, kemungkinan akibat dari endpoint yang salah atau mencoba mengambil catatan misalnya, sebuah laporan, yang tidak ada
* **409 Conflict** - sumber daya ada tetapi jika permintaan itu diizinkan, konflik akan terjadi di dalam sistem, misalnya, mengajukan laporan untuk kartu di mana laporan sudah ada
* **415 Unsupported Media Type** - file yang sedang diunggah tidak didukung oleh sistem - ini biasanya berarti file biner seperti gambar sedang diunggah tetapi Jenis Konten dengan jenis MIME terkait \(misalnya `Image / jpeg`\) belum didukung
* **429 Too Many Requests** - Anda telah melampaui kuota per detik atau per hari

## Kode Error 5xx

Eror yang dimulai dengan angka 5 biasanya menunjukkan kesalahan dari sisi server, diantaranya:

* **500 Internal Server Error** - kesalahan penampung-semua yang menunjukkan bahwa ada sesuatu yang gagal di sisi server
* **503 Service Unavailable** - layanan tidak aktif dan tidak dapat menanggapi permintaan



