# Countries

Country stores details of a country having some states.

## Get All Countries

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = ''
headers = {}
conn.request("GET", "/countries", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method GET \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/crm-plugin/countries'
```

```javascript
var requestOptions = {
  method: "GET",
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/countries", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 6,
    "name": "India",
    "is_active": true,
    "abbreviation": "IN",
    "identifier": "IN",
    "created_at": "2020-06-08T15:34:11.390Z",
    "updated_at": "2020-06-08T15:34:11.390Z",
    "states": [{
      "id": 1,
      "name": "Goa",
      "is_active": true,
      "abbreviation": "GA",
      "identifier": "GA",
      "country": 6,
      "created_at": "2020-06-08T17:00:27.897Z",
      "updated_at": "2020-06-08T17:00:27.897Z"
    },
    {
      "id": 2,
      "name": "Puducherry",
      "is_active": true,
      "abbreviation": "PY",
      "identifier": "PY",
      "country": 6,
      "created_at": "2020-06-09T14:31:52.037Z",
      "updated_at": "2020-06-09T14:31:52.037Z"
    },
    {...}]
  },
  {...}
]
```

### Description

This method returns all the country details by default or specific country details with certain conditions based on the filters passed to the method.

### HTTP Request

`GET http://localhost:1337/crm-plugin/countries`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                               |
| --------- | ----------------------------------------- |
| Filters   | Column attributes in the table (Optional) |

## Get a Specific Country

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = ''
headers = {}
conn.request("GET", "/countries/6", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method GET \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/crm-plugin/countries/6'
```

```javascript
var requestOptions = {
  method: "GET",
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/countries/6", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
{
  "id": 6,
  "name": "India",
  "is_active": true,
  "abbreviation": "IN",
  "identifier": "IN",
  "created_at": "2020-06-08T15:34:11.390Z",
  "updated_at": "2020-06-08T15:34:11.390Z",
  "states": [{
    "id": 1,
    "name": "Goa",
    "is_active": true,
    "abbreviation": "GA",
    "identifier": "GA",
    "country": 6,
    "created_at": "2020-06-08T17:00:27.897Z",
    "updated_at": "2020-06-08T17:00:27.897Z"
  },
  {
    "id": 2,
    "name": "Puducherry",
    "is_active": true,
    "abbreviation": "PY",
    "identifier": "PY",
    "country": 6,
    "created_at": "2020-06-09T14:31:52.037Z",
    "updated_at": "2020-06-09T14:31:52.037Z"
  },
  {...}]
}
```

### Description

This method returns specific country details by id.

### HTTP Request

`GET http://localhost:1337/crm-plugin/countries/<ID>`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                       |
| --------- | --------------------------------- |
| ID        | The ID of the country to retrieve |

## Count All/Specific Countries

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = ''
headers = {}
conn.request("GET", "/countries/count", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method GET \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/crm-plugin/countries/count'
```

```javascript
var requestOptions = {
  method: "GET",
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/countries/count", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
1
```

### Description

This method returns total number of data items present in a country.

### HTTP Request

`GET http://localhost:1337/crm-plugin/countries/count`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

Optional

## Save a Specific Country

```python
import http.client
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = "{\n\t \"name\": \"Europe\",\n     \"is_active\": true,\n     \"abbreviation\": \"EU\"\n}"
headers = {}
conn.request("POST", "/countries", payload, headers)
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
	  "name": "Europe",
    "is_active": true,
    "abbreviation": "EU"
}' \
   'http://localhost:1337/crm-plugin/countries'
```

```javascript
var raw =
  '{\n	 "name": "Europe",\n     "is_active": true,\n     "abbreviation": "EU"\n}';

var requestOptions = {
  method: "POST",
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/countries", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
{
  "id": 7,
  "name": "Europe",
  "is_active": true,
  "abbreviation": "EU",
  "identifier": "EU",
  "created_at": "2020-06-08T15:34:11.390Z",
  "updated_at": "2020-06-08T15:34:11.390Z",
  "states": []
}
```

### Description

This method creates a country with the attribute parameters passed to this method by default. It returns details of created country.

### HTTP Request

`POST http://localhost:1337/crm-plugin/countries/<ID>`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### Request Parameters

| Parameters        | Description                                              |
| ----------------- | -------------------------------------------------------- |
| name              | The name of the country to create                        |
| is_active         | Active status of country (Boolean value : true or false) |
| abbreviation      | Abbreviation for the country (Unique value)              |
| Column attributes | Column attributes in the table (Optional)                |

## Update a Specific Country

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = "{\n\t \"name\": \"Europe --test\",\n     \"is_active\": true,\n     \"abbreviation\": \"EU\"\n}"
headers = {}
conn.request("PUT", "/countries/7", payload, headers)
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
	 "name": "Europe --test",
     "is_active": true,
     "abbreviation": "EU"
}' \
   'http://localhost:1337/crm-plugin/countries/7'
```

```javascript
var raw =
  '{\n	 "name": "Europe --test",\n     "is_active": true,\n     "abbreviation": "EU"\n}';

var requestOptions = {
  method: "PUT",
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/countries/7", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

The above command returns JSON structured like this:

```json
{
  "id": 7,
  "name": "Europe --test",
  "is_active": true,
  "abbreviation": "EU",
  "identifier": "EU",
  "created_at": "2020-06-08T15:34:11.390Z",
  "updated_at": "2020-06-08T15:34:11.390Z",
  "states": []
}
```

### Description

This method updates the specific country by id with attribute parameters passed to it.It returns details of updated country

### HTTP Request

`UPDATE http://localhost:1337/crm-plugin/states/<ID>`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                     |
| --------- | ------------------------------- |
| ID        | The ID of the country to update |

### Request Parameters

| Parameter         | Description                    |
| ----------------- | ------------------------------ |
| Column attributes | Column attributes in the table |

## Delete a Specific Country

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = ''
headers = {}
conn.request("DELETE", "/countries/7", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method DELETE \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/crm-plugin/countries/7'
```

```javascript
var raw = "";

var requestOptions = {
  method: "DELETE",
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/countries/7", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 6,
    "name": "India",
    "is_active": true,
    "abbreviation": "IN",
    "identifier": "IN",
    "created_at": "2020-06-08T15:34:11.390Z",
    "updated_at": "2020-06-08T15:34:11.390Z",
    "states": [{
      "id": 1,
      "name": "Goa",
      "is_active": true,
      "abbreviation": "GA",
      "identifier": "GA",
      "country": 6,
      "created_at": "2020-06-08T17:00:27.897Z",
      "updated_at": "2020-06-08T17:00:27.897Z"
    },
    {
      "id": 2,
      "name": "Puducherry",
      "is_active": true,
      "abbreviation": "PY",
      "identifier": "PY",
      "country": 6,
      "created_at": "2020-06-09T14:31:52.037Z",
      "updated_at": "2020-06-09T14:31:52.037Z"
    },
    {...}]
  },
  {...}
]
```

### Description

This method deletes specific country by id and returns details of deleted country.

### HTTP Request

`DELETE http://localhost:1337/crm-plugin/countries/<ID>`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                     |
| --------- | ------------------------------- |
| ID        | The ID of the country to delete |
