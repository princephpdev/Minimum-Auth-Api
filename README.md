# Minimum-Auth-Api
Very minimum auth api with login and register

### Login Api

**POST** http://localhost:1234/login

`Request`
```
{
    "username":"abcd",
    "password":"1234"
}
```
`Response`
```
{
  "access_token": "${token}"
}
```
---
### Register Api
**POST** http://localhost:1234/register

`Request`
```
{
    "username":"abcd",
    "password":"1234"
}
```
`Response`
```
{
  "message": "user 2 created",
  "content": {
    "id": 2,
    "username": "abcd",
    "password": "1234"
  }
}
```
---
### Myself Api

**GET** http://localhost:1234/me

`Request` 

*Auth* **Protected Route**
```
Bearer ${token}
```
`Response`
```
{
  "content": {
    "sub": 2,
    "username": "abcd",
    "iat": 1654941558,
    "exp": 1654952358
  }
}
```
---
### Any Other Api

GET http://localhost:1234/anything

`Request`
```
{}
```

`Response`
```
{
  "message": "page not found"
}
```