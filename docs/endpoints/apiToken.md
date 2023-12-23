---
sidebar_position: 2
---

# GET /api/v1/api-token

URL: GET https://proxiedmail.com/api/v1/api-token

You can use this endpoint to obtain API token after authentication.
As an alternative you can use https://proxiedmail.com/en/settings API page token to do get it done.


Response (200):
```json
{
    "token": "a098ea9a8d23TOKENTOKEN066e23d6222"
}
```

Errors: -


cURL:
```bash
curl --location --request GET 'https://proxiedmail.com/api/v1/api-token' \
--header 'accept: application/json' \
--header 'authorization: Bearer TOKEN'
```

Use your Bearer token to authenticate to this request. For all further requests you can use Token header with received token as value.