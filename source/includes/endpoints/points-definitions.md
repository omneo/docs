## Point Definitions

This API allows you to create, read, update and delete point definitions.

### Point Definition Properties

| Property               | Description                                 |
|-------------------------|---------------------------------------------|
| id                      | The ID of the point definition              |
| name                    | The name of the point definition            |
| handle                  | The unique point definition handle          |
| description             | The point definition description            |
| notes                   | The point definition notes                  |
| is_reassignable         | Whether or not points can be reassignable   |
| tags                    | Tags attached to the definition             |
| created_at              | The created date                            |
| updated_at              | The updated date                            |






### Create a point definition

> JSON Response Example:
                
```json
{
    "data": {
        "id": 1,
        "name": "My Point Definition",
        "handle": "my-point-definition",
        "description": null,
        "notes": null,
        "is_reassignable": false,
        "tags": [],
        "created_at": "2018-02-01 04:58:41",
        "updated_at": "2018-02-01 03:52:31"
    }
}
```

This API allows you to a create point definition.

#### HTTP Request

`POST /api/v1/points/definitions`

#### Request Properties

| Property               | Type                                            |    
|-------------------------|-------------------------------------------------|
| name                    | `string`                                        |
| handle                  | `string`                                        |
| description             | `string` `nullable`                             |
| notes                   | `string` `nullable`                             |
| is_reassignable         | `boolean` `nullable`                            |








### List all point definitions

> JSON Response Example:
                
```json
{
    "data": [
        {
            "id": 1,
            "name": "My Point Definition",
            "handle": "my-point-definition",
            "description": null,
            "notes": null,
            "is_reassignable": false,
            "tags": [],
            "created_at": "2018-02-01 04:58:41",
            "updated_at": "2018-02-01 03:52:31"
        },
        {
            "id": 2,
            "name": "My Second Point Definition",
            "handle": "my-second-point-definition",
            "description": null,
            "notes": null,
            "is_reassignable": true,
            "tags": [],
            "created_at": "2018-02-01 02:58:41",
            "updated_at": "2018-02-01 03:32:31"
        }
    ]
}
```

This API lets you list all point definitions.

#### HTTP Request

`GET /api/v1/points/definitions`

### Retrieve a point definition

> JSON Response Example:
                
```json
{
    "data": {
        "id": 1,
        "name": "My Point Definition",
        "handle": "my-point-definition",
        "description": null,
        "notes": null,
        "is_reassignable": false,
        "tags": [],
        "created_at": "2018-02-01 04:58:41",
        "updated_at": "2018-02-01 03:52:31"
    }
}
```

This API lets you retrieve a single point definition.

#### HTTP Request

`GET /api/v1/points/definitions/{definition}`









### Update a point definition

> JSON Response Example:
                
```json
{
    "data": {
        "id": 1,
        "name": "My Point Definition",
        "handle": "my-point-definition",
        "description": null,
        "notes": null,
        "is_reassignable": false,
        "tags": [],
        "created_at": "2018-02-01 04:58:41",
        "updated_at": "2018-02-01 06:52:31"
    }
}
```

This API allows you to update point definitions.

#### HTTP Request

`PUT /api/v1/points/definitions/{definition}`

#### Request Properties

| Property               | Type                                            |    
|-------------------------|-------------------------------------------------|
| name                    | `sometimes` `string`                            |
| handle                  | `sometimes` `string`                            |
| description             | `sometimes` `string` `nullable`                 |
| notes                   | `sometimes` `string` `nullable`                 |
| is_reassignable         | `sometimes` `boolean` `nullable`                |






### Delete a point definition

This API allows you to delete point definitions.

#### HTTP Request

`DELETE /api/v1/points/definitions/{definition}`