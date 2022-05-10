---
title: 'User Linked Account Endpoints'
date: 2019-02-11T19:27:37+10:00
weight: 2
summary: "The API gateway deals with user language."
---

The API gateway deals with providing access to user language and making changes.

# **Post Linked Account**
##### Description

This endpoint returns the ...

##### URL

`https://talentaccelerator.dev/api/v1/user-linked-accounts`

##### Method

`POST`

##### URL Params

None

##### Data Params

Parameter | Required | Description
--------- | ------- | -----------
`website_url` | Yes | The link to your public account profile.
`provider_id` | Yes | The account provider, values are found via [user_linked_account.go](https://github.com/BCI-Innovation/ep-backend/blob/main/pkg/models/user_linked_account.go).

##### Success Response

  * **Status**: `200`
  * **Content**:
    ```json
    {
        "id": 1,
        "uuid": "80b011ce-0826-4f6f-8956-d7a674ff6806",
        "tenant_id": 1,
        "user_id": 7,
        "website_url": "https://news.ycombinator.com/user?id=bartmika",
        "provider_id": 6,
        "state": 1,
        "created_time": "2022-04-12T14:32:52.293171-04:00",
        "modified_time": "2022-04-12T14:32:52.293172-04:00"
    }
    ```

##### Sample Call

Run the following in your terminal:

```shell
curl -X POST -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"website_url": "https://news.ycombinator.com/user?id=bartmika","provider_id":6}' \
     https://talentaccelerator.dev/api/v1/user-linked-accounts
```

**OR**

```shell
curl -X POST -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
    -d '{"website_url": "https://news.ycombinator.com/user?id=bartmika","provider_id":6}' \
     http://localhost:8000/api/v1/user-linked-accounts
```

# **Retrieve Public User Linked Account Detail**

##### Description

This endpoint will return the full user public details.

##### URL

`https://talentaccelerator.dev/api/v1/public/user-linked-account/1234`

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
        "uuid": "80b011ce-0826-4f6f-8956-d7a674ff6806",
        "tenant_id": 1,
        "user_id": 7,
        "website_url": "https://news.ycombinator.com/user?id=bartmika",
        "provider_id": 6,
        "state": 1,
        "created_time": "2022-04-12T14:32:52.293171-04:00",
        "modified_time": "2022-04-12T14:32:52.293172-04:00"
    }
    ```

##### Sample Call

Run the following in your terminal:
```shell
curl "https://talentaccelerator.dev/api/v1/public/user-linked-account/1" \
    -H "Content-Type: application/json"
```

**OR**

Run the following in your terminal for your **developer** instance:
```shell
curl "http://localhost:8000/api/v1/public/user-linked-account/1" \
    -H "Content-Type: application/json"
```

##### Notes
If your anonymous and the user is `inactive` then you will get a `403 Forbidden` error. If you are the owner of the account, you will be granted access.

# **Update Linked Account**
##### Description

This endpoint returns the ...

##### URL

`https://talentaccelerator.dev/api/v1/user-linked-account/1`

##### Method

`PUT`

##### URL Params

None

##### Data Params

Parameter | Required | Description
--------- | ------- | -----------
`website_url` | Yes | The link to your public account profile.
`provider_id` | Yes | The account provider, values are found via [user_linked_account.go](https://github.com/BCI-Innovation/ep-backend/blob/main/pkg/models/user_linked_account.go).

##### Success Response

  * **Status**: `200`
  * **Content**:
    ```json
    {
        "id": 1,
        "uuid": "80b011ce-0826-4f6f-8956-d7a674ff6806",
        "tenant_id": 1,
        "user_id": 7,
        "website_url": "https://news.ycombinator.com/user?id=bartmika",
        "provider_id": 6,
        "state": 1,
        "created_time": "2022-04-12T14:32:52.293171-04:00",
        "modified_time": "2022-04-12T14:32:52.293172-04:00"
    }
    ```

##### Sample Call

Run the following in your terminal:

```shell
curl -X PUT -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"website_url": "https://news.ycombinator.com/user?id=bartmika","provider_id":6}' \
     https://talentaccelerator.dev/api/v1/user-linked-account/1
```

**OR**

```shell
curl -X PUT -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
    -d '{"website_url": "https://news.ycombinator.com/user?id=bartmika","provider_id":6}' \
     http://localhost:8000/api/v1/user-linked-account/1
```


# **Delete User Linked Account**

##### Description

This endpoint will delete the user linked account and return no content.

##### URL

`https://talentaccelerator.dev/api/v1/user-linked-account/1234`

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
curl -X DELETE "https://talentaccelerator.dev/api/v1/user-linked-account/1" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -H "Content-Type: application/json"
```

**OR**

Run the following in your terminal for your **developer** instance:
```shell
curl -X DELETE "http://localhost:8000/api/v1/user-linked-account/1" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -H "Content-Type: application/json"
```

##### Notes
If your anonymous and the user is `inactive` then you will get a `403 Forbidden` error. If you are the owner of the account, you will be granted access.
