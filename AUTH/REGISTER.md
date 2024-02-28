## SignUpUser

### Description
This endpoint allows a user to sign up by providing their name, email, password, and optional photo. It creates a new user record in the database, sends a verification email, and returns access and refresh tokens for the new user.

### Endpoint
`POST /api/auth/register`

### Request Body
- `name` (string, required): The name of the user.
- `email` (string, required): The email address of the user.
- `password` (string, required): The password for the user.
- `password_confirm` (string, required): Confirmation of the password.
- `photo` (string, optional): The URL of the user's photo.

```json
{
    "name": "John Doe",
    "email": "johndoe@example.com",
    "password": "password123",
    "passwordConfirm": "password123"
}
```

### Responses

#### Success Response
- Status Code: 201 Created
- Body:

```json
{
  "data": {
    "access_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE3MDkwOTkzNDEsImlhdCI6MTcwOTA5NTc0MSwibmJmIjoxNzA5MDk1NzQxLCJzdWIiOiI4ZGEwYTc4MC1hNGY0LTQ1MDctODBmMy05MWMyZDM1NmRjYmUifQ.4RIzaebgpQA8A1PtKJiPPsD4kZgTAlLvvtolDBuOhJ8",
    "refresh_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE3MDk0NDEzNDEsImlhdCI6MTcwOTA5NTc0MSwic3ViIjoiOGRhMGE3ODAtYTRmNC00NTA3LTgwZjMtOTFjMmQzNTZkY2JlIn0.-9zwj9llimER7EXMWRHQ0LBK1VtoskUjLS2jWefsLMA",
    "user": {
      "id": "8da0a780-a4f4-4507-80f3-91c2d356dcbe",
      "name": "John Doe",
      "email": "johndoe@example.com",
      "role": "user",
      "provider": "local",
      "created_at": "2024-02-28T10:48:58.315132+06:00",
      "updated_at": "2024-02-28T10:48:58.315132+06:00"
    }
  },
  "status": "success"
}
```

#### Error Responses
- Status Code: 400 Bad Request
    - Body:

  ```json
  {
      "status": "fail",
      "message": "Passwords do not match"
  }
  ```

- Status Code: 409 Conflict
    - Body:

  ```json
  {
      "status": "fail",
      "message": "User with that email already exists"
  }
  ```

- Status Code: 502 Bad Gateway
    - Body:

  ```json
  {
      "status": "error",
      "message": "Something bad happened"
  }
  ```

- Status Code: 500 Internal Server Error
    - Body:

  ```json
  {
      "status": "error",
      "message": "Failed to send verification email"
  }
  ```
