# Pemantauan TMA

Live flood gauge reports, by default reports will be returned for the last hour.

## Request Format

| Query Parameter | Description | Format | Required |
| :--- | :--- | :--- | :--- |
| city | Which city do we wish to return infrastructure for? \(one of `bdg`, `jbd`, `sby`\) | String | No |
| format | Which format should we return results in? \(one of `json`, defaults to `json`\) | String | No |
| geoformat | What format should geographic results use \(one of `topojson`, `geojson` defaults to `topojson`\) | String | No |

## GET /floodgauges

List all current flood gauge reports for Jakarta.

```text
curl "https://data.petabencana.id/floodgauges?city=jbd"
```

Results are as follows:

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

