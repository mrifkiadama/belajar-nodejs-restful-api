# User API Spec

## Register User API

Endpoint : POST /api/users

Request Body :
```json
{
    "username":"cyrus",
    "password":"123456",
    "name" : "Muhammad Rifki Adam A",
}
```

Response Body Success : 

```json
{
    "data":{
        "username" : "cyrus",
        "name" : "Muhammad Rifki Adam A",
    }
}
```

Response Body Error :

```json
{
    "errors": "Username already registered",
}
```

## Login User API

Endpoint : POST /api/users/login

Request Body :
```json
{
    "username":"cyrus",
    "password":"123456",
}
```

Response Body Success : 
```json
{
    "data":{
        "token":"unique-token",
    }
}
```

Response Body Error :
```json
{
    "errors":"Username or password worng"
}
```

## Update User API

Endpoint : PATCH /api/users/current

Headers :
- Authorization : token

Request Body : 
```json
{
    "name":"Muhammad Rifki Adam Baru", //Optional
    "password":"new password" //Optional
}
```

Response Body Success :
```json
{
    "data":{
        "username":"cyrus",
        "name":"Muhammad Rifki Adam Baru",
    }
}
```

Response Body Error :
```json
{
    "errors":"Name length max 100"
}
```

## Get User API
Endpoint : GET /api/users/current

Headers : 
- Authorization : token

Response Body Success:

```json
{
    "data":{
        "username" :"cyrus",
        "name":"Muhammad Rifki Adam A"
    }
}
```

Response Body Error : 
```json
{
    "errors":"Unauthorized"
}
```
## Logout User API
Endpoint : DELETE /api/users/logout

Headers : 
- Authorization : token

Response Body Success :
```json
{
    "data" : "OK"
}
```

Response Body Error :
```json
{
    "errors":"Unauthorized"
}
```
