# Jenis Konten

Secara default, Petabencana API mengembalikan [JSON](http://www.w3schools.com/json/) untuk semua panggilan dan merespon setiap permintaan POST berformat JSON kecuali ada permintaan format lain. [UTF-8 encoding](https://en.wikipedia.org/wiki/UTF-8) digunakan pada semua permintaan dan respon.

Data geografis yang dipanggil akan dikodekan sebagai [TopoJSON](https://github.com/topojson/topojson/wiki) by default. [GeoJson](http://geojson.org/) juga didukung jika diperlukan, dengan menyertakan `format=topojson dalam panggilan API. Detail lebih lanjut tentang hal ini dapat ditemukan dalam dokumentasi rute API spesifik. Selain TopoJSON dan GeoJSON, kami menyediakan umpan publik dari informasi banjir real-time menggunakan standar` [`Common Alerting Protocol`](https://en.wikipedia.org/wiki/Common_Alerting_Protocol)`.`

