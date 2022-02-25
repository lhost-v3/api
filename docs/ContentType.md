# Content type

The LHost API uses the `JSON API` content type.

> JSON API is a specification for how a client should request that resources be fetched or modified, and how a server should respond to those requests.  
> JSON API requires use of the JSON API media type (`application/vnd.api+json`) for exchanging data.

Any call to the API needs to send the proper `Content-Type` and `Accept` headers.

Request content data should follow the `JSON API` specification.

The currently supported JSON API version is `1.0`.

For more information please visit [JSON:API &mdash; A specification for building APIs in JSON](https://jsonapi.org/).

## Examples

An complete example of the structure of a request data for the `/shipments` endpoint with all of the possible fields would be:

```json
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
                "name" : "Receiver Name",
                "address1": "Receiver address 123",
                "city": "Muenchen",
                "postalCode": 80331,
                "country": "DE",
                "state": "",
                "phone": "987654321",
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
```

---

[README](../README.md)
