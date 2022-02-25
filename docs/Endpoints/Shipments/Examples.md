# Examples

## Creating a new shipment: success

## API client that can create shipments on behalf of multipe resorts

* `shipFrom` (resort address) is mandatory;
* Send only the minimum required `shipTo` data;

```
POST /v3-testing/shipments HTTP/1.1
Content-Type: application/vnd.api+json
Accept: application/vnd.api+json
Authorization: Bearer <JWT>
User-Agent: PostmanRuntime/7.26.8
Postman-Token: d759f490-81c8-4e07-9c1f-58ad5fd1d745
Host: api.mylhost.com
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
Content-Length: 1107
{
    "jsonapi": {
        "version": "1.0"
    },
    "data": {
        "type": "shipment",
        "attributes": {
            "shipFrom": {
                "name": "Resort Name",
                "address1": "Resort street 123",
                "address2": "",
                "city": "Milano",
                "postalCode": 20129,
                "state": "MI",
                "country": "IT",
                "contact": "Resort Contactname",
                "phone": "1234567890",
                "email": "resort@ship.from"
            },
            "shipTo": {
                "country": "DE",
                "email": "guest@ship.to"
            },
            "packages": [{
                "weight": {
                    "value": "1.9",
                    "units": "1"
                },
                "dimensions": {
                    "length": "32",
                    "width": "33",
                    "height": "34",
                    "units": "1"
                }
            }],
            "goodsDescription": "Lost item returned to guest"
        },
        "meta": {}
    }
}
HTTP/1.1 202 Accepted
Date: Mon, 20 Dec 2021 16:24:59 GMT
Server: Apache
Content-length: 97
Keep-Alive: timeout=5, max=99
Connection: Keep-Alive
Content-Type: application/vnd.api+json
{"jsonapi":{"version":"1.0"},"data":{"type":"procedure","id":"e4c4e91cda4356740839ab3cf4eac220"}}
```

## API client that belongs to an already registered resort

* `shipFrom` (resort address) data omitted (will be ingored if present);
* Send only the minimum required `shipTo` data;

```
POST /v3-testing/shipments HTTP/1.1
Content-Type: application/vnd.api+json
Accept: application/vnd.api+json
Authorization: Bearer <JWT>
User-Agent: PostmanRuntime/7.26.8
Postman-Token: da83d12d-edbe-4087-835e-abac5e270caf
Host: api.mylhost.com
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
Content-Length: 692
{
    "jsonapi": {
        "version": "1.0"
    },
    "data": {
        "type": "shipment",
        "attributes": {

            "shipTo": {
                "country": "DE",
                "email": "guest@ship.to"
            },
            "packages": [{
                "weight": {
                    "value": "1.9",
                    "units": "1"
                },
                "dimensions": {
                    "length": "32",
                    "width": "33",
                    "height": "34",
                    "units": "1"
                }
            }],
            "goodsDescription": "Lost item returned to guest"
        },
        "meta": {}
    }
}
HTTP/1.1 202 Accepted
Date: Mon, 20 Dec 2021 16:31:56 GMT
Server: Apache
Content-length: 97
Keep-Alive: timeout=5, max=100
Connection: Keep-Alive
Content-Type: application/vnd.api+json
{"jsonapi":{"version":"1.0"},"data":{"type":"procedure","id":"38d231720c5c1391ed1c87a2765add0c"}}
```

---

[README](../../../README.md)
