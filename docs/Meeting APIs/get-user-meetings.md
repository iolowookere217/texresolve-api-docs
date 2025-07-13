---
sidebar_position: 2
---

# Get User Meetings

Learn how to fetch all meetings by a user.

## Request

- **Method**: GET
- **Endpoint**: `https://tex-resolve-backend.onrender.com/api/v1/meetings/me`

## Responses

### Success

```json title="code 200: Success"
{
  "meetings": [
    {
      "_id": "654b68e9c4ab84dcc26ad908",
      "title": "DevOps Sync Call",
      "ticketId": "Ticket7",
      "date": "2025-05-20",
      "time": "10:30",
      "meeting_link": "https://us05web.zoom.us/j/86289629132?pwd=MicIHCJMlrVykmk2gyNBIczHXibbxR.1"
    },
    // other meetings
  ],
 
}
```

### Errors

```json title="statusCode 401: Authentication Error"
{
  "message": "User token is not valid or does not exist"
}
```

```json title="statusCode 404: Not Found"
{
  "message": "No meetings found for the provided ticket ID"
}
```

```json title="statusCode 500: Internal Server Error"
{
  "message": "Try again or restart service"
}
```