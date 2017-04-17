# 로그인

Login

**URL :** `/users/login`

**Method :** `POST`

**URL example :** `https://<domain name>/api/users/login`

**Running URL :** `http://haru-eb.ap-northeast-2.elasticbeanstalk.com/login/`

## Request

### Headers

`None`

### Body

-   email(required) : 이메일, String

-   password(required) : 비밀번호, String

## Responses

-   HTTP Status : 200 - OK

    -   Body

            {
                "token": "a35b9eb7e90d9ecdb5567183fb13f6b813cf2547"
            }

-   HTTP Status : 400 - Bad Request

    -   필수항목 입력값 누락 : 이메일, 비밀번호
