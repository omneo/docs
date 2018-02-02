# Attributes

This API allows you to create, read, update and delete profile attributes.

### Profile Attributes

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

* The pair of [namespace, handle] is unique. 







## Create a profile attribute

> JSON Response Example:
                
```json
{
    "data": {
        "name": "color",
        "default": "white",
        "handle": "fashion-style_color",
        "type": "string",
        "namespace": "fashion-style",
        "rules": [
            "email"
        ],
        "is_system": false,
        "created_at": "2018-02-01 23:21:46",
        "updated_at": "2018-02-01 23:21:46"
    }
}
```

This API allows you to create a profile attribute.

### HTTP Request

`POST /api/v1/profiles/attributes`

### Request Attributes

| Attribute | Type                                                                      |
|-----------|---------------------------------------------------------------------------|
| name      | `required` `string`                                                       |
| namespace | `required` `string`                                                       |
| handle    | `required` `string`                                                       |
| type      | `required` `in: integer, float, boolean, string`                          |
| default   | `sometimes` `nullable`                                                    |
| rules     | `required` `array`                                                        |
| rules.*   | `required` `string` `in: required, email, boolean, url, numeric, integer` |
| is_system | `sometimes` `boolean`                                                     |

* The pair of [namespace, handle] should be unique. 





## List all attributes

> JSON Response Example:
                
```json
{
    "data": [
        {
            "name": "color",
            "default": "white",
            "handle": "color",
            "type": "string",
            "namespace": "fashion-style",
            "rules": [
                "email"
            ],
            "is_system": false,
            "created_at": "2018-02-01 23:21:46",
            "updated_at": "2018-02-01 23:21:46"
        }
    ],
    "links": {
        "first": "http://omneo-api.dev/api/v1/profiles/attributes?page=1",
        "last": "http://omneo-api.dev/api/v1/profiles/attributes?page=1",
        "prev": null,
        "next": null
    },
    "meta": {
        "current_page": 1,
        "from": 1,
        "last_page": 1,
        "path": "http://omneo-api.dev/api/v1/profiles/attributes",
        "per_page": 15,
        "to": 1,
        "total": 1
    }
}
```

This API lets you list all profile attributes.

### HTTP Request

`GET /api/v1/profiles/attributes`







## Retrieve a profile attribute

> JSON Response Example:
                
```json
{
    "data": {
        "name": "color",
        "default": "white",
        "handle": "color",
        "type": "string",
        "namespace": "fashion-style",
        "rules": [
            "email"
        ],
        "is_system": false,
        "created_at": "2018-02-01 23:21:46",
        "updated_at": "2018-02-01 23:21:46"
    }
}
```

This API lets you retrieve a single profile attribute.

### HTTP Request

`GET /api/v1/profiles/attributes/{namespace}:{handle}`







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

`PUT /api/v1/profiles/attributes/{namespace}:{handle}`

### Request Attributes

| Attribute | Type                |
|-----------|---------------------|
| name      | `required` `string` |







## Delete a profile attribute

This API lets you delete a profile attribute.

### HTTP Request

`DELETE /api/v1/profiles/attributes/{namespace}:{handle}`
