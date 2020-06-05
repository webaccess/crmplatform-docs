# Forgot Password/Reset Password/Validate Email Api

User can reset password via this methods

## Reset Password Api

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

### Description

New password with verification code received by user is sent which resets the user password

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
| passwordConfirmation | New password is confirmed |

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

### Description

This method is used to validate user's email id by sending verification code to it.

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

### Description

This method sends message to the entered email address containing a link to reset password.

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
