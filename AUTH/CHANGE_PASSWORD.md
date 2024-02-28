## ChangePassword

### Description
This endpoint allows a user to change their password. It verifies the user's current password, hashes the new password, and updates the user's password in the database.

### Endpoint
`POST /api/auth/change_password`

### Request Headers
- `Authorization` Bearer token 
### Request Body
- `current_password` (string, required): The user's current password.
- `new_password` (string, required): The new password to set.

```json
{
    "current_password": "oldpassword123",
    "new_password": "newpassword123"
}
```

### Headers
- `Authorization`: Bearer token obtained from signing in or signing up.

### Responses

#### Success Response
- Status Code: 200 OK
- Body:

```json
{
    "status": "success",
    "message": "Password changed successfully"
}
```

#### Error Responses
- Status Code: 400 Bad Request
    - Body:

  ```json
  {
      "status": "fail",
      "message": "Invalid request body"
  }
  ```

- Status Code: 401 Unauthorized
    - Body:

  ```json
  {
      "status": "fail",
      "message": "Unauthorized"
  }
  ```

- Status Code: 403 Forbidden
    - Body:

  ```json
  {
      "status": "fail",
      "message": "Incorrect current password"
  }
  ```

- Status Code: 500 Internal Server Error
    - Body:

  ```json
  {
      "status": "fail",
      "message": "Failed to update password"
  }
  ```
