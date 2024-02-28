
## UpdateMessage

### Description
This endpoint allows a user to update their own message. It verifies the user's authorization, fetches the message to ensure it belongs to the user, and updates the message text.

### Endpoint
`PUT /api/chat/change-messages`

### Headers
- `Authorization`: Bearer token obtained from signing in or signing up.

### Request Body
- `message_id` (uint, required): The ID of the message to update.
- `text` (string, required): The updated text of the message.

```json
{
    "message_id": 1,
    "text": "Updated message text"
}
```

### Responses

#### Success Response
- Status Code: 200 OK
- Body:

```json
{
    "message": "Message updated successfully"
}
```

#### Error Responses
- Status Code: 400 Bad Request
    - Body:

  ```json
  {
      "message": "Invalid request payload"
  }
  ```

- Status Code: 401 Unauthorized
    - Body:

  ```json
  {
      "message": "Unauthorized"
  }
  ```

- Status Code: 404 Not Found
    - Body:

  ```json
  {
      "message": "Message not found"
  }
  ```

- Status Code: 500 Internal Server Error
    - Body:

  ```json
  {
      "message": "Failed to update message"
  }
  ```
