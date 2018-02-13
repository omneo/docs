# Redemptions

This API allows you to view reward, benefit and point redemptions made against a given a profile.

## Redemption Properties

| Property       | Description                                          |
|-----------------|------------------------------------------------------|
| id              | The ID of the redemption                             |
| profile_id      | The profile associated with the redemption           |
| type   | The redemption type |
| type_details   | The redemption type details |
| location_id     | The location associated with the redemption          |
| value           | The redeemed value                                |
| items | List of redemption items |



## List all profile redemptions

> JSON Response Example:
                
```json
{
    "data": [
        {
            "id": 1,
            "items": [
                {
                    "id": "1",
                    "type": "reward",
                    "type_attributes": {
                        "id": 1,
                        "value_initial": 100.00,
                        "value_remaining": 100.00,
                        "expires_at": "2018-01-02 00:00:00",
                        "issued_at": "2018-01-01 00:00:00",
                        "is_expired": false,
                        "created_at": "2018-01-01 00:00:00",
                        "updated_at": "2018-01-01 00:00:00"
                    }
                }
            ],
            "created_at": "2018-01-01 00:00:00",
            "updated_at": "2018-01-01 00:00:00"
        }
    ]
}
```

This API lets you list all profile redemptions.

### HTTP Request

`GET /api/v1/profiles/{profile}/redemptions`

## Retrieve a redemption

> JSON Response Example:
                
```json
{
    "data": {
        "id": 1,
        "items": [
            {
                "id": "1",
                "type": "reward",
                "type_attributes": {
                    "id": "1",
                    "value_initial": 100.00,
                    "value_remaining": 100.00,
                    "expires_at": "2018-01-02 00:00:00",
                    "issued_at": "2018-01-01 00:00:00",
                    "is_expired": false,
                    "created_at": "2018-01-01 00:00:00",
                    "updated_at": "2018-01-01 00:00:00"
                }
            }
        ],
        "created_at": "2018-01-01 00:00:00",
        "updated_at": "2018-01-01 00:00:00"
    }
}
```

This API lets you retrieve a single reward definition.

### HTTP Request

`GET /api/v1/profiles/{profile}/redemptions/{redemption}`










## Redeem Benefits

> JSON Response Example:

```json
{
    "data": {
        "id": 1,
        "type": "benefit",
        "type_attributes": {
            "id": 1,
            "expires_at": "2018-02-16 05:58:02",
            "issued_at": "2018-02-02 05:58:02",
            "is_expired": false,
            "is_redeemable": true,
            "redemptions_remaining": 5,
            "created_at": "2018-02-02 05:58:02",
            "updated_at": "2018-02-02 05:58:02"
        },
        "value": null,
        "created_at": "2018-02-02 05:59:58",
        "updated_at": "2018-02-02 05:59:58"
    }
}
```


This API allows you to redeem a benefit.

### HTTP Request

`POST /api/v1/profiles/{profile}/benefits/{benefit}/redeem`

### Request Properties

None









## Redeem Rewards and or Points

This API lets you redeem **points** and or **rewards**.

> JSON Response Example:
                
```json
{
    "data": {
        "total_redeemed": 100,
        "total_requested": 110,
        "profile": {
            "reward_balance": 10,
            "point_balance": 0
        }
    }
}
```

Request a redemption against a profile and transaction.

### Available Strategies

The redeem endpoint accepts a **strategy** handle which is used to determine the type and order in which
a profiles benefits are redeemed.

There are four different redeem strategies:

| Handle                  | Description                      |
|-------------------------|----------------------------------|
| rewards                 | Redeem only rewards              |
| points                  | Redeem only points               |
| rewards_points          | Redeem rewards first then points |         
| points_rewards          | Redeem points first then rewards | 

### HTTP Request

`POST /api/v1/profiles/{profile}/redeem`

### Request Properties

| Property               | Description                   | Rules                                                       |
|-------------------------|-------------------------------|-------------------------------------------------------------|
| amount                  | The amount to be redeemed     | Must be an integer greater than 0                           |
| strategy                | The strategy to use           | One of: points, rewards, rewards_points, points_rewards     |

### Response Properties

| Property               | Description                    |
|-------------------------|--------------------------------|
| total_redeemed        | The total amount redeemed      |
| total_requested        | The total amount requested      |
| profile.reward_balance  | The new profile reward balance |
| profile.point_balance   | The new profile point balance  |
