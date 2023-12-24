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



Response (201):
```json
{
    "meta": {
        "usedProxyBindings": 4,
        "availableProxyBindings": 10,
        "isVerificationEmailSend": false
    },
    "data": [
        {
            "type": "proxy_bindings",
            "id": "A1131D57-6000-0000-00000BAE",
            "attributes": {
                "real_addresses": {
                    "kkkchinazes@pxdmail.int": {
                        "is_enabled": true,
                        "is_verification_needed": false,
                        "is_verified": false
                    }
                },
                "proxy_address": "q1v9nj1gkw@proxiedmail.com",
                "received_emails": 0,
                "description": "",
                "callback_url": "",
                "created_at": "2023-12-23 23:32:12",
                "updated_at": "2023-12-23 23:32:12"
            },
            "relationships": {
                "user": {
                    "data": {
                        "type": "users",
                        "id": "A2F49023-0000-0000-00009BC6"
                    }
                }
            }
        },
        {
            "type": "proxy_bindings",
            "id": "14589847-6000-0000-00000BAE",
            "attributes": {
                "real_addresses": {
                    "kkkchinazes@pxdmail.int": {
                        "is_enabled": true,
                        "is_verification_needed": false,
                        "is_verified": false
                    }
                },
                "proxy_address": "d0zjr5gnswi@proxiedmail.com",
                "received_emails": 0,
                "description": "",
                "callback_url": "https:\/\/zalupa.int",
                "created_at": "2023-12-23 14:06:43",
                "updated_at": "2023-12-23 14:06:43"
            },
            "relationships": {
                "user": {
                    "data": {
                        "type": "users",
                        "id": "A2F49023-0000-0000-00009BC6"
                    }
                }
            }
        },
        {
            "type": "proxy_bindings",
            "id": "D6517747-6000-0000-00000BAE",
            "attributes": {
                "real_addresses": {
                    "kkkchinazes@pxdmail.int": {
                        "is_enabled": true,
                        "is_verification_needed": false,
                        "is_verified": false
                    }
                },
                "proxy_address": "d0zjr5gnwi@proxiedmail.com",
                "received_emails": 0,
                "description": "",
                "callback_url": "",
                "created_at": "2023-12-23 13:22:24",
                "updated_at": "2023-12-23 13:22:24"
            },
            "relationships": {
                "user": {
                    "data": {
                        "type": "users",
                        "id": "A2F49023-0000-0000-00009BC6"
                    }
                }
            }
        },
        {
            "type": "proxy_bindings",
            "id": "C6C4C547-6000-0000-00000BAE",
            "attributes": {
                "real_addresses": {
                    "kkkchinazes@pxdmail.int": {
                        "is_enabled": true,
                        "is_verification_needed": false,
                        "is_verified": false
                    }
                },
                "proxy_address": "v7do1zfs8w@proxiedmail.com",
                "received_emails": 0,
                "description": "",
                "callback_url": "",
                "created_at": "2023-12-23 12:56:32",
                "updated_at": "2023-12-23 12:56:32"
            },
            "relationships": {
                "user": {
                    "data": {
                        "type": "users",
                        "id": "A2F49023-0000-0000-00009BC6"
                    }
                }
            }
        },
        {
            "type": "proxy_bindings",
            "id": "DBE6A547-6000-0000-00000BAE",
            "attributes": {
                "real_addresses": {
                    "kkkchinazes@pxdmail.int": {
                        "is_enabled": true,
                        "is_verification_needed": false,
                        "is_verified": false
                    }
                },
                "proxy_address": "news-65ddf8@proxiedmail.com",
                "received_emails": 0,
                "description": "Automatic address, created to send you tips on how to stay safe online and protect the ownership of your digital assets",
                "callback_url": "",
                "created_at": "2023-12-23 12:53:22",
                "updated_at": "2023-12-23 12:53:22"
            },
            "relationships": {
                "user": {
                    "data": {
                        "type": "users",
                        "id": "A2F49023-0000-0000-00009BC6"
                    }
                }
            }
        }
    ]
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