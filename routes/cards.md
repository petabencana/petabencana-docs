# Cards

Petabencana report cards for disaster events. Note: [authentication](https://docs.petabencana.id/general/authentication.html) is required to make updates to cards.

## Request Format

| URL Parameter | Description | Format | Required |
| :--- | :--- | :--- | :--- |
| cardId | Unique identifier of the card we wish to work with, this is generated by the system when the initial card is created \(required\) | String \(7 to 14 characters\) | Yes |

| Attribute | Description | Format | Required |
| :--- | :--- | :--- | :--- |
| card\_data | User data collected in card interface | JSON | Yes |
| text | Description of the disaster event | String | No |
| image\_id | Identifier of the associated card image | String | No |
| created\_at | Date and time the card was created | Date \([ISO 8601](http://www.iso.org/iso/home/standards/iso8601.htm)\) | Yes |
| location | Geographic location of the disaster event | Lat/Long in [ESPG:4326](http://spatialreference.org/ref/epsg/wgs-84/) | Yes |

### Note on card\_data

Card data requires the object `report_type` to exist. Where `disaster_type` is set to 'flood' then the object `flood_depth` should also exist adjacent to `report_type`. Where the `disaster_type` is 'prep' then `report_type` should be one of the types as specified in server config.js.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Disaster Type</th>
      <th style="text-align:left">report_type</th>
      <th style="text-align:left">Attribute details</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Flood</td>
      <td style="text-align:left">flood</td>
      <td style="text-align:left">
        <p><b>flood_depth: </b>flood severity based on depth in cm
          <br />
        </p>
        <p>&lt; 70 cm : Minor</p>
        <p>70 - 150 cm : Moderate</p>
        <p>150 cm : Severe</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Earthquake</td>
      <td style="text-align:left">road</td>
      <td style="text-align:left"><b>accessabilityFailure: </b>the level of road damage affected by earthquake
        <br
        />
        <br />0 : &lt; 0,5 m (No Vehicle Access)
        <br />1 : 0,6 - 1 m (2-Wheel Vehicle Access)
        <br />2 or 3 : 1.1 - 1.8 m (4-Wheel Vehicle Access)
        <br />4 : &gt;1,9 m (Large Vehicle Access)</td>
    </tr>
    <tr>
      <td style="text-align:left">Earthquake</td>
      <td style="text-align:left">structure</td>
      <td style="text-align:left">
        <p><b>structureFailure: </b>the level of structure damage affected by earthquake</p>
        <p></p>
        <p>0 : Cracking
          <br />1 : Partially Collapse
          <br />2 : Fully Collapse</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Extreme Wind</td>
      <td style="text-align:left">wind</td>
      <td style="text-align:left">
        <p><b>impact</b>: level of disruption caused by extreme wind</p>
        <p></p>
        <p>0 : Low Disruption
          <br />1 : Medium Disruption
          <br />2 : High Disruption</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Haze</td>
      <td style="text-align:left">haze</td>
      <td style="text-align:left">
        <p><b>visibility</b>: the distance one can see as determined by light and
          weather conditions</p>
        <p></p>
        <p>0: can see but need to wear a mask</p>
        <p>1: can see but not clean enough to drive</p>
        <p>2: can barely see, too dangerous to go out</p>
        <p></p>
        <p><b>airQuality</b>: described by symptoms felt by humans</p>
        <p></p>
        <p>0 or 1: Poor Air Quality
          <br />2: Severe Air Quality
          <br />3 or 4 : Hazardous Air Quality</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Forest Fire</td>
      <td style="text-align:left">fire</td>
      <td style="text-align:left"><b>fireRadius</b>: the radius of a forest fire estimated by the human
        eye</td>
    </tr>
  </tbody>
</table>

For example a card with flood data including flood\_depth:

```javascript
  "disaster_type": "flood",
  "card_data":{
    "report_type": "flood",
    "flood_depth": 50
  }
```

Or, a card with pre-flood data report regarding a drain.

```javascript
  "disaster_type": "prep",
  "card_data":{
    "report_type":"drain"
  }
```

## GET /cards/:cardId

Retrieve details of a card:

Here is a simple call to GET a card:

```text
curl -X GET -H "X-Api-Key: API_KEY_GOES_HERE" "https://data.petabencana.id/cards/abcdefg"
```

The card was found:

```javascript
{
  "statusCode": 200,
  "result": {
    "pkey": "2",
    "card_id": "abcdefg",
    "username": "user",
    "network": "test",
    "language": "en",
    "received": true,
    "report_id": "1"
  }
}
```

The card does not exist:

```javascript
{
  "statusCode": 404,
  "found": false,
  "result": null
}
```

## PUT /cards/:cardId

Update a card with details a disaster event report:

Here is a simple call to PUT a card:

```text
curl -X PUT -H "X-Api-Key: API_KEY_GOES_HERE" -d '{
    "text": "test card",
    "disaster_type": "flood"
    "card_data":
      {
        "report_type": "flood",
        "flood_depth": 101
      },
    "created_at":"2016-12-09T11:32:52.011Z",
    "location": {
        "lat": -6.149531,
        "lng": 106.869342
    }
}' "https://data.petabencana.id/cards/abcdefg"
```

Card was successfully created:

```javascript
{
  "statusCode": 200,
  "cardId": "abcdefg",
  "created": true
}
```

The card does not exist:

```javascript
{
  "statusCode": 404,
  "cardId": "abcdefg",
  "message": "No card exists with id 'abcdefg'"
}
```

The report already exists for the card:

```javascript
{
  "statusCode": 409,
  "cardId": "abcdefg",
  "message": "Report already received for card 'abcdefg'"
}
```

## GET /cards/:cardId/images

GET a signed S3 URL to upload a card report, this must be done after the card report has been created and only one image can exist for a given card.

NOTE: After an image is submitted a server-side process shrinks the image to a standard size and there may be a small time lag of a few seconds before the image goes "live".

Here is a simple call to GET a new signed S3 URL for image upload:

```text
curl -X GET \
  https://api-server-dev.riskmap.in/cards/HJID8CWN-/images
```

Signed S3 URL successfully generated:

```javascript
{"signedRequest":"https://riskmap-image-uploads.s3.ap-south-1.amazonaws.com/originals/BJbTHR-Vb.jpg?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAJFMR3NR7BXZ5X7DA%2F20170629%2Fap-south-1%2Fs3%2Faws4_request&X-Amz-Date=20170629T012002Z&X-Amz-Expires=900&X-Amz-Signature=ad10a53555205fa18ecfa07da52eb0349ed1c8bda66fe2de0fa9c445c61b7c62&X-Amz-SignedHeaders=host","url":"https://s3.ap-south-1.amazonaws.com/riskmap-image-uploads/originals/BJbTHR-Vb.jpg"}
```

