# Laporan Urun-Daya

Laporan bencana urun daya secara realtime, secara default laporan akan disajikan selama periode satu jam terakhir.

## Format Permintaan

| Parameter Kueri | Deskripsi                                                                                                                                                                         | Format | Wajib |
| --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------ | ----- |
| admin           | Area mana yang laporannya ingin disajikan? (lihat [Area Didukung](https://docs.petabencana.id/general/area-didukung))                                                             | String | Tidak |
| format          | Format apa yang diperlukan dari hasil yang diberikan? (tersedia secara _default_ dalam `json`)                                                                                    | String | Tidak |
| geoformat       | Format apa yang diperlukan untuk hasil geografis? (salah satu antara `topojson`, `geojson`, _default_ ke `topojson`)                                                              | String | Tidak |
| disaster        | Jenis bencana apa yang datanya ingin disajikan? (salah satu antara `flood, earthquake, fire, haze, wind volcano, secara default,` secara default menampilkan semua jenis bencana) | String | Tidak |
| timeperiod      | Periode waktu berapa lama (dalam detik) yang dibutuhkan untuk menyajikan laporan, harus diantara 1 dan 604800 (1 minggu)                                                          | Number | Tidak |

## GET /reports

Daftar semua laporan banjir terkini untuk seluruh Indonesia

```
curl --user-agent "YOUR-UA-STRING" "https://api.petabencana.id/reports"
```

Daftar semua laporan banjir terkini untuk Jakarta (menerapkan parameter kueri admin, lihat [Kode Wilayah](../general/area-didukung.md) untuk melihat data dari provinsi lain)

```
curl --user-agent "YOUR-UA-STRING" "https://api.petabencana.id/reports?admin=ID-JK"
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
