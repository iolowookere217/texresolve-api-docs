---
sidebar_position: 2
---

# Get All Tickets

Learn how to fetch all tickets with pagination and search functionality.

## Request

- **Method**: GET
- **Endpoint**: `https://tex-resolve-backend.onrender.com/api/v1/tickets`

### Query Parameters

| Parameter  | Type   | Description                                                      |
|------------|--------|------------------------------------------------------------------|
| `page`     | Number | (Optional) Page number for pagination (default: 1)              |
| `limit`    | Number | (Optional) Number of tickets per page (default: 10)             |
| `category`   | String | (Optional) Keyword to search in ticket categories          |
| `title`   | String | (Optional) Keyword to search in ticket titles or tags          |
| `tags`     | Array  | (Optional) Filter tickets by one or more tags                   |



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

```json title="statusCode 400: Bad Request"
{
  "message": "Invalid query parameters"
}
```

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

:::tip Pagination tip

Use `page` and `limit` query parameters to navigate through results.

