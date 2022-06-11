# Minimum-Auth-Api
Very minimum auth api with login and register

## Installation
- Clone the repo using git clone OR download the zip
- Make sure you have node installed
- Use Node version 14 or greater
- Go to downloaded folder and run `npm install`
- Once installed run `npm run start`
- Server started at Port `1234`

## Api Documentation

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