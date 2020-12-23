# Stats - Flooded Regions Summary

List of all regions with currently flooded RWs.

## Request Format

| Query Parameter | Description | Format | Required |
| :--- | :--- | :--- | :--- |
| city | Which city do we wish to return infrastructure for? \(one of `bdg`, `jbd`, `sby`\) | String | No |

## GET /stats/floodedRegionsSummary

```text
curl "https://data.petabencana.id/stats/floodedRegionsSummary?city=jbd"
```

Results are as follows:

```javascript
{
  "total number of regions with flooded RWs": 4,
  "regions with flooded RWs": [
    "KAPUK",
    "RAWA TERATE",
    "CIPINANG MELAYU",
    "CENGKARENG BARAT"
  ]
}
```

