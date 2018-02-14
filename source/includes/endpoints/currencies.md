## Currencies

This API allows you to create, read, update and delete currencies.

### Currency Attributes

| Attribute | Description                                  | 
|-----------|----------------------------------------------|
| from      | Currency code that the currency convert from  |
| to        | Currency code that the currency convert to    |
| rate      | The convert rate                             |

* The pair of [from, to] are unique.
### Create a currency

> JSON Request Example:

```json
{
  "from":"AUD",
  "to":"NZD",
  "rate":1.08
}
```

> JSON Response Example:
                
```json
{
    "data": {
       "from":"AU",
       "to":"NZ",
       "rate":1.08
    }
}
```




This API allows you to create a currency.

#### HTTP Request

`POST /api/v1/currencies`

#### Request Attributes
| Attribute | Type                 |
|-----------|----------------------|
| from      | `required` `string`  |
| to        | `required` `string`  |
| rate      | `required` `decimal` |



### List all currencies

> JSON Response Example:
                
```json
{
    "data": [
        {
           "from":"AU",
           "to":"NZ",
           "rate":1.08
        },
        {
           "from":"NZ",
           "to":"AU",
           "rate":0.93
        }
    ],
    "links": {
        "first": "http://omneo-api.dev/api/v1/currencies?page=1",
        "last": "http://omneo-api.dev/api/v1/currencies?page=1",
        "prev": null,
        "next": null
    },
    "meta": {
        "current_page": 1,
        "from": 1,
        "last_page": 1,
        "path": "http://omneo-api.dev/api/v1/currencies",
        "per_page": 15,
        "to": 9,
        "total": 9
    }
}
```

This API lets you list all currencies.

#### HTTP Request

`GET /api/v1/currencies`



### Retrieve a currency

> JSON Response Example:
                
```json
{
    "data": {
        "from":"NZ",
        "to":"AU",
        "rate":0.93
    }
}
```

This API lets you retrieve a single currency.

#### HTTP Request

`GET /api/v1/currencies/{currency}`



### Update a currency

> JSON Request Example:
                
```json
{
    "from":"NZ",
    "to":"AU",
    "rate":0.90
}
```

> JSON Response Example:
                
```json
{
    "data": {
            "from":"NZ",
            "to":"AU",
            "rate":0.90
    }
}
```



This API lets you update a currency.

#### HTTP Request

`PUT /api/v1/currencies/{currency}`

#### Request Attributes
| Attribute | Type                             |
|-----------|----------------------------------|
| from      | `sometimes` `required`           |
| to        | `required` `sometimes`           |
| rate      | `sometimes` `required` `decimal` |


### Delete a currency

This API lets you delete a currency.

#### HTTP Request

`DELETE /api/v1/currencies/{currency}`

