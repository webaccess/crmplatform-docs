# Tags

Tag allows you to categorize the contacts.

## Get All Tags

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = ''
headers = {}
conn.request("GET", "/tags", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method GET \
  --timeout=0 \

   'http://localhost:1337/crm-plugin/tags'
```

```javascript
var myHeaders = new Headers();

var requestOptions = {
  method: "GET",
  headers: myHeaders,
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/tags", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "tag1",
    "description": null,
    "is_active": true,
    "created_at": "2020-06-04T13:19:23.880Z",
    "updated_at": "2020-06-04T13:19:23.880Z",
    "contacttags": []
  }
]
```

### Description

This method returns all the tag details by default or specific tag details with certain conditions based on the filters passed to the method

### HTTP Request

`GET http://localhost:1337/crm-plugin/tags`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                               |
| --------- | ----------------------------------------- |
| Filters   | Column attributes in the table (Optional) |

## Get a Specific Tag

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = ''
headers = {}
conn.request("GET", "/tags/1", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method GET \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/crm-plugin/tags/1'
```

```javascript
var requestOptions = {
  method: "GET",
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/tags/1", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "name": "tag1",
  "description": null,
  "is_active": true,
  "created_at": "2020-06-04T13:19:23.880Z",
  "updated_at": "2020-06-04T13:19:23.880Z",
  "contacttags": []
}
```

### Description

This method returns specific tag details by id

### HTTP Request

`GET http://localhost:1337/crm-plugin/tags/<ID>`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                   |
| --------- | ----------------------------- |
| ID        | The ID of the tag to retrieve |

## Save a Specific Tag

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = "{\n\t\"name\":\"tag7\"\n\t\n}"
conn.request("POST", "/tags", payload, headers)
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
	"name":"tag7"

}' \
   'http://localhost:1337/crm-plugin/tags'
```

```javascript
var raw = "{
\n	\"name\": \"tag7\"
\n}"

var requestOptions = {
  method: "POST",
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/tags", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "tag7",
  "description": null,
  "is_active": true,
  "created_at": "2020-06-04T13:19:23.880Z",
  "updated_at": "2020-06-04T13:19:23.880Z",
  "contacttags": []
}
```

### Description

This method creates a tag with the attribute parameters passed to this method by default. It returns details of created tag

### HTTP Request

`POST http://localhost:1337/crm-plugin/tags`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### Request Parameters

| Parameter         | Description                                                         |
| ----------------- | ------------------------------------------------------------------- |
| name              | The name of the tag                                                 |
| is_active         | Active status of tag (Boolean value : true or false)                |
| contact           | Array of contact tag (an organization or individual) ids (Optional) |
| Column attributes | Column attributes in the table (Optional)                           |

## Update a Specific Tag

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = "{\n    \"is_active\": false,\n    \"contacts\": [\n        1\n    ]\n}"
headers = {}
conn.request("PUT", "/tags/2", payload, headers)
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
    "is_active": false,
    "contacts": [
        1
    ]
}' \
   'http://localhost:1337/crm-plugin/tags/2'
```

```javascript
var raw = '{\n	"name": "andheri --test"\n}';

var requestOptions = {
  method: "PUT",
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/tags/2", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "tag7",
  "description": null,
  "is_active": false,
  "created_at": "2020-06-04T13:19:23.880Z",
  "updated_at": "2020-06-04T13:26:17.629Z",
  "contacttags": [
    {
      "id": 1,
      "contact": 1,
      "tag": 2,
      "created_at": "2020-06-04T13:26:17.453Z",
      "updated_at": "2020-06-04T13:26:17.477Z"
    }
  ],
  "contacts": [
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
        "id": 155,
        "name": "NewTech",
        "contact": 158,
        "created_at": "2020-06-04T13:25:03.188Z",
        "updated_at": "2020-06-04T13:25:03.354Z"
      },
      "country": null,
      "state": null,
      "district": null,
      "individual": null,
      "user": null,
      "created_at": "2020-06-04T13:25:03.298Z",
      "updated_at": "2020-06-04T13:25:03.375Z",
      "villages": [],
      "activityassignees": [],
      "contacttags": [
        {
          "id": 1,
          "contact": 1,
          "tag": 2,
          "created_at": "2020-06-04T13:26:17.453Z",
          "updated_at": "2020-06-04T13:26:17.477Z"
        }
      ]
    }
  ]
}
```

### Description

This method updates the specific tag by id with attribute parameters passed to it.It returns details of updated tag

### HTTP Request

`UPDATE http://localhost:1337/crm-plugin/tags/<ID>`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                 |
| --------- | --------------------------- |
| ID        | The ID of the tag to update |

### Request Parameters

| Parameter         | Description                    |
| ----------------- | ------------------------------ |
| Column attributes | Column attributes in the table |

## Delete a Specific Tag

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = ''
headers = {}
conn.request("DELETE", "/tags/1", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method DELETE \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/crm-plugin/tags/1'
```

```javascript
var raw = "";

var requestOptions = {
  method: "DELETE",
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/tags/1", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "name": "tag1",
  "description": null,
  "is_active": true,
  "created_at": "2020-06-04T13:19:23.880Z",
  "updated_at": "2020-06-04T13:19:23.880Z",
  "contacttags": []
}
```

### Description

This method deletes specific tag by id and returns details of deleted tag

### HTTP Request

`DELETE http://localhost:1337/crm-plugin/tags/<ID>`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                 |
| --------- | --------------------------- |
| ID        | The ID of the tag to delete |
