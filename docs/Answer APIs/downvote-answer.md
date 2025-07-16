---
sidebar_position: 7
---

# Downvote an Answer

Learn how to downvote an answer in TexResolve if you believe it is incorrect, unhelpful, or not relevant. Downvoting requires providing feedback.

---

## Request

- **Method**: `PATCH`
- **Endpoint**: `https://texresolve-backend.onrender.com/api/v1/answers/:answerId/downvote`

### Path Parameters

| Parameter   | Type   | Description                              |
| ----------- | ------ | ---------------------------------------- |
| `answerId`  | String | The unique ID of the answer to downvote |

> 🚨 You must be authenticated to downvote an answer.

---

## Body Parameters

| Parameter  | Type   | Required | Description                                  |
| ---------- | ------ | -------- | -------------------------------------------- |
| `feedback` | String | Yes      | Reason for downvoting (minimum 3 characters) |

---

## Headers

| Header          | Value             | Required | Description                          |
| --------------- | ----------------- | -------- | ------------------------------------ |
| `Authorization` | `Bearer <token>` | Yes      | JWT token of the authenticated user |

---

## Example Request

```bash
PATCH https://texresolve-backend.onrender.com/api/v1/answers/64fa8b73c9/downvote
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6...
Content-Type: application/json

{
  "feedback": "This answer is incorrect and not helpful."
}
```

---

## Responses

### ✅ Success

```json
{
  "message": "Answer downvoted and feedback recorded."
}
```

:::tip Info
Users can only downvote an answer once. If they previously upvoted, the system will switch their vote from upvote to downvote and adjust the vote counts and points accordingly.
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
  "error": "Answer ID does not exist"
}
```

```json
{
  "error": "Feedback is required for downvoting"
}
```

```json
{
  "error": "You have already downvoted this answer"
}
```

```json
{
  "error": "Something went wrong. Please try again later."
}
```

---

## Summary

- ✅ Use this endpoint to express disagreement with an answer.
- 🔐 Requires authentication.
- ⛔ Feedback is mandatory for all downvotes.
- ⛔ Each user can downvote an answer only once unless switching from an upvote.
