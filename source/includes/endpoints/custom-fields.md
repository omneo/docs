## Custom Fields

This API allows you to create, read, update and delete custom fields.

### Custom Field Properties

| Attribute               | Description                                 |
|-------------------------|---------------------------------------------|
| handle                  | The custom field handle                     |
| name                    | The display name of the custom field        |
| namespace               | The custom field namespace                  |
| value                   | The custom field value                      |
| type                    | The custom field type (e.g. string)         |

### Available Types

| Type               | Example                                 |
|-------------------------|---------------------------------------------|
| string | "1123-2314-221-4421" |
| float | 1.245 |
| integer | 100 | 
| boolean | true |

### Available Resource Endpoints

For a list of resources that support custom fields, please see below.

| Resource                | Endpoint                                            |
|-------------------------|-----------------------------------------------------|
| site                    | `api/v1/site/custom-fields`                         |
| product                 | `api/v1/products/{product}/custom-fields`           |
| transaction             | `api/v1/transactions/{transaction}/custom-fields`   |
| profile                 | `api/v1/profiles/{profile}/custom-fields`           |




### Create a custom field for a resource

> JSON Response Example:
                
```json
{
    "data": {
        "name": "Acme Plugin Last Sync Date",
        "handle": "last-synced",
        "namespace": "acme-plugin",
        "type": "string",
        "value": "2018-01-01 11:11:22",
        "created_at": "2018-02-01 04:58:41",
        "updated_at": "2018-02-01 03:52:31"
    }
}
```

This API allows you to create custom fields.

#### HTTP Request

`POST /api/v1/{resource}/{resourceId}/custom-fields`

<aside class="notice">
For a list of available resource endpoints, please see the [Available Resource Endpoints](#available-resource-endpoints) table.
</aside>

<aside class="notice">
Custom fields are unique to their owning resource ID, namespace and handle.
</aside>

#### Request Properties

| Property               | Type                                            |    
|-------------------------|-------------------------------------------------|
| name                    | `nullable`, `string` |
| handle                  | `required`, `unique:resourceId, namespace` |
| namespace               | `required`, `string`, |
| type                    | `string`, `in:string,integer,float,boolean` |
| value                   | `nullable`, `string` |








### List a resources custom fields

> JSON Response Example:
                
```json
{
    "data": [
        {
            "name": "ERP Resource ID",
            "handle": "resource-id",
            "namespace": "erp",
            "type": "string",
            "value": "1221-3322-3441-4212",
            "created_at": "2018-02-01 04:58:41",
            "updated_at": "2018-02-01 03:52:31"
        },
        {
            "name": "Ecommerce Last Synced",
            "handle": "last-synced",
            "namespace": "ecommerce",
            "type": "string",
            "value": "2018-02-01 03:52:31",
            "created_at": "2018-02-01 04:58:41",
            "updated_at": "2018-02-01 03:52:31"
        }
    ]
}
```

This API lets you list all custom fields for a given resource.

#### HTTP Request

`GET /api/v1/{resource}/{resourceId}/custom-fields`







### Retrieve a resource custom field

> JSON Response Example:
                
```json
{
    "data": {
        "name": "ERP Resource ID",
        "handle": "resource-id",
        "namespace": "erp",
        "type": "string",
        "value": "1221-3322-3441-4212",
        "created_at": "2018-02-01 04:58:41",
        "updated_at": "2018-02-01 03:52:31"
    }
}
```

This API lets you retrieve a single custom field for a given resource.

#### HTTP Request

`GET /api/v1/{resource}/{resourceId}/{namespace}:{handle}`

<aside class="notice">
Custom fields are accessed by their unique `namespace:handle` combination. e.g. `erp:resource-id`
</aside>







### Update a resources custom field

> JSON Response Example:
                
```json
{
    "data": {
        "name": "ERP Resource ID",
        "handle": "resource-id",
        "namespace": "erp",
        "type": "string",
        "value": "1221-3322-3441-1111",
        "created_at": "2018-02-01 04:58:41",
        "updated_at": "2018-03-01 06:52:44"
    }
}
```

This API allows you to update a given resources custom field.

#### HTTP Request

`PUT /api/v1/{resource}/{resourceId}/{namespace}:{handle}`

#### Request Properties

| Property               | Type                                            |    
|-------------------------|-------------------------------------------------|
| name                    | `sometimes`, `nullable`, `string` |
| handle                  | `sometimes`, `required`, `unique:resourceId, namespace` |
| namespace               | `sometimes`, `required`, `string`, |
| type                    | `sometimes`, `string`, `in:string,integer,float,boolean` |
| value                   | `nullable`, `string` |









### Delete a resources custom field

This API allows you to delete a custom field for a given resource.

#### HTTP Request

`DELETE /api/v1/{resource}/{resourceId}/{namespace}:{handle}`