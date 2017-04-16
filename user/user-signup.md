# 회원가입 {#회원가입}

Create user

**URL :**`/users`

**Method :**`POST`

**EX :**`https://<domain name>/api/v1/users`

## Request {#request}

### Headers {#headers}

`None`

### Body {#body}

#### Parameters {#parameters}

* email\(required\) : 이메일, String

* password\(required\) : 비밀번호, String

## Responses {#responses}

* HTTP Status : 201 - Created

  * Body

    ```
    {
    "token": "a35b9eb7e90d9ecdb5567183fb13f6b813cf2547"
    }
    ```

* HTTP Status : 400 - Bad Request

  * 필수항목 입력값 누락 : 이메일, 비밀번호

* HTTP Status : 409 - Conflict

  * 동일한 정보를 가지는 사용자가 이미 존재할 경우



