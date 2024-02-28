
## RefreshAccessToken

### Description
This endpoint allows a user to refresh their access token using a valid refresh token. It verifies the refresh token, generates a new access token, and returns it in the response.

### Endpoint
`POST /api/auth/refresh`

### Request Body
- `refresh_token` (string, required): The refresh token to use for refreshing the access token.

```json
{
    "refresh_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxIiwiaWF0IjoxNTE2MjM5MDIyfQ.4dUukibzs-wOwBYzNLyznxmB4t3myDPNh7zgQTOL9-c"
}
```

### Responses

#### Success Response
- Status Code: 200 OK
- Body:

```json
{
    "status": "success",
    "access_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxIiwiaWF0IjoxNTE2MjM5MDIyfQ.4dUukibzs-wOwBYzNLyznxmB4t3myDPNh7zgQTOL9-c"
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
      "message": "Invalid refresh token"
  }
  ```

- Status Code: 500 Internal Server Error
    - Body:

  ```json
  {
      "status": "fail",
      "message": "Failed to generate access token"
  }
  ```
