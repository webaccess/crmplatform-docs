# States

State stores information about the state belonging to a specific country.

## Get All States

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = ''
headers = {}
conn.request("GET", "/states", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method GET \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/crm-plugin/states'
```

```javascript
var requestOptions = {
  method: "GET",
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/states", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Goa",
    "is_active": true,
    "abbreviation": "GA",
    "identifier": "GA",
    "country": {
      "id": 1,
      "name": "India",
      "is_active": true,
      "abbreviation": "IN",
      "identifier": "IN",
      "created_at": "2020-06-08T15:34:11.390Z",
      "updated_at": "2020-06-08T15:34:11.390Z"
    },
    "created_at": "2020-06-08T17:00:27.897Z",
    "updated_at": "2020-06-08T17:00:27.897Z",
    "districts": [{
      "id": 1,
      "name": "North Goa",
      "is_active": true,
      "abbreviation": "NG",
      "identifier": "NG",
      "state": 1,
      "created_at": "2020-06-08T17:38:17.853Z",
      "updated_at": "2020-06-08T17:38:17.853Z"
    }, {
      "id": 2,
      "name": "South Goa",
      "is_active": true,
      "abbreviation": "SG",
      "identifier": "SG",
      "state": 1,
      "created_at": "2020-06-08T17:38:17.860Z",
      "updated_at": "2020-06-08T17:38:17.860Z"
    }],
    "villages": []
  },
  {
    "id": 2,
    "name": "Gujarat",
    "is_active": true,
    "abbreviation": "GJ",
    "identifier": "GJ",
    "country": {
      "id": 1,
      "name": "India",
      "is_active": true,
      "abbreviation": "IN",
      "identifier": "IN",
      "created_at": "2020-06-08T15:34:11.390Z",
      "updated_at": "2020-06-08T15:34:11.390Z"
    },
    "created_at": "2020-06-09T14:31:52.037Z",
    "updated_at": "2020-06-09T14:31:52.037Z",
    "districts": [
      {
        "id": 3,
        "name": "Ahmedabad",
        "is_active": true,
        "abbreviation": "AH",
        "identifier": "AH",
        "state": 2,
        "created_at": "2020-06-09T14:31:52.718Z",
        "updated_at": "2020-06-09T14:31:52.718Z"
      },
      {
        "id": 4,
        "name": "Bhavnagar",
        "is_active": true,
        "abbreviation": "BV",
        "identifier": "BV",
        "state": 2,
        "created_at": "2020-06-09T14:31:52.721Z",
        "updated_at": "2020-06-09T14:31:52.721Z"
      },
      {...}
    ],
    "villages": []
  },
  {...}
]
```

### Description

This method returns all the state details by default or specific state details with certain conditions based on the filters passed to the method.

### HTTP Request

`GET http://localhost:1337/crm-plugin/states`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                               |
| --------- | ----------------------------------------- |
| Filters   | Column attributes in the table (Optional) |

## Get a Specific State

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = ''
headers = {}
conn.request("GET", "/states/1", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method GET \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/crm-plugin/states/1'
```

```javascript
var requestOptions = {
  method: "GET",
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/states/1", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "name": "Goa",
  "is_active": true,
  "abbreviation": "GA",
  "identifier": "GA",
  "country": {
    "id": 1,
    "name": "India",
    "is_active": true,
    "abbreviation": "IN",
    "identifier": "IN",
    "created_at": "2020-06-08T15:34:11.390Z",
    "updated_at": "2020-06-08T15:34:11.390Z"
  },
  "created_at": "2020-06-08T17:00:27.897Z",
  "updated_at": "2020-06-08T17:00:27.897Z",
  "districts": [
    {
      "id": 1,
      "name": "North Goa",
      "is_active": true,
      "abbreviation": "NG",
      "identifier": "NG",
      "state": 1,
      "created_at": "2020-06-08T17:38:17.853Z",
      "updated_at": "2020-06-08T17:38:17.853Z"
    },
    {
      "id": 2,
      "name": "South Goa",
      "is_active": true,
      "abbreviation": "SG",
      "identifier": "SG",
      "state": 1,
      "created_at": "2020-06-08T17:38:17.860Z",
      "updated_at": "2020-06-08T17:38:17.860Z"
    }
  ],
  "villages": []
}
```

### Description

This method returns specific state details by id.

### HTTP Request

`GET http://localhost:1337/crm-plugin/states/<ID>`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                     |
| --------- | ------------------------------- |
| ID        | The ID of the state to retrieve |

## Count All/Specific States

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = ''
headers = {}
conn.request("GET", "/states/count", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method GET \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/crm-plugin/states/count'
```

```javascript
var requestOptions = {
  method: "GET",
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/states/count", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
2
```

### Description

This method returns total number of data items present in state table by default or number of states matching criteria based on the filters passed to the method.

### HTTP Request

`GET http://localhost:1337/crm-plugin/states/count`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                               |
| --------- | ----------------------------------------- |
| Filters   | Column attributes in the table (Optional) |

## Save a Specific State

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = "{\r\n\t\"name\": \"Maharashtra\",\r\n    \"is_active\": \"true\"\r\n}"
headers = {}
conn.request("POST", "/states", payload, headers)
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
	"name": "Maharashtra",
    "is_active": "true"
}' \
   'http://localhost:1337/crm-plugin/states'
```

```javascript
var raw = "{
\n	\"name\": \"Maharashtra\",
\n    \"is_active\": \"true\"
\n}";

var requestOptions = {
  method: 'POST',
  body: raw,
  redirect: 'follow'
};

fetch("http://localhost:1337/crm-plugin/states", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```

> The above command returns JSON structured like this:

```json
{
	"id": 3,
	"name": "Maharashtra",
	"is_active": true,
	"abbreviation": "MH",
	"identifier": "MH",
	"country": {
		"id": 1,
		"name": "India",
		"is_active": true,
		"abbreviation": "IN",
		"identifier": "IN",
		"created_at": "2020-06-08T15:34:11.390Z",
		"updated_at": "2020-06-08T15:34:11.390Z"
	},
	"created_at": "2020-06-08T17:00:27.916Z",
	"updated_at": "2020-06-08T17:00:27.916Z",
	"districts": [{
		"id": 10,
		"name": "Solapur",
		"is_active": true,
		"abbreviation": "SO",
		"identifier": "SO",
		"state": 38,
		"created_at": "2020-06-09T14:29:23.112Z",
		"updated_at": "2020-06-09T14:29:23.112Z"
	}, {
		"id": 11,
		"name": "Amravati",
		"is_active": true,
		"abbreviation": "AM",
		"identifier": "AM",
		"state": 38,
		"created_at": "2020-06-09T14:29:23.060Z",
		"updated_at": "2020-06-09T14:29:23.060Z"
	},
  {...}],
	"villages": []
}
```

### Description

This method creates a state with the attribute parameters passed to this method by default. It returns details of the created state.

### HTTP Request

`POST http://localhost:1337/crm-plugin/states`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### Request Parameters

| Parameter         | Description                                            |
| ----------------- | ------------------------------------------------------ |
| name              | Name of the state                                      |
| is_active         | Active status of state (Boolean value : true or false) |
| Column attributes | Column attributes in the table (Optional)              |

## Update a State

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = "{\r\n\t\"name\": \"Maharashtra --test\",\r\n    \"is_active\": \"true\"\r\n}"
headers = {}
conn.request("PUT", "/states/3", payload, headers)
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
	"name": "Maharashtra --test",
    "is_active": "true"
}' \
   'http://localhost:1337/crm-plugin/states/3'
```

```javascript
var raw = "{
\n	\"name\": \"Maharashtra --test\",
\n    \"is_active\": \"true\"
\n}";

var requestOptions = {
  method: 'PUT',
  body: raw,
  redirect: 'follow'
};

fetch("http://localhost:1337/crm-plugin/states/3", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```

> The above command returns JSON structured like this:

```json
{
	"id": 3,
	"name": "Maharashtra --test",
	"is_active": true,
	"abbreviation": "MH",
	"identifier": "MH",
	"country": {
		"id": 1,
		"name": "India",
		"is_active": true,
		"abbreviation": "IN",
		"identifier": "IN",
		"created_at": "2020-06-08T15:34:11.390Z",
		"updated_at": "2020-06-08T15:34:11.390Z"
	},
	"created_at": "2020-06-08T17:00:27.916Z",
	"updated_at": "2020-06-08T17:00:27.916Z",
	"districts": [{
		"id": 10,
		"name": "Solapur",
		"is_active": true,
		"abbreviation": "SO",
		"identifier": "SO",
		"state": 38,
		"created_at": "2020-06-09T14:29:23.112Z",
		"updated_at": "2020-06-09T14:29:23.112Z"
	}, {
		"id": 11,
		"name": "Amravati",
		"is_active": true,
		"abbreviation": "AM",
		"identifier": "AM",
		"state": 38,
		"created_at": "2020-06-09T14:29:23.060Z",
		"updated_at": "2020-06-09T14:29:23.060Z"
	},
  {...}],
	"villages": []
}
```

### Description

This method updates the specific state by id with attribute parameters passed to it.It returns details of updated state.

### HTTP Request

`POST http://localhost:1337/crm-plugin/states/<ID>`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                   |
| --------- | ----------------------------- |
| ID        | The ID of the state to update |

### Request Parameters

| Parameter         | Description                    |
| ----------------- | ------------------------------ |
| Column attributes | Column attributes in the table |

## Delete a Specific State

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = ''
headers = {}
conn.request("DELETE", "/states/3", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method DELETE \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/crm-plugin/states/3'
```

```javascript
var raw = "";

var requestOptions = {
  method: "DELETE",
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/states/3", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Goa",
    "is_active": true,
    "abbreviation": "GA",
    "identifier": "GA",
    "country": {
      "id": 1,
      "name": "India",
      "is_active": true,
      "abbreviation": "IN",
      "identifier": "IN",
      "created_at": "2020-06-08T15:34:11.390Z",
      "updated_at": "2020-06-08T15:34:11.390Z"
    },
    "created_at": "2020-06-08T17:00:27.897Z",
    "updated_at": "2020-06-08T17:00:27.897Z",
    "districts": [{
      "id": 1,
      "name": "North Goa",
      "is_active": true,
      "abbreviation": "NG",
      "identifier": "NG",
      "state": 1,
      "created_at": "2020-06-08T17:38:17.853Z",
      "updated_at": "2020-06-08T17:38:17.853Z"
    }, {
      "id": 2,
      "name": "South Goa",
      "is_active": true,
      "abbreviation": "SG",
      "identifier": "SG",
      "state": 1,
      "created_at": "2020-06-08T17:38:17.860Z",
      "updated_at": "2020-06-08T17:38:17.860Z"
    }],
    "villages": []
  },
  {
    "id": 2,
    "name": "Gujarat",
    "is_active": true,
    "abbreviation": "GJ",
    "identifier": "GJ",
    "country": {
      "id": 1,
      "name": "India",
      "is_active": true,
      "abbreviation": "IN",
      "identifier": "IN",
      "created_at": "2020-06-08T15:34:11.390Z",
      "updated_at": "2020-06-08T15:34:11.390Z"
    },
    "created_at": "2020-06-09T14:31:52.037Z",
    "updated_at": "2020-06-09T14:31:52.037Z",
    "districts": [
      {
        "id": 3,
        "name": "Ahmedabad",
        "is_active": true,
        "abbreviation": "AH",
        "identifier": "AH",
        "state": 2,
        "created_at": "2020-06-09T14:31:52.718Z",
        "updated_at": "2020-06-09T14:31:52.718Z"
      },
      {
        "id": 4,
        "name": "Bhavnagar",
        "is_active": true,
        "abbreviation": "BV",
        "identifier": "BV",
        "state": 2,
        "created_at": "2020-06-09T14:31:52.721Z",
        "updated_at": "2020-06-09T14:31:52.721Z"
      },
      {...}
    ],
    "villages": []
  },
  {...}
]
```

### Description

This method deletes specific state by id and returns details of deleted state.

### HTTP Request

`DELETE http://localhost:1337/crm-plugin/states/<ID>`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                   |
| --------- | ----------------------------- |
| ID        | The ID of the state to delete |
