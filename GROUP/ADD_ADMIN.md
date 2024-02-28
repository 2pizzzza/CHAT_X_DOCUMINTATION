
---

## Add Admin

This endpoint allows admins to add a new admin to a group chat.

### Request

- **Method:** POST
- **Path:** /api/group/added-new-admin
- **Headers:**
    - Authorization: Bearer {token}
- **Body:**
  ```json
  {
    "group_id": 1,
    "user_id": "c9159e8a-277a-4d75-b4f6-76f557cf1193"
  }
  ```

### Response

- **Success Response:**
    - **Code:** 200
    - **Content:**
      ```json
      {
        "message": "Admin added successfully"
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
curl -X POST http://localhost:3000/api/add-admin \
  -H "Authorization: Bearer {token}" \
  -d "{\"group_id\": 1, \"user_id\": \"c9159e8a-277a-4d75-b4f6-76f557cf1193\"}"
```

---

