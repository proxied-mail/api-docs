---
sidebar_position: 5
---

# PATCH /api/v1/proxy-bindings

URL: PATCH https://proxiedmail.com/api/v1/proxy-bindings

```json
{
   "data":{
      "id":"A1131D57-6000-0000-00000BAE",
      "type":"proxy_bindings",
      "attributes":{
         "real_addresses":{
            "kkkchinazes@pxdmail.int":{
               "is_enabled":true,
               "is_verification_needed":false,
               "is_verified":false
            }
         },
         "proxy_address":"q1v9nj1gkw@proxiedmail.com",
         "received_emails":0,
         "description":"abc"
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
--data-raw '{"data":{"id":"A1131D57-6000-0000-00000BAE","type":"proxy_bindings","attributes":{"real_addresses":{"kkkchinazes@pxdmail.int":{"is_enabled":true,"is_verification_needed":false,"is_verified":false}},"proxy_address":"q1v9nj1gkw@proxiedmail.com","received_emails":0,"description":"abc"}}}'
```