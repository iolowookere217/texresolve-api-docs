---
sidebar_position: 1
---


# Register a User

Learn how to register a new user with TexResolve.

---

## **Schema**

```jsx title="User Schema"
{
  email: String, // A valid email address
  password: String, // A strong and secure password
  name: String, // Full name of the buyer
}
```

---

## **Request**

- **Method**: `POST`
- **Endpoint**: `https://tex-resolve-backend.onrender.com/api/v1/registration`

### **Body Parameters**

| Parameter | Type   | Description                                                                 |
|-----------|--------|-----------------------------------------------------------------------------|
| `email`   | String | A valid email address. A verification link will be sent to this email.      |
| `password`| String | A strong and secure password.                                              |
| `name`| String | The full name of the user.   

#### Example Request Body:
```json
{
  "email": "brockc22@lvintager.com",
  "password": "pass123",
  "name": "Noelle Nozel"
}
```

---

## **Responses**

### **Success**
```jsx title="statusCode 201: Success"
An email is sent to your account, please verify.
```

:::tip Success Tip
Congratulations! You have successfully registered a new user on TexResolve.
:::

### **Error**
```jsx title="statusCode 500: Internal Server Error"
Try again or restart service.
```

---

## **Verify Your Email**

1. **Check Your Inbox**: Look for a verification link sent by TexResolve to the email address you provided.
2. **Click the Link**: Follow the instructions in the email to verify your account.

:::danger Important
Without verifying your email, you will not be able to access TexResolve's services.
:::


---
