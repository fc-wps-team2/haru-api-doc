# 사용자 프로필 수정

Update User Profile

**URL :** `/users`

**Method :** `PATCH`

**URL example :** `https://<domain name>/api/users`

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
      "id": 1,
      "email":"<email>",
      "password": "<password>",
      "created_date": "2017-04-14T11:06:21.000Z"
    }
    ```

- HTTP Status : 400 - Bad Request

  - 필수항목 입력값 누락 : 이메일, 비밀번호

- HTTP Status : 401 - Unauthorized

  - 유효하지 않은 Token으로 요청함
