# Request and Response Formats

PaySecure API uses JSON for all requests and responses. Below are examples and guidelines for formatting your API calls.

## JSON Structure for Requests

The PaySecure API uses JSON format for both requests and responses. This ensures that data is easily readable and transferable between the client and server.

**General JSON Structure for Requests:**
```json
{
  "amount": 1000,
  "currency": "USD",
  "description": "Transaction Description",
  "payment_method": {
    "type": "credit_card",
    "card_number": "4111111111111111",
    "expiry_month": "12",
    "expiry_year": "2025",
    "cvv": "123"
  }
}
```

## Sample Request and Response Examples

### Sample Request

**Endpoint:** `POST /transactions`

```http
POST /transactions HTTP/1.1
Host: api.paysecure.com
Authorization: Bearer your_access_token
Content-Type: application/json

{
  "amount": 1000,
  "currency": "USD",
  "description": "Test Transaction",
  "payment_method": {
    "type": "credit_card",
    "card_number": "4111111111111111",
    "expiry_month": "12",
    "expiry_year": "2025",
    "cvv": "123"
  }
}
```

### Sample Response

```http
HTTP/1.1 201 Created
Content-Type: application/json

{
  "transaction_id": "txn_123456789",
  "status": "pending",
  "amount": 1000,
  "currency": "USD",
  "description": "Test Transaction",
  "payment_method": {
    "type": "credit_card",
    "card_number": "4111111111111111",
    "expiry_month": "12",
    "expiry_year": "2025",
    "cvv": "123"
  },
  "created_at": "2023-07-15T12:34:56Z"
}
```

**JSON Example:**
```json
{
  "transaction_id": "txn_123456789",
  "status": "pending",
  "amount": 1000,
  "currency": "USD",
  "description": "Test Transaction",
  "payment_method": {
    "type": "credit_card",
    "card_number": "4111111111111111",
    "expiry_month": "12",
    "expiry_year": "2025",
    "cvv": "123"
  },
  "created_at": "2023-07-15T12:34:56Z"
}
```

## Error Codes and Handling

The PaySecure API returns appropriate HTTP status codes for different types of errors. Here are some common error codes and their meanings:

- **400 Bad Request:** The request could not be understood or was missing required parameters.
- **401 Unauthorized:** Authentication failed or user does not have permissions for the requested operation.
- **404 Not Found:** The requested resource could not be found.
- **500 Internal Server Error:** An error occurred on the server.

### Example Error Response

**Request:**
```http
POST /transactions HTTP/1.1
Host: api.paysecure.com
Authorization: Bearer invalid_access_token
Content-Type: application/json

{
  "amount": 1000,
  "currency": "USD",
  "description": "Test Transaction",
  "payment_method": {
    "type": "credit_card",
    "card_number": "4111111111111111",
    "expiry_month": "12",
    "expiry_year": "2025",
    "cvv": "123"
  }
}
```

**Response:**
```http
HTTP/1.1 401 Unauthorized
Content-Type: application/json

{
  "error": {
    "code": "401",
    "message": "Invalid access token"
  }
}
```

**Error Message Example:**
```json
{
  "error": {
    "code": "401",
    "message": "Invalid access token"
  }
}
```

---

[Next: Rate Limiting and Throttling](./rate-limiting.md)

---

<div style="display: flex; justify-content: space-between; margin-top: 40px; padding: 20px 0; border-top: 2px solid #eee;">
  <a href="#/api-reference/endpoints" style="text-decoration: none; color: #2c3e50; font-weight: 500;">← Previous: Endpoints</a>
  <a href="#/api-reference/rate-limiting" style="text-decoration: none; color: #2c3e50; font-weight: 500;">Next: Rate Limiting →</a>
</div>
