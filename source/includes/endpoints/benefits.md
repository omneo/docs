# Benefits

This API allows you to read benefits.

## Benefit Attributes

| Attribute             | Description                                         |
|-----------------------|-----------------------------------------------------|
| id                    | The ID of the benefit                               |
| expires_at            | The expiry date of the benefit                      |
| issue_at              | The date the benefit was created                    |
| benefit_definition_id | The benefit definition associated with this benefit |
| profile_id            | The profile associated with this benefit            |



## List all Benefits

> JSON Response Example:
                
```json
{
    "data": [
        {
            "id": 1,
            "expires_at": "2001-07-22 18:32:31",
            "issued_at": "2001-07-09 18:32:31",
            "is_expired": true,
            "definition": {
                "id": 1,
                "name": "Birthday benefit",
                "handle": "dolorem-veritatis-quo-exercitationem",
                "period": 30,
                "description": "...",
                "notes": "xxx",
                "max_redemptions": 1,
                "is_extendable": false,
                "is_reassignable": false,
                "tags": [],
                "created_at": "2018-01-31 00:41:16",
                "updated_at": "2018-02-02 04:45:55"
            },
            "created_at": "2018-01-31 00:41:16",
            "updated_at": "2018-01-31 00:41:16"
        }
    ],
    "links": {
        "first": "http://omneo-api.dev/api/v1/profiles/5/benefits?page=1",
        "last": "http://omneo-api.dev/api/v1/profiles/5/benefits?page=1",
        "prev": null,
        "next": null
    },
    "meta": {
        "current_page": 1,
        "from": 1,
        "last_page": 1,
        "path": "http://omneo-api.dev/api/v1/profiles/5/benefits",
        "per_page": 15,
        "to": 1,
        "total": 1
    }
}
```

This API lets you list all benefits associated with a certain profile.

### HTTP Request

`GET /api/v1/profiles/{profile}/benefits`



## Retrieve a benefit

> JSON Response Example:
                
```json
{
    "data": {
        "id": 1,
        "expires_at": "2001-07-22 18:32:31",
        "issued_at": "2001-07-09 18:32:31",
        "is_expired": true,
        "definition": {
            "id": 1,
            "name": "Birthday benefit",
            "handle": "dolorem-veritatis-quo-exercitationem",
            "period": 30,
            "description": "...",
            "notes": "xxx",
            "max_redemptions": 1,
            "is_extendable": false,
            "is_reassignable": false,
            "tags": [],
            "created_at": "2018-01-31 00:41:16",
            "updated_at": "2018-02-02 04:45:55"
        },
        "created_at": "2018-01-31 00:41:16",
        "updated_at": "2018-01-31 00:41:16"
    }
}
```

This API lets you retrieve a single benefit.

### HTTP Request

`GET /api/v1/profiles/{profile}/benefits/{benefit}`
