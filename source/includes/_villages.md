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
    "id": 2,
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

Optional

## Get a Specific Village

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = ''
headers = {}
conn.request("GET", "/villages/2", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method GET \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/crm-plugin/villages/2'
```

```javascript
var requestOptions = {
  method: "GET",
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/villages/2", requestOptions)
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
| ID        | The ID of the country to retrieve |

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

This method creates a village with the attribute parameters passed to this method by default. It returns details of created village

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

## Update a Village

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = "{\n\t\"name\": \"thane --test\"\n}"
headers = {}
conn.request("PUT", "/villages/2", payload, headers)
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
   'http://localhost:1337/crm-plugin/villages/2'
```

```javascript
var raw = '{\n	"name": "thane --test"\n}';

var requestOptions = {
  method: "PUT",
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/villages/2", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
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

## Delete a Specific Village

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = ''
headers = {}
conn.request("DELETE", "/villages/3", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method DELETE \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/crm-plugin/villages/3'
```

```javascript
var raw = "";

var requestOptions = {
  method: "DELETE",
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/villages/3", requestOptions)
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
| ID        | The ID of the country to delete |
