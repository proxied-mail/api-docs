---
sidebar_position: 1
---

# POST /api/v1/auth (auth)

URL: https://proxiedmail.com/api/v1/auth

Payload:
```json
{
   "data":{
      "type":"auth-request",
      "attributes":{
         "username":"ya@pxdmail.net",
         "password":"1"
      }
   }
}
```


Error (code 401):

```json
{
   "data":{
      "id":"6586bb110fe0f",
      "type":"errors",
      "attributes":{
         "message":"User or password not exists",
         "exception":"Modules\\Auth\\Exceptions\\WrongUserOrPasswordException",
         "file":"/app/Modules/Auth/Services/Auth/Authenticator.php",
         "line":79
      }
   }
}
```

Success (200):

```json
{
    "data": {
        "type": "oauth-access-tokens",
        "id": "23e7e284c25711541b395127883b7e132312321321250d619016b41fa84aa646aa3d96ebd6d0fc0",
        "attributes": {
            "token": "BEARER TOKEN",
            "expires_at": "2024-12-23 10:55:18",
            "2fa_granted": 0,
            "isNewAcc": false
        },
        "relationships": {
            "user": {
                "data": {
                    "type": "users",
                    "id": "D4057000-0000-G000-Y0009BC6"
                }
            }
        }
    }
}
```

---

cURL:
```bash
curl --location --request POST 'https://proxiedmail.com/api/v1/auth' \
--header 'content-type: application/json' \
--header 'Accept: application/json' \
--data-raw '{"data":{"type":"auth-request","attributes":{"username":"ya@pxdmail.net","password":"1"}}}'
```