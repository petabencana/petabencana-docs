# Crowdsourced Reports/Archive

Archive of disaster reports \(see [Reports endpoint](crowdsourced-reports.md) documentation\), presented as a JSON with all the flood reports received within the specified time period.

Note: authentication is required to access this API.


## Request Format

| Query Parameter | Description | Format | Required |
| :--- | :--- | :--- | :--- |
| start | Start time for archive period | String in ISO 8601 format \(YYYY-MM-DDTHH:mm:ss+ZZZZ | Yes |
| end | End time for archive period | String in ISO 8601 format \(YYYY-MM-DDTHH:mm:ss+ZZZZ | Yes |
| disaster        | Which [disaster](https://docs.petabencana.id/v/master/general/supported-hazards) should we return the result? (one of`flood, earthquake, fire, haze, wind volcano,`doesn't filter by default) | string | No |
| admin | Which province do we wish to return the reports for? \(see [supported area](https://docs.petabencana.id/v/master/general/supported-area)\) | String | No |
| geoformat | What format should geographic results use \(one of `topojson`, `geojson` defaults to `topojson`\) | String | No |

Note that time zone must be specified as +/- UTC offset which will require HTML character encoding \(e.g. +0700 becomes %2B0700\).

## Get /archive/reports

Note : Please include a User-Agent header in all of your requests. The User-Agent header helps us identify your requests and troubleshoot any issues you may have. To set the User-Agent header, add the following line to your request headers:

List flood reports in Jakarta received within specified time window

```text
curl --user-agent "YOUR-UA-STRING" -H "X-Api-Key: API_KEY_GOES_HERE"  "https://api.petabencana.id/archive/reports?start=2017-12-04T00%3A00%3A00%2B0700&end=2017-12-06T05%3A00%3A00%2B0700&geoformat=geojson&admin=ID-JK"
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

