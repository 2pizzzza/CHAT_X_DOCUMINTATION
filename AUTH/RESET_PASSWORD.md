
## ResetPasswordRequest

### Description
This endpoint allows a user to request a reset code for resetting their password. It verifies the user's email, generates a reset code, saves it in the database with an expiry date, and sends the reset code to the user's email.

### Endpoint
`POST /api/auth/reset_password_request`

### Request Body
- `email` (string, required): The email address of the user requesting the reset code.

```json
{
    "email": "johndoe@example.com"
}
```

### Responses

#### Success Response
- Status Code: 200 OK
- Body:

```json
{
    "status": "success",
    "message": "Reset code sent successfully"
}
```

#### Error Responses
- Status Code: 400 Bad Request
    - Body:

  ```json
  {
      "status": "fail",
      "message": "Invalid request payload"
  }
  ```

- Status Code: 404 Not Found
    - Body:

  ```json
  {
      "status": "fail",
      "message": "User not found"
  }
  ```

- Status Code: 500 Internal Server Error
    - Body:

  ```json
  {
      "status": "error",
      "message": "Failed to save reset code"
  }
  ```

## ResetPasswordVerify

### Description
This endpoint allows a user to verify a reset code for resetting their password. It verifies the user's email, checks if the reset code is valid and not expired, and confirms the verification.

### Endpoint
`POST /api/auth/reset_password_verify`

### Request Body
- `email` (string, required): The email address of the user verifying the reset code.
- `code` (string, required): The reset code provided by the user.

```json
{
    "email": "johndoe@example.com",
    "code": "123456"
}
```

### Responses

#### Success Response
- Status Code: 200 OK
- Body:

```json
{
    "status": "success",
    "message": "Reset code verified successfully"
}
```

#### Error Responses
- Status Code: 400 Bad Request
    - Body:

  ```json
  {
      "status": "fail",
      "message": "Invalid request payload"
  }
  ```

- Status Code: 404 Not Found
    - Body:

  ```json
  {
      "status": "fail",
      "message": "User not found"
  }
  ```

- Status Code: 401 Unauthorized
    - Body:

  ```json
  {
      "status": "fail",
      "message": "Invalid or expired reset code"
  }
  ```


## ResetPassword

### Description
This endpoint allows a user to reset their password using a valid reset code. It verifies the user's email, checks if the reset code is valid and not expired, hashes the new password, and updates the user's password in the database.

### Endpoint
`POST /api/auth/reset_password`

### Request Body
- `email` (string, required): The email address of the user resetting the password.
- `code` (string, required): The reset code provided by the user.
- `password` (string, required): The new password to set.

```json
{
    "email": "johndoe@example.com",
    "code": "123456",
    "password": "newpassword123"
}
```

### Responses

#### Success Response
- Status Code: 200 OK
- Body:

```json
{
    "status": "success",
    "message": "Password updated successfully"
}
```

#### Error Responses
- Status Code: 400 Bad Request
    - Body:

  ```json
  {
      "status": "fail",
      "message": "Invalid request payload"
  }
  ```

- Status Code: 404 Not Found
    - Body:

  ```json
  {
      "status": "fail",
      "message": "User not found"
  }
  ```

- Status Code: 401 Unauthorized
    - Body:

  ```json
  {
      "status": "fail",
      "message": "Invalid or expired reset code"
  }
  ```

- Status Code: 500 Internal Server Error
    - Body:

  ```json
  {
      "status": "error",
      "message": "Failed to update password"
  }
  ```
