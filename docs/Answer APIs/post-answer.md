---
sidebar_position: 1
---

# Post an Answer

Learn how to post an answer to a ticket in TexResolve. You can also post a reply to an existing answer by including a `parentAnswerId`.

---

### **Authentication**

This endpoint requires authentication. You must include an **access token** in the `Authorization` header of your request.

#### Example Authorization Header:

```
Authorization: Bearer <your_access_token>
```

---

## Request

- **Method**: `POST`
- **Endpoint**: `https://texresolve-backend.onrender.com/api/v1/answers`

🚨 Authentication is required.

---

### Body Parameters

| Parameter        | Type   | Description                                                         |
| ---------------- | ------ | ------------------------------------------------------------------- |
| `ticketId`       | String | The ID of the ticket you are answering                              |
| `content`        | String | The text content of the answer or reply                             |
| `parentAnswerId` | String | _(Optional)_ ID of the answer being replied to (for nested replies) |

#### Example Request Body

```json
{
  "ticketId": "6806b42cff83eb889a678a86",
  "content": "This is a reply posted to the answer posted by Goes Rodgrigo for the question posted by Tunde Williams",
  "parentAnswerId": "68684e4fb775caac577a94cf"
}
```

---

## **Responses**

### **Success**

```jsx title="statusCode 201: Success"
Answer posted successfully
```

:::tip Success Tip
Congratulations! You have successfully posted an answer to the ticket.
:::

### **Error**

```jsx title="statusCode 500: Internal Server Error"
{
  "error": "User token is not valid or does not exist"
}
```

```jsx title="statusCode 500: Internal Server Error"
{
"error": "Ticket ID is required"
}
```

```jsx title="statusCode 500: Internal Server Error"
{
  "error": "Content field is required"
}

```

```jsx title="statusCode 500: Internal Server Error"
{
  "error": "Something went wrong. Please try again later."
}


```
