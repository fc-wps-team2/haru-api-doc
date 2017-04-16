# 로그인 {#로그인}

Login

**URL :**`/users/login`

**Method :**`GET`

**URL example :**`https://<domain name>/api/v1/users/login`

## Request {#request}

### Headers {#headers}

`None`

### Body {#body}

* email\(required\) : 이메일, String

* password\(required\) : 비밀번호, String

## Responses {#responses}

* HTTP Status : 200 - OK

  * Body

    ```
    {
        "token": "a35b9eb7e90d9ecdb5567183fb13f6b813cf2547"
    }
    ```

* HTTP Status : 400 - Bad Request

  * 필수항목 입력값 누락 : 이메일, 비밀번호



