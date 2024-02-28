213
---

## Update User Profile

This endpoint allows users to update their profile information, such as name, email, and profile photo.

### Request

- **Method:** PUT
- **Path:** /api/auth/update
- **Headers:**
    - Authorization: Bearer {token}
- **Body:**
    - **Multipart Form Data:**
        - name (optional): New name of the user.
        - email (optional): New email of the user.
        - photo_url (optional): New profile photo of the user.

### Response

- **Success Response:**
    - **Code:** 200
    - **Content:**
 ```json
  {
  "ID": "348a1836-d4f6-49d1-8f48-098cca4f85c2",
  "Name": "Admin",
  "Email": "amit.jurbanov@gmail.com",
  "Password": "$2a$10$z7nK5CrGEi6GtRU6PheklOH/krzodyN3TpG48lIg14tD5Tjd2bTKu",
  "Role": "user",
  "Provider": "local",
  "Photo": "images/Снимок экрана от 2024-02-26 04-17-09.png",
  "Verified": false,
  "ConfirmationCode": "",
  "ConfirmationLink": "Y-J8fQDm",
  "ResetPasswordCode": "",
  "ResetPasswordExpiry": "0001-01-01T04:58:24+04:58",
  "CreatedAt": "2024-02-27T12:48:54.969154+06:00",
  "UpdatedAt": "2024-02-28T11:32:27.108771802+06:00",
  "Online": false
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
    - **Code:** 500 INTERNAL SERVER ERROR
        - **Content:**
          ```json
          {
            "message": "Internal Server Error"
          }
          ```

### Example

```bash
curl -X POST http://localhost:3000/api/update-profile \
  -H "Authorization: Bearer {token}" \
  -F "name=John Doe" \
  -F "email=john.doe@example.com" \
  -F "photo_url=@/path/to/new_profile_photo.jpg"
```

---

