<h1 id="profile-schema-attributes-heading">Profile Attributes</h1>

This API allows you to create, read, update and delete profile attributes.

<h2 id="profile-schema-attributes">Profile Schema Attributes</h2>

| Attribute               | Description                                 |
|-------------------------|---------------------------------------------|
| handle                  | The attribute handle |
| name                    | The display name of the attribute        |
| namespace               | The attribute namespace                  |
| value                   | The attribute value                      |
| type                    | The attribute type (e.g. string)         |
| default                 | The attribute default value        |
| rules                   | The attribute rules (e.g. must be email, url)        |
| is_system | Whether or not the attribute is deletable |




## Create a profile attribute

> JSON Response Example:
                
```json
{
    "data": {
        "name": "Subscribe to Weekly Email",
        "handle": "subscribe-weekly",
        "namespace": "preferences",
        "type": "boolean",
        "default": false,
        "rules": [
            "required",
            "boolean"
        ],
        "is_system": true,
        "created_at": "2018-02-01 04:58:41",
        "updated_at": "2018-02-01 03:52:31"
    }
}
```

This API allows you to create profile attributes.

### HTTP Request

`POST /api/v1/profiles/attributes`

<aside class="notice">
Profile attributes are unique to namespace and handle.
</aside>

<aside class="notice">
Every profile has every attribute. If a profile does not have an attribute value, the default value is used.
</aside>

### Request Attributes

| Attribute               | Type                                            |    
|-------------------------|-------------------------------------------------|
| name | `nullable` `string` |
| namespace | `required` `string` | 
| type | `required` `in: integer, float, boolean, string` | 
| rules | `required` `array` | 
| rules.* | `required` `in: email, url, required, string, boolean, float, integer`
| default | `sometimes` `nullable` `string`
| is_system | `sometimes` `required` `boolean`
| handle | `required` `unique: namespace, handle`






## List all profile attributes

> JSON Response Example:
                
```json
{
    "data": [
        {
            "name": "Subscribe to Weekly Email",
            "handle": "subscribe-weekly",
            "namespace": "preferences",
            "type": "boolean",
            "default": false,
            "rules": [
                "required",
                "boolean"
            ],
            "is_system": true,
            "created_at": "2018-02-01 04:58:41",
            "updated_at": "2018-02-01 03:52:31"
        },
        {
            "name": "Subscribe to Push Notifications",
            "handle": "subscribe-push",
            "namespace": "preferences",
            "type": "boolean",
            "default": false,
            "rules": [
                "required",
                "boolean"
            ],
            "is_system": true,
            "created_at": "2018-02-01 01:58:41",
            "updated_at": "2018-02-01 03:52:31"
        }
    ]
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
        "name": "Subscribe to Push Notifications",
        "handle": "subscribe-push",
        "namespace": "preferences",
        "type": "boolean",
        "default": false,
        "rules": [
            "required",
            "boolean"
        ],
        "is_system": true,
        "created_at": "2018-02-01 01:58:41",
        "updated_at": "2018-02-01 03:52:31"
    }
}
```

This API lets you retrieve a profile attribute.

### HTTP Request

`GET /api/v1/profiles/attributes/{namespace:handle}`

<aside class="notice">
Profile attributes are accessed by their unique `namespace:handle` combination. e.g. `preferences:subscribe-push`
</aside>







## Update a profile attribute

> JSON Response Example:
                
```json
{
    "data": {
        "name": "Subscribe to Push Notifications",
        "handle": "subscribe-push",
        "namespace": "preferences",
        "type": "boolean",
        "default": false,
        "rules": [
            "required",
            "boolean"
        ],
        "is_system": true,
        "created_at": "2018-02-01 01:58:41",
        "updated_at": "2018-03-01 03:52:31"
    }
}
```

This API allows you to update a profile attribute.

### HTTP Request

`PUT /api/v1/{resource}/{resourceId}/{namespace}:{handle}`

### Request Attributes

| Attribute               | Type                                            |    
|-------------------------|-------------------------------------------------|
| name                    | `sometimes` `nullable` `string` |






## Delete a profile attribute

This API allows you to delete a profile attribute.

### HTTP Request

`DELETE /api/v1/profiles/attributes/{namespace}:{handle}`








## List all profile attributes for a profile

> JSON Response Example:
                
```json
{
    "data": {
        "preferences": [
            {
                "name": "Subscribe to Push Notifications",
                "handle": "subscribe-push",
                "namespace": "preferences",
                "type": "boolean",
                "default": false,
                "rules": [
                    "required",
                    "boolean"
                ],
                "value": true,
                "created_at": "2018-02-01 01:58:41",
                "updated_at": "2018-03-01 03:52:31"
            },
            {
                "name": "Subscribe to Weekly Email",
                "handle": "subscribe-weekly",
                "namespace": "preferences",
                "type": "boolean",
                "default": false,
                "rules": [
                    "required",
                    "boolean"
                ],
                "value": false,
                "created_at": "2018-02-01 04:58:41",
                "updated_at": "2018-02-01 03:52:31"
            }
        ]
    }
}
```

This API allows you to list all profile attributes for a given profile.

### HTTP Request

`GET /api/v1/profiles/{profile}/attributes`

<aside class="notice">
Profile attributes are automatically grouped by their namespace.
</aside>









## Update a profile attribute for a profile

> JSON Response Example:
                
```json
{
    "data": {
        "name": "Subscribe to Push Notifications",
        "handle": "subscribe-push",
        "namespace": "preferences",
        "type": "boolean",
        "default": false,
        "rules": [
            "required",
            "boolean"
        ],
        "value": true,
        "created_at": "2018-02-01 01:58:41",
        "updated_at": "2018-03-01 03:52:31"
    }
}
```

This API allows you to update a profile attribute for a given profile.

### HTTP Request

`PUT /api/v1/profiles/{profile}/attributes/{namespace}:{handle}`

### Request Attributes

| Attribute               | Type                                            |    
|-------------------------|-------------------------------------------------|
| value                   | `sometimes` `in: rules` |




