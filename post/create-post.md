# 글 작성

**Create Post**

**URL :** `/post/`

`https://<domain name>/post/`

**Method :** `POST`

**Running URL :**

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

key        | value       | type    | description
---------- | ----------- | ------- | -------------------------------------
**author** | `<user_id>` | Integer | **필수**
**title**  | `<제목>`      | String  | **필수**
content    | `<내용>`      | String  | -
image      | `<이미지>`     | File    | -
**status** | `<기분상태 코드>` | Integer | **필수** 1:기쁨, 2:나쁨, 3:그럭저럭, 4:짜증, 5:분노

**<user_id>** : [사용자 프로필 보기](/user/get-user-profile.md) 에서 획득 

## Responses

- HTTP Status : 201 - Created

  - 글 작성 성공, 글 생성 성공

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
      "id": 18,
      "url": "http://haru.ycsinabro.com/post/18/",
      "day": "2017-04-20",
      "author": 86,
      "title": "제목",
      "content": "내용",
      "image": "https://harn-bucket.s3.amazonaws.com/media/post/django_a7Ec3Xv.jpg",
      "status": 3
    }
    ```

- HTTP Status : 400 - Bad Request

  - 필수항목 입력값 누락 : user_id, 제목, 기분상태 코드

    ```json
    {
      "title": [
        "This field is required."
      ],
      "status": [
        "This field is required."
      ],
      "author": [
        "This field is required."
      ]
    }
    ```

- HTTP Status : 520

  - Headers 에 Token 이 포함되지 않았을 경우, key name 이 잘못되었을 경우 (Authorization 외에 다른 이름 사용 시)

  - 유효하지 않은 Token 으로 요청함

  - 401 로 수정 예정
