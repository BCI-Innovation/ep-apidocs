---
title: 'User Education Endpoints'
date: 2019-02-11T19:27:37+10:00
weight: 2
summary: "The API gateway deals with user educations."
---

The API gateway deals with providing access to user education and making changes.


# **List Data**
##### Description
This endpoint will return a list of public users.

##### URL

`https://talentaccelerator.dev/api/v1/public/user-educations`

##### Method

`GET`

##### URL Params

Query Parameters | Required | Default | Description
--------- | ----------- | ----------- | -----------
`cursor` | No | 0 | The cursor of the record in the list which will be used as to filter any records less then this value.
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
    {"count":1,"results":[{"id":1,"uuid":"e43872f6-d9f9-4ce6-b992-7114b3bd19a1","tenant_id":1,"user_id":3,"school_name":"University of Western Ontario","from_time":"2020-01-24T22:45:22-05:00","to_time":"2022-01-24T22:45:22-05:00","degree_name":"Biology","field_of_study":"Science","description":null,"state":1,"created_time":"2022-05-30T20:39:28.50809-04:00","modified_time":"2022-05-30T20:39:28.50809-04:00"}]}
    ```

##### Sample Call

Run the following in your terminal:

```shell
curl "https://talentaccelerator.dev/api/v1/public/user-educations" \
    -H "Content-Type: application/json"
```

**OR**

```shell
curl "http://127.0.0.1:8000/api/v1/public/user-educations" \
    -H "Content-Type: application/json"
```

##### Notes

None


# **Post Education**
##### Description

This endpoint returns the ...

##### URL

`https://talentaccelerator.dev/api/v1/user-educations`

##### Method

`POST`

##### URL Params

None

##### Data Params

Parameter | Required | Description
--------- | ------- | -----------
`school_name` | Yes | The name of the school which the diploma/certificate originates from.
`from_time` | Yes | The start date of when the user began the program. Must be [ISO 8601 Format](https://en.wikipedia.org/wiki/ISO_8601). Example: `2020-01-24T22:45:22-05:00`.
`to_time` | Yes | The end date of when the user began the program. Must be [ISO 8601 Format](https://en.wikipedia.org/wiki/ISO_8601). Example: `2020-01-24T22:45:22-05:00`.
`degree_name` | Yes | The official name of the diploma/certificate.
`field_of_study` | Yes | The field of study this diploma/certificate belongs to.
`description` | No | A description of the program.


##### Success Response

  * **Status**: `200`
  * **Content**:
    ```json
    {
        "id": 1,
        "uuid": "485bb0f1-9e5c-4a95-be87-caa31649734b",
        "tenant_id": 1,
        "user_id": 1,
        "school_name": "University of Western Ontario",
        "from_time": "1989-12-31T19:00:00-05:00",
        "to_time": "1993-12-31T19:00:00-05:00",
        "degree_name": "Biology",
        "field_of_study": "Science",
        "description": null,
        "state": 1,
        "created_time": "2022-04-07T18:19:35.63991-04:00",
        "modified_time": "2022-04-07T18:19:35.63991-04:00"
    }
    ```

##### Sample Call

Run the following in your terminal:

```shell
curl -X POST -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"school_name":"University of Western Ontario","from_time":"2020-01-24T22:45:22-05:00","to_time":"2022-01-24T22:45:22-05:00","degree_name":"Biology","field_of_study":"Science"}' \
     https://talentaccelerator.dev/api/v1/user-educations
```

**OR**

```shell
curl -X POST -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"school_name":"University of Western Ontario","from_time":"2020-01-24T22:45:22-05:00","to_time":"2022-01-24T22:45:22-05:00","degree_name":"Biology","field_of_study":"Science"}' \
     http://localhost:8000/api/v1/user-educations
```

# **Retrieve Public User Education**

##### Description

This endpoint will return the user public education detail.

##### URL

`https://talentaccelerator.dev/api/v1/public/user-education/1234`

##### Method

`GET`

##### URL Params

None

##### Data Params

None

##### Success Response

  * **Status**: `200`
  * **Content**:
    ```text
    {
        "id": 1,
        "uuid": "485bb0f1-9e5c-4a95-be87-caa31649734b",
        "tenant_id": 1,
        "user_id": 1,
        "school_name": "University of Western Ontario",
        "from_time": "1989-12-31T19:00:00-05:00",
        "to_time": "1993-12-31T19:00:00-05:00",
        "degree_name": "Biology",
        "field_of_study": "Science",
        "description": null,
        "state": 1,
        "created_time": "2022-04-07T18:19:35.63991-04:00",
        "modified_time": "2022-04-07T18:19:35.63991-04:00"
    }
    ```

##### Sample Call

Run the following in your terminal:
```shell
curl "https://talentaccelerator.dev/api/v1/public/user-education/1234" \
    -H "Content-Type: application/json"
```

**OR**

Run the following in your terminal for your **developer** instance:
```shell
curl "http://localhost:8000/api/v1/public/user-education/1234" \
    -H "Content-Type: application/json"
```

##### Notes
If your anonymous and the user is `inactive` then you will get a `403 Forbidden` error. If you are the owner of the account, you will be granted access.

# **Update Education**
##### Description

This endpoint ...

##### URL

`https://talentaccelerator.dev/api/v1/user-education/1`

##### Method

`PUT`

##### URL Params

None

##### Data Params

Parameter | Required | Description
--------- | ------- | -----------
`school_name` | Yes | The name of the school which the diploma/certificate originates from.
`from_time` | Yes | The start date of when the user began the program. Example: `May 1, 2020 12:00 am`.
`to_time` | Yes | The end date of when the user began the program. Example: `May 1, 2020 12:00 am`.
`degree_name` | Yes | The official name of the diploma/certificate.
`field_of_study` | Yes | The field of study this diploma/certificate belongs to.
`description` | No | A description of the program.


##### Success Response

  * **Status**: `200`
  * **Content**:
    ```json
    {
        "id": 1,
        "uuid": "485bb0f1-9e5c-4a95-be87-caa31649734b",
        "tenant_id": 1,
        "user_id": 1,
        "school_name": "University of Western Ontario",
        "from_time": "1989-12-31T19:00:00-05:00",
        "to_time": "1993-12-31T19:00:00-05:00",
        "degree_name": "Biology",
        "field_of_study": "Science",
        "description": null,
        "state": 1,
        "created_time": "2022-04-07T18:19:35.63991-04:00",
        "modified_time": "2022-04-07T18:19:35.63991-04:00"
    }
    ```

##### Sample Call

Run the following in your terminal:

```shell
curl -X PUT -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"school_name":"University of Western Ontario","from_time":"May 1, 2020 12:00 am","to_time":"May 1, 2022 12:00 am","degree_name":"Biology","field_of_study":"Science"}' \
     https://talentaccelerator.dev/api/v1/user-education/1
```

**OR**

```shell
curl -X PUT -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"school_name":"University of Western Ontario","from_time":"May 1, 2020 12:00 am","to_time":"May 1, 2022 12:00 am","degree_name":"Biology","field_of_study":"Science"}' \
     http://localhost:8000/api/v1/user-education/1
```


# **Delete User Education**

##### Description

This endpoint will delete the user education and return no content.

##### URL

`https://talentaccelerator.dev/api/v1/user-education/1234`

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
curl -X DELETE "https://talentaccelerator.dev/api/v1/user-education/1" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -H "Content-Type: application/json"
```

**OR**

Run the following in your terminal for your **developer** instance:
```shell
curl -X DELETE "http://localhost:8000/api/v1/user-education/1" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -H "Content-Type: application/json"
```

##### Notes
If your anonymous and the user is `inactive` then you will get a `403 Forbidden` error. If you are the owner of the account, you will be granted access.
