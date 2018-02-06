# Profiles

This API allows you to create, read, update and delete profiles.

### Profile Properties

| Property            | Description                             |
|----------------------|-----------------------------------------|
| id                   | The ID of the profile                                     |
| title                | Title such as Mr. or Miss               |
| first_name           | Profile's first name                    |
| last_name            | Profile's last name                     |
| full_name            | Profile's full name                     |
| email                | Profile's email                         |
| gender               | Profile's gender                        |
| mobile_phone         | Mobile phone number                     |
| mobile_phone_country | Country where the phone belong to.      |
| home_phone           | Home phone number                       |
| home_phone_country   | Country where the phone belong to.      |
| work_phone           | Work phone number                       |
| work_phone_country   | Country where the phone belong to.      |
| joined_at            | Date that the profile join Omneo.       |
| joined_location_id   | The place where the profile join Omneo. |
| birth_day            | Profile's birth day                     |
| brith_month          | Profile's birth month                   |
| birth_year           | Profile's birth year                    |
| company              | Company name                            |
| occupation           | Profile's occupation                    |
| avatar_url           | avatar url                              |
| currency_id          | The currency this profile use           |
| tags                 | The tags attaching to this profile.     |
| addresses            | The profile's addresses.                |



## Create a profile

> JSON Response Example:
                
```json
{
    "data": {
        "id": 29,
        "title": "Mr.",
        "first_name": "Lei",
        "last_name": "Li",
        "full_name": "Lei Li",
        "email": "lilei@arkade.com.au",
        "mobile_phone": null,
        "mobile_phone_country": "AU",
        "mobile_phone_e164": null,
        "home_phone": null,
        "home_phone_country": null,
        "work_phone": null,
        "work_phone_country": null,
        "address": null,
        "avatar_url": null,
        "company": null,
        "occupation": null,
        "birth_year": null,
        "birth_month": null,
        "birth_day": null,
        "addresses": [],
        "balance": {
            "rewards": 0,
            "points": null
        },
        "joined_location": null,
        "tags": [],
        "created_at": "2018-02-01 06:33:49",
        "updated_at": "2018-02-01 06:33:49"
    }
}
```


This API allows you to create new profiles.

### HTTP Request

`POST /api/v1/profiles`

### Request Properties

| Property            | Type                                                                                                              |
|----------------------|-------------------------------------------------------------------------------------------------------------------|
| title                | `nullable` `string`                                                                                               |
| first_name           | `nullable` `string`                                                                                               |
| last_name            | `nullable` `string`                                                                                               |
| email                | `nullable` `email` `unique`                                                                                       |
| gender               | `nullable` `in: male, female, withheld, other`                                                                    |
| mobile_phone         | `nullable` `phone`                                                                                                |
| mobile_phone_country | Required only when mobile_phone is present. `in: AU, NZ, US`                                                      |
| home_phone           | `nullable` `phone`                                                                                                |
| home_phone_country   | Required only when home_phone is present. `in: AU, NZ, US`                                                        |
| work_phone           | `nullable` `phone`                                                                                                |
| work_phone_country   | `nullable` only when work_phone is present. `in: AU, NZ, US`                                                      |
| joined_at            | `nullable` only when joined_location_id is present. Must be in the format of "Year-Month-Date hour:minute:second" |
| joined_location_id   | `nullable` only when joined_at is present. Must be in the format of "Year-Month-Date hour:minute:second"          |
| birth_day            | `nullable` `integer` Must exist if birth_month is present.                                                        |
| brith_month          | `nullable` `integer` Must exist if birth_day is present.                                                          |
| birth_year           | `nullable` `integer` Must exist if birth_day and birth_month are present.                                         |
| company              | `nullable` `string`                                                                                               |
| occupation           | `nullable` `string`                                                                                               |
| avatar_url           | `nullable` `url`                                                                                                  |
| currency_id          | `nullable` `integer` Must from currencies table.                                                                  |
| tags                 | `nullable` Array each array elements must be in "tags" format.                                                    |
| addresses            | `nullable` Array each array elements must be in "address" format.                                                 |




## List all Profiles

> JSON Response Example:
                
```json
{
  "data": [
    {
      "id": 1,
      "title": "Mr.",
      "first_name": "Furman",
      "last_name": "Gerhold",
      "full_name": "Furman Gerhold",
      "email": "hartmann.melyssa@gmail.com",
      "mobile_phone": "0401 222 111",
      "mobile_phone_country": "AU",
      "mobile_phone_e164": "+61401222111",
      "home_phone": null,
      "home_phone_country": null,
      "work_phone": null,
      "work_phone_country": null,
      "address": null,
      "avatar_url": null,
      "company": null,
      "occupation": null,
      "birth_year": 1972,
      "birth_month": 0,
      "birth_day": 2,
      "addresses": [],
      "balance": {
        "rewards": 0,
        "points": 0
      },
      "joined_location": null,
      "tags": [],
      "created_at": "2018-01-31 00:41:16",
      "updated_at": "2018-01-31 00:41:16"
    }
  ]
}
```

This API lets you list all profiles.

### HTTP Request

`GET /api/v1/profiles`


## Retrieve a profile

> JSON Response Example:
                
```json
{
    "data": {
        "id": 2,
        "title": "Mr.",
        "first_name": "Lei",
        "last_name": "Li",
        "full_name": "Lei Li",
        "email": "lilei@arkade.com.au",
        "mobile_phone": null,
        "mobile_phone_country": "AU",
        "mobile_phone_e164": null,
        "home_phone": null,
        "home_phone_country": null,
        "work_phone": null,
        "work_phone_country": null,
        "address": null,
        "avatar_url": null,
        "company": null,
        "occupation": null,
        "birth_year": null,
        "birth_month": null,
        "birth_day": null,
        "addresses": [],
        "balance": {
            "rewards": 0,
            "points": null
        },
        "joined_location": null,
        "tags": [],
        "created_at": "2018-02-01 06:33:49",
        "updated_at": "2018-02-01 06:33:49"
    }
}
```

This API lets you retrieve a single profile.

### HTTP Request

`GET /api/v1/profiles/{profile}`




## Update a profile

> JSON Response Example:
                
```json
{
    "data": {
        "id": 8,
        "title": "Mr.",
        "first_name": "Meimei",
        "last_name": "Han",
        "full_name": "Meimei Han",
        "email": "hanmeimei@arkade.com.au",
        "mobile_phone": null,
        "mobile_phone_country": "AU",
        "mobile_phone_e164": null,
        "home_phone": null,
        "home_phone_country": null,
        "work_phone": null,
        "work_phone_country": null,
        "address": null,
        "avatar_url": null,
        "company": null,
        "occupation": null,
        "birth_year": null,
        "birth_month": null,
        "birth_day": null,
        "addresses": [],
        "balance": {
            "rewards": 0,
            "points": null
        },
        "joined_location": null,
        "tags": [],
        "created_at": "2018-01-31 04:22:19",
        "updated_at": "2018-01-31 04:23:04"
    }
}
```

This API lets you update a profile.

### HTTP Request

`PUT /api/v1/profiles/{profile}`

### Request Properties

| Property            | Type                                                                                                              |
|----------------------|-------------------------------------------------------------------------------------------------------------------|
| title                | `nullable` `string`                                                                                               |
| first_name           | `nullable` `string`                                                                                               |
| last_name            | `nullable` `string`                                                                                               |
| email                | `nullable` `email` `unique`                                                                                       |
| gender               | `nullable` `in: male, female, withheld, other`                                                                    |
| mobile_phone         | `nullable` `phone`                                                                                                |
| mobile_phone_country | Required only when mobile_phone is present. `in: AU, NZ, US`                                                      |
| home_phone           | `nullable` `phone`                                                                                                |
| home_phone_country   | Required only when home_phone is present. `in: AU, NZ, US`                                                        |
| work_phone           | `nullable` `phone`                                                                                                |
| work_phone_country   | `nullable` only when work_phone is present. `in: AU, NZ, US`                                                      |
| joined_at            | `nullable` only when joined_location_id is present. Must be in the format of "Year-Month-Date hour:minute:second" |
| joined_location_id   | `nullable` only when joined_at is present. Must be in the format of "Year-Month-Date hour:minute:second"          |
| birth_day            | `nullable` `integer` Must exist if birth_month is present.                                                        |
| brith_month          | `nullable` `integer` Must exist if birth_day is present.                                                          |
| birth_year           | `nullable` `integer` Must exist if birth_day and birth_month are present.                                         |
| company              | `nullable` `string`                                                                                               |
| occupation           | `nullable` `string`                                                                                               |
| avatar_url           | `nullable` `url`                                                                                                  |
| currency_id          | `nullable` `integer` Must from currencies table.                                                                  |
| tags                 | `nullable` Array each array elements must be in "tags" format.                                                    |
| addresses            | `nullable` Array each array elements must be in "address" format.                                                 |



## Delete a profile

This API lets you delete a profile.

### HTTP Request

`DELETE /api/v1/profiles/{profile}`
