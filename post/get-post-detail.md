# 글 상세보기

**Get Post Detail**

**URL :** `/post/<post_id>/`

`https://<domain name>/post/<post_id>/`

**Method :** `GET`

**Running URL :**

`https://haru.ycsinabro.com/post/<post_id>/`

**URL example :**

`https://haru.ycsinabro.com/post/22/`

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

  - 글 상세보기 성공, 글 정보 가져오기 성공

    ```json
    {
      "id": <post_id>,
      "url": "http://haru.ycsinabro.com/post/<post_id>/",
      "day": "<date>",
      "author": <user_id>,
      "title": "<title>",
      "content": "<content>",
      "image": "<image_url>",
      "status": <status_code>,
      "created_date": "<datetime>"
    }
    ```

    example :

    ```json
    {
      "id": 295,
      "url": "http://haru.ycsinabro.com/post/295/",
      "day": "2017-04-28",
      "author": 86,
      "title": "제목",
      "content": "내용",
      "image": "https://harn-bucket.s3.amazonaws.com/media/post/django_SxCcgMn.jpg",
      "status": 3,
      "created_date": "2017-04-28T07:55:16.722571Z"
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

- HTTP Status : 404 - Not Found

  - 유효하지 않은 post_id 로 요청함

    ```json
    {
      "detail": "Not found."
    }
    ```

- HTTP Status : 500 - Internal Server Error

  - Headers 에 Token 이 포함되지 않았을 경우, Token 형식이 잘못되었을 경우

  - 401 로 수정 예정
