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
    "id": 2,
    "name": "Gujarat",
    "is_active": true,
    "abbreviation": null,
    "identifier": null,
    "country": null,
    "created_at": "2020-05-13T14:36:12.354Z",
    "updated_at": "2020-05-13T14:36:12.354Z",
    "districts": [],
    "contacts": []
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

Optional

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
  "id": 2,
  "name": "Gujarat",
  "is_active": true,
  "abbreviation": null,
  "identifier": null,
  "country": null,
  "created_at": "2020-05-13T14:36:12.354Z",
  "updated_at": "2020-05-13T14:36:12.354Z",
  "districts": [],
  "contacts": []
}
```

### Description

This method returns specific contact details by id.

### HTTP Request

`GET http://localhost:1337/crm-plugin/contacts/<ID>`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                       |
| --------- | --------------------------------- |
| ID        | The ID of the country to retrieve |

## Count All/Specific Contacts

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("")
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
   ''
```

```javascript
var requestOptions = {
  method: "GET",
  redirect: "follow",
};

fetch("", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
2
```

### Description

This method returns total number of data items present in a contacts.

### HTTP Request

`GET http://localhost:1337/crm-plugin/contacts/count`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

Optional

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
  "id": 4,
  "name": "maharashtra",
  "is_active": true,
  "abbreviation": null,
  "identifier": null,
  "country": null,
  "created_at": "2020-05-22T15:16:49.908Z",
  "updated_at": "2020-05-22T15:16:49.908Z",
  "districts": [],
  "contacts": []
}
```

### Description

This method creates a contact with the attribute parameters passed to this method by default. It returns details of created contact

### HTTP Request

`POST http://localhost:1337/crm-plugin/contacts/<ID>`

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

## Delete a Specific Contact

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = ''
headers = {}
conn.request("DELETE", "/contact/2", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method DELETE \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/crm-plugin/contact/2'
```

```javascript
var raw = "";

var requestOptions = {
  method: "DELETE",
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/contact/2", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Gujarat",
  "is_active": true,
  "abbreviation": null,
  "identifier": null,
  "country": null,
  "created_at": "2020-05-13T14:36:12.354Z",
  "updated_at": "2020-05-13T14:36:12.354Z",
  "districts": [],
  "contacts": []
}
```

### Description

This method deletes specific contact by id and returns details of deleted contact.

### HTTP Request

`DELETE http://localhost:1337/crm-plugin/contacts/<ID>`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                     |
| --------- | ------------------------------- |
| ID        | The ID of the country to delete |
