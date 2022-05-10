---
title: 'User Operation Endpoints'
date: 2019-02-11T19:27:37+10:00
weight: 2
summary: "The API gateway deals with specific user operations."
---

The API gateway deals with providing access special operations for the user account.

# **Avatar Upload Operation**
##### Description
This endpoint uploads the user profile picture.

*Note (1): [This app](https://www.w3docs.com/tools/image-base64) which will convert images to `base64`.*

*Note (2): Replace `\u0026` with `&` in your `avatar_file_url"` field if it exists.*

##### URL

`https://talentaccelerator.dev/api/v1/user-operations/avatar`

##### Method

`POST`

##### URL Params

None

##### Required

None

##### Data Params

Field | Description
--------- | -----------
`upload_content` | The `base64` content of the image.
`upload_filename` | The file name of the image.

##### Success Response

  * **Status**: `200`
  * **Content**:
    ```json
    {
        "id": 1
    }
    ```

##### Sample Call

Run the following in your terminal:

```shell
curl -X POST \
     -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"upload_content":"xyz","upload_filename":"lalal.png"}' \
     https://talentaccelerator.dev/api/v1/user-operations
```

**OR**

```shell
curl -X POST \
     -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"upload_content":"xyz","upload_filename":"lalal.png"}' \
     http://127.0.0.1:8000/api/v1/user-operations/avatar
```

##### Notes
* To generate base64 string from a file for testing, [try this link](https://base64.guru/converter/encode/file).

* Here's a sample of a really small file. Copy and paste via: ``data:@file/x-icon;base64,AAABAAEAEBAAAAEACABoBQAAFgAAACgAAAAQAAAAIAAAAAEACAAAAAAAAAEAAAAAAAAAAAAAAAEAAAAAAACxnIgAvJqCADUpHwAMAAAAXldEAKOPdACNfWMAOS8WAGlXMgAqFgIALRMCABIDAAATAwAArI90AC8XBQDSuqIAXUQeANe0ogAWBgAAXFllAOSwnwBKR10AmoRvAD8QbQAwJg4AoIRmALOYfQDXnIgAyKyUAJ+GbAA8IgsAuZyAAJyLewDboY4AJBEGAAgAAQCKVEQADAABAI96ZACki3sANABrAOq/sQAPAwEAEgMBAGpVPwAhHSEAsI91AK6TeAByVzwAsJN4ANm6owCMckQAfndcABoKBACwloEAmYdwAK2TkwCzmH4AHwoEAJmIcwBMTlgAXVE0AHpygwCzm4cAjnRcAIp6XACiinAA0IdvALWfigCNeF8AoYx2AKWIcwDappUAdmJdAL6dhAAqL0UAvqKKAJV6ZQCEaUUAEgMCACkfDQCsk3kAUkoyAK2TeQCThWsAMxoHABkGAgCulHwAHAkCAHZdPQCzpHYALQFeAAEAAwBSPxsAoYx3AAkCAAC9n4IApZJ3ABAFAAC8pYsAMBYFAL6mjgDgq5wAFQUAAOKtmQD35NkASy0TAHlscwCHbVIAGQkDAJmEaQCwmIAAubajALSYgADZyaUAHw0GAJp+jQDHs5oAnYl4ACcVAwC7nokAu6CGACsUCQC/pIkAbVU5ABQCAQAvFgYAq5J4AEEzHQDDpYwAGggBAOaunQBOMBQANR0JAHNwgACzlnsAhHNcALSWewA3IAkAn4ZwAFQ0FwC3mn4AT1FbAK6SpQDmvKwAuJyEAJqCkQCkjHAAj3hiACgTBwC9n4QAKRMHAL6ghwA1AG8AzpR+AC0WBwARAwUAFAUCABgIAgAWCwIAopKdAJ9+YgB2XDQAmIRrAMSFdgCwm4IAHw4CAB8MBQDZnooAIA0IAEsmoQCynYgAcmdMAKCOdwAKAQAAdGpVAAwBAAC4oYsAEAEAAFNAKgA5AHAAKSQFAJuBWgAzFggAloFsADQbBQBFNBkAXEYqALKUdwA5GAUAsZV6AINyWwBiTSQAnIhvALqFkgAhDgMABAEBAFE5HwC1n4YAJBQDAL2agACAVrIAo454ACsSBgCmkHUAo5B+AIJ7iAA6NBoAvqOJAK2QdQAUBwEAr5N1ABgHAQDTv6YAsJV7AK+XgQBLMh0AXV5yAB0JBwAdCwQAx6ySAHRcSABKMiYATzQaALKYhAC0mX4AoYNqAMuhngB7XUIA6ramAIx1XABfUToAn412ADoqDwCLfWIAtZmZAAsHAgCqjHMAa1M3AL+ihwBlWz0AoIuUAL2lkABHHYkA0bynADIYBwColn8ANhYBADEbEAB5eWAAsZR5AAAAAAAAAAAAAAAAAAAAAAAAAAAAgBJf7JyoWyGaNQyuA11PKrOUlcSXGyhoQ1aesiOwnWLnTaYlOmYog3eC1H1c0tqfFoiTK3rlmUgOWHMLEse5jKuxNtubJLQUZGcibamK3wg7RJGFVfUXpLe9w6d+hLo90UqL4B9qKZAK+AnLHjPYBjBAQnjXzDyOEfdsLuTAUOlZf4nicc3ZhldvAD8sohC18FGNxXbOFUug8sb2AnK2GDJ0yHBHaxMt3qVl+uFSB04PktX5IDg+8TSRmPoa1rwd7hyq9K3zSd3vlq8NOQUvbrsnY3Ve489pe0wxob9TYaN8yr5BRo/r6kV50GAZ5lTorMHtWjfJwtwmgbgBh9HTBAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA=``.

# **CV Upload Operation**
##### Description
This endpoint uploads the user profile picture.

*Note (1): [This app](https://www.w3docs.com/tools/image-base64) which will convert images to `base64`.*

*Note (2): Replace `\u0026` with `&` in your `cv_file_url"` field if it exists.*

##### URL

`https://talentaccelerator.dev/api/v1/user-operations/cv`

##### Method

`POST`

##### URL Params

None

##### Required

None

##### Data Params

Field | Description
--------- | -----------
`upload_content` | The `base64` content of the image.
`upload_filename` | The file name of the image.

##### Success Response

  * **Status**: `200`
  * **Content**:
    ```json
    {
        "id": 1
    }
    ```

##### Sample Call

Run the following in your terminal:

```shell
curl -X POST \
     -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"upload_content":"xyz","upload_filename":"lalal.png"}' \
     https://talentaccelerator.dev/api/v1/user-operations/cv
```

**OR**

```shell
curl -X POST \
     -H "Content-Type: application/json" \
     -H "Authorization: Bearer $EMPLOYMENTPORTAL_ACCESS_TOKEN" \
     -d '{"upload_content":"xyz","upload_filename":"lalal.png"}' \
     http://127.0.0.1:8000/api/v1/user-operations/cv
```

##### Notes
* To generate base64 string from a file for testing, [try this link](https://base64.guru/converter/encode/file).

* Here's a sample of a really small file. Copy and paste via: ``data:@file/x-icon;base64,AAABAAEAEBAAAAEACABoBQAAFgAAACgAAAAQAAAAIAAAAAEACAAAAAAAAAEAAAAAAAAAAAAAAAEAAAAAAACxnIgAvJqCADUpHwAMAAAAXldEAKOPdACNfWMAOS8WAGlXMgAqFgIALRMCABIDAAATAwAArI90AC8XBQDSuqIAXUQeANe0ogAWBgAAXFllAOSwnwBKR10AmoRvAD8QbQAwJg4AoIRmALOYfQDXnIgAyKyUAJ+GbAA8IgsAuZyAAJyLewDboY4AJBEGAAgAAQCKVEQADAABAI96ZACki3sANABrAOq/sQAPAwEAEgMBAGpVPwAhHSEAsI91AK6TeAByVzwAsJN4ANm6owCMckQAfndcABoKBACwloEAmYdwAK2TkwCzmH4AHwoEAJmIcwBMTlgAXVE0AHpygwCzm4cAjnRcAIp6XACiinAA0IdvALWfigCNeF8AoYx2AKWIcwDappUAdmJdAL6dhAAqL0UAvqKKAJV6ZQCEaUUAEgMCACkfDQCsk3kAUkoyAK2TeQCThWsAMxoHABkGAgCulHwAHAkCAHZdPQCzpHYALQFeAAEAAwBSPxsAoYx3AAkCAAC9n4IApZJ3ABAFAAC8pYsAMBYFAL6mjgDgq5wAFQUAAOKtmQD35NkASy0TAHlscwCHbVIAGQkDAJmEaQCwmIAAubajALSYgADZyaUAHw0GAJp+jQDHs5oAnYl4ACcVAwC7nokAu6CGACsUCQC/pIkAbVU5ABQCAQAvFgYAq5J4AEEzHQDDpYwAGggBAOaunQBOMBQANR0JAHNwgACzlnsAhHNcALSWewA3IAkAn4ZwAFQ0FwC3mn4AT1FbAK6SpQDmvKwAuJyEAJqCkQCkjHAAj3hiACgTBwC9n4QAKRMHAL6ghwA1AG8AzpR+AC0WBwARAwUAFAUCABgIAgAWCwIAopKdAJ9+YgB2XDQAmIRrAMSFdgCwm4IAHw4CAB8MBQDZnooAIA0IAEsmoQCynYgAcmdMAKCOdwAKAQAAdGpVAAwBAAC4oYsAEAEAAFNAKgA5AHAAKSQFAJuBWgAzFggAloFsADQbBQBFNBkAXEYqALKUdwA5GAUAsZV6AINyWwBiTSQAnIhvALqFkgAhDgMABAEBAFE5HwC1n4YAJBQDAL2agACAVrIAo454ACsSBgCmkHUAo5B+AIJ7iAA6NBoAvqOJAK2QdQAUBwEAr5N1ABgHAQDTv6YAsJV7AK+XgQBLMh0AXV5yAB0JBwAdCwQAx6ySAHRcSABKMiYATzQaALKYhAC0mX4AoYNqAMuhngB7XUIA6ramAIx1XABfUToAn412ADoqDwCLfWIAtZmZAAsHAgCqjHMAa1M3AL+ihwBlWz0AoIuUAL2lkABHHYkA0bynADIYBwColn8ANhYBADEbEAB5eWAAsZR5AAAAAAAAAAAAAAAAAAAAAAAAAAAAgBJf7JyoWyGaNQyuA11PKrOUlcSXGyhoQ1aesiOwnWLnTaYlOmYog3eC1H1c0tqfFoiTK3rlmUgOWHMLEse5jKuxNtubJLQUZGcibamK3wg7RJGFVfUXpLe9w6d+hLo90UqL4B9qKZAK+AnLHjPYBjBAQnjXzDyOEfdsLuTAUOlZf4nicc3ZhldvAD8sohC18FGNxXbOFUug8sb2AnK2GDJ0yHBHaxMt3qVl+uFSB04PktX5IDg+8TSRmPoa1rwd7hyq9K3zSd3vlq8NOQUvbrsnY3Ve489pe0wxob9TYaN8yr5BRo/r6kV50GAZ5lTorMHtWjfJwtwmgbgBh9HTBAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA=``.
