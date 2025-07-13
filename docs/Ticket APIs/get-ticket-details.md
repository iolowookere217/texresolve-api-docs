---
sidebar_position: 4
---

# Get  Tickets Details

Learn how to fetch all details of a ticket.

## Request

- **Method**: GET
- **Endpoint**: `https://tex-resolve-backend.onrender.com/api/v1/user/tickets/id`

### Query Parameters

| Parameter  | Type   | Description                                                      |
|------------|--------|------------------------------------------------------------------|
| `id`     | String | The id of the ticket           |


## Responses

### Success

```json title="code 200: Success"
{
  "ticket": 
    {
      "_id": "654b68e9c4ab84dcc26ad908",
      "title": "Bug in login form",
      "description": "The login button does not respond.",
      "attempted_solution": "Cleared cache and cookies, but issue persists.",
      "tags": ["bug", "frontend"],
    },
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


