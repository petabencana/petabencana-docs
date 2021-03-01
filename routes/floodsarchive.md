# Area Banjir/Arsip

Arsip area banjir \(lihat dokumentasi [_endpoint_ Area Banjir](https://docs.petabencana.id/routes/areabanjir)\), disajikan sebagai status banjir maksimum yang tercatat untuk semua daerah yang terdampak banjir dalam periode waktu tertentu. Status maksimum area banjir dicatat di samping id area. Gunakan _endpoint_ Area Banjir untuk mendapatkan batas geospasial dari masing-masing wilayah.

‌Saat ini data yang tersedia hanya untuk wilayah Jakarta.

## Format Permintaan

| Parameter Kueri | Deskripsi | Format | Wajib |
| :--- | :--- | :--- | :--- |
| start | Waktu mulai periode arsip | String dalam format ISO 8601 \(YYYY-MM-DDTHH:mm:ss+ZZZZ | Ya |
| end | Waktu akhir periode arsip | String dalam format ISO 8601 \(YYYY-MM-DDTHH:mm:ss+ZZZZ | Ya |

Perhatikan bahwa zona waktu harus ditentukan sebagai perbedaan waktu +/- UTC yang memerlukan pengkodean karakter HTML \(mis. +0700 menjadi %2B0700\).

## Get /floods/archive

## GET /floods

Daftar semua area terdampak banjir di Jakarta dengan status banjir 1 atau lebih tinggi.

```text
curl "https://data.petabencana.id/floods/archive?start=2017-06-07T00:00:00%2B0700&end=2017-06-08T23:00:00%2B0700"
```

Hasilnya adalah sebagai berikut:

```javascript
    {
        "statusCode": 200,
        "result": [
            {
                "area_id": "509",
                "last_updated": "2017-11-03T22:57:01.387Z",
                "max_state": 1
            },
            {
                "area_id": "510",
                "last_updated": "2017-11-03T22:57:10.463Z",
                "max_state": 4
            }
        ]
    }
```

