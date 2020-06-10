# Users

User stores details such as user's name,email and other information.

## Get All Users

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/users")
payload = ''
headers = {}
conn.request("GET", "", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method GET \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/users'
```

```javascript
var requestOptions = {
  method: "GET",
  redirect: "follow",
};

fetch("http://localhost:1337/users", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "username": "demoUser",
    "email": "demouser@example.com",
    "provider": "local",
    "confirmed": true,
    "blocked": false,
    "role": {
      "id": 1,
      "name": "Authenticated",
      "description": "Default role given to authenticated user.",
      "type": "authenticated"
    },
    "created_at": "2020-05-18T06:25:24.731Z",
    "updated_at": "2020-05-28T12:43:51.512Z"
  },
  [
    {
      "id": 2,
      "username": "demoUser2",
      "email": "demo@example.com",
      "provider": "local",
      "confirmed": true,
      "blocked": false,
      "role": {
        "id": 1,
        "name": "Authenticated",
        "description": "Default role given to authenticated user.",
        "type": "authenticated"
      },
      "created_at": "2020-05-18T06:25:24.731Z",
      "updated_at": "2020-06-09T05:35:32.118Z"
    },
    {...}
  ]
]
```

### Description

This method returns all the user details by default or specific user details with certain conditions based on the filters passed to the method

### HTTP Request

`GET http://localhost:1337/users`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                               |
| --------- | ----------------------------------------- |
| Filters   | Column attributes in the table (Optional) |

## Get a Specific User

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/users")
payload = ''
headers = {}
conn.request("GET", "/1", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method GET \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/users/1'
```

```javascript
var requestOptions = {
  method: "GET",
  redirect: "follow",
};

fetch("http://localhost:1337/users/1", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "username": "demoUser",
  "email": "demouser@example.com",
  "provider": "local",
  "confirmed": true,
  "blocked": false,
  "role": {
    "id": 1,
    "name": "Authenticated",
    "description": "Default role given to authenticated user.",
    "type": "authenticated"
  },
  "created_at": "2020-05-18T06:25:24.731Z",
  "updated_at": "2020-05-28T12:43:51.512Z"
}
```

### Description

This method returns specific user details by id.

### HTTP Request

`GET http://localhost:1337/users/<ID>`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                    |
| --------- | ------------------------------ |
| ID        | The ID of the user to retrieve |

## Save a Specific User

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/users")
payload = "{\n\t \"username\": \"testuser\",\n        \"email\": \"testUser@example.com\",\n        \"provider\": \"local\",\n        \"confirmed\": true,\n        \"password\":\"password\",\n        \"blocked\": false\n}"
headers = {}
conn.request("POST", "", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method POST \
  --timeout=0 \
  --header '' \
  --body-data '{
	 "username": "testUser",
        "email": "testuser@example.com",
        "provider": "local",
        "confirmed": true,
        "password":"password",
        "blocked": false
}' \
   'http://localhost:1337/users'
```

```javascript
var raw =
  '{\n	 "username": "testUser",\n        "email": "testuser@example.com",\n        "provider": "local",\n        "confirmed": true,\n        "password":"password",\n        "blocked": false\n}';

var requestOptions = {
  method: "POST",
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/users", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
{
  "id": 3,
  "username": "testUser",
  "email": "testuser@example.com",
  "provider": "local",
  "password": "$2a$10$kkQwn0/fI0VOK3iYRkIo.eSYuOJuqGgL0TZFwOABOOZ5yKNLqwwnq",
  "resetPasswordToken": null,
  "confirmed": true,
  "blocked": false,
  "role": {
    "id": 1,
    "name": "Authenticated",
    "description": "Default role given to authenticated user.",
    "type": "authenticated"
  },
  "created_at": "2020-06-05T11:12:53.752Z",
  "updated_at": "2020-06-05T11:12:53.938Z"
}
```

### Description

This method creates an user with the attribute parameters passed to this method by default. It returns details of created user

### HTTP Request

`POST http://localhost:1337/users`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### Request Parameters

| Parameter         | Description                               |
| ----------------- | ----------------------------------------- |
| name              | The name of the user                      |
| password          | Password of the user                      |
| email             | Email of the user                         |
| Column attributes | Column attributes in the table (Optional) |

## Update a Specific User

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/users")
payload = "{\n\t\"username\": \"testuser2\"\n}"
headers = {}
conn.request("PUT", "/3", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method PUT \
  --timeout=0 \
  --header '' \
  --body-data '{
	"username": "testuser2"
}' \
   'http://localhost:1337/users/3'
```

```javascript
var raw = '{\n	"username": "testuser2"\n}';

var requestOptions = {
  method: "PUT",
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/users/3", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

The above command returns JSON structured like this:

```json
{
  "id": 3,
  "username": "testuser2",
  "email": "testuser@example.com",
  "provider": "local",
  "password": "$2a$10$kkQwn0/fI0VOK3iYRkIo.eSYuOJuqGgL0TZFwOABOOZ5yKNLqwwnq",
  "resetPasswordToken": null,
  "confirmed": true,
  "blocked": false,
  "role": {
    "id": 1,
    "name": "Authenticated",
    "description": "Default role given to authenticated user.",
    "type": "authenticated"
  },
  "created_at": "2020-06-05T11:12:53.752Z",
  "updated_at": "2020-06-05T11:14:36.566Z"
}
```

### Description

This method updates the specific user by id with attribute parameters passed to it.It returns details of updated user

### HTTP Request

`UPDATE http://localhost:1337/users/<ID>`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                  |
| --------- | ---------------------------- |
| ID        | The ID of the user to update |

### Request Parameters

| Parameter         | Description                    |
| ----------------- | ------------------------------ |
| Column attributes | Column attributes in the table |

## Delete a Specific User

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/users")
payload = ''
headers = {}
conn.request("DELETE", "/3", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method DELETE \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/users/3'
```

```javascript
var raw = "";

var requestOptions = {
  method: "DELETE",
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/users/3", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
{
  "id": 3,
  "username": "testuser2",
  "email": "testuser@example.com",
  "provider": "local",
  "password": "$2a$10$kkQwn0/fI0VOK3iYRkIo.eSYuOJuqGgL0TZFwOABOOZ5yKNLqwwnq",
  "resetPasswordToken": null,
  "confirmed": true,
  "blocked": false,
  "role": {
    "id": 1,
    "name": "Authenticated",
    "description": "Default role given to authenticated user.",
    "type": "authenticated"
  },
  "created_at": "2020-06-05T11:12:53.752Z",
  "updated_at": "2020-06-05T11:14:36.566Z"
}
```

### Description

This method deletes specific user by id and returns details of deleted user.

### HTTP Request

`DELETE http://localhost:1337/users/<ID>`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                  |
| --------- | ---------------------------- |
| ID        | The ID of the user to delete |
