---
title: 'Company Endpoints'
date: 2019-02-11T19:27:37+10:00
weight: 2
summary: "The API gateway deals with company."
---

The API gateway deals with providing access to user skill and making changes.

# **List**
##### Description
This endpoint will return a list of companies.

##### URL

`https://talentaccelerator.dev/api/v1/public/companies`

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

*Note (1): Query parameter inputted values must be **number of milliseconds since January 1, 1970 00:00:00** as found in the JavaScript [`getTime()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getTime) function.*

*Note (2): Try running `console.log(new Date().getTime())` in your console to get an example of how the query parameter inputted value looks like.*

##### Data Params

None

##### Success Response

  * **Status**: `200`
  * **Content**:
    ```json
    {
        "next_id": 1,
        "count": 1,
        "results": [
            {
                "tenant_id": 1,
                "id": 1,
                "name": "xxx"
            }
        ]
    }
    ```

##### Sample Call

Run the following in your terminal:

```shell
curl "https://talentaccelerator.dev/api/v1/public/companies" \
    -H "Content-Type: application/json"
```

**OR**

```shell
curl "http://127.0.0.1:8000/api/v1/public/companies" \
    -H "Content-Type: application/json"
```

##### Notes

None

# **Create**
##### Description

This endpoint returns the ...

##### URL

`https://talentaccelerator.dev/api/v1/companies`

##### Method

`POST`

##### URL Params

None

##### Data Params

Parameter | Required | Description
--------- | ------- | -----------
`name` | Yes | The name of the skill.
`website_url` | no | The website URL of the company.
`logo_image_external_url` | Yes | xxx.
`upload_content` | No | xxx.
`upload_filename` | No | xxx.
`employees_count` | No | xxx.

##### Success Response

  * **Status**: `200`
  * **Content**:
    ```json
    {
        "id":19656,
        "uuid":"f4027092-ece0-45f0-9c5b-ce08978921aa",
        "tenant_id":1,
        "name":"BCI Innovation Labs",
        "website_url":"https://bci.institute",
        "logo_image_external_url":"https://biometricscloud-apidocs-html-6kpru.ondigitalocean.app/bci.png",
        "logo_image_s3_key":null,
        "logo_image_name":null,
        "employees_count":0,
        "state":0,
        "created_time":"2022-04-30T01:25:00.270003-04:00",
        "modified_time":"2022-04-30T01:25:00.270003-04:00"
    }
    ```

##### Sample Call

Run the following in your terminal:

```shell
curl -X POST -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"name": "Golang","expertise":3,"rating":5}' \
     https://talentaccelerator.dev/api/v1/companies
```

**OR**

```shell
curl -X POST -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"name": "BCI Innovation Labs","logo_image_external_url":"https://biometricscloud-apidocs-html-6kpru.ondigitalocean.app/bci.png","website_url":"https://bci.institute"}' \
     http://localhost:8000/api/v1/companies
```

# **Retrieve Detail**

##### Description

This endpoint will return the full user public details.

##### URL

`https://talentaccelerator.dev/api/v1/public/company/1234`

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
        "id":19656,
        "uuid":"f4027092-ece0-45f0-9c5b-ce08978921aa",
        "tenant_id":1,
        "name":"BCI Innovation Labs",
        "website_url":"https://bci.institute",
        "logo_image_external_url":"https://biometricscloud-apidocs-html-6kpru.ondigitalocean.app/bci.png",
        "logo_image_s3_key":null,
        "logo_image_name":null,
        "employees_count":0,
        "state":0,
        "created_time":"2022-04-30T01:25:00.270003-04:00",
        "modified_time":"2022-04-30T01:25:00.270003-04:00"
    }
    ```

##### Sample Call

Run the following in your terminal:
```shell
curl "https://talentaccelerator.dev/api/v1/public/company/1" \
    -H "Content-Type: application/json"
```

**OR**

Run the following in your terminal for your **developer** instance:
```shell
curl "http://localhost:8000/api/v1/public/company/1" \
    -H "Content-Type: application/json"
```

##### Notes
If your anonymous and the user is `inactive` then you will get a `403 Forbidden` error. If you are the owner of the account, you will be granted access.

# **Update Skill**
##### Description

This endpoint ...

##### URL

`https://talentaccelerator.dev/api/v1/company/1`

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
     https://talentaccelerator.dev/api/v1/company/1
```

**OR**

```shell
curl -X PUT -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"name": "Golang","expertise":3,"rating":5}' \
     http://localhost:8000/api/v1/company/1
```

# **Delete Company**

##### Description

This endpoint will delete the user skill and return no content.

##### URL

`https://talentaccelerator.dev/api/v1/company/1234`

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
curl -X DELETE "https://talentaccelerator.dev/api/v1/company/1" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -H "Content-Type: application/json"
```

**OR**

Run the following in your terminal for your **developer** instance:
```shell
curl -X DELETE "http://localhost:8000/api/v1/company/1" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -H "Content-Type: application/json"
```

##### Notes
If your anonymous and the user is `inactive` then you will get a `403 Forbidden` error. If you are the owner of the account, you will be granted access.
