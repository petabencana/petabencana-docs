# Kartu Laporan

Kartu laporan PetaBencana untuk kejadian bencana. Catatan: [autentikasi](https://docs.petabencana.id/general/authentication) diperlukan untuk membuat pembaruan pada kartu.

## Format Permintaan

| Parameter URL | Deskripsi | Format | Wajib |
| :--- | :--- | :--- | :--- |
| cardId | Pengenal unik dari kartu yang ingin kita gunakan, dihasilkan oleh sistem ketika kartu awal dibuat \(wajib\) | String \(7 sampai 14 karakter\) | Ya |

| Atribut | Deskripsi | Format | Wajib |
| :--- | :--- | :--- | :--- |
| card\_data | Data pengguna yang dikumpulkan dalam antarmuka kartu | JSON | Ya |
| text | Deskripsi dari kejadian bencana | String | Tidak |
| image\_id | Pengenal gambar kartu terkait | String | Tidak |
| created\_at | Tanggal dan jam kartu dibuat | Date \([ISO 8601](http://www.iso.org/iso/home/standards/iso8601.htm)\) | Ya |
| location | Lokasi geografis dari kejadian bencana | Lat/Long in [ESPG:4326](http://spatialreference.org/ref/epsg/wgs-84/) | Ya |

### Catatan untuk card\_data

Data kartu membutuhkan objek `report_type` untuk ada. Dimana`disaster_type` diatur ke 'flood' dan objek `flood_depth` juga harus ada di sebelah `report_type`. Jika `disaster_type` adalah 'prep' maka `report_type` harus menjadi salah satu jenis seperti yang ditentukan di server config.js.

Misalnya kartu dengan data banjir termasuk flood\_depth:

```javascript
  "disaster_type": "flood",
  "card_data":{
    "report_type": "flood",
    "flood_depth": 50
  }
```

Atau, kartu dengan laporan data pra-banjir tentang saluran pembuangan.

```javascript
  "disaster_type": "prep",
  "card_data":{
    "report_type":"drain"
  }
```

## GET /cards/:cardId

Dapatkan detail kartu:

Berikut adalah panggilan sederhana untuk GET kartu:

```text
curl -X GET -H "X-Api-Key: API_KEY_GOES_HERE" "https://data.petabencana.id/cards/abcdefg"
```

Kartu telah ditemukan:

```javascript
{
  "statusCode": 200,
  "result": {
    "pkey": "2",
    "card_id": "abcdefg",
    "username": "user",
    "network": "test",
    "language": "en",
    "received": true,
    "report_id": "1"
  }
}
```

Kartu tidak ada:

```javascript
{
  "statusCode": 404,
  "found": false,
  "result": null
}
```

## PUT /cards/:cardId

Memperbarui kartu dengan detail laporan kejadian bencana: 

Berikut adalah panggilan sederhana untuk PUT kartu:

```text
curl -X PUT -H "X-Api-Key: API_KEY_GOES_HERE" -d '{
    "text": "test card",
    "disaster_type": "flood"
    "card_data":
      {
        "report_type": "flood",
        "flood_depth": 101
      },
    "created_at":"2016-12-09T11:32:52.011Z",
    "location": {
        "lat": -6.149531,
        "lng": 106.869342
    }
}' "https://data.petabencana.id/cards/abcdefg"
```

Kartu telah berhasil dibuat:

```javascript
{
  "statusCode": 200,
  "cardId": "abcdefg",
  "created": true
}
```

Kartu tidak ada:

```javascript
{
  "statusCode": 404,
  "cardId": "abcdefg",
  "message": "No card exists with id 'abcdefg'"
}
```

Laporan sudah ada untuk kartu:

```javascript
{
  "statusCode": 409,
  "cardId": "abcdefg",
  "message": "Report already received for card 'abcdefg'"
}
```

## GET /cards/:cardId/images

GET URL S3 yang ditandai untuk mengunggah laporan kartu, ini harus dilakukan setelah laporan kartu dibuat dan hanya satu gambar yang ada untuk kartu tertentu.

CATATAN: Setelah gambar dikirim, proses sisi server mengkompres gambar ke ukuran standar dan mungkin ada sedikit jeda waktu beberapa detik sebelum gambar tampil secara "live".

Berikut ini panggilan sederhana GET untuk URL S3 baru yang telah ditandai untuk unggahan gambar:

```text
curl -X GET \
  https://api-server-dev.riskmap.in/cards/HJID8CWN-/images
```

URL S3 yang telah ditandai berhasil dibuat:

```javascript
{"signedRequest":"https://riskmap-image-uploads.s3.ap-south-1.amazonaws.com/originals/BJbTHR-Vb.jpg?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAJFMR3NR7BXZ5X7DA%2F20170629%2Fap-south-1%2Fs3%2Faws4_request&X-Amz-Date=20170629T012002Z&X-Amz-Expires=900&X-Amz-Signature=ad10a53555205fa18ecfa07da52eb0349ed1c8bda66fe2de0fa9c445c61b7c62&X-Amz-SignedHeaders=host","url":"https://s3.ap-south-1.amazonaws.com/riskmap-image-uploads/originals/BJbTHR-Vb.jpg"}
```

