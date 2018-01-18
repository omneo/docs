---
title: Omneo Loyalty API

language_tabs: # must be one of https://git.io/vQNgJ
  - javascript

toc_footers:
  - Get In touch <a href='mailto:support@omneo.io'>support@omneo.io</a>
  - <a href='https://omneo.io'>Omneo.io</a>

includes:
  - errors

search: true
---

# Omneo Loyalty Engine
Welcome to the Omneo API documentation - here you can learn about all API calls and methods, what they are for, and how they are used.

## Media Types
Where applicable this API uses the [JSON](json.md) media-type to represent resources states and affordances.

Requests with a message-body are using plain JSON to set or update resource states.

## Error States
The common [HTTP Response Status Codes](https://github.com/for-GET/know-your-http-well/blob/master/status-codes.md) are used.

## Support

If you have any questions about this API specification, please contact Omneo Support by sending an email to [support@omneo.io](mailto:support@omneo.io?subject=Omneo+Loyalty+API+V2+Support)

# Authentication
```javascript
const omneo = require('omneo');

let api = omneo.authorize('meowmeowmeow');
```

**Omneo Loyalty Engine** uses OAuth Authorization using the client credentials grant type. Tokens are created by Omneo and provided to third parties. After you have acquired your token you can use it to access other resources within token's scope.

Information about obtaining an access token can be found in the **Authorization** endpoint documentation.

Omneo expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: Bearer meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

## Scopes
Each endpoint has been scoped to allow granular access control to each resource. 

| Resource                | Scope                         | Action |
|-------------------------|-------------------------------|--------|
| Achievements            | read-achievements             | Read   |
| Achievements            | write-achievements            | Write  |
| Achievement Definitions | read-achievement_definitions  | Read   |
| Achievement Definitions | write-achievement_definitions | Write  |
| Benefits                | read-benefits                 | Read   |
| Benefits                | write-benefits                | Write  |
| Benefit Definitions     | read-benefit_definitions      | Read   |
| Benefit Definitions     | write-benefit_definitions     | Write  |
| Benefit Redemptions     | write-benefit_redemptions     | Write  |
| Cards                   | read-cards                    | Read   |
| Cards                   | write-cards                   | Write  |
| Currencies              | read-currencies               | Read   |
| Currencies              | write-currencies              | Write  |
| Members                 | read-members                  | Read   |
| Members                 | write-members                 | Write  |
| Member Tiers            | read-member-tiers             | Read   |
| Member Tiers            | write-member-tiers            | Write  |
| Points                  | read-points                   | Read   |
| Points                  | write-points                  | Write  |
| Points Balance          | read-points                   | Read   |
| Points Definitions      | read-points_definitions       | Read   |
| Points Definitions      | write-points_definitions      | Write  |
| Points Types            | read-points_types             | Read   |
| Points Types            | write-points_types            | Write  |
| Products                | read-products                 | Read   |
| Products                | write-products                | Write  |
| Redeem                  | write-reward_redemptions      | Write  |
| Redemptions             | read-reward_redemptions       | Read   |
| Rewards                 | read-reward                   | Read   |
| Rewards                 | write-reward                  | Read   |
| Staff                   | read-staff                    | Read   |
| Staff                   | write-staff                   | Write  |
| Stores                  | read-store                    | Read   |
| Stores                  | write-store                   | Write  |
| Transactions            | read-transactions             | Read   |
| Transactions            | write-transactions            | Write  |





# Achievements

## Get achievement definitions

```javascript
import Omneo from 'Omneo';
let achievementDefinitions = Omneo.getAchievementDefinitions('achievementDefinitions');
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'omneo'

api = omneo::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import omneo

api = omneo.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const omneo = require('omneo');

let api = omneo.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```ruby
require 'omneo'

api = omneo::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import omneo

api = omneo.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
const omneo = require('omneo');

let api = omneo.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete

