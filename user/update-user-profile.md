# 사용자 프로필 수정

**Update User Profile**

**URL :** `/user/<user_id>/`

`https://<domain name>/user/<user_id>/`

**Method :** `PATCH`

**Running URL :**

`http://haru-eb.ap-northeast-2.elasticbeanstalk.com/user/<user_id>/`

or

`https://haru.ycsinabro.com/user/<user_id>/`

**URL example :**

`https://haru.ycsinabro.com/user/86/`

## Request

### Headers

key           | value
------------- | -------------------------
Authorization | Token `<token key value>`

**example :**

key           | value
------------- | ------------------------------------------------
Authorization | `Token a35b9eb7e90d9ecdb5567183fb13f6b813cf2547`

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
      "id": <user_id>,
      "email":"<email>"
    }
    ```

- HTTP Status : 400 - Bad Request

  - 필수항목 입력값 누락 : 이메일

    ```json
    {
      "email": [
        "This field may not be blank."
      ]
    }
    ```

- HTTP Status : 401 - Unauthorized

  - Headers 에 Token 이 포함되지 않았을 경우, key name 이 잘못되었을 경우 (Authorization 외에 다른 이름 사용 시)

    ```json
    {
      "detail": "Authentication credentials were not provided."
    }
    ```

  - 유효하지 않은 Token 으로 요청함

    ```json
    {
      "detail": "Invalid token."
    }
    ```
