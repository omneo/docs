# Example

This API allows you to create, read, update and delete examples.

## Example Properties

| Property               | Description                                 |
|-------------------------|---------------------------------------------|
| id                      | The ID of the example                       |
| name                    | The name of the example                     |
| handle                  | The unique example handle                   |
| description             | The example description                     |






## Create an example

> JSON Response Example:
                
```json
{
    "data": {
        "id": 1,
        "name": "My Example",
        "handle": "my-example",
        "description": null,
        "created_at": "2018-02-01 04:58:41",
        "updated_at": "2018-02-01 03:52:31"
    }
}
```

This API allows you to create examples.

### HTTP Request

`POST /api/v1/examples`

### Request Properties

| Property               | Type                                            |    
|-------------------------|-------------------------------------------------|
| name                    | `string`                                        |
| handle                  | `string`                                        |
| description             | `string` `nullable`                             |









## List all examples

> JSON Response Example:
                
```json
{
    "data": [
        {
            "id": 1,
            "name": "My Examples",
            "handle": "my-example",
            "description": null,
            "created_at": "2018-02-01 04:58:41",
            "updated_at": "2018-02-01 03:52:31"
        },
        {
            "id": 2,
            "name": "My Second Example",
            "handle": "my-second-example",
            "description": null,
            "created_at": "2018-02-01 02:58:41",
            "updated_at": "2018-02-01 03:32:31"
        }
    ]
}
```

This API lets you list all examples.

### HTTP Request

`GET /api/v1/examples`

## Retrieve an example

> JSON Response Example:
                
```json
{
    "data": {
        "id": 1,
        "name": "My Example",
        "handle": "my-example",
        "description": null,
        "created_at": "2018-02-01 04:58:41",
        "updated_at": "2018-02-01 03:52:31"
    }
}
```

This API lets you retrieve a single example.

### HTTP Request

`GET /api/v1/examples/{example}`









## Update an example

> JSON Response Example:
                
```json
{
    "data": {
        "id": 1,
        "name": "My Example",
        "handle": "my-example",
        "description": null,
        "created_at": "2018-02-01 04:58:41",
        "updated_at": "2018-02-01 06:52:31"
    }
}
```

This API allows you to update examples.

### HTTP Request

`PUT /api/v1/examples/{example}`

### Request Properties

| Property               | Type                                            |    
|-------------------------|-------------------------------------------------|
| name                    | `sometimes` `string`                            |
| handle                  | `sometimes` `string`                            |
| description             | `sometimes` `string` `nullable`                 |










## Delete an example

This API allows you to delete examples.

### HTTP Request

`DELETE /api/v1/examples/{example}`