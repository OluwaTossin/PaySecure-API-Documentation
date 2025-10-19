# Request and Response Formats

PaySecure API uses JSON for all requests and responses. Below are examples and guidelines for formatting your API calls.

## Request Format
- All requests must include the `Authorization` header with your API key.
- Content-Type must be set to `application/json`.

**Example Request:**
```http
POST /transactions HTTP/1.1
Host: api.paysecure.com
Authorization: Bearer your_api_key_here
Content-Type: application/json

{
  "amount": 100.00,
  "currency": "USD",
  "recipient": "user@example.com"
}
```

## Response Format
- Responses are returned in JSON format.
- Standard fields include `status`, `message`, and `data`.

**Example Response:**
```json
{
  "status": "success",
  "message": "Transaction created successfully.",
  "data": {
    "transaction_id": "abc123",
    "amount": 100.00,
    "currency": "USD",
    "recipient": "user@example.com"
  }
}
```

---

[Next: Rate Limiting and Throttling](./rate-limiting.md)
