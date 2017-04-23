# 사용자 프로필 보기

**Get User Profile**

**URL :** `/user/`

`https://<domain name>/user/`

**Method :** `GET`

**Running URL :**

`https://haru.ycsinabro.com/user/`

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

  - 사용자 정보 가져오기 성공

    ```json
    {
      "count": 1,
      "next": null,
      "previous": null,
      "results": [
        {
          "id": <user_id>,
          "email": "test@jeeyong.kr"
        }
      ]
    }
    ```

    example :

    ```json
    {
      "count": 1,
      "next": null,
      "previous": null,
      "results": [
        {
          "id": 26,
          "email": "test@jeeyong.kr"
        }
      ]
    }
    ```

  - **Headers 에 Token 이 포함되지 않았을 경우**

    key           | value
    ------------- | ------------------------------------------------
    Authorization | `null`
    ```json
    {
      "count": 0,
      "next": null,
      "previous": null,
      "results": []
    }
    ```

- HTTP Status : 401 - Unauthorized

  - key name 이 잘못되었을 경우 (Authorization 외에 다른 이름 사용 시)

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
