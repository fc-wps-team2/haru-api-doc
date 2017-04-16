# 글 목록보기 {#글-목록보기}

Get Post List

* PAGE\_SIZE : 9 \(한 페이지에 9개의 글 표시\)

* 첫 페이지의 previous 값은 null

* 마지막 페이지의 next 값은 null

**URL :**`/posts`

**Method :**`GET`

**URL example :**`http://<domain name>/api/v1/posts`

## Request {#request}

### Headers {#headers}

```
{
    "token": "a35b9eb7e90d9ecdb5567183fb13f6b813cf2547"
}
```

### Body {#body}

`None`

## Responses {#responses}

* HTTP Status : 200 - OK

  * Body

    ```
    {
        "count": 11,
        "next": null,
        "previous": "http://<domain name>/api/v1/posts?page=1",
        "results": [
            {
                "id": 10,
                "author": {
                    "id": 1,
                    "email": "<email>"
                },
                "title": "title 10",
                "content": "content 10",
                "image_link": "http://www.djangoproject.com/s/img/logos/django-logo-negative.svg",
                "status_code": 2,
                "created_date": "2017-04-14T11:30:15.000Z"
            },
            {
                "id": 11,
                "author": {
                    "id": 1,
                    "email": "<email>"
                },
                "title": "title 11",
                "content": "content 11",
                "image_link": "http://www.djangoproject.com/s/img/logos/django-logo-negative.svg",
                "status_code": 2,
                "created_date": "2017-04-14T11:31:15.000Z"
            }
        ]
    }
    ```

* HTTP Status : 400 - Bad Request

* HTTP Status : 404 - Not Found

  * 유효하지 않은 user\_id로 요청함



