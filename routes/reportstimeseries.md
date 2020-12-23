# Reports/Timeseries

Time series of flood reports \(see [Reports endpoint](reports.md) documentation\), presented as the count of flood reports every hour within the specified time period. Count is recorded alongside an hourly timestamp in ISO8601 format at UTC+0.

## Request Format

| Query Parameter | Description | Format | Required |
| :--- | :--- | :--- | :--- |
| start | Start time for timeseries period | String in ISO 8601 format \(YYYY-MM-DDTHH:mm:ss+ZZZZ | Yes |
| end | End time for timeseries period | String in ISO 8601 format \(YYYY-MM-DDTHH:mm:ss+ZZZZ | Yes |

Note that time zone must be specified as +/- UTC offset which will require HTML character encoding \(e.g. +0700 becomes %2B0700\).

## Get /reports/timeseries

## GET /reports/timeseries

Get count of flood reports within specified time period.

```text
    curl "https://data.petabencana.id/reports/timeseries?start=2017-11-26T12%3A00%3A00%2B0700&end=2017-11-26T15%3A00%3A00%2B0700"
```

Results are as follows:

```javascript
    {
        "statusCode": 200,
        "result": [
            {
                "ts": "2017-11-26T05:00:00.000Z",
                "count": "0"
            },
            {
                "ts": "2017-11-26T06:00:00.000Z",
                "count": "0"
            },
            {
                "ts": "2017-11-26T07:00:00.000Z",
                "count": "2"
            },
            {
                "ts": "2017-11-26T08:00:00.000Z",
                "count": "3"
            }
        ]
    }
```

