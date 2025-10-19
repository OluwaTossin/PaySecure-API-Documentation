# Authentication and Authorization Methods

To ensure secure access to the PaySecure API, all requests must be authenticated and authorized. PaySecure API uses API keys for authentication and supports both user-level and application-level authorization.

## API Key Generation

![API Key Page](https://github.com/OluwaTossin/PaySecure-API-Documentation-Images/raw/main/API%20Key%20Page.png)

1. Log in to PaySecure Dashboard:
   - Navigate to the PaySecure dashboard and log in with your credentials.
2. Generate API Key:
   - Go to the "API Keys" section.
   - Click on "Generate New API Key" and provide a name for the key.
   - Select the appropriate permissions for the key (read, write, etc.).
   - Click "Generate" to create the API key.
   - Copy the generated API key and store it securely.

**Example API Key:**
```python
api_key = "your_api_key_here"
```

## Using API Key for Authentication
To authenticate API requests, include the API key in the `Authorization` header:

```http
Authorization: Bearer your_api_key_here
```

### Authorization Methods
- **User-Level Authorization:** Ensures that actions are performed by authenticated users. Each user has a unique API key with specific permissions.
- **Application-Level Authorization:** Grants API access to applications. Each application has a unique API key with defined scopes and permissions.

**Example Authorization Header:**
```http
GET /transactions HTTP/1.1
Host: api.paysecure.com
Authorization: Bearer your_api_key_here
Content-Type: application/json
```

---

[Next: API Architecture Diagram](./architecture.md)
