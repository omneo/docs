# Redeem

This API lets you redeem **points** and or **rewards**.

## Request a redemption

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

`POST /api/v1/profiles/{profile}/transactions/{transaction}/redeem`

### Request Attributes

| Attribute               | Description                   | Rules                                                       |
|-------------------------|-------------------------------|-------------------------------------------------------------|
| amount                  | The amount to be redeemed     | Must be an integer greater than 0                           |
| strategy                | The strategy to use           | One of: points, rewards, rewards_points, points_rewards     |

### Response Attributes

| Attribute               | Description                    |
|-------------------------|--------------------------------|
| redemption_total        | The total amount redeemed      |
| profile.reward_balance  | The new profile reward balance |
| profile.point_balance   | The new profile point balance  |

> JSON Response Example:
                
```json
{
    "data": [
        {
            "redemption_total": 100,
            "profile": {
                "reward_balance": 10,
                "point_balance": 0
            }
        }
    ]
}
```