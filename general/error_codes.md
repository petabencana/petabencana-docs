# Error Codes

Petabencana uses the standard [HTTP Status Codes](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes) to communicate errors together with a json formatted error message giving more information as to the root cause of the error. The main codes used are as follows:

## 4xx Errors

Errors starting with a 4 generally indicate a client side issue that must be resolved before re-querying the service such as:

* **400 Bad Request** - normally caused by an incorrect query parameter e.g. `"child \"type\" fails because [\"type\" must be one of [floodgates, pumps, waterways]]"`
* **403 Forbidden** - the authentication token is invalid
* **404 Not Found** - the resource was not found, this may indicate an incorrect endpoint or trying to retrieve a record for example, a report, which does not exist
* **409 Conflict** - the resource exists but if the request was allowed a conflict would be created in the system, for example, filing a report for a card where a report already exists
* **415 Unsupported Media Type** - the file being uploaded is not supported by the system - this usually means a binary file such as an image is being uploaded but the Content-Type header with the associated MIME type \(e.g. \`image/jpeg\`\) has not been supplied
* **429 Too Many Requests** - you have exceeded your per second or per day quota of requests

## 5xx Errors

Errors starting with a 5 generally indicate a server side fault and should be immediately:

* **500 Internal Server Error** - a catch-all error indicating that something has failed server side
* **503 Service Unavailable** - the service is down and cannot respond to requests

