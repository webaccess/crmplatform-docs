# Forgot Password/Reset Password/Validate Email Api

## Forgot Password

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/auth")
payload = "{\n\t\"code\": \"privateCode\",\n    \"password\": \"vishal@123\",\n    \"passwordConfirmation\": \"vishal@123\"\n}"
headers = {}
conn.request("POST", "/reset-password", payload, headers)
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
	"code": "privateCode",
    "password": "vishal@123",
    "passwordConfirmation": "vishal@123"
}' \
   'http://localhost:1337/auth/reset-password'
```

```javascript
var raw =
  '{\n	"code": "privateCode",\n    "password": "vishal@123",\n    "passwordConfirmation": "vishal@123"\n}';

var requestOptions = {
  method: "POST",
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/auth/reset-password", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "username": "ankita.shinde",
    "email": "demo@gmail.com",
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
]
```

### Description

### HTTP Request

`GET http://localhost:1337/auth/reset-password`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter            | Description               |
| -------------------- | ------------------------- |
| privateCode          | Verification code         |
| password             | New password              |
| passwordConfirmation | New password is reentered |

## Email Validation Api

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/auth")
payload = "{\n\t \"email\": \"vishal.tambe@webaccessglobal.com\"\n}"
headers = {}
conn.request("POST", "/send-email-confirmation", payload, headers)
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
	 "email": "vishal.tambe@webaccessglobal.com"
}' \
   'http://localhost:1337/auth/send-email-confirmation'
```

```javascript
var raw = '{\n	 "email": "vishal.tambe@webaccessglobal.com"\n}';

var requestOptions = {
  method: "POST",
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/auth/send-email-confirmation", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json

```

### Description

### HTTP Request

`GET http://localhost:1337/auth/send-email-confirmation`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description       |
| --------- | ----------------- |
| email     | Email of the user |

## Forgot Password Email Api

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/auth")
payload = "{\n\t\"email\":\"vishal.tambe@webaccessglobal.com\"\n\t\n}"
headers = {}
conn.request("POST", "/forgot-password", payload, headers)
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
	"email":"vishal.tambe@webaccessglobal.com"

}' \
   'http://localhost:1337/auth/forgot-password'
```

```javascript
var raw = '{\n	"email":"vishal.tambe@webaccessglobal.com"\n	\n}';

var requestOptions = {
  method: "POST",
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/auth/forgot-password", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json

```

### Description

### HTTP Request

`POST http://localhost:1337/auth/forgot-password`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### Request Parameters

| Parameter | Description       |
| --------- | ----------------- |
| email     | Email of the user |
