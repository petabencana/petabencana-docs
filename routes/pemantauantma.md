# Pemantauan TMA

Laporan pemantauan tinggi muka air secara _live_, secara default laporan akan ditampilkan untuk satu jam terakhir.

## Format Permintaan

| Parameter Kueri | Deskripsi | Format | Wajib |
| :--- | :--- | :--- | :--- |
| admin | Area mana yang infrastrukturnya ingin disediakan? \(saat ini hanya mendukung`ID-JK`\) | String | Tidak |
| format | Format apa yang diperlukan dari hasil yang diberikan? \(tersedia secara default dalam `json`\) | String | Tidak |
| geoformat | Format apa yang diperlukan untuk hasil geografis? \(salah satu antara `topojson`, `geojson`, default ke `topojson`\) | String | Tidak |

## GET /floodgauges

Daftar semua laporan alat ukur tinggi muka air saat ini untuk Jakarta.

```text
curl "https://data.petabencana.id/floodgauges?admin=ID-JK"
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
              "gaugeid": "TMA00001",
              "gaugenameid": "Bendung Katulampa",
              "observations": [
                {
                  "f1": "2016-12-09T04:00:00+00:00",
                  "f2": 30,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T05:00:00+00:00",
                  "f2": 30,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T06:00:00+00:00",
                  "f2": 30,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T07:00:00+00:00",
                  "f2": 30,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T08:00:00+00:00",
                  "f2": 40,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T09:00:00+00:00",
                  "f2": 40,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T10:00:00+00:00",
                  "f2": 40,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T11:00:00+00:00",
                  "f2": 40,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T12:00:00+00:00",
                  "f2": 40,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T13:00:00+00:00",
                  "f2": 40,
                  "f3": 4,
                  "f4": "SIAGA IV "
                }
              ]
            },
            "coordinates": [
              6271,
              0
            ]
          },
          {
            "type": "Point",
            "properties": {
              "gaugeid": "TMA00002",
              "gaugenameid": "Pos Depok",
              "observations": [
                {
                  "f1": "2016-12-09T04:00:00+00:00",
                  "f2": 100,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T05:00:00+00:00",
                  "f2": 100,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T06:00:00+00:00",
                  "f2": 100,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T07:00:00+00:00",
                  "f2": 100,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T08:00:00+00:00",
                  "f2": 100,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T09:00:00+00:00",
                  "f2": 100,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T10:00:00+00:00",
                  "f2": 100,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T11:00:00+00:00",
                  "f2": 95,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T12:00:00+00:00",
                  "f2": 95,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T13:00:00+00:00",
                  "f2": 95,
                  "f3": 4,
                  "f4": "SIAGA IV "
                }
              ]
            },
            "coordinates": [
              5354,
              3943
            ]
          },
          // etc. etc. //
          {
            "type": "Point",
            "properties": {
              "gaugeid": "TMA00012",
              "gaugenameid": "Waduk Pluit",
              "observations": [
                {
                  "f1": "2016-12-09T04:00:00+00:00",
                  "f2": -165,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T05:00:00+00:00",
                  "f2": -170,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T06:00:00+00:00",
                  "f2": -175,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T07:00:00+00:00",
                  "f2": -175,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T08:00:00+00:00",
                  "f2": -175,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T09:00:00+00:00",
                  "f2": -175,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T10:00:00+00:00",
                  "f2": -175,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T11:00:00+00:00",
                  "f2": -175,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T12:00:00+00:00",
                  "f2": -175,
                  "f3": 4,
                  "f4": "SIAGA IV "
                },
                {
                  "f1": "2016-12-09T13:00:00+00:00",
                  "f2": -170,
                  "f3": 4,
                  "f4": "SIAGA IV "
                }
              ]
            },
            "coordinates": [
              4559,
              9999
            ]
          }
        ]
      }
    },
    "arcs": [],
    "transform": {
      "scale": [
        0.00002272427242724299,
        0.000052198219821982215
      ],
      "translate": [
        106.69416,
        -6.63304
      ]
    },
    "bbox": [
      106.69416,
      -6.63304,
      106.92138,
      -6.11111
    ]
  }
}
```

