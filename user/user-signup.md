# 회원가입

**Create User**

**URL :** `/signup/`

`https://<domain name>/singup/`

**Method :** `POST`

**Running URL :**

`http://haru-eb.ap-northeast-2.elasticbeanstalk.com/signup/`

or

`https://haru.ycsinabro.com/signup/`

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
      "id": <user_id>,
      "email": "<email>"
    }
    ```

    example :

    ```json
    {
      "id": 86,
      "email":"test@jeeyong.kr"
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
