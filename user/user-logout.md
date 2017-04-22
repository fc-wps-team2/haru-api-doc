# 로그아웃

**Logout**

**URL :** `/logout/`

`https://<domain name>/logout/`

**Method :** `POST`

**Running URL :**

`https://haru.ycsinabro.com/logout/`

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

`None`

## Responses

- HTTP Status : 200 - OK

  - 로그아웃 성공

    ```json
    {
      "detail": "Log-Out Success"
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
