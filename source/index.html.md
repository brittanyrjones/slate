---
title: API Reference

language_tabs: # must be one of https://github.com/rouge-ruby/rouge/wiki/List-of-supported-languages-and-lexers
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the Data Resource API
---

# Introduction

Welcome to the Data Resource API! You can use our API to access Data Resource API endpoints.

We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/slatedocs/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Authentication

> To authorize, use this code:

```ruby
require 'resource'

api = Data Resource::APIClient.authorize!('123')
```

```python
import resource

api = resource.authorize('123')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here" \
  -H "Authorization: 123"
```

```javascript
const resource = require('resource');

let api = resource.authorize('123');
```

> Make sure to replace `123` with your API key.

Data Resource uses API keys to allow access to the API. You can register a new Data Resource API key at our [developer portal](http://example.com/developers).

Data Resource expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: 123`

<aside class="notice">
You must replace <code>123</code> with your personal API key.
</aside>

# Resources

## Get All Resources

```ruby
require 'resource'

api = Data Resource::APIClient.authorize!('123')
api.resources.get
```

```python
import resource

api = resource.authorize('123')
api.resources.get()
```

```shell
curl "http://example.com/api/resources" \
  -H "Authorization: 123"
```

```javascript
const resource = require('resource');

let api = resource.authorize('123');
let resources = api.resources.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "postgres-1",
    "resource_kind": "postgresql",
    "plan": "standard-0",
    "version": 15
  },
  {
    "id": 2,
    "name": "postgres-2",
    "resource_kind": "postgresql",
    "plan": "standard-0",
    "version": 15
  }
]
```

This endpoint retrieves all resources.

### HTTP Request

`GET http://example.com/api/resources`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_something | false | If set to true, the result will also include something.

## Get a Specific Resource

```ruby
require 'resource'

api = Data Resource::APIClient.authorize!('123')
api.resources.get(2)
```

```python
import resource

api = resource.authorize('123')
api.resources.get(2)
```

```shell
curl "http://example.com/api/resources/2" \
  -H "Authorization: 123"
```

```javascript
const resource = require('resource');

let api = resource.authorize('123');
let max = api.resources.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "postgres-3",
  "resource_kind": "postgresql",
  "plan": "standard-0",
  "version": 15
}
```

This endpoint retrieves a specific resource.

### HTTP Request

`GET http://example.com/resources/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the resource to retrieve

## Delete a Specific Resource

```ruby
require 'resource'

api = Data Resource::APIClient.authorize!('123')
api.resources.delete(2)
```

```python
import resource

api = resource.authorize('123')
api.resources.delete(2)
```

```shell
curl "http://example.com/api/resources/2" \
  -X DELETE \
  -H "Authorization: 123"
```

```javascript
const resource = require('resource');

let api = resource.authorize('123');
let max = api.resources.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific resource.

### HTTP Request

`DELETE http://example.com/resources/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the resource to delete

