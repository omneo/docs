# Profile Identities

This API allows you to read, update and delete profile identities.

## Profile Identity Properties

| Property               | Description                                 |
|-------------------------|---------------------------------------------|
| handle | The identity handle |
| identifier | The identifier |
| is_active | Whether or not this is the identity is active (e.g. inactive could represent an ex staff member) |
| is_primary | Whether or not this is the primary identity for the user |

## Available Identities

| Handle               | Description                                 |
|-------------------------|---------------------------------------------|
| ecommerce | Ecommerce identifier for the profile |
| pos | Point of Sale identifier for the profile |
| staff | Staff identifier for the profile |
| fingerprint | Fingerprint identifier for the profile |

## Update a profile identity

> JSON Response Example:
                
```json
{
    "data": {
        "handle": "ecommerce",
        "identifier": "2323-2325-2214-2195",
        "is_active": true,
        "is_primary": false,
        "created_at": "2018-02-01 04:58:41",
        "updated_at": "2018-02-01 03:52:31"
    }
}
```

This API allows you to update profile identities.

### HTTP Request

`PUT /api/v1/profiles/{profile}/identities/{handle}`

### Request Properties

| Property               | Type                                            |    
|-------------------------|-------------------------------------------------|
| identifier | `required` `string` |
| is_active | `sometimes` `required` `boolean` | 
| is_primary | `sometimes` `required` `boolean` | 






## List all profile identities

> JSON Response Example:
                
```json
{
    "data": [
        {
            "handle": "ecommerce",
            "identifier": "2323-2325-2214-2195",
            "is_active": true,
            "is_primary": false,
            "created_at": "2018-02-01 04:58:41",
            "updated_at": "2018-02-01 03:52:31"
        },
        {
            "handle": "pos",
            "identifier": "52215252",
            "is_active": true,
            "is_primary": true,
            "created_at": "2018-02-01 04:58:41",
            "updated_at": "2018-02-01 03:52:31"
        },
        {
            "handle": "staff",
            "identifier": "ST-2105",
            "is_active": false,
            "is_primary": true,
            "created_at": "2018-02-01 04:58:41",
            "updated_at": "2018-02-01 03:52:31"
        }
    ]
}
```

This API lets you list all profile attributes.

### HTTP Request

`GET /api/v1/profiles/{profile}/identities`







## Retrieve a profile identity

> JSON Response Example:
                
```json
{
    "data": {
        "handle": "ecommerce",
        "identifier": "2323-2325-2214-2195",
        "is_active": true,
        "is_primary": false,
        "created_at": "2018-02-01 04:58:41",
        "updated_at": "2018-02-01 03:52:31"
    }
}
```

This API lets you retrieve a profile identity.

### HTTP Request

`GET /api/v1/profiles/{profile}/identities/{handle}`
