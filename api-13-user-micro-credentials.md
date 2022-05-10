---
title: 'User Micro Credential Endpoints'
date: 2019-02-11T19:27:37+10:00
weight: 2
summary: "The API gateway deals with user educations."
---

The API gateway deals with providing access to user education and making changes.

# **Post Micro Credential Set**
##### Description

This endpoint returns the ...

##### URL

`https://talentaccelerator.dev/api/v1/user-micro-credentials`

##### Method

`POST`

##### URL Params

None

##### Data Params

Parameter | Required | Description
--------- | ------- | -----------
`title` | Yes | The title of the micro-credential which the diploma/certificate originates from.
`issued` | Yes | The start date of when the user began the program. Example: `1990-01-01T00:00:00Z`.
`expires` | Yes | The end date of when the user began the program. Example: `1990-01-01T00:00:00Z`.

##### Success Response

  * **Status**: `200`
  * **Content**:
    ```json
    {"id":8,"uuid":"30b26dd1-49f8-40e2-8cc1-7b492e2cb0be","tenant_id":1,"user_id":2,"title":"Degree in Computer Science","issued":"1989-12-31T19:00:00-05:00","expires":"1993-12-31T19:00:00-05:00","website_url":"","state":1,"created_time":"2022-04-19T18:06:25.01283-04:00","modified_time":"2022-04-19T18:06:25.012831-04:00"}
    ```

##### Sample Call

Run the following in your terminal:

```shell
curl -X POST -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"title":"Degree in Computer Science","issued":"1990-01-01T00:00:00Z","expires":"1994-01-01T00:00:00Z"}' \
     https://talentaccelerator.dev/api/v1/user-micro-credentials
```

**OR**

```shell
curl -X POST -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"title":"Degree in Computer Science","issued":"1990-01-01T00:00:00Z","expires":"1994-01-01T00:00:00Z","website_url":"https://uwo.ca"}' \
     http://localhost:8000/api/v1/user-micro-credentials
```

# **Retrieve Public User Micro Credential**

##### Description

This endpoint will return the user public education detail.

##### URL

`https://talentaccelerator.dev/api/v1/public/user-micro-credential/1234`

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
    {"id":8,"uuid":"30b26dd1-49f8-40e2-8cc1-7b492e2cb0be","tenant_id":1,"user_id":2,"title":"Degree in Computer Science","issued":"1989-12-31T19:00:00-05:00","expires":"1993-12-31T19:00:00-05:00","website_url":"","state":1,"created_time":"2022-04-19T18:06:25.01283-04:00","modified_time":"2022-04-19T18:06:25.012831-04:00"}
    ```

##### Sample Call

Run the following in your terminal:
```shell
curl "https://talentaccelerator.dev/api/v1/public/user-micro-credential/1234" \
    -H "Content-Type: application/json"
```

**OR**

Run the following in your terminal for your **developer** instance:
```shell
curl "http://localhost:8000/api/v1/public/user-micro-credential/1234" \
    -H "Content-Type: application/json"
```

##### Notes
If your anonymous and the user is `inactive` then you will get a `403 Forbidden` error. If you are the owner of the account, you will be granted access.

# **Delete User Micro Credential**

##### Description

This endpoint will delete the user micro credential and return no content.

##### URL

`https://talentaccelerator.dev/api/v1/user-micro-credential/1234`

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
curl -X DELETE "https://talentaccelerator.dev/api/v1/user-micro-credential/1" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -H "Content-Type: application/json"
```

**OR**

Run the following in your terminal for your **developer** instance:
```shell
curl -X DELETE "http://localhost:8000/api/v1/user-micro-credential/1" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -H "Content-Type: application/json"
```

##### Notes
If your anonymous and the user is `inactive` then you will get a `403 Forbidden` error. If you are the owner of the account, you will be granted access.
