
---

## Update Group

This endpoint allows users to update information about a group chat.

### Request

- **Method:** PUT
- **Path:** /api/change-group/:id
- **Headers:**
    - Authorization: Bearer {token}
- **Path Parameters:**
    - id (required): The ID of the group to update.
- **Body (Multipart Form):**
    - photo_url (optional): New photo for the group.

### Response

- **Success Response:**
    - **Code:** 200
    - **Content:**
      ```json
      {
        "message": "Group updated successfully"
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
    - **Code:** 403 FORBIDDEN
        - **Content:**
          ```json
          {
            "message": "You are not an admin of this group"
          }
          ```
    - **Code:** 400 BAD REQUEST
        - **Content:**
          ```json
          {
            "message": "Invalid group ID"
          }
          ```
    - **Code:** 500 INTERNAL SERVER ERROR
        - **Content:**
          ```json
          {
            "message": "Failed to update group"
          }
          ```

### Example

```bash
curl -X PUT http://localhost:3000/api/update-group/1 \
  -H "Authorization: Bearer {token}" \
  -F "photo_url=@/path/to/new_photo.jpg"
```

---

