# 글 작성

Create Post

**URL :** `/posts`

**Method :** `POST`

**URL example :** `https://<domain name>/api/posts`

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

- title : 제목, String

- content : 내용, String

- image : 이미지, File

- status_code : 기분상태 코드, Integer

## Responses

- HTTP Status : 201 - Created

  - Body

    ```json
    {
      "id": 1,
      "author": {
        "id": 1,
        "email": "<email>"
      },
      "title": "test title",
      "content": "test content",
      "image_link": "https://www.djangoproject.com/s/img/logos/django-logo-negative.svg",
      "status_code": 2,
      "created_date": "2017-04-14T11:12:52.000Z"
    }
    ```

- HTTP Status : 400 - Bad Request

  - 필수항목 입력값 누락 : 이메일, 비밀번호

- HTTP Status : 401 - Unauthorized

  - 유효하지 않은 Token으로 요청함
