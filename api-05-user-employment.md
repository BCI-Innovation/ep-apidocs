---
title: 'User Employment Endpoints'
date: 2019-02-11T19:27:37+10:00
weight: 2
summary: "The API gateway deals with user employments."
---

The API gateway deals with providing access to user employment and making changes.


# **List Data**
##### Description
This endpoint will return a list of public employments.

##### URL

`https://talentaccelerator.dev/api/v1/public/user-employments`

##### Method

`GET`

##### URL Params

Query Parameters | Required | Default | Description
--------- | ----------- | ----------- | -----------
`offset` | No | 0 | The offset of the record in the list which will be used as to filter any records less then this value.
`limit`| No | 250 | The maximum number of entries to return in the pagination. Backend will not allow any value larger then 500.
`sort_order` | No | DESC | The sort order to return the records by.
`sort_field` | No | id | The sort field to sort the records by.
`search` | No | "" | The keywords to search through the database for.
`user_id` | No | "" | The record which belongs to the specific user.

*Note (1): Query parameter inputted values must be **number of milliseconds since January 1, 1970 00:00:00** as found in the JavaScript [`getTime()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getTime) function.*

*Note (2): Try running `console.log(new Date().getTime())` in your console to get an example of how the query parameter inputted value looks like.*

##### Data Params

None

##### Success Response

  * **Status**: `200`
  * **Content**:
    ```json

    ```

##### Sample Call

Run the following in your terminal:

```shell
curl "https://talentaccelerator.dev/api/v1/public/user-employments" \
    -H "Content-Type: application/json"
```

**OR**

```shell
curl "http://127.0.0.1:8000/api/v1/public/user-employments" \
    -H "Content-Type: application/json"
```

##### Notes

None


# **Create Employment**
##### Description

This endpoint returns the ...

##### URL

`https://talentaccelerator.dev/api/v1/user-employments`

##### Method

`POST`

##### URL Params

None

##### Data Params

Parameter | Required | Description
--------- | ------- | -----------
`company_name` | Yes | The company name of the employment record.
`city` | Yes | The city of the employment record.
`province` | Yes | The province of the employment record.
`country` | Yes | The country of the employment record.
`title` | Yes | The title of the employment record.
`from_time` | No | The start
`to_time` | No | A xxx
`is_still_employed_there` | No | A xxx
`description` | No | A xxx


##### Success Response

  * **Status**: `200`
  * **Content**:
    ```json
    {
        "id": 3,
        "uuid": "90ecb734-40f2-4c39-9676-a8a248895ae7",
        "tenant_id": 1,
        "user_id": 1,
        "company_name": "BCI Innovation Labs",
        "city": "London",
        "province": "Ontario",
        "country": "Canada",
        "title": "Web Developer",
        "from_time": "1989-12-31T19:00:00-05:00",
        "to_time": "1989-12-31T19:00:00-05:00",
        "is_still_employed_there": true,
        "description": "This is a sample.",
        "state": 1,
        "created_time": "2022-04-07T22:05:44.282947-04:00",
        "modified_time": "2022-04-07T22:05:44.282947-04:00"
    }
    ```

##### Sample Call

Run the following in your terminal:

```shell
curl -X POST -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"company_name":"BCI Innovation Labs","city":"London","province":"Ontario","country":"Canada","title":"Web Developer","from_time":"1990-01-01T00:00:00Z","to_time":"1990-01-01T00:00:00Z","is_still_employed_there":"true","description":"This is a sample."}' \
     https://talentaccelerator.dev/api/v1/user-employments
```

**OR**

```shell
curl -X POST -H "Content-Type: application/json" \
    -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
    -d '{"company_name":"BCI Innovation Labs","city":"London","province":"Ontario","country":"Canada","title":"Web Developer","from_time":"1990-01-01T00:00:00Z","to_time":"1990-01-01T00:00:00Z","is_still_employed_there":"true","description":"This is a sample."}' \
     http://localhost:8000/api/v1/user-employments
```

# **Retrieve Public User Employment**

##### Description

This endpoint will return the user public employment detail.

##### URL

`https://talentaccelerator.dev/api/v1/public/user-employment/1234`

##### Method

`GET`

##### URL Params

None

##### Data Params

None

##### Success Response

  * **Status**: `200`
  * **Content**:
    ```json
    {
        "id": 3,
        "uuid": "90ecb734-40f2-4c39-9676-a8a248895ae7",
        "tenant_id": 1,
        "user_id": 1,
        "company_name": "BCI Innovation Labs",
        "city": "London",
        "province": "Ontario",
        "country": "Canada",
        "title": "Web Developer",
        "from_time": "1989-12-31T19:00:00-05:00",
        "to_time": "1989-12-31T19:00:00-05:00",
        "is_still_employed_there": true,
        "description": "This is a sample.",
        "state": 1,
        "created_time": "2022-04-07T22:05:44.282947-04:00",
        "modified_time": "2022-04-07T22:05:44.282947-04:00"
    }
    ```

##### Sample Call

Run the following in your terminal:
```shell
curl "https://talentaccelerator.dev/api/v1/public/user-employment/1234" \
    -H "Content-Type: application/json"
```

**OR**

Run the following in your terminal for your **developer** instance:
```shell
curl "http://localhost:8000/api/v1/public/user-employment/1234" \
    -H "Content-Type: application/json"
```

##### Notes
If your anonymous and the user is `inactive` then you will get a `403 Forbidden` error. If you are the owner of the account, you will be granted access.

# **Update Employment**
##### Description

This endpoint ...

##### URL

`https://talentaccelerator.dev/api/v1/user-employment/1`

##### Method

`PUT`

##### URL Params

None

##### Data Params

Parameter | Required | Description
--------- | ------- | -----------
`company_name` | Yes | The company name of the employment record.
`city` | Yes | The city of the employment record.
`province` | Yes | The province of the employment record.
`country` | Yes | The country of the employment record.
`title` | Yes | The title of the employment record.
`from_time` | No | The start
`to_time` | No | A xxx
`is_still_employed_there` | No | A xxx
`description` | No | A xxx


##### Success Response

  * **Status**: `200`
  * **Content**:
    ```json
    {
        "id": 3,
        "uuid": "90ecb734-40f2-4c39-9676-a8a248895ae7",
        "tenant_id": 1,
        "user_id": 1,
        "company_name": "BCI Innovation Labs",
        "city": "London",
        "province": "Ontario",
        "country": "Canada",
        "title": "Web Developer",
        "from_time": "1989-12-31T19:00:00-05:00",
        "to_time": "1989-12-31T19:00:00-05:00",
        "is_still_employed_there": true,
        "description": "This is a sample.",
        "state": 1,
        "created_time": "2022-04-07T22:05:44.282947-04:00",
        "modified_time": "2022-04-07T22:05:44.282947-04:00"
    }
    ```

##### Sample Call

Run the following in your terminal:

```shell
curl -X PUT -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"company_name":"BCI Innovation Labs","city":"London","province":"Ontario","country":"Canada","title":"Web Developer","from_time":"1990-01-01T00:00:00Z","to_time":"1990-01-01T00:00:00Z","is_still_employed_there":true,"description":"This is a sample."}' \
     https://talentaccelerator.dev/api/v1/user-employment/1
```

**OR**

```shell
curl -X PUT -H "Content-Type: application/json" \
    -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
    -d '{"company_name":"BCI Innovation Labs","city":"London","province":"Ontario","country":"Canada","title":"Web Developer","from_time":"1990-01-01T00:00:00Z","to_time":"1990-01-01T00:00:00Z","is_still_employed_there":true,"description":"This is a sample."}' \
     http://localhost:8000/api/v1/user-employment/1
```

# **Delete User Employment**

##### Description

This endpoint will delete the user skill and return no content.

##### URL

`https://talentaccelerator.dev/api/v1/user-employment/1234`

##### Method

`DELETE`

##### URL Params

None

##### Data Params

None

##### Success Response

  * **Status**: `204`
  * **Content**:
    ```text
    No content
    ```

##### Sample Call

Run the following in your terminal:
```shell
curl -X DELETE "https://talentaccelerator.dev/api/v1/user-employment/1" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -H "Content-Type: application/json"
```

**OR**

Run the following in your terminal for your **developer** instance:
```shell
curl -X DELETE "http://localhost:8000/api/v1/user-employment/1" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -H "Content-Type: application/json"
```

##### Notes
If your anonymous and the user is `inactive` then you will get a `403 Forbidden` error. If you are the owner of the account, you will be granted access.
