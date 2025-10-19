# API Endpoints and Methods

PaySecure API provides a comprehensive set of endpoints for payment processing, transaction management, and user authentication.

## Core Endpoints

### 1. Authentication
- **POST /auth/login**: Authenticate user and obtain access token
- **POST /auth/logout**: Invalidate user session

### 2. Transactions
- **POST /transactions**: Create a new transaction
- **GET /transactions/{id}**: Retrieve transaction details
- **GET /transactions**: List all transactions
- **PUT /transactions/{id}**: Update transaction
- **DELETE /transactions/{id}**: Cancel transaction

### 3. Payments
- **POST /payments**: Process a payment
- **GET /payments/{id}**: Get payment status

### 4. Refunds & Chargebacks
- **POST /refunds**: Initiate a refund
- **GET /refunds/{id}**: Get refund status
- **POST /chargebacks**: Initiate a chargeback
- **GET /chargebacks/{id}**: Get chargeback status

### 5. Transaction History
- **GET /transactions/history**: Retrieve transaction history

## Example Request
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

---

[Next: Request and Response Formats](./formats.md)
