---
sidebar_position: 3
---

# Update Ticket

Learn how to update a ticket in TexResolve.

## Request

- **Method**: PUT
- **Endpoint**: `https://tex-resolve-backend.onrender.com/api/v1/user/tickets/id`

### Query Parameters

| Parameter  | Type   | Description                                                      |
|------------|--------|------------------------------------------------------------------|
| `id`     | String | The id of the ticket           |


### Body Parameters

- **Ticket Update Details**: Provide the fields to update.

```jsx title="update ticket schema"
{
  title?: string, // Updated title of the issue
  description?: string, // Updated issue description
  attempted_solution?: string, // Updated steps attempted to resolve the issue
  attachments?: Array<{ public_id: string; url: string }>, // Optional updated attachments
  tags?: string[], // Updated array of tags
}
```

Here's an example request body for updating a ticket:

```jsx title="updating ticket example"
{
  "title": "Updated Login Issue",
  "description": "Still unable to log in, even after resetting the password.",
  "attempted_solution": "Checked browser settings and tried incognito mode.",
  "tags": ["login", "authentication", "error"],
}
```

## Responses

### Success

```jsx title="statusCode 200: success"
Ticket details updated successfully
```

### Errors

```jsx title="statusCode 401: Authentication error"
User token is not valid or does not exist
```

```jsx title="statusCode 403: Forbidden"
User not authorized to update this ticket
```

```jsx title="statusCode 400: Bad Request"
Invalid request parameters
```

```jsx title="statusCode 404: Not Found"
Ticket ID does not exist
```

```jsx title="statusCode 500: Internal Server Error"
Try again or restart service
```

