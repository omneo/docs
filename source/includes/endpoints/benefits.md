## Benefits

This API allows you to read all benefits or retrieve a single benefit.

### Benefit Attributes

| Property             | Description                                          |
|-----------------------|-----------------------------------------------------|
| id                    | The ID of the benefit                               |
| expires_at            | The expiry date of the benefit                      |
| issue_at              | The date the benefit was created                    |
| benefit_definition_id | The benefit definition associated with this benefit |
| profile_id            | The profile associated with this benefit            |
| is_redeemable         | Whether this benefit is still redeemable            |
| redemptions_remaining | Define how many times this benefit can be redeemed  |
| definition            | The benefit definition associated with this benefit |
| created_at            | The create date of this benefit                     |
| updated_at            | The last update date of this benefit                |



### List all Benefits

> JSON Response Example:
                
```json
{
    "data": 
    [
      {
          "id": 1,
          "expires_at": "1973-07-23 10:35:28",
          "issued_at": "1973-07-13 10:35:28",
          "is_expired": true,
          "is_redeemable": false,
          "redemptions_remaining": 7,
          "definition": {
              "id": 1,
              "name": "Birthday gift",
              "handle": "birthday-gift",
              "period": 10,
              "description": "Your special birthday gift",
              "notes": "Select from wallet, scarf and necklace",
              "max_redemptions": 7,
              "is_extendable": false,
              "is_reassignable": false,
              "tags": [],
              "created_at": "2018-02-12 05:51:22",
              "updated_at": "2018-02-12 05:51:22"
          },
          "created_at": "2018-02-12 05:51:22",
          "updated_at": "2018-02-12 05:51:22"
      }
    ]
}
```

This API lets you list all benefits in the system with pagination.

#### HTTP Request

`GET /api/v1/benefits`



### Retrieve a benefit

> JSON Response Example:
                
```json
{
    "data": {
        "id": 1,
        "expires_at": "2018-07-23 10:35:28",
        "issued_at": "2018-07-13 10:35:28",
        "is_expired": true,
        "is_redeemable": false,
        "redemptions_remaining": 7,
        "definition": {
            "id": 1,
            "name": "Birthday gift",
            "handle": "birthday-gift",
            "period": 10,
            "description": "Your special birthday gift",
            "notes": "Select from wallet, scarf and necklace",
            "max_redemptions": 7,
            "is_extendable": false,
            "is_reassignable": false,
            "tags": [],
            "created_at": "2018-02-12 05:51:22",
            "updated_at": "2018-02-12 05:51:22"
        },
        "created_at": "2018-02-12 05:51:22",
        "updated_at": "2018-02-12 05:51:22"
    }
}
```

This API lets you retrieve a single benefit.

#### HTTP Request

`GET /api/v1/benefits/{benefit}`
