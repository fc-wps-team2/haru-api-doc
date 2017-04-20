# 로그인

**Login**

**URL :** `/login/`

`https://<domain name>/login/`

**Method :** `POST`

**Running URL :**

`http://haru-eb.ap-northeast-2.elasticbeanstalk.com/login/`

or

`https://haru.ycsinabro.com/login/`

## Request

### Headers

`None`

### Body

key          | value           | type   | description
------------ | --------------- | ------ | -----------
**email**    | (user email)    | string | 필수
**password** | (user password) | string | 필수

## Responses

- HTTP Status : 200 - OK

  - Body

    ```json
    {
      "key": "a35b9eb7e90d9ecdb5567183fb13f6b813cf2547"
    }
    ```

- HTTP Status : 400 - Bad Request

  - 필수항목 입력값 누락 : 이메일, 비밀번호

    ```json
    {
      "email": [
        "This field may not be blank."
      ],
      "password": [
        "This field may not be blank."
      ]
    }
    ```

- HTTP Status : 500 - Internal Server Error

  - 입력값 오류 : 이메일, 비밀번호
