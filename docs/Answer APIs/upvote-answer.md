---
sidebar_position: 6
---

# Upvote an Answer

Learn how to upvote an answer in TexResolve to show support or agreement with a solution provided by another user.

---

## Request

- **Method**: `PATCH`
- **Endpoint**: `https://texresolve-backend.onrender.com/api/v1/answers/:answerId/upvote`

### Path Parameters

| Parameter   | Type   | Description                            |
| ----------- | ------ | -------------------------------------- |
| `answerId`  | String | The unique ID of the answer to upvote |

> 🚨 You must be authenticated to upvote an answer.

---

## Body Parameters

No body parameters are required for this request. The answer ID in the URL and the user token in the headers are sufficient.

---

## Headers

| Header          | Value             | Required | Description                          |
| --------------- | ----------------- | -------- | ------------------------------------ |
| `Authorization` | `Bearer <token>` | Yes      | JWT token of the authenticated user |

---

## Example Request

```bash
PATCH https://texresolve-backend.onrender.com/api/v1/answers/64fa8b73c9/upvote
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6...
```

---

## Responses

### ✅ Success

```json
{
  "message": "Upvoted answer successfully."
}
```

:::tip Info
Users can only upvote an answer once. If they previously downvoted, the system will switch their vote from downvote to upvote and adjust the vote counts and points accordingly.
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
  "error": "You have already upvoted this answer"
}
```

```json
{
  "error": "Something went wrong. Please try again later."
}
```

---

## Summary

- ✅ Use this endpoint to show support for an answer provided by another user.
- 🔐 Requires authentication.
- ⛔ Each user can upvote an answer only once unless switching from a downvote.
