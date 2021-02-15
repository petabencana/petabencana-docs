# Batas Administrasi

PetaBencana mendukung seluruh provinsi di Indonesia yang dibedakan berdasarkan wilayah geografis. Endpoint ini akan mengembalikan kota yang didukung beserta batas geografisnya.

## Format Permintaan

| Parameter Kueri | Deskripsi | Format | Wajib |
| :--- | :--- | :--- | :--- |
| format | Format apa yang diperlukan dari hasil yang diberikan? \(salah satu `json`, _default_ ke `json`\) | String | Tidak |
| geoformat | Format apa yang diperlukan untuk hasil geografis? \(salah satu antara `topojson`, `geojson` _default_ ke `topojson`\) | String | Tidak |

## GET /cities

Menampilkan semua kota dalam format default \(topojson\).

```text
curl "https://data.petabencana.id/cities"
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
            "type": "Polygon",
            "properties": {
              "code": "jbd",
              "name": "Jabodetabek"
            },
            "arcs": [
              [
                0
              ]
            ]
          },
          {
            "type": "Polygon",
            "properties": {
              "code": "bdg",
              "name": "Bandung"
            },
            "arcs": [
              [
                1
              ]
            ]
          },
          {
            "type": "Polygon",
            "properties": {
              "code": "sby",
              "name": "Surabaya"
            },
            "arcs": [
              [
                2
              ]
            ]
          }
        ]
      }
    },
    "arcs": [
      [
        [
          0,
          4891
        ],
        [
          1061,
          0
        ],
        [
          0,
          5108
        ],
        [
          -1061,
          0
        ],
        [
          0,
          -5108
        ]
      ],
      [
        [
          1357,
          2305
        ],
        [
          857,
          0
        ],
        [
          0,
          2976
        ],
        [
          -857,
          0
        ],
        [
          0,
          -2976
        ]
      ],
      [
        [
          9031,
          0
        ],
        [
          968,
          0
        ],
        [
          0,
          3207
        ],
        [
          -968,
          0
        ],
        [
          0,
          -3207
        ]
      ]
    ],
    "transform": {
      "scale": [
        0.0006552455245524552,
        0.000167006700670067
      ],
      "translate": [
        106.48,
        -7.5499
      ]
    },
    "bbox": [
      106.48,
      -7.5499,
      113.0318,
      -5.88
    ]
  }
}
```

Menampilkan semua kota dalam format default \(geojson\)

```text
curl "https://data.petabencana.id/cities?geoformat=geojson"
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
          "type": "Polygon",
          "coordinates": [
            [
              [
                106.48,
                -6.733
              ],
              [
                107.175,
                -6.733
              ],
              [
                107.175,
                -5.88
              ],
              [
                106.48,
                -5.88
              ],
              [
                106.48,
                -6.733
              ]
            ]
          ]
        },
        "properties": {
          "code": "jbd",
          "name": "Jabodetabek"
        }
      },
      {
        "type": "Feature",
        "geometry": {
          "type": "Polygon",
          "coordinates": [
            [
              [
                107.369,
                -7.165
              ],
              [
                107.931,
                -7.165
              ],
              [
                107.931,
                -6.668
              ],
              [
                107.369,
                -6.668
              ],
              [
                107.369,
                -7.165
              ]
            ]
          ]
        },
        "properties": {
          "code": "bdg",
          "name": "Bandung"
        }
      },
      {
        "type": "Feature",
        "geometry": {
          "type": "Polygon",
          "coordinates": [
            [
              [
                112.3975,
                -7.5499
              ],
              [
                113.0318,
                -7.5499
              ],
              [
                113.0318,
                -7.0143
              ],
              [
                112.3975,
                -7.0143
              ],
              [
                112.3975,
                -7.5499
              ]
            ]
          ]
        },
        "properties": {
          "code": "sby",
          "name": "Surabaya"
        }
      }
    ]
  }
}
```

