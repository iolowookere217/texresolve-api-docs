---
sidebar_position: 3
---

# Get User Tickets

Learn how to fetch all tickets by a user.

## Request

- **Method**: GET
- **Endpoint**: `https://tex-resolve-backend.onrender.com/api/v1/tickets/me`




## Responses

### Success

```json title="code 200: Success"
{
  "tickets": [
    {
      "_id": "654b68e9c4ab84dcc26ad908",
      "title": "Bug in login form",
      "description": "The login button does not respond.",
      "attempted_solution": "Cleared cache and cookies, but issue persists.",
      "tags": ["bug", "frontend"],
    },
    // other tickets
  ],
  "totalPages": 5,
  "currentPage": 1
}
```

### Errors


```json title="statusCode 401: Authentication Error"
{
  "message": "User token is not valid or does not exist"
}
```

```json title="statusCode 404: Not Found"
{
  "message": "No tickets found"
}
```

```json title="statusCode 500: Internal Server Error"
{
  "message": "Try again or restart service"
}
```


