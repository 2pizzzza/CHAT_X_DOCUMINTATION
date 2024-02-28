
---

## Get User Groups

This endpoint allows users to retrieve all groups they are a part of.

### Request

- **Method:** GET
- **Path:** /api/group/get-all-group
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
            "message": "Failed to get user groups"
          }
          ```

### Example

```bash
curl -X GET http://localhost:3000/api/get-user-groups \
  -H "Authorization: Bearer {token}"
```

---

