# 사용자 프로필 수정

Update User Profile

**URL :** `/users`

**Method :** `PATCH`

**URL example :** `https://<domain name>/api/users`

## Request

### Headers

    {
        "token": "a35b9eb7e90d9ecdb5567183fb13f6b813cf2547"
    }

### Body

-   email(required) : 이메일, String

-   password(required) : 비밀번호, String

## Responses

-   HTTP Status : 200 - OK

    -   Body

            {
                "id": 1,
                "email":"<email>",
                "password": "<password>",
                "created_date": "2017-04-14T11:06:21.000Z"
            }

-   HTTP Status : 400 - Bad Request

    -   필수항목 입력값 누락 : 이메일, 비밀번호

-   HTTP Status : 401 - Unauthorized

    -   유효하지 않은 Token으로 요청함
