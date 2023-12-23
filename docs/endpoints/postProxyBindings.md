---
sidebar_position: 4
---

# POST /api/v1/proxy-bindings

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
         "callback_url": "https://zalupa.com/callback"
      }
   }
}
```

Pretty clear. Everything else you can add in PATCH request.