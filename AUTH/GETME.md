
---

## Get Current User

This endpoint returns information about the current authenticated user.

### Request

- **Method:** GET
- **Path:** /api/users/me
- **Headers:**
    - Authorization: Bearer {token}

### Response

- **Success Response:**
    - **Code:** 200
    - **Content:**
```json
{
"data": {
"user": {
"id": "348a1836-d4f6-49d1-8f48-098cca4f85c2",
"name": "Admin",
"email": "amit.jurbanov@gmail.com",
"role": "user",
"photo": "images/Снимок экрана от 2024-02-26 04-17-09.png",
"provider": "local",
"created_at": "2024-02-27T12:48:54.969154+06:00",
"updated_at": "2024-02-28T11:32:27.108771+06:00"
}
},
"status": "success"
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
curl -X GET http://localhost:3000/api/me \
  -H "Authorization: Bearer {token}"
```

---

