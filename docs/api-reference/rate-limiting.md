# Rate Limiting and Throttling

To ensure fair usage and system stability, PaySecure API enforces rate limits on all endpoints.

## Rate Limits
- **Standard Users:** 100 requests per minute
- **Premium Users:** 500 requests per minute
- **Enterprise Users:** Custom limits available upon request

## Throttling Behavior
- If you exceed your rate limit, the API will return a `429 Too Many Requests` response.
- Wait for the specified time in the `Retry-After` header before retrying.

**Example Response:**
```http
HTTP/1.1 429 Too Many Requests
Retry-After: 60
Content-Type: application/json

{
  "status": "error",
  "message": "Rate limit exceeded. Please try again later."
}
```

## Best Practices
- Implement exponential backoff for retries
- Monitor your usage and adjust requests accordingly
- Contact support for higher limits if needed

---

[Next: Security Considerations](./security.md)
