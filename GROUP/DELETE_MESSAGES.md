
---

## Delete Group Messages

This endpoint allows users to delete messages from a group chat.

### Request

- **Method:** POST
- **Path:** /api/group/delete-messages
- **Headers:**
    - Authorization: Bearer {token}
- **Body:**
  ```json
  {
    "group_id": 1,
    "message_ids": [1, 2, 3]
  }
  ```

### Response

- **Success Response:**
    - **Code:** 200
    - **Content:**
      ```json
      {
        "message": "Messages deleted successfully"
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
            "message": "Group not found"
          }
          ```

### Example

```bash
curl -X DELETE http://localhost:3000/api/delete-group-messages \
  -H "Authorization: Bearer {token}" \
  -d "{\"group_id\": 1, \"message_ids\": [1, 2, 3]}"
```

---

