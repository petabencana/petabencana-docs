# Floods/Archive

Archive of flooded areas \(see [Floods endpoint](floods.md) documentation\), presented as the maximum flood state recorded for all flood affected areas within the specified time period. Maximum state is recorded alongside area id. Use the Floods endpoint to get geospatial boundaries of individual areas.

Currently this data is only available for Jakarta.

## Request Format

| Query Parameter | Description | Format | Required |
| :--- | :--- | :--- | :--- |
| start | Start time for archive period | String in ISO 8601 format \(YYYY-MM-DDTHH:mm:ss+ZZZZ | Yes |
| end | End time for archive period | String in ISO 8601 format \(YYYY-MM-DDTHH:mm:ss+ZZZZ | Yes |

Note that time zone must be specified as +/- UTC offset which will require HTML character encoding \(e.g. +0700 becomes %2B0700\).

## Get /floods/archive

## GET /floods

List all flooded areas in Jakarta with a flood state of 1 or higher.

```text
curl "https://data.petabencana.id/floods/archive?start=2017-06-07T00:00:00%2B0700&end=2017-06-08T23:00:00%2B0700"
```

Results are as follows:

```javascript
    {
        "statusCode": 200,
        "result": [
            {
                "area_id": "509",
                "last_updated": "2017-11-03T22:57:01.387Z",
                "max_state": 1
            },
            {
                "area_id": "510",
                "last_updated": "2017-11-03T22:57:10.463Z",
                "max_state": 4
            }
        ]
    }
```

