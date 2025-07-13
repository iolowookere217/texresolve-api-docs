---
sidebar_position: 3
---

# Add a resolver to meeting

Learn how to update a meeting by adding a resolver in TexResolve.

## Request

- **Method**: PATCH
- **Endpoint**: `https://tex-resolve-backend.onrender.com/api/v1/meetings/{id}`

### Body Parameters

- **Meeting Update Details**: Provide the fields to update(resolver).

```jsx title="update meeting schema"
{
  resolver_name: string, // Name of the resolver to be added/updated
}
```

Here's an example request body for updating a meeting:

```jsx title="updating meeting example"
{
  "resolver_name": "John Doe"
}
```

### Responses

#### Success

```json title="statusCode 200: success"
{
  "message": "Resolver name updated successfully"
}
```

#### Errors

```json title="statusCode 401: Authentication error"
{
  "message": "User token is not valid or does not exist"
}
```

```json title="statusCode 403: Forbidden"
{
  "message": "User not authorized to update this meeting"
}
```

```json title="statusCode 400: Bad Request"
{
  "message": "Invalid request parameters"
}
```

```json title="statusCode 500: Internal Server Error"
{
  "message": "Try again or restart service"
}
```