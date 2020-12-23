# Reports

Live disaster reports, by default reports will be returned for the last hour.

## Request Format

| Query Parameter | Description | Format | Required |
| :--- | :--- | :--- | :--- |
| city | Which city do we wish to return infrastructure for? \(one of `bdg`, `jbd`, `sby`\) | String | No |
| format | Which format should we return results in? \(one of `json`, defaults to `json`\) | String | No |
| geoformat | What format should geographic results use \(one of `topojson`, `geojson` defaults to `topojson`\) | String | No |
| timeperiod | What time period \(in seconds\) to list reports for, must be strictly between 1 and 604800 \(1 week\) | Number | No |

## GET /reports

List all current flood reports for Jakarta.

```text
curl "https://data.petabencana.id/reports?city=jbd"
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

