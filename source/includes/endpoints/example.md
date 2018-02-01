# Example

This is an example documentation for a fake endpoint.

## Create an example

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

## List all examples

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

This API lets you list all examples.

### HTTP Request

`GET /api/v1/examples`

### Response Attributes

| Attribute               | Description                    |
|-------------------------|--------------------------------|
| example                 | The example                    |
| tags                    | The example tags               |

## Retrieve an example

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

## Update an example

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

## Delete an example

This API lets you delete an example.

### HTTP Request

`DELETE /api/v1/examples/{example}`

### Request Attributes

None

### Response Attributes

None