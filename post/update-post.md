# 글 수정

**Update Post**

**URL :** `/post/<post_id>/`

`https://<domain name>/post/<post_id>/`

**Method :** `PATCH`

**Running URL :**

`http://haru-eb.ap-northeast-2.elasticbeanstalk.com/post/<post_id>/`

or

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

key     | value     | type    | description
------- | --------- | ------- | ------------------------------
author  | (user_id) | Integer |                                |
title   | (제목)      | String  |                                |
content | (내용)      | String  |                                |
image   | (이미지)     | File    |                                |
status  | (기분상태 코드) | Integer | 1:기쁨, 2:나쁨, 3:그럭저럭, 4:짜증, 5:분노

## Responses

- HTTP Status : 200 - OK

  - 글 수정 성공

    ```json
    {
      "id": <post_id>,
      "url": "http://haru.ycsinabro.com/post/<post_id>/",
      "day": "<date>",
      "author": <user_id>,
      "title": "<title>",
      "content": "<content>",
      "image": "<image_url>",
      "status": <status_code>
    }
    ```

    example :

    ```json
    {
      "id": 22,
      "url": "http://haru.ycsinabro.com/post/22/",
      "day": "2017-04-20",
      "author": 86,
      "title": "제목 updated",
      "content": "내용",
      "image": "https://harn-bucket.s3.amazonaws.com/media/post/django_gbq5I4K.jpg",
      "status": 3
    }
    ```

- HTTP Status : 404 - Bad Request

  - status 에 유효하지 않은 값(1~5 이외의 값)이 포함되었을 경우

    ```json
    {
      "status": [
        "\"<입력한 status 값>\" is not a valid choice."
      ]
    }
    ```

- HTTP Status : 401 - Unauthorized

  - Headers 에 Token 이 포함되지 않았을 경우, key name 이 잘못되었을 경우 (Authorization 외에 다른 이름 사용 시),

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

  - 유효하지 않은 user_id 로 요청함

    ```json
    {
      "detail": "Not found."
    }
    ```
