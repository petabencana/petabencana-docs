# Crowdsourced Reports

Live disaster reports, by default reports will be returned for the last 3 hour.

## Request Format

| Query Parameter | Description                                                                                                                                                                                   | Format | Required |
| --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------ | -------- |
| admin           | Which province do we wish to return the reports for? (see [supported area](https://docs.petabencana.id/v/master/general/supported-area))                                                      | String | No       |
| format          | Which format should we return results in? (one of `json , xml`, defaults to `json`)                                                                                                           | String | No       |
| disaster        | Which [disaster](https://docs.petabencana.id/v/master/general/supported-hazards) should we return the result? (one of`flood, earthquake, fire, haze, wind volcano,`doesn't filter by default) | string | No       |
| geoformat       | What format should geographic results use (one of `topojson`, `geojson, cap` defaults to `topojson`)                                                                                          | String | No       |
| timeperiod      | What time period (in seconds) to list reports for, must be strictly between 1 and 604800 (1 week)                                                                                             | Number | No       |

## GET /reports

List all current reports from Indonesia


Note : Please include a User-Agent header in all of your requests. The User-Agent header helps us identify your requests and troubleshoot any issues you may have. To set the User-Agent header, add the following line to your request headers:

```javascript
curl --user-agent "YOUR-UA-STRING" "https://api.petabencana.id/reports"
```

List all current reports from Jakarta.

```
curl --user-agent "YOUR-UA-STRING" "https://api.petabencana.id/reports?admin=ID-JK"
```

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
                "instance_region_code": "ID-JK",
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
