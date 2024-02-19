---
sidebar_position: 4
---

# GET /api/v1/received-emails-links/{id}

URL: GET https://proxiedmail.com/api/v1/received-emails-links/{id}

List of links to received emails. Use the link attribute with endpoint that indicates call url (with the same headers) to get email payload and more details.

Payload:

```json
{
  "data": [
    {
      "type": "received_emails_link",
      "id": "81F8AD00-0000-0000-00003CC8",
      "attributes": {
        "recipient_email": "7ndas0szr0@pxdmail.net",
        "sender_email": "webfay1@gmail.com",
        "subject": "hihihi",
        "attachmentsCounter": 0,
        "link": "/api/v1/received-emails/81F8AD00-0000-0000-00003CC8",
        "is_processed": true,
        "created_at": "2023-07-17 10:59:05",
        "updated_at": "2023-07-17 10:59:08"
      }
    },
    {
      "type": "received_emails_link",
      "id": "A38E8D00-0000-0000-00003CC8",
      "attributes": {
        "recipient_email": "7ndas0szr0@pxdmail.net",
        "sender_email": "webfay1@gmail.com",
        "subject": "hihihi",
        "attachmentsCounter": 0,
        "link": "/api/v1/received-emails/A38E8D00-0000-0000-00003CC8",
        "is_processed": true,
        "created_at": "2023-07-17 10:50:48",
        "updated_at": "2023-07-17 10:50:55"
      }
    }
  ]
}
```

Please note that proxy-email should be browsable. (is_browsable attribute).

cUrl:

```bash
curl --location --request GET 'https://proxiedmail.com/api/v1/received-emails-links/received-emails-links' \
--header 'accept: application/json' \
--header 'content-type: application/json' \
--header 'Token: Auth_TOKEN'
```