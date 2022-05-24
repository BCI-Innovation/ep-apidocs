---
title: 'User Endpoints'
date: 2019-02-11T19:27:37+10:00
weight: 2
summary: "The API gateway deals with users making changes with their accounts."
---

The API gateway deals with providing access to public users and users making changes to their accounts.


# **List Data**
##### Description
This endpoint will return a list of public users.

##### URL

`https://talentaccelerator.dev/api/v1/public/users`

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
`is_verified` | No | "" | The is_verified to filter for.

*Note (1): Query parameter inputted values must be **number of milliseconds since January 1, 1970 00:00:00** as found in the JavaScript [`getTime()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getTime) function.*

*Note (2): Try running `console.log(new Date().getTime())` in your console to get an example of how the query parameter inputted value looks like.*

##### Data Params

None

##### Success Response

  * **Status**: `200`
  * **Content**:
    ```json
    {
        "count":1,
        "results":[
            {
                "id":1,
                "uuid":"5125404d-7271-4993-913f-aee081089807",
                "tenant_id":1,
                "username":"fherbert",
                "email":"fherbert@dune.com",
                "first_name":"Frank",
                "last_name":"Herbert",
                "name":"Frank Herbert",
                "lexical_name":"Herbert, Frank",
                "state":1,
                "city":"London",
                "province":"Ontario",
                "country":"Canada",
                "country_tel_code":"1",
                "telephone":"(123) 456-7898",
                "avatar_file_url":null,
                "date_of_birth":null,
                "gender":null,
                "open_for_ft":null,
                "open_for_pt":null,
                "open_for_freelance":null,
                "open_for_founder":null,
                "is_verified":false
            }
        ]
    }
    ```

##### Sample Call

Run the following in your terminal:

```shell
curl "https://talentaccelerator.dev/api/v1/public/users" \
    -H "Content-Type: application/json"
```

**OR**

```shell
curl "http://127.0.0.1:8000/api/v1/public/users" \
    -H "Content-Type: application/json"
```

##### Notes

None


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
     -d '{"about_me": "I am a go getter!","open_for_founder":"true","open_for_freelance":"true","open_for_ft":"true","open_for_pt":"true"}' \
     https://talentaccelerator.dev/api/v1/user/1/about-yourself
```

```shell
curl -X PUT -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"about_me": "I am a go getter!","open_for_founder":"true","open_for_freelance":"true","open_for_ft":"true","open_for_pt":"true"}' \
     http://localhost:8000/api/v1/user/3/about-yourself
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
        "id":1,
        "uuid":"5125404d-7271-4993-913f-aee081089807",
        "email":"fherbert@dune.com",
        "first_name":"Frank",
        "last_name":"Herbert",
        "name":"Frank Herbert",
        "lexical_name":"Herbert, Frank",
        "state":1,
        "timezone":"UTC",
        "language":"en",
        "country":"Canada",
        "country_tel_code":"1",
        "telephone":"(123) 456-7898",
        "agree_tos":true,
        "created_time":"2022-05-09T23:56:23.003606-04:00",
        "modified_time":"2022-05-09T23:56:23.003607-04:00",
        "joined_time":"2022-05-09T23:56:23.003607-04:00",
        "avatar_title":null,
        "avatar_file_url":null,
        "cv_title":null,
        "cv_file_url":null,
        "date_of_birth":null,
        "gender":null,
        "about_me":null,
        "open_for_ft":null,
        "open_for_pt":null,
        "open_for_freelance":null,
        "open_for_founder":null,
        "website":null,
        "is_verified":false,
        "skills":[],
        "portfolios":[],
        "micro_credentials":[],
        "macro_credentials":[],
        "linked_accounts":[],
        "languages":[],
        "employment_history":[],
        "education_history":[]
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
