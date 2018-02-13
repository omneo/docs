## Roles

This API allows you to read roles.

### Role Attributes

| Attribute  | Description                     | 
|------------|---------------------------------|
| id         | ID of the role                  |
| name       | The name of the role            |
| guard_name |                                 |
| permissions| The permissions this role has   |
| users      | The users assigned to this role |


### List all Roles

> JSON Response Example:
                
```json
{
    "data": [
        {
            "id": 3,
            "name": "Store Manager",
            "guard_name": "web",
            "permissions": [],
            "users": [
                {
                    "id": 1,
                    "name": "Orie Kutch DDS",
                    "email": "lionel10@example.net",
                    "created_at": "2018-02-05 22:25:53",
                    "updated_at": "2018-02-05 22:25:53",
                    "pivot": {
                        "role_id": 3,
                        "model_id": 1
                    }
                },
                {
                    "id": 9,
                    "name": "Test",
                    "email": "test2@arkade.com.au",
                    "created_at": "2018-02-06 05:25:40",
                    "updated_at": "2018-02-06 05:25:40",
                    "pivot": {
                        "role_id": 3,
                        "model_id": 9
                    }
                }
            ]
        }
    ],
    "links": {
        "first": "http://omneo-api.dev/api/v1/roles?page=1",
        "last": "http://omneo-api.dev/api/v1/roles?page=1",
        "prev": null,
        "next": null
    },
    "meta": {
        "current_page": 1,
        "from": 1,
        "last_page": 1,
        "path": "http://omneo-api.dev/api/v1/roles",
        "per_page": 15,
        "to": 1,
        "total": 1
    }
}
```

This API lets you list all roles.

#### HTTP Request

`GET /api/v1/roles`



### Retrieve a role

> JSON Response Example:
                
```json
{
    "data": {
        "id": 3,
        "name": "Store Manager",
        "guard_name": "web",
        "permissions": [],
        "users": [
            {
                "id": 1,
                "name": "Orie Kutch DDS",
                "email": "lionel10@example.net",
                "created_at": "2018-02-05 22:25:53",
                "updated_at": "2018-02-05 22:25:53",
                "pivot": {
                    "role_id": 3,
                    "model_id": 1
                }
            },
            {
                "id": 9,
                "name": "Test",
                "email": "test2@arkade.com.au",
                "created_at": "2018-02-06 05:25:40",
                "updated_at": "2018-02-06 05:25:40",
                "pivot": {
                    "role_id": 3,
                    "model_id": 9
                }
            }
        ]
    }
}
```

This API lets you retrieve a single role.

#### HTTP Request

`GET /api/v1/roles/{role}`