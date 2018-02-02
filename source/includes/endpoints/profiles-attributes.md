# Profile's Attributes

This API allows you to read profile's attributes and update its value.
Attributes are attached to profiles by default with default value. 

### Profile's Attributes

| Attribute | Description                                                                        |
|-----------|------------------------------------------------------------------------------------|
| id        | The ID of the attribute                                                            |
| name      | The display name of the attribute                                                  |
| namespace | The category the attribute belongs to                                              |
| handle    | The handle of the attribute                                                        |
| type      | The type of the attribute. Must be from 'string', 'boolean', 'integer', and 'float'|
| default   | The default value of the attribute                                                 |
| rules     | The rule to set attribute value                                                    |
| is_system | Whether this attribute is set by system                                            |




## List all profile's attributes

> JSON Response Example:
                
```json
{
    "data": {
        "fashion-style": [
            {
                "name": "test",
                "default": "white",
                "handle": "color",
                "type": "string",
                "namespace": "fashion-style",
                "rules": [
                    "email"
                ],
                "is_system": false,
                "value": null
            }
        ]
    }
}
```

This API lets you list all attributes belong to a certain profile.

### HTTP Request

`GET /api/v1/profiles/1/attributes`







## Retrieve a profile's attribute

> JSON Response Example:
                
```json
{
    "data": {
        "name": "test",
        "default": "white",
        "handle": "color",
        "type": "string",
        "namespace": "fashion-style",
        "rules": [
            "email"
        ],
        "is_system": false,
        "value": "white"
    }
}
```

This API lets you retrieve a single profile attribute.

### HTTP Request

`GET /api/v1/profiles/1/attributes/{namespace}:{handle}`







## Update a profile attribute

> JSON Response Example:
                
```json
{
    "data": {
        "name": "name update",
        "default": "white",
        "handle": "color",
        "type": "string",
        "namespace": "fashion-style",
        "rules": [
            "email"
        ],
        "is_system": false,
        "created_at": "2018-02-01 23:21:46",
        "updated_at": "2018-02-01 23:36:56"
    }
}
```

This API lets you update a profile attribute.

### HTTP Request

`PUT /api/v1/profiles/1/attributes/{namespace}:{handle}`

### Request Attributes

| Attribute | Type       |
|-----------|------------|
| value     | `required` |

* The type of the value will be based on the rules set in the attribute. 
