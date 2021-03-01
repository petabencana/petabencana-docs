# Area Banjir/Timeseries

Timeseries area terdampak banjir \(lihat dokumentasi [_endpoint_ Area Banjir](https://docs.petabencana.id/routes/areabanjir)\), disajikan sebagai penghitungan area terdampak banjir setiap jam dalam periode waktu tertentu. Hitungan dicatat dengan stempel waktu per jam dalam format ISO8601 pada UTC + 0. 

Saat ini data yang tersedia hanya untuk wilayah Jakarta.

## Format Permintaan

| Parameter Kueri | Deskripsi | Format | Wajib |
| :--- | :--- | :--- | :--- |
| start | Waktu mulai periode _timeseries_ | String in ISO 8601 format \(YYYY-MM-DDTHH:mm:ss+ZZZZ | Ya |
| end | Waktu akhir periode _timeseries_ | String in ISO 8601 format \(YYYY-MM-DDTHH:mm:ss+ZZZZ | Ya |

Perhatikan bahwa zona waktu harus ditentukan sebagai perbedaan waktu +/- UTC yang memerlukan pengkodean karakter HTML \(mis. +0700 menjadi% 2B0700\).

## Get /floods/timeseries

## GET /floods

Daftar semua area terdampak banjir di Jakarta dengan status banjir 1 atau lebih tinggi.

```text
curl "https://data.petabencana.id/floods/timeseries?start=2017-11-20T11%3A00%3A00-0500&end=2017-11-20T15%3A00%3A00-0500"
```

Hasilnya adalah sebagai berikut:

```javascript
    {
        "statusCode": 200,
        "result": [
            {
                "ts": "2017-11-20T16:00:00.000Z",
                "count": "0"
            },
            {
                "ts": "2017-11-20T17:00:00.000Z",
                "count": "0"
            },
            {
                "ts": "2017-11-20T18:00:00.000Z",
                "count": "0"
            },
            {
                "ts": "2017-11-20T19:00:00.000Z",
                "count": "0"
            },
            {
                "ts": "2017-11-20T20:00:00.000Z",
                "count": "0"
            }
        ]
    }
```

