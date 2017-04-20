# 글 목록보기

**Get Post List**

- PAGE_SIZE : 9 (한 페이지에 9개의 글 표시)

- 첫 페이지 응답결과의 previous 값은 null

- 마지막 페이지 응답결의 next 값은 null

**URL :** `/post/`

`https://<domain name>/post/`

**Method :** `GET`

**Running URL :**

`http://haru-eb.ap-northeast-2.elasticbeanstalk.com/post/`

or

`https://haru.ycsinabro.com/post/`

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

- `None` : 첫번째 페이지 요청

- `page` : 페이지 번호, 해당 페이지 요청

## Responses

- HTTP Status : 200 - OK

  - Body

  ```json
  {
    "count": <post_count>,
    "next": "<next_page_url>",
    "previous": null,
    "results": [
      {
        "id": <post_id>,
        "url": "<post_url>",
        "day": "<date>",
        "author": <user_id>,
        "title": "<title>",
        "content": "<content>",
        "image": "<image_url>",
        "status": <status_code>
      },

      ...

    ]
  }
  ```

  example :

  ```json
  {
    "count": 12,
    "next": "http://haru.ycsinabro.com/post/?page=2",
    "previous": null,
    "results": [
      {
        "id": 29,
        "url": "http://haru.ycsinabro.com/post/29/",
        "day": "2017-04-20",
        "author": 86,
        "title": "제목",
        "content": "내용",
        "image": "https://harn-bucket.s3.amazonaws.com/media/post/django_3HmPgjm.jpg",
        "status": 3
      },
      {
        "id": 27,
        "url": "http://haru.ycsinabro.com/post/27/",
        "day": "2017-04-20",
        "author": 86,
        "title": "제목 updated",
        "content": "내용",
        "image": "https://harn-bucket.s3.amazonaws.com/media/post/django_b0r7GE7.jpg",
        "status": 3
      },

      ...

    ]
  }
  ```

- HTTP Status : 401 - Unauthorized

  - 유효하지 않은 Token 으로 요청함

    ```json
    {
      "detail": "Invalid token."
    }
    ```

- HTTP Status : 500 - Internal Server Error

  - Headers 에 Token 이 포함되지 않았을 경우, Token 형식이 잘못되었을 경우
  - key name 이 잘못되었을 경우 (Authorization 외에 다른 이름 사용 시)
  - 401 로 수정 예정
