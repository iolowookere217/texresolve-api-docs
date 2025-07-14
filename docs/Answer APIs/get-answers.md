---
sidebar_position: 2
---

# Get All Answers for a ticket

Learn how to retrieve all answers for a ticket from the TexResolve platform.

---

### **Authentication**

This endpoint requires authentication. You must include an **access token** in the `Authorization` header of your request.

#### Example Authorization Header:

```
Authorization: Bearer <your_access_token>
```

---

## **Request**

- **Method**: `GET`
- **Endpoint**: `https://texresolve-backend.onrender.com/api/v1/answers/ticketId`

### Body Parameters

| Parameter  | Type   | Description                                            |
| ---------- | ------ | ------------------------------------------------------ |
| `ticketId` | String | The ID of the ticket you wish to retrieve it's answers |

## **Responses**

### ✅ **Success**

```json
{
  "success": true,
  "answers": [
    {
      "_id": "68684e4fb775caac577a94cf",
      "ticketId": "6806b42cff83eb889a678a86",
      "content": "This is an answer to the question posted by Tunde Williams",
      "answeredBy": {
        "id": "6833a2064f1e33ef9e0549a1",
        "name": "Goes Rodgrido",
        "jobTitle": "Devops Engineer",
        "photo": "https://example.com/photo.jpg"
      },
      "parentAnswerId": null,
      "createdAt": "2025-07-04T21:57:35.389Z",
      "updatedAt": "2025-07-04T21:57:35.389Z",
      "__v": 0,
      "replies": [
        {
          "_id": "68684fbab775caac577a94d1",
          "ticketId": "6806b42cff83eb889a678a86",
          "content": "This is a reply posted to the answer posted by Goes Rodgrigo for the question posted by Tunde Williams",
          "answeredBy": {
            "id": "685da5abedd5a694d6e8c7dd",
            "name": "Kylen",
            "jobTitle": "Lead Designer",
            "photo": "https://example.com/photo.jpg"
          },
          "parentAnswerId": "68684e4fb775caac577a94cf",
          "createdAt": "2025-07-04T22:03:38.707Z",
          "updatedAt": "2025-07-04T22:03:38.707Z",
          "__v": 0
        }
      ]
    }
  ]
}
```

:::tip Success Tip
All available answers are retrieved from the database and returned in the response.
:::

---

### ❌ **Errors**

#### **Unauthorized**

```json
{
  "error": "Invalid or expired token."
}
```

#### **Internal Server Error**

```json
{
  "error": "Something went wrong. Please try again later."
}
```

---

## **Summary**

- 📥 Use this endpoint to fetch all posted answers.
- 🔐 Requires a valid access token.
- 📊 Useful for displaying answer feeds, search, or moderation views.
