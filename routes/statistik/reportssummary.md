# Stat - Rangkuman Laporan Urun-Daya

Perhitungan laporan urun daya berdasarkan sumber \("qlue" untuk Qlue, "detik" untuk Detik \(Pasangmata\), atau "grasp" untuk laporan dari kombinasi Twitter, Facebook, Telegram dan Website PetaBencana.id\), secara default laporan akan disajikan untuk satu jam terakhir.

## Format Permintaan

| Parameter Kueri | Deskripsi | Format | Wajib |
| :--- | :--- | :--- | :--- |
| admin | Area mana yang laporannya ingin disajikan? \(lihat [Area Didukung](https://docs.petabencana.id/general/area-didukung)\) | String | Tidak |
| timeperiod | Periode waktu berapa lama \(dalam detik\) yang dibutuhkan untuk menyajikan laporan, harus diantara 1 dan 604800 \(1 minggu\) | Number | Tidak |

## GET /stats/getReportsSummary.md

```text
curl "https://data.petabencana.id/stats/reportsSummary?city=jbd"
```

Hasilnya adalah sebagai berikut:

```javascript
{
  "statusCode": 200,
  "result": {
    "type": "Topology",
    "objects": {
      "output": {
        "type": "GeometryCollection",
        "geometries": [
          {
            "type": "Point",
            "properties": {
              "pkey": "5519",
              "created_at": "2016-12-09T21:37:00.000Z",
              "source": "qlue",
              "status": "confirmed",
              "url": null,
              "image_url": "https://lh3.googleusercontent.com/ByClSrW6QhFkBxUhZo0rFt6eiVdvnEHisSzsgjaC9KxdGAQ6CYksTZRA1rcNP9cBGZiv6s4Vp5D8NzkAjPyrBs6c6R4h=s480-c",
              "disaster_type": "flood",
              "report_data": null,
              "tags": {
                "instance_region_code": "jbd",
                "local_area_id": "350"
              },
              "title": " ",
              "text": "Perlu penataan dan dirapihkan @ahokbtp semoga bisa lbh baik, bersih dan teratur"
            },
            "coordinates": [
              0,
              0
            ]
          }
        ]
      }
    },
    "arcs": [],
    "transform": {
      "scale": [
        1,
        1
      ],
      "translate": [
        106.817276,
        -6.138229
      ]
    },
    "bbox": [
      106.817276,
      -6.138229,
      106.817276,
      -6.138229
    ]
  }
}
```

