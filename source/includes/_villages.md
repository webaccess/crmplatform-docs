# Villages

Village stores village information belonging to a specific district.

## Get All Villages

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = ''
headers = {}
conn.request("GET", "/villages", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method GET \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/crm-plugin/villages'
```

```javascript
var raw = "";

var requestOptions = {
  method: "GET",
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/villages", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Hivre",
    "abbreviation": null,
    "identifier": null,
    "is_active": true,
    "state": null,
    "district": null,
    "created_at": "2020-05-22T06:25:50.650Z",
    "updated_at": "2020-05-22T06:25:50.650Z",
    "contacts": []
  },
    {
    "id": 2,
    "name": "Junnar",
    "abbreviation": null,
    "identifier": null,
    "is_active": true,
    "state": null,
    "district": null,
    "created_at": "2020-05-22T07:30:20.650Z",
    "updated_at": "2020-05-22T07:30:20.650Z",
    "contacts": []
  },
  {...}
]
```

### Description

This method returns all the village details by default or specific village details with certain conditions based on the filters passed to the method

### HTTP Request

`GET http://localhost:1337/crm-plugin/villages`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                               |
| --------- | ----------------------------------------- |
| Filters   | Column attributes in the table (Optional) |

## Get a Specific Village

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = ''
headers = {}
conn.request("GET", "/villages/1", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method GET \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/crm-plugin/villages/1'
```

```javascript
var requestOptions = {
  method: "GET",
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/villages/1", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "name": "Hivre",
  "abbreviation": null,
  "identifier": null,
  "is_active": true,
  "state": null,
  "district": null,
  "created_at": "2020-05-22T06:25:50.650Z",
  "updated_at": "2020-05-22T06:25:50.650Z",
  "contacts": []
}
```

### Description

This method returns specific village details by id.

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
| ID        | The ID of the village to retrieve |

## Count All/Specific Villages

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = ''
headers = {}
conn.request("GET", "/villages/count", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method GET \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/crm-plugin/villages/count'
```

```javascript
var requestOptions = {
  method: "GET",
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/villages/count", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
2
```

### Description

This method returns total number of data items present in the village.

### HTTP Request

`GET http://localhost:1337/crm-plugin/villages/count`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

Optional

## Save a Specific Village

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = "{\n\t\"name\": \"thane\"\n}"
headers = {}
conn.request("POST", "/villages", payload, headers)
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
	"name": "thane"
}' \
   'http://localhost:1337/crm-plugin/villages'
```

```javascript
var raw = '{\n	"name": "Thane"\n}';

var requestOptions = {
  method: "POST",
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/villages", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Thane",
  "abbreviation": null,
  "identifier": null,
  "is_active": true,
  "state": null,
  "district": null,
  "created_at": "2020-06-04T12:56:38.181Z",
  "updated_at": "2020-06-04T12:56:38.181Z",
  "contacts": []
}
```

### Description

This method creates a village with the attribute parameters passed to this method by default. It returns details of created village

### HTTP Request

`POST http://localhost:1337/crm-plugin/villages`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### Request Parameters

| Parameter         | Description                               |
| ----------------- | ----------------------------------------- |
| name              | The name of the village                   |
| Column attributes | Column attributes in the table (Optional) |

## Update a Specific Village

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = "{\n\t\"name\": \"thane --test\"\n}"
headers = {}
conn.request("PUT", "/villages/3", payload, headers)
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
	"name": "thane --test"
}' \
   'http://localhost:1337/crm-plugin/villages/3'
```

```javascript
var raw = '{\n	"name": "thane --test"\n}';

var requestOptions = {
  method: "PUT",
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/villages/3", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

The above command returns JSON structured like this:

```json
{
  "id": 3,
  "name": "Thane --test",
  "abbreviation": null,
  "identifier": null,
  "is_active": true,
  "state": null,
  "district": null,
  "created_at": "2020-06-04T12:56:38.181Z",
  "updated_at": "2020-06-04T12:56:38.181Z",
  "contacts": []
}
```

### Description

This method updates the specific village by id with attribute parameters passed to it.It returns details of updated village

### HTTP Request

`UPDATE http://localhost:1337/crm-plugin/villages/<ID>`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                     |
| --------- | ------------------------------- |
| ID        | The ID of the village to update |

### Request Parameters

| Parameter         | Description                    |
| ----------------- | ------------------------------ |
| Column attributes | Column attributes in the table |

## Delete a Specific Village

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = ''
headers = {}
conn.request("DELETE", "/villages/1", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method DELETE \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/crm-plugin/villages/1'
```

```javascript
var raw = "";

var requestOptions = {
  method: "DELETE",
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/villages/1", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
{
  "id": 98,
  "name": "Hivre",
  "abbreviation": null,
  "identifier": null,
  "is_active": true,
  "state": null,
  "district": null,
  "created_at": "2020-05-22T06:25:50.650Z",
  "updated_at": "2020-05-22T06:25:50.650Z",
  "contacts": []
}
```

### Description

This method deletes specific village by id and returns details of deleted village

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
| ID        | The ID of the village to delete |
