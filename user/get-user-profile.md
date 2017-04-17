# 사용자 프로필 보기

Get User Profile

**URL :** `/users`

**Method :** `GET`

**URL example :** `https://<domain name>/api/users`

## Request

### Headers

    {
        "token": "a35b9eb7e90d9ecdb5567183fb13f6b813cf2547"
    }

### Body

`None`

## Responses

-   HTTP Status : 200 - OK

    -   Body

            {
                "id": 1,
                "email":"<email>",
                "password": "<password>",
                "created_date": "2017-04-14T11:06:21.000Z"
            }

-   HTTP Status : 401 - Unauthorized

    -   유효하지 않은 Token으로 요청함
