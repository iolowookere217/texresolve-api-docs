---
sidebar_position: 6
---

# Delete  Ticket

Learn how to delete a ticket.

## Request

- **Method**: DELETE
- **Endpoint**: `https://tex-resolve-backend.onrender.com/api/v1/user/tickets/id`

### Query Parameters

| Parameter  | Type   | Description                                                      |
|------------|--------|------------------------------------------------------------------|
| `id`     | String | The id of the ticket           |


## Responses

### Success

```json title="code 200: Success"
{
"message": "Ticket and its attachments deleted successfully"
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


