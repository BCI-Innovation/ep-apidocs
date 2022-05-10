---
title: 'User Language Endpoints'
date: 2019-02-11T19:27:37+10:00
weight: 2
summary: "The API gateway deals with user language."
---

The API gateway deals with providing access to user language and making changes.

# **Post Language**
##### Description

This endpoint returns the ...

##### URL

`https://talentaccelerator.dev/api/v1/user-languages`

##### Method

`POST`

##### URL Params

None

##### Data Params

Parameter | Required | Description
--------- | ------- | -----------
`text` | Yes | The text of the language.
`expertise` | Yes | The expertise level of the language. Pick between range of `1` to `3`.
`proficiency` | Yes | The proficiency level of the language. Pick between range of `1` to `5`. Please see [this link](https://corporatefinanceinstitute.com/resources/careers/resume/language-proficiency-levels/) for more details about the levels.

##### Success Response

  * **Status**: `200`
  * **Content**:
    ```json
    {
        "id": 1,
        "uuid": "9bbd87bb-f8af-46d3-9f23-d8ae9fbe311c",
        "tenant_id": 1,
        "user_id": 7,
        "text": "English",
        "proficiency": 5,
        "state": 1,
        "created_time": "2022-04-12T13:59:54.584907-04:00",
        "modified_time": "2022-04-12T13:59:54.584908-04:00"
    }
    ```

##### Sample Call

Run the following in your terminal:

```shell
curl -X POST -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"text": "English","proficiency":5,"expertise":3}' \
     https://talentaccelerator.dev/api/v1/user-languages
```

**OR**

```shell
curl -X POST -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"text": "English","proficiency":5,"expertise":3}' \
     http://localhost:8000/api/v1/user-languages
```

# **Retrieve Public User Language Detail**

##### Description

This endpoint will return the full user public details.

##### URL

`https://talentaccelerator.dev/api/v1/public/user-language/1234`

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
        "id": 1,
        "uuid": "9bbd87bb-f8af-46d3-9f23-d8ae9fbe311c",
        "tenant_id": 1,
        "user_id": 7,
        "text": "English",
        "proficiency": 5,
        "state": 1,
        "created_time": "2022-04-12T13:59:54.584907-04:00",
        "modified_time": "2022-04-12T13:59:54.584908-04:00"
    }
    ```

##### Sample Call

Run the following in your terminal:
```shell
curl "https://talentaccelerator.dev/api/v1/public/user-language/1" \
    -H "Content-Type: application/json"
```

**OR**

Run the following in your terminal for your **developer** instance:
```shell
curl "http://localhost:8000/api/v1/public/user-language/1" \
    -H "Content-Type: application/json"
```

##### Notes
If your anonymous and the user is `inactive` then you will get a `403 Forbidden` error. If you are the owner of the account, you will be granted access.

# **Update Language**
##### Description

This endpoint ...

##### URL

`https://talentaccelerator.dev/api/v1/user-language/1`

##### Method

`PUT`

##### URL Params

None

##### Data Params

Parameter | Required | Description
--------- | ------- | -----------
`text` | Yes | The text of the language.
`expertise` | Yes | The expertise level of the language. Pick between range of `1` to `3`.
`proficiency` | Yes | The proficiency level of the language. Pick between range of `1` to `5`. Please see [this link](https://corporatefinanceinstitute.com/resources/careers/resume/language-proficiency-levels/) for more details about the levels.

##### Success Response

  * **Status**: `200`
  * **Content**:
    ```json
    {
        "id": 1,
        "uuid": "9bbd87bb-f8af-46d3-9f23-d8ae9fbe311c",
        "tenant_id": 1,
        "user_id": 7,
        "text": "English",
        "proficiency": 5,
        "state": 1,
        "created_time": "2022-04-12T13:59:54.584907-04:00",
        "modified_time": "2022-04-12T13:59:54.584908-04:00"
    }
    ```

##### Sample Call

Run the following in your terminal:

```shell
curl -X PUT -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"text": "English","proficiency":5}' \
     https://talentaccelerator.dev/api/v1/user-language/1
```

**OR**

```shell
curl -X PUT -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"text": "English","proficiency":5}' \
     http://localhost:8000/api/v1/user-language/1
```

# **Delete User Language**

##### Description

This endpoint will delete the user language and return no content.

##### URL

`https://talentaccelerator.dev/api/v1/user-language/1234`

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
curl -X DELETE "https://talentaccelerator.dev/api/v1/user-language/1" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -H "Content-Type: application/json"
```

**OR**

Run the following in your terminal for your **developer** instance:
```shell
curl -X DELETE "http://localhost:8000/api/v1/user-language/1" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -H "Content-Type: application/json"
```

##### Notes
If your anonymous and the user is `inactive` then you will get a `403 Forbidden` error. If you are the owner of the account, you will be granted access.
