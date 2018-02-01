# Profile

This is the api endpoint to query profiles.



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


This API lets you create a profile.

### HTTP Request

`POST /api/v1/profiles`

### Request Attributes

| Attribute            | Description                             | Rules                                                                                                               |
|----------------------|-----------------------------------------|---------------------------------------------------------------------------------------------------------------------|
| title                | Title such as Mr. or Miss               | Nullable. Must be a string.                                                                                           |
| first_name           | Profile's first name                    | Required. Must be a string.                                                                                      |
| last_name            | Profile's last name                     | Required. Must be a string.                                                                                       |
| email                | Profile's email                         | Required. Must be in email format. Must be Unique.                                                             |
| gender               | Profile's gender                        | Nullable. Must be one of "male", "female", "withheld" and "other".                                              |
| mobile_phone         | Mobile phone number                     | Nullable. Must be in the correct phone format.                                                                 |
| mobile_phone_country | Country where the phone belong to.      | Required only when mobile_phone is present. Must be one of "AU", "NZ", and "US"                                 |
| home_phone           | Home phone number                       | Nullable. Must be in the correct phone format.                                                                 |
| home_phone_country   | Country where the phone belong to.      | Required only when home_phone is present. Must be one of "AU", "NZ", and "US"                                   |
| work_phone           | Work phone number                       | Nullable. Must be in the correct phone format.                                                                 |
| work_phone_country   | Country where the phone belong to.      | Required. only when work_phone is present. Must be one of "AU", "NZ", and "US"                                   |
| joined_at            | Date that the profile join Omneo.       | Required. only when joined_location_id is present. Must be in the format of "Year-Month-Date hour:minute:second" |
| joined_location_id   | The place where the profile join Omneo. | Required. only when joined_at is present. Must be in the format of "Year-Month-Date hour:minute:second"          |
| birth_day            | Profile's birth day                     | Nullable. Must be an integer. Must exist if birth_month is present.                                            |
| brith_month          | Profile's birth month                   | Nullable. Must be an integer. Must exist if birth_day is present.                                              |
| birth_year           | Profile's birth year                    | Nullable. Must be an integer. Must exist if birth_day and birth_month are present.                             |
| company              | Company name                            | Nullable. Must be an string.                                                                                     |
| occupation           | Profile's occupation                    | Nullable. Must be an string.                                                                                     |
| avatar_url           | avatar url                              | Nullable. Must be in url format.                                                                                 |
| currency_id          | The currency this profile use           | Nullable. Must be an integer. Must from currencies table.                                                      |
| tags                 | The tags attaching to this profile.     | Nullable. Array each array elements must be in "tags" format.                                                  |
| addresses            | The profile's addresses.                | Nullable. Array each array elements must be in "address" format.                                               |
### Response Attributes

| Attribute            | Description                             |
|----------------------|-----------------------------------------|
| id                   | id                                      |
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
        "points": null
      },
      "joined_location": null,
      "tags": [],
      "created_at": "2018-01-31 00:41:16",
      "updated_at": "2018-01-31 00:41:16"
    },
    {
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
  ],
  "links": {
    "first": "http://omneo-api.dev/api/v1/profiles?page=1",
    "last": "http://omneo-api.dev/api/v1/profiles?page=1",
    "prev": null,
    "next": null
  },
  "meta": {
    "current_page": 1,
    "from": 1,
    "last_page": 1,
    "path": "http://omneo-api.dev/api/v1/profiles",
    "per_page": 15,
    "to": 11,
    "total": 11
  }
}
```

This API lets you list all profiles.

### HTTP Request

`GET /api/v1/profiles`

### Request Attributes

None

### Response Attributes

| Attribute            | Description                             |
|----------------------|-----------------------------------------|
| id                   | id                                      |
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

### Request Attributes

None

### Response Attributes

| Attribute            | Description                             |
|----------------------|-----------------------------------------|
| id                   | id                                      |
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



## Update a profile

> JSON Response Example:
                
```json
{
  "title": "Mr.",
  "first_name": "Meimei",
  "last_name": "Han",
  "email": "hanmeimei@arkade.com.au",
  "gender": "female",
  "mobile_phone_country":"AU",
  "mobile_phone": null,
  "home_phone":null,
  "work_phone":null,
  "birth_day":null,
  "birth_month":null,
  "birth_year":null,
  "company":null,
  "occupation":null,
  "joined_at":null
}
```

This API lets you update a profile.

### HTTP Request

`PUT /api/v1/profiles/{profile}`

### Request Attributes

| Attribute            | Description                             | Rules                                                                                                               |
|----------------------|-----------------------------------------|---------------------------------------------------------------------------------------------------------------------|
| title                | Title such as Mr. or Miss               | Nullable. Must be a string.                                                                                           |
| first_name           | Profile's first name                    | Nullable. Must be a string.                                                                                      |
| last_name            | Profile's last name                     | Nullable. Must be a string.                                                                                       |
| email                | Profile's email                         | Nullable. Must be in email format. Must be Unique.                                                             |
| gender               | Profile's gender                        | Nullable. Must be one of "male", "female", "withheld" and "other".                                              |
| mobile_phone         | Mobile phone number                     | Nullable. Must be in the correct phone format.                                                                 |
| mobile_phone_country | Country where the phone belong to.      | Nullable only when mobile_phone is present. Must be one of "AU", "NZ", and "US"                                 |
| home_phone           | Home phone number                       | Nullable. Must be in the correct phone format.                                                                 |
| home_phone_country   | Country where the phone belong to.      | Nullable only when home_phone is present. Must be one of "AU", "NZ", and "US"                                   |
| work_phone           | Work phone number                       | Nullable. Must be in the correct phone format.                                                                 |
| work_phone_country   | Country where the phone belong to.      | Nullable. only when work_phone is present. Must be one of "AU", "NZ", and "US"                                   |
| joined_at            | Date that the profile join Omneo.       | Nullable. only when joined_location_id is present. Must be in the format of "Year-Month-Date hour:minute:second" |
| joined_location_id   | The place where the profile join Omneo. | Nullable. only when joined_at is present. Must be in the format of "Year-Month-Date hour:minute:second"          |
| birth_day            | Profile's birth day                     | Nullable. Must be an integer. Must exist if birth_month is present.                                            |
| brith_month          | Profile's birth month                   | Nullable. Must be an integer. Must exist if birth_day is present.                                              |
| birth_year           | Profile's birth year                    | Nullable. Must be an integer. Must exist if birth_day and birth_month are present.                             |
| company              | Company name                            | Nullable. Must be an string.                                                                                     |
| occupation           | Profile's occupation                    | Nullable. Must be an string.                                                                                     |
| avatar_url           | avatar url                              | Nullable. Must be in url format.                                                                                 |
| currency_id          | The currency this profile use           | Nullable. Must be an integer. Must from currencies table.                                                      |
| tags                 | The tags attaching to this profile.     | Nullable. Array each array elements must be in "tags" format.                                                  |
| addresses            | The profile's addresses.                | Nullable. Array each array elements must be in "address" format.                                               |

### Response Attributes

| Attribute            | Description                             |
|----------------------|-----------------------------------------|
| id                   | id                                      |
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



## Delete a profile

This API lets you delete a profile.

### HTTP Request

`DELETE /api/v1/profiles/{profile}`

### Request Attributes

None

### Response Attributes

None