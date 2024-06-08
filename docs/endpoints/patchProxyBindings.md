---
sidebar_position: 5
---

# PATCH /api/v1/proxy-bindings/{id}

URL: PATCH https://proxiedmail.com/api/v1/proxy-bindings/{id}

```json
{
   "data":{
      "id":"A1131D57-6000-0000-00000BAE",
      "type":"proxy_bindings",
      "attributes":{
         "real_addresses":{
            "kkkchinazes@pxdmail.int": true
         },
         "proxy_address":"q1v9nj1gkw@proxiedmail.com",
         "received_emails":0,
         "description":"abc"
      }
   }
}
```


Response (200):
```json
{
  "meta": {
    "isVerificationEmailSend": false,
    "firstProxyBinding": false
  },
  "data": {
    "type": "proxy_bindings",
    "id": "8BE3D44A-6000-0000-00000BAE",
    "attributes": {
      "real_addresses": {
        "bblabla@proxiedmail.int": {
          "is_enabled": true,
          "is_verified": false
        }
      },
      "type": 0,
      "proxy_address": "7uj7s9gbnp@proxiedmail.com",
      "received_emails": 0,
      "description": "abc",
      "callback_url": "",
      "created_at": "2024-01-08 00:08:22",
      "updated_at": "2024-01-08 00:22:50"
    },
    "relationships": {
      "user": {
        "data": {
          "type": "users",
          "id": "BE090B33-0000-0000-00009BC6"
        }
      }
    }
  }
}
```


Quite the same as POST request with only one difference in "real_addresses". 


cURL:
```bash
curl --location --request PATCH 'https://proxiedmail.com/api/v1/proxy-bindings/A1131D57-6000-0000-00000BAE' \
--header 'content-type: application/json' \
--header 'Token: Token' \
--data-raw '{"data":{"id":"A1131D57-6000-0000-00000BAE","type":"proxy_bindings","attributes":{"real_addresses":{"kkkchinazes@pxdmail.int":true},"proxy_address":"q1v9nj1gkw@proxiedmail.com","received_emails":0,"description":"abc"}}}'
```