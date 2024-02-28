
---

## Search Group By Name

This endpoint allows users to search for group chats by name.

### Request

- **Method:** GET
- **Path:** /api/chat/search
- **Headers:**
    - Authorization: Bearer {token}
- **Query Parameters:**
    - text (required): The text to search for in group names.

### Response

- **Success Response:**
    - **Code:** 200
    - **Content:**
      ```json
      [
        {
          "id": 1,
          "name": "Group Chat",
          "description": "A group chat",
          "photo_url": "/images/group.jpg",
          "participants": ["John Doe", "Jane Smith"],
          "created_at": "2024-02-28T12:00:00Z",
          "updated_at": "2024-02-28T12:01:00Z"
        }
      ]
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
            "message": "Missing search text"
          }
          ```
    - **Code:** 500 INTERNAL SERVER ERROR
        - **Content:**
          ```json
          {
            "message": "Failed to search groups",
            "error": "Internal Server Error"
          }
          ```

### Example

```bash
curl -X GET http://localhost:3000/api/search-groups?text=group \
  -H "Authorization: Bearer {token}"
```

---

