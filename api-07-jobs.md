---
title: 'Job Endpoints'
date: 2019-02-11T19:27:37+10:00
weight: 2
summary: "The API gateway deals with jobs."
---

The API gateway deals with providing access to user skill and making changes.

# **List Data**
##### Description
This endpoint will return a list of jobs.

##### URL

`https://talentaccelerator.dev/api/v1/public/jobs`

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
`category` | No | "" | The category to filter for.
`city` | No | "" | The city to filter for.
`province` | No | "" | The province to filter for.
`country` | No | "" | The country to filter for.
`salary` | No | "" | The salary to filter for.
`salary_type` | No | "" | The salary_type to filter for.
`company_id` | No | "" | The company_id to filter for.
`company_name` | No | "" | The company_name to filter for.
`is_full_time` | No | "" | The is_full_time to filter for.
`is_part_time` | No | "" | The is_part_time to filter for.
`is_freelancer` | No | "" | The is_freelancer to filter for.
`is_temporary` | No | "" | The is_temporary to filter for.
`is_for_all` | No | "" | The is_for_all to filter for.
`is_for_male` | No | "" | The is_for_male to filter for.
`is_for_female` | No | "" | The is_for_female to filter for.
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
        "next_cursor":59,
        "count":0,
        "results":[
            {
                "tenant_id":1,
                "id":60,
                "title":"Software Engineer",
                "vacancies":0,
                "salary":0,
                "salary_type":0,
                "state":1,
                "is_full_time":false,
                "is_part_time":false,
                "is_freelancer":false,
                "is_temporary":false,
                "is_for_all":false,
                "is_for_male":false,
                "is_for_female":false,
                "is_verified":false,
                "country":"Canada",
                "province":"ON",
                "city":"Ottawa",
                "external_url":"https://ca.indeed.com/viewjob?t=Software+Engineer\u0026c=Canonical\u0026l=Ottawa,+ON\u0026jk=c7a16ea3b5d97ed0\u0026rtk=1g27q1ie13kp0000\u0026from=rss",
                "category":"",
                "longitude":45.41117,
                "latitude":-75.69812,
                "company_id":54,
                "company_name":"Golang, Python, Android"
            }
        ]
    }
    ```

##### Sample Call

Run the following in your terminal:

```shell
curl "https://talentaccelerator.dev/api/v1/public/jobs" \
    -H "Content-Type: application/json"
```

**OR**

```shell
curl "http://127.0.0.1:8000/api/v1/public/jobs" \
    -H "Content-Type: application/json"
```

##### Notes

None

# **Post Job**
##### Description

This endpoint ...

##### URL

`https://talentaccelerator.dev/api/v1/jobs`

##### Method

`POST`

##### URL Params

None

##### Data Params

Parameter | Required | Description
--------- | ------- | -----------
`title` | Yes | xxx
`description` | Yes | xxx
`vacancies` | Yes | xxx
`salary` | Yes | xxx
`salary_type` | Yes | xxx
`is_full_time` | Yes | xxx
`is_part_time` | Yes | xxx
`is_freelancer` | Yes | xxx
`is_temporary` | Yes | xxx
`is_for_all` | Yes | xxx
`is_for_male` | Yes | xxx
`is_for_female` | Yes | xxx
`is_verified` | Yes | xxx
`country` | Yes | xxx
`province` | Yes | xxx
`city` | Yes | xxx
`address` | Yes | xxx

##### Success Response

  * **Status**: `200`
  * **Content**:
    ```json
    {}
    ```

##### Sample Call

Run the following in your terminal:

```shell
curl -X POST -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"title":"Computer Programmer","description":"xxx","vacancies":1,"salary":1500,"salary_type":1,"is_full_time":true,"is_part_time":true,"is_freelancer":true,"is_temporary":true,"is_for_all":true,"is_for_male":true,"is_for_female":true,"is_verified":true,"country":"xxx","province":"xxx","city":"xxx","address":"xxx"}' \
     https://talentaccelerator.dev/api/v1/jobs
```

**OR**

```shell
curl -X POST -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"title":"Computer Programmer","description":"Code in Golang and React.js","vacancies":1,"salary":1500,"salary_type":1,"is_full_time":true,"is_part_time":true,"is_freelancer":true,"is_temporary":true,"is_for_all":true,"is_for_male":true,"is_for_female":true,"is_verified":true,"country":"xxx","province":"xxx","city":"xxx","address":"xxx"}' \
     http://localhost:8000/api/v1/jobs
```

# **Retrieve Public Job Detail**

##### Description

This endpoint will return the full public job details.

##### URL

`https://talentaccelerator.dev/api/v1/public/job/1`

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
        "uuid": "5328b291-3ec5-4d02-aaf0-112f808cd966",
        "tenant_id": 1,
        "user_id": 2,
        "company_id": null,
        "company_name": "",
        "company_logo_image_url": null,
        "company_logo_image_s3_key": null,
        "company_logo_image_name": null,
        "title": "xxx",
        "description": "xxx",
        "summary": null,
        "vacancies": 1,
        "salary": 1500,
        "salary_type": 1,
        "state": 1,
        "is_full_time": true,
        "is_part_time": true,
        "is_freelancer": true,
        "is_temporary": true,
        "is_for_all": true,
        "is_for_male": true,
        "is_for_female": true,
        "is_verified": true,
        "country": "xxx",
        "province": "xxx",
        "city": "xxx",
        "address": "xxx",
        "minimum_education": "",
        "language": "",
        "category": "",
        "created_time": "2022-04-19T22:45:23.546535-04:00",
        "modified_time": "2022-04-19T22:45:23.546535-04:00"
    }
    ```

##### Sample Call

Run the following in your terminal:
```shell
curl "https://talentaccelerator.dev/api/v1/public/job/1" \
    -H "Content-Type: application/json"
```

**OR**

Run the following in your terminal for your **developer** instance:
```shell
curl "http://localhost:8000/api/v1/public/job/1" \
    -H "Content-Type: application/json"
```

##### Notes
If your anonymous and the user is `inactive` then you will get a `403 Forbidden` error. If you are the owner of the account, you will be granted access.

# **Update Job**
##### Description

This endpoint ...

##### URL

`https://talentaccelerator.dev/api/v1/job/1`

##### Method

`PUT`

##### URL Params

None

##### Data Params

Parameter | Required | Description
--------- | ------- | -----------
`title` | Yes | xxx
`description` | Yes | xxx
`vacancies` | Yes | xxx
`salary` | Yes | xxx
`salary_type` | Yes | xxx
`is_full_time` | Yes | xxx
`is_part_time` | Yes | xxx
`is_freelancer` | Yes | xxx
`is_temporary` | Yes | xxx
`is_for_all` | Yes | xxx
`is_for_male` | Yes | xxx
`is_for_female` | Yes | xxx
`is_verified` | Yes | xxx
`country` | Yes | xxx
`province` | Yes | xxx
`city` | Yes | xxx
`address` | Yes | xxx

##### Success Response

  * **Status**: `200`
  * **Content**:
    ```json
    {
    }
    ```

##### Sample Call

Run the following in your terminal:

```shell
curl -X PUT -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"title":"xxx","description":"xxx","vacancies":1,"salary":1500,"salary_type":1,"is_full_time":true,"is_part_time":true,"is_freelancer":true,"is_temporary":true,"is_for_all":true,"is_for_male":true,"is_for_female":true,"is_verified":true,"country":"xxx","province":"xxx","city":"xxx","address":"xxx"}' \
     https://talentaccelerator.dev/api/v1/job/1
```

**OR**

```shell
curl -X PUT -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
    -d '{"title":"xxx","description":"xxx","vacancies":1,"salary":1500,"salary_type":1,"is_full_time":true,"is_part_time":true,"is_freelancer":true,"is_temporary":true,"is_for_all":true,"is_for_male":true,"is_for_female":true,"is_verified":true,"country":"xxx","province":"xxx","city":"xxx","address":"xxx"}' \
     http://localhost:8000/api/v1/job/1
```


# **Delete Job**

##### Description

This endpoint will delete the user linked account and return no content.

##### URL

`https://talentaccelerator.dev/api/v1/job/1`

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
curl -X DELETE "https://talentaccelerator.dev/api/v1/job/1" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -H "Content-Type: application/json"
```

**OR**

Run the following in your terminal for your **developer** instance:
```shell
curl -X DELETE "http://localhost:8000/api/v1/job/1" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -H "Content-Type: application/json"
```

##### Notes
If your anonymous and the user is `inactive` then you will get a `403 Forbidden` error. If you are the owner of the account, you will be granted access.
