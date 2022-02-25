# `/test`

Test the LHost API.

Methods : `GET`, `HEAD`

Please see also [Testing the API](../Testing.md).

The test endpoint simply returns the data received.

---

## Examples

### Simple test

```
GET /v3-testing/test HTTP/1.1
Accept: application/vnd.api+json
Authorization: Bearer <JWT>
User-Agent: PostmanRuntime/7.26.8
Postman-Token: 5e699f97-af4d-4302-94b9-33b718ba73e7
Host: api.mylhost.com
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
HTTP/1.1 200 OK
Date: Mon, 20 Dec 2021 13:46:22 GMT
Server: Apache
Content-length: 84
Keep-Alive: timeout=5, max=100
Connection: Keep-Alive
Content-Type: application/vnd.api+json
{"jsonapi":{"version":"1.0"},"data":{"type":"test","id":"","meta":{"method":"GET"}}}
```

### Specify an id

* Test sending parameters to the API.

```
GET /v3-testing/test/123 HTTP/1.1
Accept: application/vnd.api+json
Authorization: Bearer <JWT>
User-Agent: PostmanRuntime/7.26.8
Postman-Token: 4257aa91-6cf4-4b14-985f-018f6e551e2e
Host: api.mylhost.com
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
HTTP/1.1 200 OK
Date: Mon, 20 Dec 2021 13:47:38 GMT
Server: Apache
Content-length: 87
Keep-Alive: timeout=5, max=100
Connection: Keep-Alive
Content-Type: application/vnd.api+json
{"jsonapi":{"version":"1.0"},"data":{"type":"test","id":"123","meta":{"method":"GET"}}}
```

### Add query paramters

```
GET /v3-testing/test/123?key1=value1&key2=value2 HTTP/1.1
Accept: application/vnd.api+json
Authorization: Bearer <JWT>
User-Agent: PostmanRuntime/7.26.8
Postman-Token: 86ccac8b-6f07-4357-b375-97127dae5520
Host: api.mylhost.com
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
HTTP/1.1 200 OK
Date: Mon, 20 Dec 2021 13:48:34 GMT
Server: Apache
Content-length: 144
Keep-Alive: timeout=5, max=100
Connection: Keep-Alive
Content-Type: application/vnd.api+json
{"jsonapi":{"version":"1.0"},"data":{"type":"test","id":"123","attributes":{"query":{"key1":"value1","key2":"value2"}},"meta":{"method":"GET"}}}
```

---

[README](../../README.md)
