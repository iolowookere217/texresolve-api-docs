---
sidebar_position: 4
---

# Get User Information

Learn how to retrieve user information with TexResolve.

---

## **Request**

- **Method**: `GET`
- **Endpoint**: `https://tex-resolve-backend.onrender.com/api/v1/me`

### **Authentication**

This endpoint requires authentication. You must include an **access token** in the `Authorization` header of your request.

#### Example Authorization Header:
```
Authorization: Bearer <your_access_token>
```

---

## **Responses**

### **Success**
```jsx title="statusCode 200: Success"
User information retrieved successfully.
```

:::tip Success Tip
The user's details are fetched from the cache or database and returned in the response.
:::

#### Example Response:
```json
{
  "success": true,
  "user": {
   //user data
  }
}
```

### **Errors**

#### **User Not Found**
```jsx title="statusCode 404: User Not Found"
User information not found.
```

#### **Invalid Token**
```jsx title="statusCode 401: Unauthorized"
Invalid or expired token.
```

#### **Internal Server Error**
```jsx title="statusCode 500: Internal Server Error"
Try again or restart service.
```

---


