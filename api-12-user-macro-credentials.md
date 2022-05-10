---
title: 'User Macro Credential Endpoints'
date: 2019-02-11T19:27:37+10:00
weight: 2
summary: "The API gateway deals with user educations."
---

The API gateway deals with providing access to user education and making changes.

# **Post Macro Credential Set**
##### Description

This endpoint returns the ...

##### URL

`https://talentaccelerator.dev/api/v1/user-macro-credentials`

##### Method

`POST`

##### URL Params

None

##### Data Params

Parameter | Required | Description
--------- | ------- | -----------
`title` | Yes | The title of the macro-credential which the diploma/certificate originates from.
`from_time` | Yes | The start date of when the user began the program. Example: `1990-01-01T00:00:00Z`.
`to_time` | Yes | The end date of when the user began the program. Example: `1990-01-01T00:00:00Z`.

##### Success Response

  * **Status**: `200`
  * **Content**:
    ```json
    {
        "id": 1,
        "uuid": "485bb0f1-9e5c-4a95-be87-caa31649734b",
        "tenant_id": 1,
        "user_id": 1,
        "title": "Degree in Computer Science",
        "from_time": "1989-12-31T19:00:00-05:00",
        "to_time": "1993-12-31T19:00:00-05:00",
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
     -d '{"title":"Degree in Computer Science","from_time":"1990-01-01T00:00:00Z","to_time":"1994-01-01T00:00:00Z"}' \
     https://talentaccelerator.dev/api/v1/user-macro-credentials
```

**OR**

```shell
curl -X POST -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"title":"Degree in Computer Science","from_time":"1990-01-01T00:00:00Z","to_time":"1994-01-01T00:00:00Z"}' \
     http://localhost:8000/api/v1/user-macro-credentials
```

# **Retrieve Public User Macro Credential**

##### Description

This endpoint will return the user public education detail.

##### URL

`https://talentaccelerator.dev/api/v1/public/user-macro-credential/1234`

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
        "title": "Computer Science",
        "from_time": "1989-12-31T19:00:00-05:00",
        "to_time": "1993-12-31T19:00:00-05:00",
        "state": 1,
        "created_time": "2022-04-07T18:19:35.63991-04:00",
        "modified_time": "2022-04-07T18:19:35.63991-04:00"
    }
    ```

##### Sample Call

Run the following in your terminal:
```shell
curl "https://talentaccelerator.dev/api/v1/public/user-macro-credential/1234" \
    -H "Content-Type: application/json"
```

**OR**

Run the following in your terminal for your **developer** instance:
```shell
curl "http://localhost:8000/api/v1/public/user-macro-credential/1234" \
    -H "Content-Type: application/json"
```

##### Notes
If your anonymous and the user is `inactive` then you will get a `403 Forbidden` error. If you are the owner of the account, you will be granted access.


# **Delete User Macro Credential**

##### Description

This endpoint will delete the user macro credential and return no content.

##### URL

`https://talentaccelerator.dev/api/v1/user-macro-credential/1234`

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
curl -X DELETE "https://talentaccelerator.dev/api/v1/user-macro-credential/1" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -H "Content-Type: application/json"
```

**OR**

Run the following in your terminal for your **developer** instance:
```shell
curl -X DELETE "http://localhost:8000/api/v1/user-macro-credential/1" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -H "Content-Type: application/json"
```

##### Notes
If your anonymous and the user is `inactive` then you will get a `403 Forbidden` error. If you are the owner of the account, you will be granted access.
