# 회원가입

Create User

**URL :** `/signup/`

**Method :** `POST`

**URL example :** `https://<domain name>/singup/`

**Running URL :**

`http://haru-eb.ap-northeast-2.elasticbeanstalk.com/signup/`

`https://haru.ycsinabro.com/singup/`

## Request

### Headers

`None`

### Body

key          | value           | type   | description
------------ | --------------- | ------ | -----------
**email**    | (user email)    | string | 필수
**password** | (user password) | string | 필수

## Responses

- HTTP Status : 201 - Created

  - Body

    ```json
    {
      "id": 1,
      "email": "<email>"
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

  - 동일한 정보를 가지는 사용자가 이미 존재할 경우

    ```json
    {
        "email": [
          "This field must be unique."
        ]
    }
    ```
