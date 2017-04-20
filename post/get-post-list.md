# 글 목록보기

**Get Post List**

- PAGE_SIZE : 10 (한 페이지에 10개의 글 표시)

- 첫 페이지 응답결과의 previous 값은 null

- 마지막 페이지 응답결의 next 값은 null

**URL :** `/post/`

`https://{domain name}/post/`

**Method :** `GET`

**Running URL :**

`http://haru-eb.ap-northeast-2.elasticbeanstalk.com/post/`

or

`https://haru.ycsinabro.com/post/`

**URL example :**

`https://haru.ycsinabro.com/post/` `https://haru.ycsinabro.com/post/?page=2`

## Request

### Headers

key           | value
------------- | -------------------------
Authorization | Token `{token key value}`

**example :**

key           | value
------------- | ------------------------------------------------
Authorization | `Token a35b9eb7e90d9ecdb5567183fb13f6b813cf2547`

### Body

key  | value         | type    | description
---- | ------------- | ------- | ----------------
page | {page_number} | Integer | 미포함 시 첫번째 페이지 반환

가장 최근에 생성한 글이 상단에 표시 (post_id, descending)

## Responses

- HTTP Status : 200 - OK

  - 글 목록보기 성공, 글 목록 가져오기 성공

    {next_page_url} : 다음 페이지가 없을 경우 null

    {previous_page_url} : 이전 페이지가 없을 경우 null

    ```json
    {
      "count": {post_count},
      "next": "{next_page_url}",
      "previous": "{previous_page_url}",
      "results": [
        {
          "id": {post_id},
          "url": "{post_url}",
          "day": "{date}",
          "author": {user_id},
          "title": "{title}",
          "content": "{content}",
          "image": "{image_url}",
          "status": {status_code}
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

    - 작성된 글이 하나도 없을 경우

      ```json
      {
        "count": 0,
        "next": null,
        "previous": null,
        "results": []
      }
      ```

    - 작성된 글이 10개 이하인 경우

      ```json
      {
        "count": 1,
        "next": null,
        "previous": null,
        "results": [
          {
            "id": 31,
            "url": "http://haru.ycsinabro.com/post/31/",
            "day": "2017-04-20",
            "author": 9,
            "title": "제목",
            "content": "내용",
            "image": "https://harn-bucket.s3.amazonaws.com/media/post/django_uCXq4CL.jpg",
            "status": 3
          }
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
