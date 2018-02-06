# Users

This API allows you to create, read, update and delete users.

## User Attributes

| Attribute   | Description                                  | 
|-------------|----------------------------------------------|
| id          | ID of the user.                              |
| name        | The profile associate with this transaction  |
| email       | The location that this transaction happened  |
| roles       | The currency this transaction use            |


## Create a user

> JSON Response Example:
                
```json
{
    "data": {
        "id": 11,
        "name": "Test",
        "email": "test@arkade.com.au",
        "roles": [
            {
                "id": 3,
                "name": "Store Manager",
                "guard_name": "web",
                "created_at": "2018-02-05 23:02:13",
                "updated_at": "2018-02-05 23:02:13",
                "pivot": {
                    "model_id": 11,
                    "role_id": 3
                }
            }
        ]
    }
}
```

> JSON Request Example:

```json
{
  "name":"Test",
  "email":"test@arkade.com.au",
  "password":"default",
  "roles":[
    {
      "id": 3
    }
  ]
}
```


This API allows you to create a user and associate roles with the user.

### HTTP Request

`POST /api/v1/users`

### Request Attributes
| Attribute   | Type                                        |
|-------------|---------------------------------------------|
| name        | `required` `string`                         |
| email       | `required` `string` `email` `unique:users`  |
| roles       | `sometimes` `required` `array`              |
| roles.*.id  | `required` `exists:roles,id`                |



## List all users

> JSON Response Example:
                
```json
{
    "data": [
        {
            "id": 1,
            "name": "Orie Kutch DDS",
            "email": "lionel10@example.net",
            "roles": [
                {
                    "id": 3,
                    "name": "Store Manager",
                    "guard_name": "web",
                    "created_at": "2018-02-05 23:02:13",
                    "updated_at": "2018-02-05 23:02:13",
                    "pivot": {
                        "model_id": 1,
                        "role_id": 3
                    }
                }
            ]
        },
        {
            "id": 9,
            "name": "Test",
            "email": "test2@arkade.com.au",
            "roles": [
                {
                    "id": 3,
                    "name": "Store Manager",
                    "guard_name": "web",
                    "created_at": "2018-02-05 23:02:13",
                    "updated_at": "2018-02-05 23:02:13",
                    "pivot": {
                        "model_id": 9,
                        "role_id": 3
                    }
                }
            ]
        }
    ],
    "links": {
        "first": "http://omneo-api.dev/api/v1/users?page=1",
        "last": "http://omneo-api.dev/api/v1/users?page=1",
        "prev": null,
        "next": null
    },
    "meta": {
        "current_page": 1,
        "from": 1,
        "last_page": 1,
        "path": "http://omneo-api.dev/api/v1/users",
        "per_page": 15,
        "to": 9,
        "total": 9
    }
}
```

This API lets you list all users.

### HTTP Request

`GET /api/v1/users`



## Retrieve a user

> JSON Response Example:
                
```json
{
    "data": {
        "id": 1,
        "name": "Orie Kutch DDS",
        "email": "lionel10@example.net",
        "roles": [
            {
                "id": 3,
                "name": "Store Manager",
                "guard_name": "web",
                "created_at": "2018-02-05 23:02:13",
                "updated_at": "2018-02-05 23:02:13",
                "pivot": {
                    "model_id": 1,
                    "role_id": 3
                }
            }
        ]
    }
}
```

This API lets you retrieve a single user.

### HTTP Request

`GET /api/v1/users/{user}`



## Update a user

> JSON Response Example:
                
```json
{
    "data": {
        "id": 1,
        "name": "Test2",
        "email": "lionel10@example.net",
        "roles": [
            {
                "id": 3,
                "name": "Store Manager",
                "guard_name": "web",
                "created_at": "2018-02-05 23:02:13",
                "updated_at": "2018-02-05 23:02:13",
                "pivot": {
                    "model_id": 1,
                    "role_id": 3
                }
            }
        ]
    }
}
```

> JSON Request Example:
                
```json
{
  "name":"Test2",
  "password":"default",
  "roles":[
    {
      "id": 1
    }
  ]
}
```

This API lets you update a user.

### HTTP Request

`PUT /api/v1/users/{user}`

### Request Attributes
| Attribute   | Type                                                    |
|-------------|---------------------------------------------------------|
| name        | `sometimes` `required` `string`                         |
| email       | `sometimes` `required` `string` `email` `unique:users`  |
| roles       | `sometimes` `required` `array`                          |
| roles.*.id  | `required` `exists:roles,id`                            |


## Delete a user

This API lets you delete a user.

### HTTP Request

`DELETE /api/v1/users/{user}`

