# Activitytypes

Activitytype stores details about basic types of activities that are stored in activity content type

## Get All Activitytypes

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = ''
headers = {}
conn.request("GET", "/activitytypes", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method GET \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/crm-plugin/activitytypes'
```

```javascript
var requestOptions = {
  method: "GET",
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/activitytypes", requestOptions)
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
    "villages": []
  }
]
```

### Description

This method returns all the activitytype details by default or specific activitytype details with certain conditions based on the filters passed to the method

### HTTP Request

`GET http://localhost:1337/crm-plugin/villages`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

Optional

## Get a Specific Activitytype

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = ''
headers = {}
conn.request("GET", "/activitytypes/1", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method GET \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/crm-plugin/activitytypes/1'
```

```javascript
var requestOptions = {
  method: "GET",
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/activitytypes/1", requestOptions)
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
  "villages": []
}
```

### Description

This method returns specific activitytype details by id.

### HTTP Request

`GET http://localhost:1337/crm-plugin/villages/<ID>`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                       |
| --------- | --------------------------------- |
| ID        | The ID of the country to retrieve |

## Save a Specific Activitytype

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = "{\n\t\"name\": \"piggery\",\n    \"is_active\": \"true\"\n}"
headers = {}
conn.request("POST", "/activitytypes", payload, headers)
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
	"name": "piggery",
    "is_active": "true"
}' \
   'http://localhost:1337/crm-plugin/activitytypes'
```

```javascript
var raw = '{\n	"name": "piggery",\n    "is_active": "true"\n}';

var requestOptions = {
  method: "POST",
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/activitytypes", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
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
  "villages": []
}
```

### Description

This method creates an activitytype with the attribute parameters passed to this method by default. It returns details of created activitytype

### HTTP Request

`POST http://localhost:1337/crm-plugin/villages/<ID>`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                     |
| --------- | ------------------------------- |
| ID        | The ID of the country to delete |

## Update a Activitytype

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = "{\n\t\"name\": \"fishery -- test\",\n    \"is_active\": \"true\"\n}"
headers = {}
conn.request("PUT", "/activitytypes/3", payload, headers)
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
	"name": "fishery -- test",
    "is_active": "true"
}' \
   'http://localhost:1337/crm-plugin/activitytypes/3'
```

```javascript
var raw = '{\n	"name": "fishery -- test",\n    "is_active": "true"\n}';

var requestOptions = {
  method: "PUT",
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/activitytypes/3", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

### Description

This method updates the specific activitytype by id with attribute parameters passed to it.It returns details of updated activitytype

### HTTP Request

`UPDATE http://localhost:1337/crm-plugin/activitytypes/<ID>`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                          |
| --------- | ------------------------------------ |
| ID        | The ID of the activitytype to update |

## Delete a Specific Activitytype

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = ''
headers = {}
conn.request("DELETE", "/activitytypes/3", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method DELETE \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/crm-plugin/activitytypes/3'
```

```javascript
var raw = "";

var requestOptions = {
  method: "DELETE",
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/activitytypes/3", requestOptions)
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
  "villages": []
}
```

### Description

This method deletes specific activitytype by id and returns details of deleted activitytype

### HTTP Request

`DELETE http://localhost:1337/crm-plugin/villages/<ID>`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                     |
| --------- | ------------------------------- |
| ID        | The ID of the country to delete |
