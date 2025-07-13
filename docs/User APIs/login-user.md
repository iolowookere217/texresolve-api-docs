---
sidebar_position: 3
---

# Login User

Learn how to log in as user with TexResolve.

---

## **Request**

- **Method**: `POST`
- **Endpoint**: `https://tex-resolve-backend.onrender.com/api/v1/login`

### **Body Parameters**

| Parameter | Type   | Description                     |
|-----------|--------|-----------------------------------|
| `email`   | String | User email address.              |
| `password`| String | User password.                  |

#### Example Request Body:
```json
{
  "email": "brockc22@lvintager.com",
  "password": "pass123"
}
```

---

## **Responses**

### **Success**
```jsx title="statusCode 200: Success"
{
  "success": true,
  "user": {
    "email": "brockc22@lvintager.com"
  },
  "accessToken": "your_access_token_here",
  "refreshToken": "your_refresh_token_here"
}
```

:::tip Info Tip
The user token will be used to authenticate other user services.
:::


### **Errors**


#### **Invalid Credentials**
```jsx title="statusCode 400: Internal Server Error"
Invalid email or password.
```

```jsx title="statusCode 500: Internal Server Error"
Try again or restart service.
```

---

