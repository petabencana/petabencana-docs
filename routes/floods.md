# Area Banjir

Informasi banjir realtime - berdasarkan kota dan status banjir \(jika diperlukan\). Mendukung _endpoint_ /states yang non-geografis dan hanya memberikan status wilayah terdampak banjir serta _endpoint_ geografis yang akan memberikan wilayah tergenang dengan _minimum\_state_ atau semua wilayah dengan status banjirnya saat ini. Selain [topojson](https://github.com/topojson/topojson/wiki) dan [geojson](http://geojson.org/), titik akhir ini mendukung [Common Alerting Protocol \(CAP\)](https://en.wikipedia.org/wiki/Common_Alerting_Protocol). 

Perhatikan bahwa status banjir dalam format CAP memiliki waktu kadaluarsa _default_ 6 jam sejak permintaan API dibuat.

## Kode Status Banjir

Kode numerik yang digunakan untuk merepresentasikan kondisi banjir adalah sebagai berikut:

| Kode | Keparahan | Deskripsi |
| :--- | :--- | :--- |
| 1 | _Unknown_ | KETINGGIAN BANJIR TIDAK DIKETAHUI - HATI-HATI - |
| 2 | _Minor_ | BANJIR ANTARA 10 hingga 70 SENTIMETER |
| 3 | _Moderate_ | BANJIR ANTARA 71 hingga 150 SENTIMETER |
| 4 | _Severe_ | BANJIR LEBIH DARI 150 SENTIMETER |

## Format Permintaan

| Parameter Kueri | Deskripsi | Format | Wajib |
| :--- | :--- | :--- | :--- |
| admin | Area mana yang laporannya ingin disajikan? \(saat ini hanya mendukung`ID-JK`\) | String | Tidak |
| format | Format apa yang diperlukan dari hasil yang disajikan? \(salah satu `json`, `xml`, default ke `json`\) | String | Tidak |
| geoformat | Format apa yang diperlukan untuk hasil geografis? \(salah satu antara `topojson`, `geojson`, `cap`, default ke `topojson`\) | String | Tidak |
| minimum\_state | Berapa status banjir minimal yang ingin ditampilkan? \(min: `1`, maks: `4`\) | Number | Tidak |

## GET /floods

{% tabs %}
{% tab title="https" %}
Daftar semua wilayah terdampak banjir di Jakarta dengan status banjir 1 atau lebih tinggi.

```text
curl "https://data.petabencana.id/floods?admin=ID-JK&minimum_state=1"
```
{% endtab %}

{% tab title="https" %}
Daftar semua wilayah terdampak banjir di Jakarta dengan status banjir 1 atau lebih tinggi dalam format CAP.

```text
curl "https://data.petabencana.id/floods?admin=ID-JK&minimum_state=1&format=xml&geoformat=cap"
```
{% endtab %}
{% endtabs %}

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
              "area_id": "5",
              "geom_id": "3174040004009000",
              "area_name": "RW 09",
              "parent_name": "GROGOL",
              "city_name": "Jakarta",
              "state": 1,
              "last_updated": "2016-12-19T13:53:52.274Z"
            },
            "arcs": [
              [
                0
              ]
            ]
          }
        ]
      }
    },
    "arcs": [
      [
        [
          9999,
          7847
        ],
        [
          -507,
          -6
        ],
        [
          -695,
          -70
        ],
        [
          -317,
          -221
        ],
        [
          -761,
          -18
        ],
        [
          -516,
          98
        ],
        [
          -641,
          -61
        ],
        [
          -649,
          -119
        ],
        [
          -169,
          -762
        ],
        [
          -181,
          -519
        ],
        [
          48,
          -602
        ],
        [
          -130,
          -162
        ],
        [
          64,
          -1235
        ],
        [
          81,
          -2351
        ],
        [
          136,
          -1098
        ],
        [
          15,
          -675
        ],
        [
          -1250,
          -40
        ],
        [
          -879,
          -6
        ],
        [
          -924,
          217
        ],
        [
          -924,
          425
        ],
        [
          -1800,
          138
        ],
        [
          830,
          1540
        ],
        [
          565,
          1455
        ],
        [
          764,
          1975
        ],
        [
          1018,
          2079
        ],
        [
          384,
          788
        ],
        [
          389,
          1061
        ],
        [
          1398,
          -76
        ],
        [
          296,
          -25
        ],
        [
          360,
          6
        ],
        [
          392,
          -9
        ],
        [
          360,
          -9
        ],
        [
          377,
          12
        ],
        [
          323,
          25
        ],
        [
          354,
          76
        ],
        [
          296,
          89
        ],
        [
          211,
          42
        ],
        [
          290,
          52
        ],
        [
          217,
          28
        ],
        [
          341,
          110
        ],
        [
          43,
          -67
        ],
        [
          57,
          -174
        ],
        [
          109,
          -159
        ],
        [
          154,
          -257
        ],
        [
          115,
          -370
        ],
        [
          99,
          -346
        ],
        [
          124,
          -357
        ],
        [
          133,
          -422
        ]
      ]
    ],
    "transform": {
      "scale": [
        0.0000003311331833192323,
        0.00000032713269326930546
      ],
      "translate": [
        106.7917869997,
        -6.158925
      ]
    },
    "bbox": [
      106.7917869997,
      -6.158925,
      106.7950980004,
      -6.1556540002
    ]
  }
}
```

Hasilnya adalah sebagai berikut:

```markup
<?xml version="1.0"?>
<feed xmlns="http://www.w3.org/2005/Atom">
    <id>https://data.petabencana.id/floods</id>
    <title>petabencana.id Flood Affected Areas</title>
    <updated>2016-12-19T23:08:52+07:00</updated>
    <author>
        <name>petabencana.id</name>
        <uri>https://petabencana.id/</uri>
    </author>
    <entry>
        <id>https://data.petabencana.id/floods?parent_name=GROGOL&amp;area_name=RW%2009&amp;time=2016-12-19T22:41:35+07:00</id>
        <title>GROGOL.RW_09.2016-12-19T22:41:35+07:00 Flood Affected Area</title>
        <updated>2016-12-19T22:41:35+07:00</updated>
        <content type="text/xml">
            <alert xmlns="urn:oasis:names:tc:emergency:cap:1.2">
                <identifier>GROGOL.RW_09.2016-12-19T22:41:35+07:00</identifier>
                <sender>BPBD.JAKARTA.GOV.ID</sender>
                <sent>2016-12-19T22:41:35+07:00</sent>
                <status>Actual</status>
                <msgType>Alert</msgType>
                <scope>Public</scope>
                <info>
                    <category>Met</category>
                    <event>FLOODING</event>
                    <urgency>Immediate</urgency>
                    <severity>Minor</severity>
                    <certainty>Observed</certainty>
                    <senderName>JAKARTA EMERGENCY MANAGEMENT AGENCY</senderName>
                    <headline>FLOOD WARNING</headline>
                    <description>AT 22:41 WIB THE JAKARTA EMERGENCY MANAGEMENT AGENCY OBSERVED FLOODING OF BETWEEN 10 and 70 CENTIMETERS IN GROGOL, RW 09.</description>
                    <web>https://petabencana.id/</web>
                    <area>
                        <areaDesc>RW 09, GROGOL</areaDesc>
                        <polygon>-6.1563580003,106.7950980004 -6.1563600004,106.7949299998 -6.1563829997,106.7947 -6.1564550003,106.7945949997 -6.1564609997,106.7943429997 -6.156429,106.7941719999 -6.156449,106.7939600001 -6.156488,106.793745 -6.1567369998,106.7936890001 -6.1569070004,106.7936290001 -6.1571040005,106.7936449999 -6.1571570003,106.7936019997 -6.157561,106.7936229998 -6.1583300004,106.7936500001 -6.1586889999,106.7936950004 -6.1589100002,106.7936999998 -6.1589229999,106.7932860005 -6.158925,106.7929949996 -6.1588540003,106.7926889999 -6.1587150002,106.7923830002 -6.1586699999,106.7917869997 -6.158166,106.7920619998 -6.1576899997,106.7922490003 -6.1570440005,106.7925020003 -6.1563639997,106.7928389996 -6.1561060004,106.7929660001 -6.1557589997,106.7930949997 -6.1557839999,106.7935580004 -6.1557920003,106.7936560004 -6.1557900002,106.7937749996 -6.1557930003,106.7939050002 -6.1557960005,106.7940240003 -6.1557920003,106.7941489998 -6.1557839999,106.7942560002 -6.1557589997,106.7943730002 -6.1557300001,106.7944710002 -6.1557160004,106.7945409999 -6.1556990005,106.7946369998 -6.1556900001,106.7947090004 -6.1556540002,106.7948220002 -6.1556760003,106.794836 -6.1557330003,106.794855 -6.155785,106.7948909998 -6.1558690002,106.7949420004 -6.1559900004,106.7949800003 -6.1561030002,106.7950130001 -6.1562200002,106.7950540001 -6.1563580003,106.7950980004 </polygon>
                    </area>
                </info>
            </alert>
        </content>
    </entry>
</feed>
```

## GET /floods/states

Daftar semua status area terdampak banjir di Jakarta dengan status banjir 1 atau lebih tinggi.

```text
curl "https://data.petabencana.id/floods/states?city=jbd&minimum_state=1"
```

Hasilnya adalah sebagai berikut:

```javascript
{
  "statusCode": 200,
  "result": [
    {
      "area_id": "5",
      "state": 1,
      "last_updated": "2016-12-19T13:53:52.274Z"
    }
  ]
}
```

## PUT /floods/:localAreaId

PUT \(Menambahkan\) status banjir baru dalam sistem untuk area lokal tertentu \(aman, memerlukan token otorisasi\).

```text
curl -X PUT -H "Content-Type: application/json" -d '{
    "state": 2
}' "https://data.petabencana.id/floods/5"
```

Hasilnya adalah sebagai berikut:

```javascript
{
  "localAreaId": 5,
  "state": 2,
  "updated": true
}
```

## DELETE /floods/:localAreaId

Menghapus seluruh status banjir untuk area lokal tertentu \(aman, memerlukan token otorisasi\).

```text
curl -X DELETE "https://data.petabencana.id/floods/5"
```

Hasilnya adalah sebagai berikut:

```javascript
{
  "localAreaId": 5,
  "state": null,
  "updated": true
}
```

