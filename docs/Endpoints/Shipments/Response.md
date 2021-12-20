# Response

On success, the API will return a `JSON API` document with a `procedure` object as the `data` member.  
The `id` member of the response object will contain the LHost procedure token.  

The `shipment` meta will contain the `status` member (please see status codes below).

## Response codes

| Result    | HTTP status code  |
|-----------|-------------------|
| Success   | `200 OK`          |
| Success   | `202 Accepted`    |
| Error     | `400 Bad Request` |
| Not Found | `404 Not Found`   |

Please see the [Error Handling documentation](/docs/ErrorHandling.md) for further information about errors.
