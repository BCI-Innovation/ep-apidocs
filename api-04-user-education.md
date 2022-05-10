---
title: 'User Education Endpoints'
date: 2019-02-11T19:27:37+10:00
weight: 2
summary: "The API gateway deals with user educations."
---

The API gateway deals with providing access to user education and making changes.

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
`from_time` | Yes | The start date of when the user began the program. Example: `1990-01-01T00:00:00Z`.
`to_time` | Yes | The end date of when the user began the program. Example: `1990-01-01T00:00:00Z`.
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
     -d '{"school_name":"University of Western Ontario","from_time":"1990-01-01T00:00:00Z","to_time":"1994-01-01T00:00:00Z","degree_name":"Biology","field_of_study":"Science"}' \
     https://talentaccelerator.dev/api/v1/user-educations
```

**OR**

```shell
curl -X POST -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"school_name":"University of Western Ontario","from_time":"1990-01-01T00:00:00Z","to_time":"1994-01-01T00:00:00Z","degree_name":"Biology","field_of_study":"Science"}' \
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
`from_time` | Yes | The start date of when the user began the program. Example: `1990-01-01T00:00:00Z`.
`to_time` | Yes | The end date of when the user began the program. Example: `1990-01-01T00:00:00Z`.
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
     -d '{"school_name":"University of Western Ontario","from_time":"1990-01-01T00:00:00Z","to_time":"1994-01-01T00:00:00Z","degree_name":"Biology","field_of_study":"Science"}' \
     https://talentaccelerator.dev/api/v1/user-education/1
```

**OR**

```shell
curl -X PUT -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"school_name":"University of Western Ontario","from_time":"1990-01-01T00:00:00Z","to_time":"1994-01-01T00:00:00Z","degree_name":"Biology","field_of_study":"Science"}' \
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
