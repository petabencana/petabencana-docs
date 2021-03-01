# Infrastruktur

Lokasi infrastruktur lokal seperti pintu air \(`floodgates`\), pompa \(`pumps`\) dan saluran air \(`waterways`\).

## Format Permintaan

| Parameter URL | Deskripsi | Format | Wajib |
| :--- | :--- | :--- | :--- |
| type | Tipe infrastruktur apa yang ingin diperoleh daftarnya? \(salah satu antara `floodgates`, `pumps`, `waterways`\) | String | Yes |

| Parameter Kueri | Deskripsi | Format | Wajib |
| :--- | :--- | :--- | :--- |
| city | Kota mana yang ingin diperoleh data infrastrukturnya? \(saat ini hanya mendukung `ID-JK`\) | String | Tidak |
| format | Format apa yang diperlukan dari hasil yang diberikan? \(tersedia secara _default_ dalam `json`\) | String | Tidak |
| geoformat | What format should geographic results use \(one of `topojson`, `geojson` defaults to `topojson`\) Format apa yang diperlukan untuk hasil geografis? \(salah satu antara `topojson`, `geojson`, _default_ ke `topojson`\) | String | Tidak |

## GET /infrastructure/:type

Menyajikan daftar pompa di Jakarta.

```text
curl "https://data.petabencana.id/infrastructure/pumps?admin=ID-JK"
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
              "name": "PA Marina"
            },
            "coordinates": [
              7164,
              7352,
              0
            ]
          },
          {
            "type": "Point",
            "properties": {
              "name": "Pompa Waduk Setia Budi Barat"
            },
            "coordinates": [
              5312,
              5077,
              0
            ]
          },
          // etc. etc. //
          {
            "type": "Point",
            "properties": {
              "name": "Pompa UP Senen"
            },
            "coordinates": [
              6143,
              6544,
              0
            ]
          }
        ]
      }
    },
    "arcs": [],
    "transform": {
      "scale": [
        0.000020651319451945148,
        0.000020217245084508508
      ],
      "translate": [
        106.7188310623,
        -6.3060956581
      ]
    },
    "bbox": [
      106.7188310623,
      -6.3060956581,
      106.9253236055,
      -6.1039434245
    ]
  }
}
```

