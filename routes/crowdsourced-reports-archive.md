# Crowdsourced Reports/Archive

Archive of disaster reports \(see [Reports endpoint](crowdsourced-reports.md) documentation\), presented as a JSON with all the flood reports received within the specified time period.

## Request Format

| Query Parameter | Description | Format | Required |
| :--- | :--- | :--- | :--- |
| start | Start time for archive period | String in ISO 8601 format \(YYYY-MM-DDTHH:mm:ss+ZZZZ | Yes |
| end | End time for archive period | String in ISO 8601 format \(YYYY-MM-DDTHH:mm:ss+ZZZZ | Yes |
| admin | Which province do we wish to return the reports for? \(see [supported area](https://docs.petabencana.id/v/master/general/supported-area)\) | String | No |
| geoformat | What format should geographic results use \(one of `topojson`, `geojson` defaults to `topojson`\) | String | No |

Note that time zone must be specified as +/- UTC offset which will require HTML character encoding \(e.g. +0700 becomes %2B0700\).

## Get /reports/archive

## GET /reports

List flood reports in Jakarta received within specified time window

```text
curl "https://api.petabencana.id/reports/archive?start=2017-12-04T00%3A00%3A00%2B0700&end=2017-12-06T05%3A00%3A00%2B0700&geoformat=geojson&admin=ID-JK"
```

Results are as follows:

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
                        "instance_region_code": "ID-JK",
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

