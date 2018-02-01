# Example

This is an example documentation for a fake endpoint.

## Create an example

This API lets you list examples.

### HTTP Request

`POST /api/v1/examples`

### Request Attributes

| Attribute               | Description                   | Rules                                |
|-------------------------|-------------------------------|--------------------------------------|
| example_id              | The example ID                | Must exist                           |

### Response Attributes

| Attribute               | Description                    |
|-------------------------|--------------------------------|
| example                 | The example                    |
| tags                    | The example tags               |

> JSON Response Example:
                
```json
{
    "data": {
        "example": "My Example",
        "tags": [
            {
                "id": 1
            },
            {
                "id": 2
            }
        ]
    }
}
```

## List all examples

This API lets you list all examples.

### HTTP Request

`GET /api/v1/examples`

### Response Attributes

| Attribute               | Description                    |
|-------------------------|--------------------------------|
| example                 | The example                    |
| tags                    | The example tags               |

> JSON Response Example:
                
```json
{
    "data": [
        {
            "example": "My Example",
            "tags": [
                {
                    "id": 1
                },
                {
                    "id": 2
                }
            ]
        }
    ]
}
```

## Retrieve an example

This API lets you retrieve a single example.

### HTTP Request

`GET /api/v1/examples/{example}`

### Request Attributes

None

### Response Attributes

| Attribute               | Description                    |
|-------------------------|--------------------------------|
| example                 | The example                    |
| tags                    | The example tags               |

> JSON Response Example:
                
```json
{
    "data": {
        "example": "My Example",
        "tags": [
            {
                "id": 1
            },
            {
                "id": 2
            }
        ]
    }
}
```

## Update an example

This API lets you update an example.

### HTTP Request

`PUT /api/v1/examples/{example}`

### Request Attributes

| Attribute               | Description                   | Rules                                |
|-------------------------|-------------------------------|--------------------------------------|
| example_id              | The example ID                | Must exist                           |

### Response Attributes

| Attribute               | Description                    |
|-------------------------|--------------------------------|
| example                 | The example                    |
| tags                    | The example tags               |

> JSON Response Example:
                
```json
{
    "data": {
        "example": "My Example",
        "tags": [
            {
                "id": 1
            },
            {
                "id": 2
            }
        ]
    }
}
```

## Delete an example

This API lets you delete an example.

### HTTP Request

`DELETE /api/v1/examples/{example}`

### Request Attributes

None

### Response Attributes

None