
---

## Create Group

This endpoint allows users to create a new group chat.

### Request

- **Method:** POST
- **Path:** /api/group/create-group
- **Headers:**
    - Authorization: Bearer {token}
  - **Body:**
    ```json
    {
      "name": "Group Name",
      "description": "Group Description",
      "photo_url": "/images/group.jpg"
    }
    ```

### Response

- **Success Response:**
    - **Code:** 200
    - **Content:**
      ```json
      {
        "message": "Group created successfully",
        "group": {
          "id": 1,
          "name": "Group Name",
          "description": "Group Description",
          "photo_url": "/images/group.jpg",
          "admins": [
            {
              "id": 1,
              "name": "John Doe",
              "email": "john.doe@example.com",
              "photo_url": "/images/profile.jpg"
            }
          ],
          "participants": [
            {
              "id": 1,
              "name": "John Doe",
              "email": "john.doe@example.com",
              "photo_url": "/images/profile.jpg"
            }
          ],
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
            "message": "Failed to create group"
          }
          ```

### Example

```bash
curl -X POST http://localhost:3000/api/create-group \
  -H "Authorization: Bearer {token}" \
  -d "{\"name\": \"Group Name\", \"description\": \"Group Description\", \"photo_url\": \"/images/group.jpg\"}"
```

---

