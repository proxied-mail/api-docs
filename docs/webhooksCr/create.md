# POST /api/v1/callback


URL: POST https://proxiedmail.com/api/v1/callback

Response (200):

```json
{
  "status": "ok",
  "call_url": "https://proxiedmail.com/api/v1/callback/call/27c4f31ebcb6307e8daa68f681f84161",
  "get_url": "https://proxiedmail.com/api/v1/callback/get/27c4f31ebcb6307e8daa68f681f84161"
}
```

status - always should be "ok"
"call_url" - URL to call to send data to your webhook. Recording any kind of data from payload (form-data/json) and called method. 
Doesn't recording headers yet.
"get_url" - URL to call to get data from your webhook. 

You can send any data to url placed in "call_url" and then call "get_url" to get this data back.

----

cURL:

```bash
curl --location --request POST 'https://proxiedmail.com/api/v1/callback' \
--header 'authority: proxiedmail.com' \
--header 'accept: application/json' \
--header 'Token: YOUR_TOKEN' \
--header 'content-type: application/json'
```