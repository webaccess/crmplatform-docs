# Activities

Activity stores details about what the activity is and also tracks when the activity took place as well as information about that activity

## Get All Activities

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = ''
headers = {}
conn.request("GET", "/activities", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method GET \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/crm-plugin/activities'
```

```javascript
var requestOptions = {
  method: "GET",
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/activities", requestOptions)
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

This method returns all the activity details by default or specific activity details with certain conditions based on the filters passed to the method

### HTTP Request

`GET http://localhost:1337/crm-plugin/villages`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

Optional

## Get a Specific Activity

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

This method returns specific activity details by id.

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

## Save a Specific Activity

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = "{\n\t\"title\":\"ponding\"\n}"
headers = {}
conn.request("POST", "/activities", payload, headers)
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
	"title":"ponding"
}' \
   'http://localhost:1337/crm-plugin/activities'
```

```javascript
var raw = '{\n	"title":"ponding"\n}';

var requestOptions = {
  method: "POST",
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/activities", requestOptions)
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

This method creates an activity with the attribute parameters passed to this method by default. It returns details of created activity

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

## Update a Activity

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = "{\n\t\"title\":\"piggery --test\"\n}"
headers = {}
conn.request("PUT", "/activities/4", payload, headers)
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
	"title":"piggery --test"
}' \
   'http://localhost:1337/crm-plugin/activities/4'
```

```javascript
var raw = '{\n	"title":"piggery --test"\n}';

var requestOptions = {
  method: "PUT",
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/activities/4", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

### Description

This method updates the specific activity by id with attribute parameters passed to it.It returns details of updated activity

### HTTP Request

`UPDATE http://localhost:1337/crm-plugin/activities/<ID>`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                      |
| --------- | -------------------------------- |
| ID        | The ID of the activity to update |

## Delete a Specific Activity

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = ''
headers = {}
conn.request("DELETE", "/activities/4", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method DELETE \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/crm-plugin/activities/4'
```

```javascript
var raw = "";

var requestOptions = {
  method: "DELETE",
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/activities/4", requestOptions)
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

This method deletes specific activity by id and returns details of deleted activity.

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
