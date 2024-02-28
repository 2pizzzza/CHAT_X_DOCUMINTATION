
## DeleteMessage

### Description
This endpoint allows a user to delete their own messages. It verifies the user's authorization, checks if the messages belong to the user, and deletes the messages.

### Endpoint
`POST /api/chat/delete-messages`

### Headers
- `Authorization`: Bearer token obtained from signing in or signing up.

### Request Body
- `message_ids` (array of uint, required): The IDs of the messages to delete.

```json
{
    "message_ids": [1, 2, 3]
}
```

### Responses

#### Success Response
- Status Code: 200 OK
- Body:

```json
{
    "message": "Messages deleted successfully"
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

- Status Code: 403 Forbidden
    - Body:

  ```json
  {
      "message": "User can only delete their own messages"
  }
  ```

- Status Code: 500 Internal Server Error
    - Body:

  ```json
  {
      "message": "Failed to delete messages"
  }
  ```
