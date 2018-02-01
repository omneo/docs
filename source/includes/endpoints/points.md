# Points

This API allows you to view a profiles points.

## Point Attributes

| Attribute               | Description                        |
|-------------------------|------------------------------------|
| id                      | The ID of the point                |
| value_initial           | The initial value of the point     |
| value_remaining         | The remaining value of the point   |
| issued_at               | The date of issue                  |
| definition              | The point definition               |
| created_at              | The created date                   |
| updated_at              | The updated date                   |

## List all points

> JSON Response Example:
                
```json
{
    "data": [
        {
            "id": 1,
            "value_initial": 2.00,
            "value_remaining": 1.00,
            "issued_at": "2018-08-23 16:40:07",
            "definition": {
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
            "created_at": "2018-02-01 04:58:41",
            "updated_at": "2018-02-01 03:52:31"
        },
        {
            "id": 2,
            "value_initial": 1.00,
            "value_remaining": 1.00,
            "issued_at": "2017-08-23 16:40:07",
            "definition": {
                "id": 2,
                "name": "My Second Point Definition",
                "handle": "my-second-point-definition",
                "description": null,
                "notes": null,
                "is_reassignable": true,
                "created_at": "2018-02-01 02:58:41",
                "updated_at": "2018-02-01 03:32:31"
            },
            "created_at": "2018-02-01 03:52:41",
            "updated_at": "2018-02-01 04:52:31"
        }
    ]
}
```

This API lets you list all points for a given profile.

### HTTP Request

`GET /api/v1/profiles/{profile}/points`

## Retrieve a point

> JSON Response Example:
                
```json
{
    "data": {
        "id": 2,
        "value_initial": 1.00,
        "value_remaining": 1.00,
        "issued_at": "2017-08-23 16:40:07",
        "definition": {
            "id": 2,
            "name": "My Second Point Definition",
            "handle": "my-second-point-definition",
            "description": null,
            "notes": null,
            "is_reassignable": true,
            "created_at": "2018-02-01 02:58:41",
            "updated_at": "2018-02-01 03:32:31"
        },
        "created_at": "2018-02-01 03:52:41",
        "updated_at": "2018-02-01 04:52:31"
    }
}
```

This API lets you retrieve a single point.

### HTTP Request

`GET /api/v1/profiles/{profile}/points/{point}`