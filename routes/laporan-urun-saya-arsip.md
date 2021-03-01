# Laporan Urun-Daya/Arsip

Arsip laporan banjir \(lihat dokumentasi _endpoint_ [Laporan Urun-Daya](https://docs.petabencana.id/routes/laporan-urun-daya)\), disajikan sebagai JSON berupa semua laporan banjir yang diterima dalam periode waktu tertentu.

## Format Permintaan

| Parameter Kueri | Deskripsi | Format | Wajib |
| :--- | :--- | :--- | :--- |
| start | Waktu mulai periode arsip | String dalam format ISO 8601 \(YYYY-MM-DDTHH:mm:ss+ZZZZ | Ya |
| end | Waktu akhir periode arsip | String dalam format ISO 8601 \(YYYY-MM-DDTHH:mm:ss+ZZZZ | Ya |
| city | Area mana yang laporannya ingin disajikan? \(lihat [Area Didukung](https://docs.petabencana.id/general/area-didukung)\) | String | Tidak |
| geoformat | Format apa yang diperlukan untuk hasil geografis? \(salah satu antara `topojson`, `geojson`, _default_ ke `topojson`\) | String | Tidak |

Perhatikan bahwa zona waktu harus ditentukan sebagai perbedaan waktu +/- UTC yang memerlukan pengkodean karakter HTML \(mis. +0700 menjadi% 2B0700\).

## Get /reports/archive

## GET /reports

Daftar laporan banjir di Jabodetabek yang diterima dalam jangka waktu tertentu

```text
curl "https://data.petabencana.id/reports/archive?start=2017-12-04T00%3A00%3A00%2B0700&end=2017-12-06T05%3A00%3A00%2B0700&geoformat=geojson"
```

Hasilnya adalah sebagai berikut:

```javascript
{
    "statusCode": 200,
    "result": {
        "type": "FeatureCollection",
        "features": [
            {
                "type": "Feature",
                "geometry": {
                    "type": "Point",
                    "coordinates": [
                        106.815842,
                        -6.183179
                    ]
                },
                "properties": {
                    "pkey": "0001",
                    "created_at": "2017-12-04T09:51:00.000Z",
                    "source": "qlue",
                    "status": "confirmed",
                    "url": null,
                    "image_url": null,
                    "disaster_type": "flood",
                    "report_data": null,
                    "tags": {
                        "instance_region_code": "jbd",
                        "local_area_id": "782"
                    },
                    "title": " ",
                    "text": "#flood report"
                }
            }
          ]
        }
      }
```

