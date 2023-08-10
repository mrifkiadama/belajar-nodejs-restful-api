# Address API Spec

## Create Address API
Endpoint : POST /api/contacts/:contactId/addresses

Headers : 
- Authorization : token

Request Body : 
```json
{
    "street" : "Jalan apa",
    "city": "Kota apa",
    "province":"Province apa",
    "country" :"Negara apa",
    "postal_code" : "Kode pos apa"
}
```

Response Body Success : 
```json
{
   "data" :{
        "id":1,
        "street" : "Jalan apa",
        "city": "Kota apa",
        "province":"Province apa",
        "country" :"Negara apa",
        "postal_code" : "Kode pos apa"
   }
}
```

Response Body Error :
```json
{
    "errors" : "Country is required"
}
```


## Update Address API
Endpoint : PUT /api/contacts/:contactId/addresses/:addressId

Headers : 
- Authorization : token

Request Body : 
```json
{
    "street" : "Jalan apa",
    "city": "Kota apa",
    "province":"Province apa",
    "country" :"Negara apa",
    "postal_code" : "Kode pos apa"
}
``` 

Response Body Success : 
```json
{
    "data" : {
        "id" : 1,
        "street" : "Jalan apa",
        "city": "Kota apa",
        "province":"Province apa",
        "country" :"Negara apa",
        "postal_code" : "Kode pos apa"
    }
}
```

Response Body Error :
```json
{
    "errors" : "Country is required" 
}
```

## Get Address API
Endpoint : GET /api/contacts/:id/addresses/:addressId

Headers : 
- Authorization : token

Response Body Success : 
```json
{
    "data" : {
        "id" : 1,
        "street" : "Jalan apa",
        "city": "Kota apa",
        "province":"Province apa",
        "country" :"Negara apa",
        "postal_code" : "Kode pos apa"
    }
}
```

Response Body Error :
```json
{
    "errors" : "contact is not found" 
}
```


## List Address API
Endpoint : GET /api/contacts/:contactId/addresses

Headers : 
- Authorization : token

Response Body Success : 
```json
{
    "data" :[
         {
            "id" : 1,
            "street" : "Jalan apa",
            "city": "Kota apa",
            "province":"Province apa",
            "country" :"Negara apa",
            "postal_code" : "Kode pos apa"
        },
        {
            "id" : 2,
            "street" : "Jalan apa",
            "city": "Kota apa",
            "province":"Province apa",
            "country" :"Negara apa",
            "postal_code" : "Kode pos apa"
        }
    ]
}
```

Response Body Error :
```json
{
    "errors" : "contact is not found" 
}
```

## Remove Address API
Endpoint : POST /api/contacts/:id/addresses

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
    "errors" : "Address is not found"
}
```