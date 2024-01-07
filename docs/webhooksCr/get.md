# GET /api/v1/callback/get/{hash}


URL: GET https://proxiedmail.com/api/v1/callback/get/{hash}

Response (200):

In case we haven't received any callback yet:
```json
{
  "status": "ok",
  "payload": null,
  "code": "ok",
  "is_received": false,
  "method": null
}
```


In case we have received callback:

```json
{
    "status": "ok",
    "payload": {
        "data": {
            "type": "proxy_bindings",
            "attributes": {
                "real_addresses": [
                    "example@gmail.com"
                ],
                "proxy_address": "mafffaffddffawd1d1afff@proxiedmail.com"
            }
        }
    },
    "code": "ok",
    "is_received": true,
    "method": "POST"
}
```

Payload is always json object in case it was JSON. Otherwise it will be string.

```bash
curl --location --request GET 'https://proxiedmail.com/api/v1/callback/get/14431720055a1d06d59f7c8bf095ddc6' \
--header 'accept: application/json' \
--header 'content-type: application/json' \
--header 'Token: YOUR_AUTH_TOKEN'
```