# User API Spec

## Register User API

Endpoint : POST /api/users

Request Body :

```json
{
  "username": "amriarendy",
  "password": "admin",
  "name": "Amria Rendy D"
}
```

Response Body Success :

```json
{
  "data": {
    "username": "amriarendy",
    "name": "Amria Rendy D"
  }
}
```

Response Body Error :

```json
{
  "errors": "Username already registered!"
}
```

## Login User API

Endpoint : POST /api/users/login

Request Body :

```json
{
  "username": "amriarendy",
  "password": "admin"
}
```

Response Body Success :

```json
{
  "data": {
    "token": "unique-token"
  }
}
```

Response Body Error :

```json
{
  "errors": "Username or Password Incorrect!"
}
```

## Update User API

Endpoint : PATCH /api/users/current

Headers :

- Authorization : token

Request Body :

```json
{
  "name": "Amria Rendy D",
  "password": "admin" // new password or optional
}
```

Response Body Success :

```json
{
  "data": {
    "username": "amriarendy",
    "name": "Amria Rendy D"
  }
}
```

Response Body Error :

```json
{
  "errors": "Name length max 100"
}
```

## Get User API

Endpoint : POST /api/users/current

Headers :

- Authorization : token

Response Body Success :

```json
{
  "data": {
    "username": "amriarendy",
    "name": "Amria Rendy D"
  }
}
```

Response Body Error :

```json
{
  "errors": "Unauthorized!"
}
```

## Logout User API

Endpoint : Delete /api/users/logout

Headers :

- Authorization : token

Response Body Success :

```json
{
  "data": "OK"
}
```

Response Body Error :

```json
{
  "errrors": "Unauthorized!"
}
```
