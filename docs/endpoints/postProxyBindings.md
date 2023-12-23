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
         "callback_url": ""
      }
   }
}
```

Pretty clear. Everything else you can add in PATCH request. 

You can specify callback_url or just left it blank. Example:
"callback_url": "https://zalupa.com/callback"