
## LOGOUT

### Endpoint
`GET /api/auth/logout`

### headers
jwt token

#### Success Response
- Status Code: 200
```json

{
    "status": "success"
}

```

### if dont have 

```json 
{
    "message": "You are not logged in",
    "status": "fail"
}
```