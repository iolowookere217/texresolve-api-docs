---
sidebar_position: 2
---

# Activate User Account

Learn how to activate a user account with TexResolve after registration.

---

## **Request**

- **Method**: `POST`
- **Endpoint**: `https://tex-resolve-backend.onrender.com/api/v1/activate-user`

### **Body Parameters**

| Parameter         | Type   | Description                                                                 |
|-------------------|--------|-----------------------------------------------------------------------------|
| `activation_token`| String | The activation token sent via email during registration.                   |
| `activation_statusCode` | String | The unique activation statusCode associated with the activation token.           |

#### Example Request Body:
```json
{
  "activation_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiI2NTQ2NWE1YTdlYjFiYmU4ZDMyYjI1ZDciLCJlbWFpbCI6InJvcm9ub2FAZ21haWwuY29tIiwiaWF0IjoxNjk5MTA5NDg2LCJleHAiOjE2OTkxOTU4ODZ9.axRUZ4Rw_9J5WqXvDSI8lC6E5oX-_Kw9SPghDLLGKH4",
  "activation_code": "123456"
}
```

---

## **Responses**

### **Success**
```jsx title="statusCode 201: Success"
Account activated successfully.
```

:::tip Success Tip
Your account has been successfully activated! You can now log in to Hajorah.
:::

### **Errors**

#### **Invalid Activation statusCode**
```jsx title="statusCode 400: Invalid Activation statusCode"
Invalid activation statusCode.
```

#### **Email Already Exists**
```jsx title="statusCode 400: Email Already Exists"
Email already exists. Please use a different email or log in if you already have an account.
```

#### **Internal Server Error**
```jsx title="statusCode 500: Internal Server Error"
Try again or restart service.
```

