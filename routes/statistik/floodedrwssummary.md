# Stats - Flooded RWs Summary

Count of all RWs by flood height range.

## Request Format

| Query Parameter | Description | Format | Required |
| :--- | :--- | :--- | :--- |
| city | Which city do we wish to return infrastructure for? \(one of `bdg`, `jbd`, `sby`\) | String | No |

## GET /stats/floodedRWsSummary

```text
curl "https://data.petabencana.id/stats/floodedRWsSummary?city=jbd"
```

Results are as follows:

```javascript
{
  "# hati-hati RWs": 0,
  "# 10-70cm RWs": 9,
  "# 71-150cm RWs": 0,
  "# 151cm+ RWs": 0
}
```

