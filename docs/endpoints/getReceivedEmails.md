---
sidebar_position: 4
---

# GET /api/v1/receivedEmailId/{receivedEmailId}

URL: GET https://proxiedmail.com/api/v1/receivedEmailId/{receivedEmailId}

Message payload of specific received email.

Payload:

```json
{
  "data": {
    "type": "received_emails_details",
    "id": "81F8AD00-0000-0000-00003CC8",
    "attributes": {
      "recipient_email": "7ndas0szr0@pxdmail.net",
      "sender_email": "webfay1@gmail.com",
      "payload": {
        "To": "<7ndas0szr0@pxdmail.net>",
        "From": "\"Alex Yatsenko\" <webfay1@gmail.com>",
        "Subject": "hihihi",
        "recipient": "7ndas0szr0@pxdmail.net",
        "sender": "webfay1@gmail.com",
        "body-html": "<div dir=\"ltr\">helllloooo</div>",
        "body-plain": "helllloooo",
        "attachments": null
      },
      "attachments": [],
      "is_processed": true,
      "created_at": "2023-07-17 10:59:05",
      "updated_at": "2023-07-17 10:59:08"
    }
  }
}
```

cUrl:

```bash
curl --location --request GET 'https://proxiedmail.com/api/v1/received-emails/{receivedEmailId}' \
--header 'accept: application/json' \
--header 'content-type: application/json' \
--header 'Token: Auth_TOKEN'
```