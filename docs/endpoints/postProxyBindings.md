---
sidebar_position: 4
---

# POST /api/v1/proxy-bindings

URL: POST https://proxiedmail.com/api/v1/proxy-bindings

Creating proxy-email.

Payload:

```json
{
   "data":{
      "type":"proxy_bindings",
      "attributes":{
         "real_addresses":[
            "kkkchinazes@pxdmail.int"
         ],
         "proxy_address":"d0zjr5gnwi@proxiedmail.com",
         "callback_url": ""
      }
   }
}
```

Pretty clear. Everything else you can add in PATCH request. 

You can specify callback_url or just left it blank. Example:
"callback_url": "https://zalupa.com/callback".

"proxy_address":"d0zjr5gnwi@proxiedmail.com" stands for proxy-email we will issue for you.

real_addresses is an array of real email addresses where we will forward all incoming emails.


Please note, that if you wish to omit email delivery somewhere and use only webhook, please use the following email addresses domains:
    @int.proxiedmail.com
    @proxiedmail-int.int
Example: testingadw@proxiedmail-int.int


Response (201):
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
            "description": "",
            "callback_url": "",
            "created_at": "2024-01-08 00:08:22",
            "updated_at": "2024-01-08 00:08:22"
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



---

cUrl:

```bash
curl --location --request POST 'https://proxiedmail.com/api/v1/proxy-bindings' \
--header 'accept: application/json' \
--header 'content-type: application/json' \
--header 'Token: Auth_TOKEN' \
--data-raw '{"data":{"type":"proxy_bindings","attributes":{"real_addresses":["kkkchinazes@pxdmail.int"],"proxy_address":"q1v9nj1gkw@proxiedmail.com"}}}'
```