---
sidebar_position: 4
---

# Onboard a User

Learn how to onboard a verified user on TexResolve by submitting their onboarding form.

---

## **Overview**

Before onboarding, ensure the user has:

1. **Completed registration** by providing a valid email, password, and full name.
2. **Verified their email address** via the link sent to their inbox.

Only **verified users** can proceed with the onboarding form.

---

## **Onboarding Form Schema**

```json title="Onboarding Form Schema"
{
  "role": "user",
  "photo": "https://example.com/photo.jpg",
  "jobTitle": "DevOps Engineer",
  "skills": ["AWS", "Linux", "Kubernetes"],
  "experienceLevel": "Intermediate",
  "portfolio": "https://myportfolio.com",
  "linkedin": "https://www.linkedin.com/in/isaac-olowookere"
}
```

---

## **Onboarding Request**

- **Method**: `POST`
- **Endpoint**: `https://texresolve-backend.onrender.com/api/v1/onboarding`

### **Body Parameters**

| Parameter         | Type   | Description                                                       |
| ----------------- | ------ | ----------------------------------------------------------------- |
| `role`            | String | The role assigned to the user (`user`, `mentor`, `company`, etc.) |
| `photo`           | String | A URL link to the user's profile image                            |
| `jobTitle`        | String | The user's professional title or current job role                 |
| `skills`          | Array  | List of user skills (e.g., `["JavaScript", "React"]`)             |
| `experienceLevel` | String | Level of experience (`Beginner`, `Intermediate`, `Expert`)        |
| `portfolio`       | String | Link to the user's personal or project portfolio                  |
| `linkedin`        | String | Link to the user's LinkedIn profile                               |

---

### **Example Onboarding Request Body**

```json
{
  "role": "user",
  "photo": "https://example.com/photo.jpg",
  "jobTitle": "DevOps Engineer",
  "skills": ["AWS", "Linux", "Kubernetes"],
  "experienceLevel": "Intermediate",
  "portfolio": "https://myportfolio.com",
  "linkedin": "https://www.linkedin.com/in/isaac-olowookere"
}
```

---

## **Onboarding Response**

### ✅ Success

```json title="201 Created"
{
  "message": "User onboarded successfully."
}
```

:::tip Onboarding Complete
The user can now access TexResolve services based on their role and profile.
:::

### ❌ Error

```json title="500 Internal Server Error"
{
  "message": "An error occurred while onboarding. Please try again later."
}
```

---

## ✅ **Flow Summary**

1. 📩 **User Registers** via `/api/v1/registration`
2. 📧 **User Verifies Email** through a verification link
3. 📝 **User Fills Onboarding Form** via `/api/v1/onboarding`
4. 🎉 **User Is Now Fully Onboarded**

---

## ⚠️ Note

- Users must complete email verification before submitting the onboarding form.
- Ensure valid URLs and correct data types are sent in the onboarding payload.
