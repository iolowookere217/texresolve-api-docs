---
sidebar_position: 2
---

# Create Ticket

Learn how to create a ticket in TexResolve.

## Request

- **Method**: POST
- **Endpoint**: `https://tex-resolve-backend.onrender.com/api/v1/tickets`




### Body Parameters

- **Ticket Details**: Enter the details for the ticket.

title="Ticket Schema"
| Parameter         | Type     | Description                                  |
|------------------|---------|----------------------------------------------|
| title           | String  | Title of the issue                           |
| category           | String  | Category of the issue                           |
| description     | String  | Detailed issue description                   |
| attempted_solution | String  | Steps attempted to resolve the issue        |
| attachments?    | File    | Optional file attachments                    |
| tags?          | String[] | Array of tags                                |


Here's an example request body for creating a ticket:

```jsx title="creating ticket example"
{
  "title": "Login Issue",
  "description": "Unable to log in with correct credentials.",
  "attempted_solution": "Tried resetting password and clearing cache.",
  "tags": ["login", "authentication"],
  "attachments": [file1.png, file2.png]
}
```

## Responses

### Success

```jsx title="statusCode 201: success"
Ticket created successfully
```

### Errors

```jsx title="statusCode 401: Authentication error"
User token is not valid or does not exist or expired
```

```jsx title="statusCode 400: Bad Request"
Invalid request parameters or failed to upload attachments
```

```jsx title="statusCode 500: Internal Server Error"
Try again or restart service
```

