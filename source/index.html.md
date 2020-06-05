---
title: CRM Platform API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - javascript
  - python
  - shell

toc_footers:
  - <a href='https://github.com/webaccess/crmplatform' target='_blank'>Documentation by <br/>CRM Platform Developers</a>

includes:
  - users
  - password
  - activitytypes
  - activities
  - contacts
  - tags
  - countries
  - states
  - districts
  - villages
  - errors

search: true
---

# Introduction

Welcome to the CRM Platform API Documentation! You can use our APIs to access different modules, which can get information about states,districts, countries etc. in our database.

We have language bindings in Shell, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

> To get an access token, use this code:

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/auth")
payload = "{\n\t\"identifier\":\"demo\",\n\t\"password\":\"demo123\"\n}"
headers = {
  'Content-Type': 'application/json'
}
conn.request("POST", "/local", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method POST \
  --timeout=0 \
  --header 'Content-Type: application/json' \
  --body-data '{
	"identifier":"demo",
	"password":"demo123"
}' \
   'http://localhost:1337/auth/local'
```

```javascript
var myHeaders = new Headers();
myHeaders.append("Content-Type", "application/json");

var raw = JSON.stringify({ identifier: "demo", password: "demo123" });

var requestOptions = {
  method: "POST",
  headers: myHeaders,
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/auth/local", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
{
  "jwt": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiaWF0IjoxNTkxMzQyNjA3LCJleHAiOjE1OTM5MzQ2MDd9.5a7Z0qUB7nI8y1CBzGesJcxH4q9mU00S6CbSz1cbwuI",
  "user": {
    "id": 1,
    "username": "demo",
    "email": "demo@test.com",
    "provider": "local",
    "confirmed": true,
    "blocked": false,
    "role": {
      "id": 1,
      "name": "Authenticated",
      "description": "Default role given to authenticated user.",
      "type": "authenticated"
    },
    "created_at": "2020-05-18T07:15:54.051Z",
    "updated_at": "2020-05-18T15:32:11.564Z"
  }
}
```

You can get your username and password from the CRM Platform UI. With it you can request an API access token.

CRM Platform expects for the access token to be included in all API requests to the server in a header that looks like the following:

Authorization: Bearer API_TOKEN

<aside class="notice">
You must replace token with your personal access token.
</aside>
