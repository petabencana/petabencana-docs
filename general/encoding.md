# Content Types

By default the Petabencana API returns [JSON](http://www.w3schools.com/json/) for all calls and expects any POST requests to supply JSON formatted bodies unless otherwise advised. [UTF-8 encoding](https://en.wikipedia.org/wiki/UTF-8) is used on all requests and responses.

Where Geographic data is returned this is will be encoded as [TopoJSON](https://github.com/topojson/topojson/wiki) by default. [GeoJson](http://geojson.org/) is also supported if required, by supplying `format=topojson in the API call. More details of this can be found in the specific API route documentation. In addition to TopoJSON and GeoJson we provide a public feed of real-time flood information using the`[`Common Alerting Protocol`](https://en.wikipedia.org/wiki/Common_Alerting_Protocol)`standard.`

