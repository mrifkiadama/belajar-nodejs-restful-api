# Contact API Spec

## Create Contact API
Endpoint : POST /api/contacts

Headers " 
- Authorization : token

Request Body : 
```json
{
    "first_name" : "Rifki",
    "last_name" : "Adam",
    "email":"rifkiadam@gmail.com",
    "phone" : "089213892301"
}
```

Request Body Success : 
```json
{
    "data" :{
        "id": 1,
        "first_name":"Rifki",
        "last_name":"Adam",
        "email":"rifkiadam@gmail.com",
        "phone":"089213892301",
    }
}
```

Request Body Error :
```json
{
    "errors" :"Email is not valid format",
}
```

## Update Contact API

Endpoint : PUT /api/contacts/:id

Headers : 
- Authorization : token

Request Body : 
```json
{
    "first_name":"Rifki",
    "last_name" : "Adam",
    "email" : "rifkiadam@gmail.com",
    "phone":"089213892301", 
}
```

Request Body Success : 
```json
{
    "data" : {
        "id": 1,
        "first_name":"Rifki",
        "last_name":"Adam",
        "email":"rifkiadam@gmail.com",
        "phone":"089213892301",
    }
}
```

Request Body Error :
```json
{
    "errors" : "Email is not valid format"
}
```

## Get Contact API
Endpoint : GET /api/contacts/:id

Headers :
- Authorization : token

Request Body Success : 
```json
{
    "data" : {
        "id": 1,
        "first_name":"Rifki",
        "last_name":"Adam",
        "email":"rifkiadam@gmail.com",
        "phone":"089213892301",
    }
}
```

Request Body Error :

```json
{
    "errors" : "Contact is not found"
}
```

## Search Contact API
Endpoint : GET /api/contacts

Headers : 
- Authorization : token

Query params : 
- name : Search by first_name or last_name, using Like, optional
- email : Search by email using Like, optional
- phone : Search by phone using Like, optional
- page : Number of page, default 1
- size : Size per page, default 10


Request Body Success : 
```json
{
    "data":[
        {
            "id": 1,
            "first_name":"Rifki",
            "last_name":"Adam",
            "email":"rifkiadam@gmail.com",
            "phone":"089213892301",
        },
        {
            "id": 2,
            "first_name":"Rifki",
            "last_name":"Adam",
            "email":"rifkiadam@gmail.com",
            "phone":"089213892301",
        }
    ],
    "paging" : {
        "page" : 1,
        "total_page" : 3,
        "total_item" : 30,
    }
}
```
Request Body Error :
```json
{
    "errors" : "Data Not Found"
}
```

## Remove Contact API
Endpoint : DELETE /api/contacts/:id

Headers : 
- Authorization : token

Request Body Success : 
```json
{
    "data":"OK"
}
```

Request Body Error :
```json
{
    "errors" : "Contact is not found"
}
```