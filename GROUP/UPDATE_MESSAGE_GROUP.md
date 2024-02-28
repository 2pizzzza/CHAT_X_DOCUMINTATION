
---

## Update Group Message

This endpoint allows users to update a message in a group chat.

### Request

- **Method:** POST
- **Path:** /api/group/change-messages
- **Headers:**
    - Authorization: Bearer {token}
- **Body:**
  ```json
  {
    "group_id": 1,
    "message_id": 1,
    "text": "New message text"
  }
  ```

### Response

- **Success Response:**
    - **Code:** 200
    - **Content:**
      ```json
      {
        "message": "Message updated successfully",
        "data": {
          "id": 1,
          "group_id": 1,
          "user_id": 1,
          "text": "New message text",
          "created_at": "2024-02-28T12:00:00Z",
          "updated_at": "2024-02-28T12:01:00Z"
        }
      }
      ```

- **Error Response:**
    - **Code:** 401 UNAUTHORIZED
        - **Content:**
          ```json
          {
            "message": "Unauthorized"
          }
          ```
    - **Code:** 400 BAD REQUEST
        - **Content:**
          ```json
          {
            "message": "Invalid request"
          }
          ```
    - **Code:** 500 INTERNAL SERVER ERROR
        - **Content:**
          ```json
          {
            "message": "Message not found"
          }
          ```

### Example

```bash
curl -X PUT http://localhost:3000/api/update-group-message \
  -H "Authorization: Bearer {token}" \
  -d "{\"group_id\": 1, \"message_id\": 1, \"text\": \"New message text\"}"
```

---

