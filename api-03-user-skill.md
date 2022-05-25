---
title: 'User Skill Endpoints'
date: 2019-02-11T19:27:37+10:00
weight: 2
summary: "The API gateway deals with user skills."
---

The API gateway deals with providing access to user skill and making changes.

# **Post Skill**
##### Description

This endpoint returns the ...

##### URL

`https://talentaccelerator.dev/api/v1/user-skills`

##### Method

`POST`

##### URL Params

None

##### Data Params

Parameter | Required | Description
--------- | ------- | -----------
`name` | Yes | The name of the skill.
`expertise` | Yes | The expertise level of the skill. Pick between range of `1` to `3`.
`rating` | Yes | The rating level of the skill. Pick between range of `1` to `5`.

##### Success Response

  * **Status**: `200`
  * **Content**:
    ```json
    {"id":6,"uuid":"dddd5e72-a89f-4795-be1b-03ec8f9687c2","tenant_id":1,"user_id":1,"name":"Golang","rating":5,"expertise":3,"state":0,"created_time":"2022-04-07T01:30:48.974515-04:00","modified_time":"2022-04-07T01:30:48.974515-04:00"}
    ```

##### Sample Call

Run the following in your terminal:

```shell
curl -X POST -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"name": "Golang","expertise":"3","rating":"5"}' \
     https://talentaccelerator.dev/api/v1/user-skills
```

**OR**

```shell
curl -X POST -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"name": "Golang","expertise":"3","rating":"5"}' \
     http://localhost:8000/api/v1/user-skills
```

# **Retrieve Public User Skill Detail**

##### Description

This endpoint will return the full user public details.

##### URL

`https://talentaccelerator.dev/api/v1/public/user-skill/1234`

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
    Employment Portal Backend v1.0
    ```

##### Sample Call

Run the following in your terminal:
```shell
curl "https://talentaccelerator.dev/api/v1/public/user-skill/1" \
    -H "Content-Type: application/json"
```

**OR**

Run the following in your terminal for your **developer** instance:
```shell
curl "http://localhost:8000/api/v1/public/user-skill/1" \
    -H "Content-Type: application/json"
```

##### Notes
If your anonymous and the user is `inactive` then you will get a `403 Forbidden` error. If you are the owner of the account, you will be granted access.

# **Update Skill**
##### Description

This endpoint ...

##### URL

`https://talentaccelerator.dev/api/v1/user-skill/1`

##### Method

`PUT`

##### URL Params

None

##### Data Params

Parameter | Required | Description
--------- | ------- | -----------
`name` | Yes | The name of the skill.
`expertise` | Yes | The expertise level of the skill. Pick between range of `1` to `3`.
`rating` | Yes | The rating level of the skill. Pick between range of `1` to `5`.

##### Success Response

  * **Status**: `200`
  * **Content**:
    ```json
    {"id":6,"uuid":"dddd5e72-a89f-4795-be1b-03ec8f9687c2","tenant_id":1,"user_id":1,"name":"Golang","rating":5,"expertise":3,"state":0,"created_time":"2022-04-07T01:30:48.974515-04:00","modified_time":"2022-04-07T01:30:48.974515-04:00"}
    ```

##### Sample Call

Run the following in your terminal:

```shell
curl -X PUT -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"name": "Golang","expertise":3,"rating":5}' \
     https://talentaccelerator.dev/api/v1/user-skill/1
```

**OR**

```shell
curl -X PUT -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"name": "Golang","expertise":3,"rating":5}' \
     http://localhost:8000/api/v1/user-skill/1
```

# **Delete User Skill**

##### Description

This endpoint will delete the user skill and return no content.

##### URL

`https://talentaccelerator.dev/api/v1/user-skill/1234`

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
curl -X DELETE "https://talentaccelerator.dev/api/v1/user-skill/1" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -H "Content-Type: application/json"
```

**OR**

Run the following in your terminal for your **developer** instance:
```shell
curl -X DELETE "http://localhost:8000/api/v1/user-skill/1" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -H "Content-Type: application/json"
```

##### Notes
If your anonymous and the user is `inactive` then you will get a `403 Forbidden` error. If you are the owner of the account, you will be granted access.
