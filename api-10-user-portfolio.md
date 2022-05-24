---
title: 'User Portfolio Endpoints'
date: 2019-02-11T19:27:37+10:00
weight: 2
summary: "The API gateway deals with user portfolios."
---

The API gateway deals with providing access to user portfolio and making changes.

# **Post Portfolio**
##### Description

This endpoint returns the ...

##### URL

`https://talentaccelerator.dev/api/v1/user-portfolios`

##### Method

`POST`

##### URL Params

None

##### Data Params

Parameter | Required | Description
--------- | ------- | -----------
`name` | Yes | The name of the portfolio.
`category` | Yes | The type to order by
`upload_content` | Yes |The `base64` content of the image.
`upload_filename` | Yes | The file name of the image.
`website_url` | Yes | The URL of the website.

##### Success Response

  * **Status**: `200`
  * **Content**:
    ```json
    {"id":1,"uuid":"23574bc4-b2c8-42a3-9dbe-2e0c82d03194","tenant_id":1,"user_id":2,"name":"Employment Portal","category":"3","image_s3_key":null,"image_name":"lalal.png","image_url":"https://biometricscloud.nyc3.digitaloceanspaces.com/tenant/1/private/uploads/files/d26fefc0-1d25-45f5-bee7-3ca1b014445d-lalal.png?X-Amz-Algorithm=AWS4-HMAC-SHA256\u0026X-Amz-Credential=ECYCCCUHLER27NMNI5OE%2F20220414%2Fus-east-1%2Fs3%2Faws4_request\u0026X-Amz-Date=20220414T052037Z\u0026X-Amz-Expires=900\u0026X-Amz-SignedHeaders=host\u0026X-Amz-Signature=3761caebc6e98342a64bc04b639af3b06e1e392d37878c2a6c366b0b2bb82a46","website_url":"https://google.com","state":1,"created_time":"2022-04-14T01:17:53.892906-04:00","modified_time":"2022-04-14T01:17:53.892907-04:00"}
    ```

##### Sample Call

Run the following in your terminal:

```shell
curl -X POST -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"name": "Employment Portal","category":"3,"website_url":"https://google.com","upload_content":"xyz","upload_filename":"lalal.png"}' \
     https://talentaccelerator.dev/api/v1/user-portfolios
```

**OR**

```shell
curl -X POST -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"name": "Employment Portal","category":"3","website_url":"https://google.com","upload_content":"xyz","upload_filename":"lalal.png"}' \
     http://localhost:8000/api/v1/user-portfolios
```

##### Notes:

* To generate base64 string from a file for testing, [try this link](https://base64.guru/converter/encode/file).

* Here's a sample of a really small file. Copy and paste via: ``data:@file/x-icon;base64,AAABAAEAEBAAAAEACABoBQAAFgAAACgAAAAQAAAAIAAAAAEACAAAAAAAAAEAAAAAAAAAAAAAAAEAAAAAAACxnIgAvJqCADUpHwAMAAAAXldEAKOPdACNfWMAOS8WAGlXMgAqFgIALRMCABIDAAATAwAArI90AC8XBQDSuqIAXUQeANe0ogAWBgAAXFllAOSwnwBKR10AmoRvAD8QbQAwJg4AoIRmALOYfQDXnIgAyKyUAJ+GbAA8IgsAuZyAAJyLewDboY4AJBEGAAgAAQCKVEQADAABAI96ZACki3sANABrAOq/sQAPAwEAEgMBAGpVPwAhHSEAsI91AK6TeAByVzwAsJN4ANm6owCMckQAfndcABoKBACwloEAmYdwAK2TkwCzmH4AHwoEAJmIcwBMTlgAXVE0AHpygwCzm4cAjnRcAIp6XACiinAA0IdvALWfigCNeF8AoYx2AKWIcwDappUAdmJdAL6dhAAqL0UAvqKKAJV6ZQCEaUUAEgMCACkfDQCsk3kAUkoyAK2TeQCThWsAMxoHABkGAgCulHwAHAkCAHZdPQCzpHYALQFeAAEAAwBSPxsAoYx3AAkCAAC9n4IApZJ3ABAFAAC8pYsAMBYFAL6mjgDgq5wAFQUAAOKtmQD35NkASy0TAHlscwCHbVIAGQkDAJmEaQCwmIAAubajALSYgADZyaUAHw0GAJp+jQDHs5oAnYl4ACcVAwC7nokAu6CGACsUCQC/pIkAbVU5ABQCAQAvFgYAq5J4AEEzHQDDpYwAGggBAOaunQBOMBQANR0JAHNwgACzlnsAhHNcALSWewA3IAkAn4ZwAFQ0FwC3mn4AT1FbAK6SpQDmvKwAuJyEAJqCkQCkjHAAj3hiACgTBwC9n4QAKRMHAL6ghwA1AG8AzpR+AC0WBwARAwUAFAUCABgIAgAWCwIAopKdAJ9+YgB2XDQAmIRrAMSFdgCwm4IAHw4CAB8MBQDZnooAIA0IAEsmoQCynYgAcmdMAKCOdwAKAQAAdGpVAAwBAAC4oYsAEAEAAFNAKgA5AHAAKSQFAJuBWgAzFggAloFsADQbBQBFNBkAXEYqALKUdwA5GAUAsZV6AINyWwBiTSQAnIhvALqFkgAhDgMABAEBAFE5HwC1n4YAJBQDAL2agACAVrIAo454ACsSBgCmkHUAo5B+AIJ7iAA6NBoAvqOJAK2QdQAUBwEAr5N1ABgHAQDTv6YAsJV7AK+XgQBLMh0AXV5yAB0JBwAdCwQAx6ySAHRcSABKMiYATzQaALKYhAC0mX4AoYNqAMuhngB7XUIA6ramAIx1XABfUToAn412ADoqDwCLfWIAtZmZAAsHAgCqjHMAa1M3AL+ihwBlWz0AoIuUAL2lkABHHYkA0bynADIYBwColn8ANhYBADEbEAB5eWAAsZR5AAAAAAAAAAAAAAAAAAAAAAAAAAAAgBJf7JyoWyGaNQyuA11PKrOUlcSXGyhoQ1aesiOwnWLnTaYlOmYog3eC1H1c0tqfFoiTK3rlmUgOWHMLEse5jKuxNtubJLQUZGcibamK3wg7RJGFVfUXpLe9w6d+hLo90UqL4B9qKZAK+AnLHjPYBjBAQnjXzDyOEfdsLuTAUOlZf4nicc3ZhldvAD8sohC18FGNxXbOFUug8sb2AnK2GDJ0yHBHaxMt3qVl+uFSB04PktX5IDg+8TSRmPoa1rwd7hyq9K3zSd3vlq8NOQUvbrsnY3Ve489pe0wxob9TYaN8yr5BRo/r6kV50GAZ5lTorMHtWjfJwtwmgbgBh9HTBAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA=``.

# **Retrieve Public User Portfolio Detail**

##### Description

This endpoint will return the full user public details.

##### URL

`https://talentaccelerator.dev/api/v1/public/user-portfolio/1234`

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
    {"id":1,"uuid":"23574bc4-b2c8-42a3-9dbe-2e0c82d03194","tenant_id":1,"user_id":2,"name":"Employment Portal","category":3,"image_s3_key":null,"image_name":"lalal.png","image_url":"https://biometricscloud.nyc3.digitaloceanspaces.com/tenant/1/private/uploads/files/d26fefc0-1d25-45f5-bee7-3ca1b014445d-lalal.png?X-Amz-Algorithm=AWS4-HMAC-SHA256\u0026X-Amz-Credential=ECYCCCUHLER27NMNI5OE%2F20220414%2Fus-east-1%2Fs3%2Faws4_request\u0026X-Amz-Date=20220414T052037Z\u0026X-Amz-Expires=900\u0026X-Amz-SignedHeaders=host\u0026X-Amz-Signature=3761caebc6e98342a64bc04b639af3b06e1e392d37878c2a6c366b0b2bb82a46","website_url":"https://google.com","state":1,"created_time":"2022-04-14T01:17:53.892906-04:00","modified_time":"2022-04-14T01:17:53.892907-04:00"}
    ```

##### Sample Call

Run the following in your terminal:
```shell
curl "https://talentaccelerator.dev/api/v1/public/user-portfolio/1" \
    -H "Content-Type: application/json"
```

**OR**

Run the following in your terminal for your **developer** instance:
```shell
curl "http://localhost:8000/api/v1/public/user-portfolio/1" \
    -H "Content-Type: application/json"
```

##### Notes
If your anonymous and the user is `inactive` then you will get a `403 Forbidden` error. If you are the owner of the account, you will be granted access.

# **Update Portfolio**
##### Description

This endpoint returns the ...

##### URL

`https://talentaccelerator.dev/api/v1/user-portfolio/1`

##### Method

`PUT`

##### URL Params

None

##### Data Params

Parameter | Required | Description
--------- | ------- | -----------
`name` | Yes | The name of the portfolio.
`category` | Yes | The type to order by
`upload_content` | Yes |The `base64` content of the image.
`upload_filename` | Yes | The file name of the image.
`website_url` | Yes | The URL of the website.

##### Success Response

  * **Status**: `200`
  * **Content**:
    ```json
    {"id":1,"uuid":"23574bc4-b2c8-42a3-9dbe-2e0c82d03194","tenant_id":1,"user_id":2,"name":"Employment Portal","category":3,"image_s3_key":null,"image_name":"lalal.png","image_url":"https://biometricscloud.nyc3.digitaloceanspaces.com/tenant/1/private/uploads/files/d26fefc0-1d25-45f5-bee7-3ca1b014445d-lalal.png?X-Amz-Algorithm=AWS4-HMAC-SHA256\u0026X-Amz-Credential=ECYCCCUHLER27NMNI5OE%2F20220414%2Fus-east-1%2Fs3%2Faws4_request\u0026X-Amz-Date=20220414T052037Z\u0026X-Amz-Expires=900\u0026X-Amz-SignedHeaders=host\u0026X-Amz-Signature=3761caebc6e98342a64bc04b639af3b06e1e392d37878c2a6c366b0b2bb82a46","website_url":"https://google.com","state":1,"created_time":"2022-04-14T01:17:53.892906-04:00","modified_time":"2022-04-14T01:17:53.892907-04:00"}
    ```

##### Sample Call

Run the following in your terminal:

```shell
curl -X PUT -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"name": "Employment Portal","category":"3","website_url":"https://google.com","upload_content":"xyz","upload_filename":"lalal.png"}' \
     https://talentaccelerator.dev/api/v1/user-portfolio/1
```

**OR**

```shell
curl -X PUT -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"name": "Employment Portal","category":"3","website_url":"https://google.com","upload_content":"xyz","upload_filename":"lalal.png"}' \
     http://localhost:8000/api/v1/user-portfolio/1
```

##### Notes:

* To generate base64 string from a file for testing, [try this link](https://base64.guru/converter/encode/file).

* Here's a sample of a really small file. Copy and paste via: ``data:@file/x-icon;base64,AAABAAEAEBAAAAEACABoBQAAFgAAACgAAAAQAAAAIAAAAAEACAAAAAAAAAEAAAAAAAAAAAAAAAEAAAAAAACxnIgAvJqCADUpHwAMAAAAXldEAKOPdACNfWMAOS8WAGlXMgAqFgIALRMCABIDAAATAwAArI90AC8XBQDSuqIAXUQeANe0ogAWBgAAXFllAOSwnwBKR10AmoRvAD8QbQAwJg4AoIRmALOYfQDXnIgAyKyUAJ+GbAA8IgsAuZyAAJyLewDboY4AJBEGAAgAAQCKVEQADAABAI96ZACki3sANABrAOq/sQAPAwEAEgMBAGpVPwAhHSEAsI91AK6TeAByVzwAsJN4ANm6owCMckQAfndcABoKBACwloEAmYdwAK2TkwCzmH4AHwoEAJmIcwBMTlgAXVE0AHpygwCzm4cAjnRcAIp6XACiinAA0IdvALWfigCNeF8AoYx2AKWIcwDappUAdmJdAL6dhAAqL0UAvqKKAJV6ZQCEaUUAEgMCACkfDQCsk3kAUkoyAK2TeQCThWsAMxoHABkGAgCulHwAHAkCAHZdPQCzpHYALQFeAAEAAwBSPxsAoYx3AAkCAAC9n4IApZJ3ABAFAAC8pYsAMBYFAL6mjgDgq5wAFQUAAOKtmQD35NkASy0TAHlscwCHbVIAGQkDAJmEaQCwmIAAubajALSYgADZyaUAHw0GAJp+jQDHs5oAnYl4ACcVAwC7nokAu6CGACsUCQC/pIkAbVU5ABQCAQAvFgYAq5J4AEEzHQDDpYwAGggBAOaunQBOMBQANR0JAHNwgACzlnsAhHNcALSWewA3IAkAn4ZwAFQ0FwC3mn4AT1FbAK6SpQDmvKwAuJyEAJqCkQCkjHAAj3hiACgTBwC9n4QAKRMHAL6ghwA1AG8AzpR+AC0WBwARAwUAFAUCABgIAgAWCwIAopKdAJ9+YgB2XDQAmIRrAMSFdgCwm4IAHw4CAB8MBQDZnooAIA0IAEsmoQCynYgAcmdMAKCOdwAKAQAAdGpVAAwBAAC4oYsAEAEAAFNAKgA5AHAAKSQFAJuBWgAzFggAloFsADQbBQBFNBkAXEYqALKUdwA5GAUAsZV6AINyWwBiTSQAnIhvALqFkgAhDgMABAEBAFE5HwC1n4YAJBQDAL2agACAVrIAo454ACsSBgCmkHUAo5B+AIJ7iAA6NBoAvqOJAK2QdQAUBwEAr5N1ABgHAQDTv6YAsJV7AK+XgQBLMh0AXV5yAB0JBwAdCwQAx6ySAHRcSABKMiYATzQaALKYhAC0mX4AoYNqAMuhngB7XUIA6ramAIx1XABfUToAn412ADoqDwCLfWIAtZmZAAsHAgCqjHMAa1M3AL+ihwBlWz0AoIuUAL2lkABHHYkA0bynADIYBwColn8ANhYBADEbEAB5eWAAsZR5AAAAAAAAAAAAAAAAAAAAAAAAAAAAgBJf7JyoWyGaNQyuA11PKrOUlcSXGyhoQ1aesiOwnWLnTaYlOmYog3eC1H1c0tqfFoiTK3rlmUgOWHMLEse5jKuxNtubJLQUZGcibamK3wg7RJGFVfUXpLe9w6d+hLo90UqL4B9qKZAK+AnLHjPYBjBAQnjXzDyOEfdsLuTAUOlZf4nicc3ZhldvAD8sohC18FGNxXbOFUug8sb2AnK2GDJ0yHBHaxMt3qVl+uFSB04PktX5IDg+8TSRmPoa1rwd7hyq9K3zSd3vlq8NOQUvbrsnY3Ve489pe0wxob9TYaN8yr5BRo/r6kV50GAZ5lTorMHtWjfJwtwmgbgBh9HTBAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA=``.


# **Delete User Portfolio**

##### Description

This endpoint will delete the user portfolio and return no content.

##### URL

`https://talentaccelerator.dev/api/v1/user-portfolio/1234`

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
curl -X DELETE "https://talentaccelerator.dev/api/v1/user-portfolio/1" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -H "Content-Type: application/json"
```

**OR**

Run the following in your terminal for your **developer** instance:
```shell
curl -X DELETE "http://localhost:8000/api/v1/user-portfolio/1" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -H "Content-Type: application/json"
```

##### Notes
If your anonymous and the user is `inactive` then you will get a `403 Forbidden` error. If you are the owner of the account, you will be granted access.
