
---

## Get Group Info

This endpoint retrieves information about a specific group chat.

### Request

- **Method:** GET
- **Path:** /api/group/:id
- **Path Parameters:**
    - id (required): The ID of the group.

### Response

- **Success Response:**
    - **Code:** 200
    - **Content:**
      ```json
      {
        "id": 1,
        "name": "Group Name",
        "description": "Group Description",
        "photo_url": "/images/group.jpg",
        "messages": [
          {
            "id": 1,
            "group_id": 1,
            "user_id": 1,
            "text": "Hello!",
            "created_at": "2024-02-28T12:00:00Z",
            "updated_at": "2024-02-28T12:01:00Z"
          }
        ],
        "created_at": "2024-02-28T12:00:00Z",
        "updated_at": "2024-02-28T12:01:00Z"
      }
      ```

- **Error Response:**
    - **Code:** 400 BAD REQUEST
        - **Content:**
          ```json
          {
            "message": "Invalid group ID"
          }
          ```
    - **Code:** 404 NOT FOUND
        - **Content:**
          ```json
          {
            "message": "Group not found"
          }
          ```

### Example

```bash
curl -X GET http://localhost:3000/api/group/1
```

---

