# Contacts

Contact stores contact details like address, email, phone, etc of an individual or an organization or a user in the system.

## Get All Contacts

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = ''
headers = {}
conn.request("GET", "/contact", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method GET \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/crm-plugin/contact'
```

```javascript
var requestOptions = {
  method: "GET",
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/contact", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "NewTech",
    "phone": null,
    "phone_other": null,
    "email": null,
    "email_other": null,
    "address_1": null,
    "address_2": null,
    "city": null,
    "pincode": null,
    "contact_type": "organization",
    "organization": {
      "id": 1,
      "name": "NewTech",
      "contact": 156,
      "created_at": "2020-06-04T11:15:32.751Z",
      "updated_at": "2020-06-04T11:15:33.054Z"
    },
    "country": null,
    "state": null,
    "district": null,
    "individual": null,
    "user": null,
    "created_at": "2020-06-04T11:15:32.945Z",
    "updated_at": "2020-06-04T11:15:33.077Z",
    "villages": [],
    "activityassignees": [],
    "contacttags": []
  }
]
```

### Description

This method returns all the contact details by default or specific contact details with certain conditions based on the filters passed to the method

### HTTP Request

`GET http://localhost:1337/crm-plugin/contacts`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                               |
| --------- | ----------------------------------------- |
| Filters   | Column attributes in the table (Optional) |

## Get a Specific Contact

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = ''
headers = {}
conn.request("GET", "/contact/1", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method GET \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/crm-plugin/contact/1'
```

```javascript
var requestOptions = {
  method: "GET",
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/contact/1", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "name": "NewTech",
  "phone": null,
  "phone_other": null,
  "email": null,
  "email_other": null,
  "address_1": null,
  "address_2": null,
  "city": null,
  "pincode": null,
  "contact_type": "organization",
  "organization": {
    "id": 1,
    "name": "NewTech",
    "contact": 156,
    "created_at": "2020-06-04T11:15:32.751Z",
    "updated_at": "2020-06-04T11:15:33.054Z"
  },
  "country": null,
  "state": null,
  "district": null,
  "individual": null,
  "user": null,
  "created_at": "2020-06-04T11:15:32.945Z",
  "updated_at": "2020-06-04T11:15:33.077Z",
  "villages": [],
  "activityassignees": [],
  "contacttags": []
}
```

### Description

This method returns specific contact details by id.

### HTTP Request

`GET http://localhost:1337/crm-plugin/contact/<ID>`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                       |
| --------- | --------------------------------- |
| ID        | The ID of the contact to retrieve |

## Save a Specific Contact

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = " { \"name\": \"Tech Providers\",\r\n  \"contact_type\": \"organization\"\r\n \t\r\n }"
headers = {}
conn.request("POST", "/contact/", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method POST \
  --timeout=0 \
  --header '' \
  --body-data ' { "name": "Tech Providers",
  "contact_type": "organization"

 }' \
   'http://localhost:1337/crm-plugin/contact/'
```

```javascript
var raw = " { \"name\": \"Tech Providers\",
\n  \"contact_type\": \"organization\"
\n
\n }";

var requestOptions = {
  method: 'POST',
  body: raw,
  redirect: 'follow'
};

fetch("http://localhost:1337/crm-plugin/contact/", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Tech Providers",
  "phone": null,
  "phone_other": null,
  "email": null,
  "email_other": null,
  "address_1": null,
  "address_2": null,
  "city": null,
  "pincode": null,
  "contact_type": "organization",
  "organization": {
    "id": 2,
    "name": "Tech Providers",
    "contact": 2,
    "created_at": "2020-06-04T11:21:35.951Z",
    "updated_at": "2020-06-04T11:21:36.205Z"
  },
  "country": null,
  "state": null,
  "district": null,
  "individual": null,
  "user": null,
  "created_at": "2020-06-04T11:21:36.122Z",
  "updated_at": "2020-06-04T11:21:36.223Z",
  "villages": [],
  "activityassignees": [],
  "contacttags": []
}
```

### Description

This method creates a contact with the attribute parameters passed to this method by default. It returns details of created contact

### HTTP Request

`POST http://localhost:1337/crm-plugin/contact/<ID>`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameters        | Description                                                      |
| ----------------- | ---------------------------------------------------------------- |
| name              | The name of the individual or organization or user in the system |
| contact_type      | Type of contact (values : organization/individual)               |
| Column attributes | Optional                                                         |

## Update a Specific Contact

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = " { \r\n\t\"name\": \"Tech Providers --test\",\r\n\t\"contact_type\": \"organization\"\r\n }"
headers = {}
conn.request("PUT", "/contact/2", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method PUT \
  --timeout=0 \
  --header '' \
  --body-data ' {
	"name": "Tech Providers --test",
	"contact_type": "organization"
 }' \
   'http://localhost:1337/crm-plugin/contact/2'
```

```javascript
var raw = " {
\n	\"name\": \"Tech Providers --test\",
\n	\"contact_type\": \"organization\"
\n }";

var requestOptions = {
  method: 'PUT',
  body: raw,
  redirect: 'follow'
};

fetch("http://localhost:1337/crm-plugin/contact/2", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```

The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Tech Providers --test",
  "phone": null,
  "phone_other": null,
  "email": null,
  "email_other": null,
  "address_1": null,
  "address_2": null,
  "city": null,
  "pincode": null,
  "contact_type": "organization",
  "organization": {
    "id": 2,
    "name": "Tech Providers --test",
    "contact": 2,
    "created_at": "2020-06-04T11:21:35.951Z",
    "updated_at": "2020-06-04T11:24:49.450Z"
  },
  "country": null,
  "state": null,
  "district": null,
  "individual": null,
  "user": null,
  "created_at": "2020-06-04T11:21:36.122Z",
  "updated_at": "2020-06-04T11:24:49.653Z",
  "villages": [],
  "activityassignees": [],
  "contacttags": []
}
```

### Description

This method updates the specific contact by id with attribute parameters passed to it.It returns details of updated contact

### HTTP Request

`UPDATE http://localhost:1337/crm-plugin/contact/<ID>`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                     |
| --------- | ------------------------------- |
| ID        | The ID of the contact to update |

## Delete a Specific Contact

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = ''
headers = {}
conn.request("DELETE", "/contact/1", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method DELETE \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/crm-plugin/contact/1'
```

```javascript
var raw = "";

var requestOptions = {
  method: "DELETE",
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/contact/1", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "name": "NewTech",
  "phone": null,
  "phone_other": null,
  "email": null,
  "email_other": null,
  "address_1": null,
  "address_2": null,
  "city": null,
  "pincode": null,
  "contact_type": "organization",
  "organization": {
    "id": 1,
    "name": "NewTech",
    "contact": 156,
    "created_at": "2020-06-04T11:15:32.751Z",
    "updated_at": "2020-06-04T11:15:33.054Z"
  },
  "country": null,
  "state": null,
  "district": null,
  "individual": null,
  "user": null,
  "created_at": "2020-06-04T11:15:32.945Z",
  "updated_at": "2020-06-04T11:15:33.077Z",
  "villages": [],
  "activityassignees": [],
  "contacttags": []
}
```

### Description

This method deletes specific contact by id and returns details of deleted contact.

### HTTP Request

`DELETE http://localhost:1337/crm-plugin/contact/<ID>`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                     |
| --------- | ------------------------------- |
| ID        | The ID of the contact to delete |
