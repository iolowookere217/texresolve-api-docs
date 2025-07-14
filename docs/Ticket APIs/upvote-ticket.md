---
sidebar_position: 6
---

# Upvote a Ticket

Learn how to upvote a ticket in TexResolve to show support or agreement with an issue raised by another user.

---

## Request

- **Method**: `POST`
- **Endpoint**: `https://texresolve-backend.onrender.com/api/v1/tickets/id/upvote`

### Path Parameters

| Parameter | Type   | Description                           |
| --------- | ------ | ------------------------------------- |
| `id`      | String | The unique ID of the ticket to upvote |

> 🚨 You must be authenticated to upvote a ticket.

---

## Body Parameters

No body parameters are required for this request. The ticket ID in the URL and the user token in the headers are sufficient.

---

## Headers

| Header          | Value            | Required | Description                         |
| --------------- | ---------------- | -------- | ----------------------------------- |
| `Authorization` | `Bearer <token>` | Yes      | JWT token of the authenticated user |

---

## Example Request

```bash
POST https://texresolve-backend.onrender.com/api/v1/tickets/64fa8b73c9/upvote
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6...
```

---

## Responses

### ✅ Success

```json
{
  "message": "Upvoted successfully",
  "upvotes": 12
}
```

:::tip Info
Users can only upvote a ticket once. Additional upvote attempts by the same user will be ignored or rejected.
:::

---

### ❌ Errors

```json
{
  "error": "User token is not valid or does not exist"
}
```

```json
{
  "error": "User not allowed to upvote this ticket"
}
```

```json
{
  "error": "Ticket ID does not exist"
}
```

```json
{
  "error": "You have already upvoted this ticket"
}
```

```json
{
  "error": "Something went wrong. Please try again later."
}
```

---

## Summary

- ✅ Use this endpoint to show support for a ticket raised by another user.
- 🔐 Requires authentication.
- ⛔ Each user can upvote a ticket only once.
