---
sidebar_position: 7
---

# Downvote a Ticket

Learn how to downvote a ticket in TexResolve and provide constructive feedback on why the ticket is not helpful, clear, or relevant.

---

## Request

- **Method**: `POST`
- **Endpoint**: `https://texresolve-backend.onrender.com/api/v1/tickets/id/downvote`

### Path Parameters

| Parameter | Type   | Description                             |
| --------- | ------ | --------------------------------------- |
| `id`      | String | The unique ID of the ticket to downvote |

> 🚨 You must be authenticated to downvote a ticket.

---

## Body Parameters

| Parameter  | Type   | Description                             |
| ---------- | ------ | --------------------------------------- |
| `feedback` | String | Explanation for the downvote (required) |

### Example Body

```json
{
  "feedback": "The question to me Goes Rodrigo, is unclear and lacks details."
}
```

---

## Headers

| Header          | Value            | Required | Description                         |
| --------------- | ---------------- | -------- | ----------------------------------- |
| `Authorization` | `Bearer <token>` | Yes      | JWT token of the authenticated user |

---

## Example Request

```bash
POST https://texresolve-backend.onrender.com/api/v1/tickets/64fa8b73c9/downvote
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6...
Content-Type: application/json

{
  "feedback": "The question to me Goes Rodrigo, is unclear and lacks details."
}
```

---

## Responses

### ✅ Success

```json
{
  "message": "Ticket downvoted and feedback recorded"
}
```

:::tip Info
Each user can only downvote a ticket once, and feedback is required to ensure accountability.
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
  "error": "User not allowed to downvote this ticket"
}
```

```json
{
  "error": "Ticket ID does not exist"
}
```

```json
{
  "error": "You have already downvoted this ticket"
}
```

```json
{
  "error": "Feedback is required for downvoting"
}
```

```json
{
  "error": "Something went wrong. Please try again later."
}
```

---

## Summary

- 👎 Use this endpoint to downvote a ticket that is unclear or not useful.
- 🗣️ Feedback is mandatory to promote constructive criticism.
- 🔐 Requires authentication.
- ⛔ Each user can downvote a ticket only once.
