
API Documentation
This documentation provides details on how to use the API endpoints.

📥 Get Domains
Endpoint: api/domains/{apiKey}/{type}

Method: GET

Parameters:

apiKey – Your API key.

type – Type of domains to fetch (free, premium, all).

Example Request:

http
Copy
Edit
GET api/domains/your-api-key/all
Example Response:

json
Copy
Edit
{
  "status": true,
  "data": {
    "domains": [
      {
        "domain": "free.com",
        "type": "Free"
      },
      {
        "domain": "lobage.com",
        "type": "Free"
      },
      {
        "domain": "premium.com",
        "type": "Premium"
      }
    ]
  }
}
📧 Create Email
Endpoint: api/emails/{apiKey}

Method: POST

Parameters:

apiKey – Your API key.

Example Request:

http
Copy
Edit
POST api/emails/your-api-key
Example Response:

json
Copy
Edit
{
  "status": true,
  "data": {
    "email": "random@example.com",
    "domain": "example.com",
    "ip": "127.0.0.1",
    "fingerprint": "eef780ab2ec7535e66c1405c0bff1c64",
    "expire_at": "2025-01-01T00:00:00.000000Z",
    "created_at": "2025-01-01T00:00:00.000000Z",
    "id": 1,
    "email_token": "email_token"
  }
}
✏️ Update Email
Endpoint: api/emails/{apiKey}/{email}/{username}/{domain}

Method: POST

Parameters:

apiKey – Your API key.

email – The current email address.

username – The new username.

domain – The new domain.

Example Request:

http
Copy
Edit
POST api/emails/your-api-key/old@example.com/newuser/newexample.com
Example Response:

json
Copy
Edit
{
  "status": true,
  "data": {
    "email": "newuser@newexample.com",
    "domain": "newexample.com",
    "ip": "127.0.0.1",
    "fingerprint": "eef780ab2ec7535e66c1405c0bff1c64",
    "expire_at": "2025-01-01T00:00:00.000000Z",
    "created_at": "2025-01-01T00:00:00.000000Z",
    "id": 2,
    "email_token": "email_token"
  }
}
🗑️ Delete Email
Endpoint: api/emails/{apiKey}/{email}

Method: POST

Parameters:

apiKey – Your API key.

email – The email address to delete.

Example Request:

http
Copy
Edit
POST api/emails/your-api-key/old@example.com
Example Response:

json
Copy
Edit
{
  "status": true,
  "message": "Email has been successfully deleted."
}
📬 Get Messages
Endpoint: api/messages/{apiKey}/{email}

Method: GET

Parameters:

apiKey – Your API key.

email – The email address to fetch messages for.

Example Request:

http
Copy
Edit
GET api/messages/your-api-key/example@example.com
Example Response:

json
Copy
Edit
{
  "status": true,
  "mailbox": "example@example.com",
  "messages": [
    {
      "is_seen": true,
      "subject": "Test Subject",
      "from": "John Doe",
      "from_email": "john@example.com",
      "to": "example@example.com",
      "receivedAt": "2025-01-01 00:00:38",
      "id": "ap94AWDg123ELQz07vrVB9dLXlbqZM5NGwYxOJKko8n6m1",
      "html": true,
      "content": "Test content",
      "attachments": [
        {
          "name": "file.txt",
          "extension": "txt",
          "size": 91,
          "url": "http://yoursite.com/api/d/ap94AWDg123ELQz07vrVB9dLXlbqZM5NGwYxOJKko8n6m1/file.txt"
        }
      ]
    }
  ]
}
📨 Get Message
Endpoint: api/messages/{apiKey}/message/{messageId}

Method: GET

Parameters:

apiKey – Your API key.

messageId – The message ID to retrieve.

Example Request:

http
Copy
Edit
GET api/messages/your-api-key/message/ap94AWDg123ELQz07vrVB9dLXlbqZM5NGwYxOJKko8n6m1
Example Response:

json
Copy
Edit
{
  "status": true,
  "message": {
    "subject": "Test Subject",
    "from": "John Doe",
    "from_email": "john@example.com",
    "to": "example@example.com",
    "receivedAt": "2025-01-01 00:00:38",
    "id": "ap94AWDg123ELQz07vrVB9dLXlbqZM5NGwYxOJKko8n6m1",
    "html": true,
    "content": "Test content",
    "attachments": [
      {
        "name": "file.txt",
        "extension": "txt",
        "size": 91,
        "url": "http://yoursite.com/api/d/ap94AWDg123ELQz07vrVB9dLXlbqZM5NGwYxOJKko8n6m1/file.txt"
      }
    ]
  }
}
