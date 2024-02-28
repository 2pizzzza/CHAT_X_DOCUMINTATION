## LOGIN

### Description
This endpoint allows a user to sign in by providing their email and password. It validates the credentials, generates access and refresh tokens, and sets them as cookies in the response.

### Endpoint
`POST /api/auth/login`

### Request Body
- `email` (string, required): The email address of the user.
- `password` (string, required): The password for the user.

```json
{
    "email": "johndoe@example.com",
    "password": "password123"
}
```

### Responses

#### Success Response
- Status Code: 200 OK
- Body:

```json
{
  "access_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE3MDkwOTg5MjksImlhdCI6MTcwOTA5NTMyOSwibmJmIjoxNzA5MDk1MzI5LCJzdWIiOiIzNDhhMTgzNi1kNGY2LTQ5ZDEtOGY0OC0wOThjY2E0Zjg1YzIifQ.4jwgqxMC0SvQ3jL6_JFfPzLi686CzASYv-apZYd7VY8",
  "refresh_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE3MDk0NDA5MjksImlhdCI6MTcwOTA5NTMyOSwic3ViIjoiMzQ4YTE4MzYtZDRmNi00OWQxLThmNDgtMDk4Y2NhNGY4NWMyIn0.ftmdNf1lQ-vWIDqMlcQPuMLfvwXRrLuhpNJoIlJ5KxY",
  "status": "success"
}
```

#### Error Responses
- Status Code: 400 Bad Request
    - Body:

  ```json
  {
      "status": "fail",
      "message": "Invalid email or Password"
  }
  ```

- Status Code: 500 Internal Server Error
    - Body:

  ```json
  {
      "status": "error",
      "message": "Failed to generate tokens"
  }
  ```
