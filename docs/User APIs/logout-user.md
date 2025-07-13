---
sidebar_position: 5
---

# Logout User

Learn how to log out a user and clear their session with TexResolve.

---

## **Request**

- **Method**: `POST`
- **Endpoint**: `https://tex-resolve-backend.onrender.com/api/v1/logout`

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
logged out successfully
```

:::tip Success Tip
The user's session has been cleared, and they have been logged out successfully.
:::

### **Errors**

#### **Invalid Token**
```jsx title="statusCode 401: Unauthorized"
Invalid or expired token.
```

#### **Internal Server Error**
```jsx title="statusCode 500: Internal Server Error"
Try again or restart service.
```
