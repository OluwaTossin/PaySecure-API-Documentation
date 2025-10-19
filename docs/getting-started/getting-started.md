# Getting Started with PaySecure API

This guide will help you set up and begin using the PaySecure API for secure payment processing.

## Prerequisites
- PaySecure account with API access
- API key generated from the PaySecure dashboard
- Basic understanding of RESTful APIs
- Development environment with internet access

## API Key Generation

To start using the PaySecure API, you need to generate an API key. This key will authenticate your requests and ensure secure communication between your application and the PaySecure API.

### Steps to Generate an API Key

1. **Log in to PaySecure Dashboard:**
   - Navigate to the [PaySecure Dashboard](https://dashboard.paysecure.com/) and log in with your credentials.

   ![Login Page](https://github.com/OluwaTossin/PaySecure-API-Documentation-Images/raw/main/Login%20to%20PaySecure.png)

2. **Access API Key Section:**
   - Click on the "API Keys" tab in the navigation bar.

3. **Generate a New API Key:**
   - Click on the "Generate New API Key" button.
   - Provide a name for the API key (e.g., "Development Key").
   - Select the appropriate permissions (read, write, etc.).
   - Click "Generate" to create the API key.

   ![API Key Generation](https://github.com/OluwaTossin/PaySecure-API-Documentation-Images/raw/main/API%20Key%20Generation%20Page.png)

4. **Copy and Secure Your API Key:**
   - Copy the generated API key and store it securely. Do not share this key publicly.

## Sandbox Environment Setup

The sandbox environment allows you to test the PaySecure API without processing real transactions. This is ideal for development and testing purposes.

### Steps to Set Up Sandbox Environment

1. **Access Sandbox Settings:**
   - Navigate to the "Settings" tab in the PaySecure Dashboard.
   - Select "Sandbox Environment" from the dropdown menu.

   ![Sandbox Settings](https://github.com/OluwaTossin/PaySecure-API-Documentation-Images/raw/main/Sandbox%20Settings.png)

2. **Configure Sandbox Parameters:**
   - Enable the sandbox mode by toggling the switch.
   - Set up test payment methods and accounts.
   - Save the changes to activate the sandbox environment.

   ![Sandbox Configuration](https://github.com/OluwaTossin/PaySecure-API-Documentation-Images/raw/main/Sandbox%20Configuration.png)

## Making Your First API Call

Once you have your API key and sandbox environment set up, you can make your first API call. This example demonstrates how to create a test transaction.

### Steps to Make Your First API Call

1. **Set Up Your HTTP Client:**
   - You can use any HTTP client (e.g., Postman, cURL) to make API calls.
   - For this example, we will use cURL.

2. **Create a Test Transaction:**
   - Use the following cURL command to create a test transaction:

```bash
curl -X POST https://api.paysecure.com/v1/transactions \
  -H "Authorization: Bearer your_api_key_here" \
  -H "Content-Type: application/json" \
  -d '{
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
  }'
```

3. **Verify the Response:**
   - Upon successful execution, you should receive a response with transaction details.

**Example Response:**
```json
{
  "transaction_id": "txn_123456789",
  "status": "success",
  "amount": 1000,
  "currency": "USD",
  "description": "Test Transaction"
}
```

## Next Steps
- Explore available endpoints in the [API Reference](api-reference/endpoints.md)
- Review best practices in the [Guides](guides/best-practices.md)
- Learn about security in the [Security Considerations](guides/security.md)

---

[Next: API Endpoints and Methods](api-reference/endpoints.md)
