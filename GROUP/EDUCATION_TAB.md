
---

## Get All Education Groups

This endpoint retrieves all education groups of the authenticated user.

### Request

- **Method:** GET
- **Path:** /api/group/education
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
          "name": "Education Group 1",
          "description": "Education Group Description",
          "photo_url": "/images/education.jpg",
          "participants": ["John Doe", "Jane Smith"],
          "last_message": {
            "id": 1,
            "group_id": 1,
            "user_id": 1,
            "text": "Hello!",
            "created_at": "2024-02-28T12:00:00Z",
            "updated_at": "2024-02-28T12:01:00Z"
          },
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
    - **Code:** 500 INTERNAL SERVER ERROR
        - **Content:**
          ```json
          {
            "message": "Failed to fetch education groups"
          }
          ```

### Example

```bash
curl -X GET http://localhost:3000/api/education-groups \
  -H "Authorization: Bearer {token}"
```

---

