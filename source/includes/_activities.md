# Activities

Activity stores the details about the activity such as title, date and time and description.

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
    "id": 1,
    "title": "fishery",
    "start_datetime": null,
    "end_datetime": null,
    "description": null,
    "activitytype": null,
    "created_at": "2020-05-28T23:52:16.303Z",
    "updated_at": "2020-05-28T23:52:43.459Z",
    "activityassignees": []
  },
    {
    "id": 2,
    "title": "farming",
    "start_datetime": null,
    "end_datetime": null,
    "description": null,
    "activitytype": null,
    "created_at": "2020-05-28T22:08:20.303Z",
    "updated_at": "2020-05-28T22:08:20.459Z",
    "activityassignees": []
  },
  {...}
]
```

### Description

This method returns all the activity details by default or specific activity details with certain conditions based on the filters passed to the method

### HTTP Request

`GET http://localhost:1337/crm-plugin/activities`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                               |
| --------- | ----------------------------------------- |
| Filters   | Column attributes in the table (Optional) |

## Get a Specific Activity

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = ''
headers = {}
conn.request("GET", "/activities/1", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method GET \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/crm-plugin/activities/1'
```

```javascript
var requestOptions = {
  method: "GET",
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/activities/1", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "title": "fishery",
  "start_datetime": null,
  "end_datetime": null,
  "description": null,
  "activitytype": null,
  "created_at": "2020-05-28T23:52:16.303Z",
  "updated_at": "2020-05-28T23:52:43.459Z",
  "activityassignees": []
}
```

### Description

This method returns specific activity details by id.

### HTTP Request

`GET http://localhost:1337/crm-plugin/activities/<ID>`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                        |
| --------- | ---------------------------------- |
| ID        | The ID of the activity to retrieve |

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
  "id": 3,
  "title": "ponding",
  "start_datetime": null,
  "end_datetime": null,
  "description": null,
  "activitytype": null,
  "created_at": "2020-06-04T12:47:38.398Z",
  "updated_at": "2020-06-04T12:47:38.398Z",
  "activityassignees": []
}
```

### Description

This method creates an activity with the attribute parameters passed to this method by default. It returns details of created activity

### HTTP Request

`POST http://localhost:1337/crm-plugin/activities`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### Request Parameters

| Parameter         | Description                                                               |
| ----------------- | ------------------------------------------------------------------------- |
| title             | The name of the activity                                                  |
| contact           | Array of activity assignee (an organization or individual) ids (Optional) |
| Column attributes | Column attributes in the table (Optional)                                 |

## Update a Specific Activity

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = "{\n\t\"title\":\"piggery --test\"\n}"
headers = {}
conn.request("PUT", "/activities/3", payload, headers)
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
   'http://localhost:1337/crm-plugin/activities/3'
```

```javascript
var raw = '{\n	"title":"piggery --test"\n}';

var requestOptions = {
  method: "PUT",
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/activities/3", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

The above command returns JSON structured like this:

```json
{
  "id": 3,
  "title": "piggery --test",
  "start_datetime": null,
  "end_datetime": null,
  "description": null,
  "activitytype": null,
  "created_at": "2020-06-04T12:47:38.398Z",
  "updated_at": "2020-06-04T12:49:29.419Z",
  "activityassignees": []
}
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

### Request Parameters

| Parameter         | Description                    |
| ----------------- | ------------------------------ |
| Column attributes | Column attributes in the table |

## Delete a Specific Activity

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("http://localhost:1337/crm-plugin")
payload = ''
headers = {}
conn.request("DELETE", "/activities/1", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method DELETE \
  --timeout=0 \
  --header '' \
   'http://localhost:1337/crm-plugin/activities/1'
```

```javascript
var raw = "";

var requestOptions = {
  method: "DELETE",
  body: raw,
  redirect: "follow",
};

fetch("http://localhost:1337/crm-plugin/activities/1", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
```

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "title": "fishery",
  "start_datetime": null,
  "end_datetime": null,
  "description": null,
  "activitytype": null,
  "created_at": "2020-05-28T23:52:16.303Z",
  "updated_at": "2020-05-28T23:52:43.459Z",
  "activityassignees": []
}
```

### Description

This method deletes specific activity by id and returns details of deleted activity.

### HTTP Request

`DELETE http://localhost:1337/crm-plugin/activities/<ID>`

### Headers

| Key           | Value            |
| ------------- | ---------------- |
| Content-Type  | application/json |
| Authorization | Bearer API_TOKEN |

### URL Parameters

| Parameter | Description                      |
| --------- | -------------------------------- |
| ID        | The ID of the activity to delete |
