---
sidebar_position: 1
---

# Create Meeting

Learn how to create a meeting in TexResolve.

## Request

- **Method**: POST
- **Endpoint**: `https://tex-resolve-backend.onrender.com/api/v1/meetings`

### Body Parameters

- **Meeting Details**: Enter the details for the meeting.

| Parameter   | Type     | Description                                       |
|-------------|----------|---------------------------------------------------|
| title       | String   | Title of the meeting                             |
| ticketId    | String   | Associated ticket ID                             |
| date        | String   | Date of the meeting (format: YYYY-MM-DD)         |
| time        | String   | Time of the meeting (format: HH:mm)              |

Here's an example request body for creating a meeting:

```jsx title="creating meeting example"
{
  "title": "DevOps Sync Call",
  "ticketId": "Ticket7",
  "date": "2025-05-20",
  "time": "10:30"
}
```

## Responses

### Success

```jsx title="statusCode 201: success"
{
  message: "Meeting created successfully",
  link: zoomMeetingUrl //zoom meeting link,
}

```

### Errors

```jsx title="statusCode 401: Authentication error"
User token is not valid or does not exist or expired
```

```jsx title="statusCode 400: Bad Request"
Invalid request parameters or access
```

```jsx title="statusCode 500: Internal Server Error"
Try again or restart service
```

---