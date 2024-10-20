---
sidebar_position: 1
---

# Tokens difference

There is 2 types of tokens in ProxiedMail API:
- API token
- Bearer Token

## Bearer Token

Bearer token you're getting on endpoint /api/v1/auth
To authenticate via Bearer token you need to pass it to the `Authorization` header.
Bearer token has some expiration date and currently it's not refreshable.
In order to refresh bearer token you need to re-login.

## API token

API token you can get via /api/v1/api-token endpoint.
In order to use API token you would need to pass it to the `Token` header.
This token doesn't have an expiration date, but could be revoked by request.

## Which token to use?

You can obtain API Token manually when you login into the ProxiedMail web interface.
Just visit the Settings page: https://proxiedmail.com/en/settings.
You can hard code this token into your application.
If your use case of ProxiedMail app is different and you want to automatically obtain token, just use the following steps:
1. Authenticate via /api/v1/auth endpoint.
2. Obtain Bearer token.
3. Obtain API token via /api/v1/api-token endpoint.
4. Use API token for further requests.

If you have any further questions about tokens -  feel free to reach us out by email specified on the website or "Ask Us" button.





