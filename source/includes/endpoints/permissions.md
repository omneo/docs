## Permissions

This API allows you to read permissions.

### Permission Attributes

| Attribute  | Description                | 
|------------|----------------------------|
| id         | ID of the permission.      |
| name       | The name of the permission |
| guard_name |                            |



### List all Permissions

> JSON Response Example:
                
```json
{
    "data": [
        {
            "id": 7,
            "name": "read",
            "guard_name": "web"
        },
        {
            "id": 8,
            "name": "create",
            "guard_name": "web"
        }
    ],
    "links": {
        "first": "http://omneo-api.dev/api/v1/permissions?page=1",
        "last": "http://omneo-api.dev/api/v1/permissions?page=1",
        "prev": null,
        "next": null
    },
    "meta": {
        "current_page": 1,
        "from": 1,
        "last_page": 1,
        "path": "http://omneo-api.dev/api/v1/permissions",
        "per_page": 15,
        "to": 4,
        "total": 4
    }
}
```

This API lets you list all permissions.

#### HTTP Request

`GET /api/v1/permissions`



### Retrieve a permission

> JSON Response Example:
                
```json
{
    "data": {
        "id": 7,
        "name": "read",
        "guard_name": "web"
    }
}
```

This API lets you retrieve a single permission.

#### HTTP Request

`GET /api/v1/permissions/{permission}`