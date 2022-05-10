---
title: 'User Endpoints'
date: 2019-02-11T19:27:37+10:00
weight: 2
summary: "The API gateway deals with users making changes with their accounts."
---

The API gateway deals with providing access to public users and users making changes to their accounts.


# **Retrieve Public User Profile**

##### Description

This endpoint will return the full user public details.

##### URL

`https://talentaccelerator.dev/api/v1/public/user/1234`

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
curl "https://talentaccelerator.dev/api/v1/public/user/1234" \
    -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
    -H "Content-Type: application/json"
```

**OR**

Run the following in your terminal for your **developer** instance:
```shell
curl "http://localhost:8000/api/v1/public/user/1" \
    -H "Content-Type: application/json"
```

##### Notes
If your anonymous and the user is `inactive` then you will get a `403 Forbidden` error. If you are the owner of the account, you will be granted access.

# **Update About Yourself**
##### Description

This endpoint returns the user profile after updating the "About Yourself" section.

##### URL

`https://talentaccelerator.dev/api/v1/user/1/about-yourself`

##### Method

`PUT`

##### URL Params

None

##### Data Params

Parameter | Required | Description
--------- | ------- | -----------
`about_me` | Yes | The description of the user.

##### Success Response

  * **Status**: `200`
  * **Content**:
    ```json
    {"about_me":"I am a go getter!"}
    ```

##### Sample Call

Run the following in your terminal:

```shell
curl -X PUT -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"about_me": "I am a go getter!","open_for_founder":true,"open_for_freelance":true,"open_for_ft":true,"open_for_pt":true}' \
     https://talentaccelerator.dev/api/v1/user/1/about-yourself
```

**OR**

```shell
curl -X PUT -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"about_me": "I am a go getter!","open_for_founder":true,"open_for_freelance":true,"open_for_ft":true,"open_for_pt":true}' \
     http://localhost:8000/api/v1/user/1/about-yourself
```

# **Update Personal Details**
##### Description

This endpoint returns the user profile after updating the "Personal Details" section.

##### URL

`https://talentaccelerator.dev/api/v1/user/1/personal-details`

##### Method

`PUT`

##### URL Params

None

##### Data Params

Parameter | Required | Description
--------- | ------- | -----------
`email` | Yes | xxx.
`first_name` | Yes | xxx.
`middle_name` | No | xxx.
`last_name` | Yes | xxx.
`city` | Yes | xxx.
`province` | Yes | xxx.
`country` | Yes | xxx.
`country_tel_code` | Yes | xxx.
`telephone` | Yes | xxx.
`date_of_birth` | Yes | xxx.
`gender` | Yes | xxx.
`website` | Yes | xxx.

##### Success Response

  * **Status**: `200`
  * **Content**:
    ```json
    {
        "id": 1,
        "uuid": "46a43c8e-ef50-4b03-a51d-319521e97bb0",
        "email": "fherbert@dune.com",
        "first_name": "Frank",
        "last_name": "Herbert",
        "name": "Frank  Herbert",
        "lexical_name": "Herbert, , Frank",
        "state": 1,
        "timezone": "UTC",
        "language": "en",
        "country": "Canada",
        "country_tel_code": "1",
        "telephone": "123 456 7890",
        "agree_tos": true,
        "created_time": "2022-04-13T00:50:38.540943-04:00",
        "modified_time": "2022-04-13T00:52:17.681317-04:00",
        "joined_time": "2022-04-13T00:50:38.540943-04:00",
        "avatar_title": null,
        "avatar_file_url": null,
        "date_of_birth": "1989-12-31T19:00:00Z",
        "gender": "m",
        "about_me": null,
        "open_for_ft": null,
        "open_for_pt": null,
        "open_for_freelance": null,
        "open_for_founder": null,
        "website": "https://dune.com",
        "is_verified": false
    }
    ```

##### Sample Call

Run the following in your terminal:

```shell
curl -X PUT -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"email":"fherbert@dune.com","first_name":"Frank","middle_name":"","last_name":"Herbert","city":"London","province":"Ontario","country":"Canada","country_tel_code":"1","telephone":"123 456 7890","date_of_birth":"1989-12-31T19:00:00-05:00","gender":"m","website":"https://dune.com"}' \
     https://talentaccelerator.dev/api/v1/user/1/personal-details
```

**OR**

```shell
curl -X PUT -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"email":"fherbert@dune.com","first_name":"Frank","middle_name":"","last_name":"Herbert","city":"London","province":"Ontario","country":"Canada","country_tel_code":"1","telephone":"123 456 7890","date_of_birth":"1989-12-31T19:00:00-05:00","gender":"m","website":"https://dune.com"}' \
     http://localhost:8000/api/v1/user/1/personal-details
```
