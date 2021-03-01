# Laporan Urun-Daya/Timeseries

Rangkaian waktu laporan banjir \(lihat dokumentasi _endpoint_ [Laporan Urun-Daya](https://docs.petabencana.id/routes/laporan-urun-daya)\), disajikan sebagai penghitungan laporan banjir setiap jam dalam periode waktu tertentu. Hitungan dicatat di samping stempel waktu per jam dalam format ISO8601 pada UTC + 0.

## Format Permintaan

| Parameter Kueri | Deskripsi | Format | Wajib |
| :--- | :--- | :--- | :--- |
| start | Waktu mulai periode _timeseries_ | String dalam format ISO 8601 \(YYYY-MM-DDTHH:mm:ss+ZZZZ | Ya |
| end | Waktu akhir periode _timeseries_ | String dalam format ISO 8601 \(YYYY-MM-DDTHH:mm:ss+ZZZZ | Ya |

Perhatikan bahwa zona waktu harus ditentukan sebagai perbedaan waktu +/- UTC yang memerlukan pengkodean karakter HTML \(mis. +0700 menjadi% 2B0700\).

## Get /reports/timeseries

## GET /reports/timeseries

GET \(mendapatkan\) hitungan laporan banjir dalam periode waktu tertentu.

```text
    curl "https://data.petabencana.id/reports/timeseries?start=2017-11-26T12%3A00%3A00%2B0700&end=2017-11-26T15%3A00%3A00%2B0700"
```

Hasilnya adalah sebagai berikut:

```javascript
    {
        "statusCode": 200,
        "result": [
            {
                "ts": "2017-11-26T05:00:00.000Z",
                "count": "0"
            },
            {
                "ts": "2017-11-26T06:00:00.000Z",
                "count": "0"
            },
            {
                "ts": "2017-11-26T07:00:00.000Z",
                "count": "2"
            },
            {
                "ts": "2017-11-26T08:00:00.000Z",
                "count": "3"
            }
        ]
    }
```

