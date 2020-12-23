# Infrastructure

Locations of local infrastructure including flood gates, pumps and waterways.

## Request Format

| URL Parameter | Description | Format | Required |
| :--- | :--- | :--- | :--- |
| type | What type of infrastructure do we wish to list?  \(one of `floodgates`, `pumps`, `waterways`\) | String | Yes |

| Query Parameter | Description | Format | Required |
| :--- | :--- | :--- | :--- |
| city | Which city do we wish to return infrastructure for? \(one of `bdg`, `jbd`, `sby`\) | String | No |
| format | Which format should we return results in? \(one of `json`, defaults to `json`\) | String | No |
| geoformat | What format should geographic results use \(one of `topojson`, `geojson` defaults to `topojson`\) | String | No |

## GET /infrastructure/:type

Return a list of pumps in Jakarta.

```text
curl "https://data.petabencana.id/infrastructure/pumps?city=jbd"
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
              "name": "PA Marina"
            },
            "coordinates": [
              7164,
              7352,
              0
            ]
          },
          {
            "type": "Point",
            "properties": {
              "name": "Pompa Waduk Setia Budi Barat"
            },
            "coordinates": [
              5312,
              5077,
              0
            ]
          },
          // etc. etc. //
          {
            "type": "Point",
            "properties": {
              "name": "Pompa UP Senen"
            },
            "coordinates": [
              6143,
              6544,
              0
            ]
          }
        ]
      }
    },
    "arcs": [],
    "transform": {
      "scale": [
        0.000020651319451945148,
        0.000020217245084508508
      ],
      "translate": [
        106.7188310623,
        -6.3060956581
      ]
    },
    "bbox": [
      106.7188310623,
      -6.3060956581,
      106.9253236055,
      -6.1039434245
    ]
  }
}
```

