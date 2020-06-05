# Activity types

Activitytype stores details about basic types of activities that are stored in activity content type

## Get All Activity types

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
    "id": 1,
    "name": "Horticulture",
    "is_active": true,
    "created_at": "2020-05-15T17:57:09.304Z",
    "updated_at": "2020-05-15T17:57:09.304Z",
    "activities": []
  }
]
```

### Description

This method returns all the activitytype details by default or specific activitytype details with certain conditions based on the filters passed to the method

### HTTP Request

`GET http://localhost:1337/crm-plugin/activitytypes`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                               |
| --------- | ----------------------------------------- |
| Filters   | Column attributes in the table (Optional) |

## Get a Specific Activity type

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
  "id": 1,
  "name": "Horticulture",
  "is_active": true,
  "created_at": "2020-05-15T17:57:09.304Z",
  "updated_at": "2020-05-15T17:57:09.304Z",
  "activities": []
}
```

### Description

This method returns specific activitytype details by id.

### HTTP Request

`GET http://localhost:1337/crm-plugin/activitytypes/<ID>`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                            |
| --------- | -------------------------------------- |
| ID        | The ID of the activitytype to retrieve |

## Save a Specific Activity type

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
  "id": 2,
  "name": "piggery",
  "is_active": true,
  "created_at": "2020-06-04T13:06:29.683Z",
  "updated_at": "2020-06-04T13:06:29.683Z",
  "activities": []
}
```

### Description

This method creates an activitytype with the attribute parameters passed to this method by default. It returns details of created activitytype

### HTTP Request

`POST http://localhost:1337/crm-plugin/activitytypes`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### Request Parameters

| Parameter         | Description                                                   |
| ----------------- | ------------------------------------------------------------- |
| title             | The name of the activity                                      |
| is_active         | Active status of activitytype (Boolean value : true or false) |
| Column attributes | Column attributes in the table (Optional)                     |

## Update a Specific Activity type

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = "{\n\t\"name\": \"fishery -- test\",\n    \"is_active\": \"true\"\n}"
headers = {}
conn.request("PUT", "/activitytypes/2", payload, headers)
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
   'http://localhost:1337/crm-plugin/activitytypes/2'
```

```javascript
var raw = '{\n	"name": "fishery -- test",\n    "is_active": "true"\n}';

var requestOptions = {
  method: "PUT",
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/activitytypes/2", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "fishery -- test",
  "is_active": true,
  "created_at": "2020-06-04T13:06:29.683Z",
  "updated_at": "2020-06-04T13:06:29.683Z",
  "activities": []
}
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

### Request Parameters

| Parameter         | Description                    |
| ----------------- | ------------------------------ |
| Column attributes | Column attributes in the table |

## Delete a Specific Activity type

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = ''
headers = {}
conn.request("DELETE", "/activitytypes/1", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method DELETE \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/crm-plugin/activitytypes/1'
```

```javascript
var raw = "";

var requestOptions = {
  method: "DELETE",
  body: raw,
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
  "id": 1,
  "name": "Horticulture",
  "is_active": true,
  "created_at": "2020-05-15T17:57:09.304Z",
  "updated_at": "2020-05-15T17:57:09.304Z",
  "activities": []
}
```

### Description

This method deletes specific activitytype by id and returns details of deleted activitytype

### HTTP Request

`DELETE http://localhost:1337/crm-plugin/activitytypes/<ID>`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                          |
| --------- | ------------------------------------ |
| ID        | The ID of the activitytype to delete |
