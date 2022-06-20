# Umpan

Petabencana memanfaatkan umpan data dari sejumlah sumber pihak ketiga. Endpoint ini memungkinkan pembuatan data ke dalam sistem untuk pengguna yang berwenang. Catatan: [autentikasi](https://docs.petabencana.id/general/authentication) diperlukan untuk mengirim data melalui endpoint /feeds \(/umpan\).

## POST /feeds/qlue

Menambahkan laporan ke sistem dari [Qlue](https://www.qlue.co.id/). Atribut-atribut yang didukung untuk laporan Qlue:

| Atribut | Deskripsi | Format | Wajib |
| :--- | :--- | :--- | :--- |
| post\_id | Pengenal unik untuk laporan Qlue | Integer | Ya |
| created\_at | Tanggal dan jam kartu dibuat | Date \([ISO 8601](http://www.iso.org/iso/home/standards/iso8601.htm)\) | Ya |
| title | Judul laporan yang dimasukkan | String | Tidak |
| text | Deskripsi dari kejadian bencana | String | Tidak |
| image\_url | URL dari gambar terkait | String | Tidak |
| qlue\_city | Dari area mana laporan berasal? \(lihat Area Didukung\) | String | Ya |
| disaster\_type | Jenis bencana apa yang dilaporkan? \(Saat ini hanya mendukung bencana `flood /`banjir\) | String | Ya |
| location | Lokasi geografis dari kejadian bencana | Lat/Long in [ESPG:4326](http://spatialreference.org/ref/epsg/wgs-84/) | Ya |

Berikut adalah panggilan sederhana untuk POST laporan baru dari Qlue:

```text
curl -X POST -H "X-Api-Key: API_KEY_GOES_HERE" -d '{
    "post_id":1234567802,
    "created_at":"2016-12-09T11:32:52.011Z",
    "image_url":"http://myimg",
    "qlue_city":"jabodetabek",
    "disaster_type":"flood",
    "text":"A big flood",
    "location": {
        "lat": -6.149531,
        "lng": 106.869342
    }
}' "https://data.petabencana.id/feeds/qlue"
```

Laporan telah berhasil dibuat:

```javascript
{
  "post_id": 1234567802,
  "created": true
}
```

Permintaan telah berhasil namun laporannya sudah ada:

```javascript
{
  "post_id": 1234567802,
  "created": false,
  "message": "1234567802 already exists in reports table"
}
```

