---
title: 'User Skill Endpoints'
date: 2019-02-11T19:27:37+10:00
weight: 2
summary: "The API gateway deals with user skills."
---

The API gateway deals with providing access to user skill and making changes.

# **List Data**
##### Description
This endpoint will return a list of public skills.

##### URL

`https://talentaccelerator.dev/api/v1/public/user-skills`

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
    {"count":6,"results":[{"id":6,"uuid":"f347c429-f308-4111-81c4-f706c0443cb0","tenant_id":1,"user_id":7,"name":"Programming","rating":5,"expertise":3,"state":1,"created_time":"2022-05-31T01:24:05.211076Z","modified_time":"2022-05-31T01:24:05.211076Z"},{"id":5,"uuid":"b7ebbe00-11c7-4e73-a2fd-38102fdffe13","tenant_id":1,"user_id":6,"name":"Postgres","rating":4,"expertise":2,"state":1,"created_time":"2022-05-27T19:38:06.067155Z","modified_time":"2022-05-27T19:38:06.067156Z"},{"id":4,"uuid":"3507f2ff-5fe0-40e1-af84-f9b41db8ee6b","tenant_id":1,"user_id":6,"name":"Python","rating":5,"expertise":3,"state":1,"created_time":"2022-05-27T19:37:49.738986Z","modified_time":"2022-05-27T19:37:49.738986Z"},{"id":3,"uuid":"ad84415f-ede1-4441-8b4b-543c63c8d843","tenant_id":1,"user_id":6,"name":"Golang","rating":4,"expertise":3,"state":1,"created_time":"2022-05-27T19:37:20.876342Z","modified_time":"2022-05-27T19:37:20.876342Z"},{"id":2,"uuid":"a028739a-cd10-43be-8ffe-63fcceaa633a","tenant_id":1,"user_id":3,"name":"Quality Assurance","rating":4,"expertise":2,"state":1,"created_time":"2022-05-27T04:32:28.135169Z","modified_time":"2022-05-27T04:32:28.135169Z"},{"id":1,"uuid":"19d3586d-b8d4-4674-94b1-b987c856d61e","tenant_id":1,"user_id":3,"name":"Software Engineering","rating":5,"expertise":3,"state":1,"created_time":"2022-05-27T04:32:16.1231Z","modified_time":"2022-05-27T04:32:16.1231Z"}]}
    ```

##### Sample Call

Run the following in your terminal:

```shell
curl "https://talentaccelerator.dev/api/v1/public/user-skills" \
    -H "Content-Type: application/json"
```

**OR**

```shell
curl "http://127.0.0.1:8000/api/v1/public/user-skills" \
    -H "Content-Type: application/json"
```

##### Notes

None


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
