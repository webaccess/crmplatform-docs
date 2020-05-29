---
title: CRM Platform API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - javascript
  - python
  - shell

toc_footers:
  - <a href='https://github.com/slatedocs/slate'>Documentation by <br/>CRM Platform Developers</a>

includes:
  - states
  - errors

search: true
---

# Introduction

Welcome to the CRM Platform API Documentation! You can use our APIs to access different modules, which can get information about states,districts, countries etc. in our database.

We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require("kittn");

let api = kittn.authorize("meowmeowmeow");
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>
