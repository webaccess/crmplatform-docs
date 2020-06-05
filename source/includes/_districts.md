# Districts

District stores district information belonging to a specific state.

## Get All Districts

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = ''
headers = {}
conn.request("GET", "/districts", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method GET \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/crm-plugin/districts'
```

```javascript
var requestOptions = {
  method: "GET",
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/districts", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Sangli",
    "is_active": true,
    "abbreviation": null,
    "identifier": null,
    "state": null,
    "created_at": "2020-05-19T10:02:49.989Z",
    "updated_at": "2020-05-19T10:02:50.422Z",
    "villages": []
  }
]
```

### Description

This method returns all the district details by default or specific district details with certain conditions based on the filters passed to the method

### HTTP Request

`GET http://localhost:1337/crm-plugin/districts`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                               |
| --------- | ----------------------------------------- |
| Filters   | Column attributes in the table (Optional) |

## Get a Specific District

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = ''
headers = {}
conn.request("GET", "/districts/1", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method GET \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/crm-plugin/districts/1'
```

```javascript
var requestOptions = {
  method: "GET",
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/districts/1", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
    {
        "id": 1,
        "name": "Sangli",
        "is_active": true,
        "abbreviation": null,
        "identifier": null,
        "state": null,
        "created_at": "2020-05-19T10:02:49.989Z",
        "updated_at": "2020-05-19T10:02:50.422Z",
        "villages": []
    },
```

### Description

This method returns specific district details by id.

### HTTP Request

`GET http://localhost:1337/crm-plugin/districts/<ID>`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                        |
| --------- | ---------------------------------- |
| ID        | The ID of the district to retrieve |

## Count All/Specific Districts

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = ''
headers = {}
conn.request("GET", "/districts/count", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method GET \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/crm-plugin/districts/count'
```

```javascript
var requestOptions = {
  method: "GET",
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/districts/count", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
1
```

### Description

This method returns total number of data items present in the district.

### HTTP Request

`GET http://localhost:1337/crm-plugin/districts/count`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

Optional

## Save a Specific District

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = "{\n\t\"name\": \"andheri\",\n    \"is_active\": \"true\"\n}"
headers = {}
conn.request("POST", "/districts", payload, headers)
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
	"name": "andheri",
    "is_active": "true"
}' \
   'http://localhost:1337/crm-plugin/districts'
```

```javascript
var raw = '{\n	"name": "andheri",\n    "is_active": "true"\n}';

var requestOptions = {
  method: "POST",
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/districts", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "andheri",
  "is_active": true,
  "abbreviation": null,
  "identifier": null,
  "state": null,
  "created_at": "2020-06-04T11:53:03.795Z",
  "updated_at": "2020-06-04T11:53:03.795Z",
  "villages": []
}
```

### Description

This method creates a district with the attribute parameters passed to this method by default. It returns details of created district

### HTTP Request

`POST http://localhost:1337/crm-plugin/districts`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### Request Parameters

| Parameter         | Description                                               |
| ----------------- | --------------------------------------------------------- |
| name              | The name of the district                                  |
| is_active         | Active status of district (Boolean value : true or false) |
| Column attributes | Column attributes in the table (Optional)                 |

## Update a Specific District

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = "{\n\t\"name\": \"andheri --test\",\n    \"is_active\": \"true\"\n}"
headers = {}
conn.request("PUT", "/districts/2", payload, headers)
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
	"name": "andheri --test",
    "is_active": "true"
}' \
   'http://localhost:1337/crm-plugin/districts/2'
```

```javascript
var raw = '{\n	"name": "andheri --test",\n    "is_active": "true"\n}';

var requestOptions = {
  method: "PUT",
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/districts/2", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "andheri --test",
  "is_active": true,
  "abbreviation": null,
  "identifier": null,
  "state": null,
  "created_at": "2020-06-04T11:53:03.795Z",
  "updated_at": "2020-06-04T11:55:10.831Z",
  "villages": []
}
```

### Description

This method updates the specific district by id with attribute parameters passed to it.It returns details of updated district

### HTTP Request

`UPDATE http://localhost:1337/crm-plugin/districts/<ID>`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                      |
| --------- | -------------------------------- |
| ID        | The ID of the district to update |

## Delete a Specific District

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = ''
headers = {}
conn.request("DELETE", "/districts/1", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method DELETE \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/crm-plugin/districts/1'
```

```javascript
var raw = "";

var requestOptions = {
  method: "DELETE",
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/districts/1", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "name": "Sangli",
  "is_active": true,
  "abbreviation": null,
  "identifier": null,
  "state": null,
  "created_at": "2020-05-19T10:02:49.989Z",
  "updated_at": "2020-05-19T10:02:50.422Z",
  "villages": []
}
```

### Description

This method deletes specific district by id and returns details of deleted district

### HTTP Request

`DELETE http://localhost:1337/crm-plugin/districts/<ID>`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                     |
| --------- | ------------------------------- |
| ID        | The ID of the country to delete |
