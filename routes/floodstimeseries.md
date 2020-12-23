# Floods/Timeseries

Time series of flooded areas \(see [Floods endpoint](floods.md) documentation\), presented as the count of flood affected areas every hour within the specified time period. Count is recorded alongside an hourly timestamp in ISO8601 format at UTC+0.

Currently this data is only available for Jakarta.

## Request Format

| Query Parameter | Description | Format | Required |
| :--- | :--- | :--- | :--- |
| start | Start time for timeseries period | String in ISO 8601 format \(YYYY-MM-DDTHH:mm:ss+ZZZZ | Yes |
| end | End time for timeseries period | String in ISO 8601 format \(YYYY-MM-DDTHH:mm:ss+ZZZZ | Yes |

Note that time zone must be specified as +/- UTC offset which will require HTML character encoding \(e.g. +0700 becomes %2B0700\).

## Get /floods/timeseries

## GET /floods

List all flooded areas in Jakarta with a flood state of 1 or higher.

```text
curl "https://data.petabencana.id/floods/timeseries?start=2017-11-20T11%3A00%3A00-0500&end=2017-11-20T15%3A00%3A00-0500"
```

Results are as follows:

```javascript
    {
        "statusCode": 200,
        "result": [
            {
                "ts": "2017-11-20T16:00:00.000Z",
                "count": "0"
            },
            {
                "ts": "2017-11-20T17:00:00.000Z",
                "count": "0"
            },
            {
                "ts": "2017-11-20T18:00:00.000Z",
                "count": "0"
            },
            {
                "ts": "2017-11-20T19:00:00.000Z",
                "count": "0"
            },
            {
                "ts": "2017-11-20T20:00:00.000Z",
                "count": "0"
            }
        ]
    }
```

