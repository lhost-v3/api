# `/clients/current`

Retrieve information about the current client.

Methods : `GET`, `HEAD`

## Request

#### `GET` `/clients/current`
#### `HEAD` `/clients/current`

The request should contain no content body.

## Response

On success, the API will return a `JSON API` document with a `client` object as the `data` member.  
The `id` member of the `client` object will contain the LHost API client id.

Tip: in order to simply verify the authentication status, one could issue a `HEAD` request instead of `GET`.

### Response codes

| Result  | HTTP status code   |
|---------|--------------------|
| Success | `200 OK`           |
| Error   | `401 Unauthorized` |

Please see the [Error Handling documentation](/docs/ErrorHandling.md) for further information about errors.

Please see the [Authentication documentation](/docs/Authentication.md) for further information about the authentication process and error handling.

---

## Response document structure

### `client` object attributes

| Name   | Description | Type  |
|--------|-------------|-------|
| `type` | Object type |string |
| `id`   | Client id   |string |

---

## Examples

### Valid authentication

```
GET /v3-testing/clients/current HTTP/1.1
Accept: application/vnd.api+json
Authorization: Bearer <JWT>
User-Agent: PostmanRuntime/7.26.8
Postman-Token: ebd14688-59b2-45af-b1c6-b3a5ab19edff
Host: api.mylhost.com
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
HTTP/1.1 200 OK
Date: Mon, 20 Dec 2021 13:50:16 GMT
Server: Apache
Content-length: 71
Keep-Alive: timeout=5, max=100
Connection: Keep-Alive
Content-Type: application/vnd.api+json
{"jsonapi":{"version":"1.0"},"data":{"type":"client","id":"apitester"}}
```

### Invalid authentication

* Missing `Authorization` header

```
GET /v3-testing/clients/current HTTP/1.1
Accept: application/vnd.api+json
User-Agent: PostmanRuntime/7.26.8
Postman-Token: 36661ee4-e080-48c7-939a-6e359dfa8e3a
Host: api.mylhost.com
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
HTTP/1.1 401 Unauthorized
Date: Mon, 20 Dec 2021 13:53:38 GMT
Server: Apache
WWW-Authenticate: Bearer realm="api.mylhost.com", error="401", error_description="Missing or invalid authorization header"
Content-length: 129
Keep-Alive: timeout=5, max=100
Connection: Keep-Alive
Content-Type: application/vnd.api+json
{"jsonapi":{"version":"1.0"},"errors":[{"status":401,"title":"Unauthorized","detail":"Missing or invalid authorization header"}]}
```
