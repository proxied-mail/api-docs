---
sidebar_position: 3
---

# GET /api/v1/proxy-bindings


URL: GET https://proxiedmail.com/api/v1/proxy-bindings

Response (200):

```json
{
    "meta": {
        "usedProxyBindings": 1,
        "availableProxyBindings": 10,
        "isVerificationEmailSend": false
    },
    "data": [
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


Main things you have to know: it's a proxy-binding entity. Proxy-binding entity represents single proxy-email.
Single proxy-email could forward message to multiple real addresses.

In this example "kkkchinazes@pxdmail.int" is the real address where incoming emails will be forwarded.

Callback url is url where we will send callback in case of: a) callback url is set; b) new email is received. You can learn more about callbacks in other sections of documentation.

Please do not put proxiedmail emails as real addresses.

is_verified is the attribute that indicates that real address is verified via link send to this email.

If you want to omit sending any emails to the real address from the proxy-email please use the domain "int.proxiedmail.com" as a real address. Callbacks for this email will still go through.