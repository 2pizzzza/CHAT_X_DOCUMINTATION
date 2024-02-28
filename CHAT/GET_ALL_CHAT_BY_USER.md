
---

## Get All Chats By User

This endpoint retrieves all chats, including personal and group chats, for the authenticated user.

### Request

- **Method:** GET
- **Path:** /api/chats
- **Headers:**
    - Authorization: Bearer {token}

### Response

- **Success Response:**
    - **Code:** 200
    - **Content:**
      ```json
      [
        {
          "id": 1,
          "name": "John Doe",
          "user1_id": 1,
          "user2_id": 2,
          "last_message": "Hello!",
          "created_at": "2024-02-28T12:00:00Z",
          "updated_at": "2024-02-28T12:01:00Z",
          "class": "chat"
        },
        {
          "id": 1,
          "name": "Group Chat",
          "description": "A group chat",
          "photo_url": "/images/group.jpg",
          "participants": ["John Doe", "Jane Smith"],
          "last_message": "What's up?",
          "created_at": "2024-02-28T12:00:00Z",
          "updated_at": "2024-02-28T12:01:00Z",
          "class": "group"
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
    - **Code:** 500 INTERNAL SERVER ERROR
        - **Content:**
          ```json
          {
            "message": "Internal Server Error"
          }
          ```

### Example

```bash
curl -X GET http://localhost:3000/api/chats \
  -H "Authorization: Bearer {token}"
```

---

