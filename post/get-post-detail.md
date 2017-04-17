# 글 상세보기 {#글-상세보기}

Get Post Detail

**URL :**`/posts/{post_id}`

**Method :**`GET`

**URL example :**`https://<domain name>/api/posts/{post_id}`

## Request {#request}

### Headers {#headers}

```
{
    "token": "a35b9eb7e90d9ecdb5567183fb13f6b813cf2547"
}
```

### Body {#body}

`None`

## Responses {#responses}

* HTTP Status : 200 - OK

  * Body

    ```
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

* HTTP Status : 404 - Not Found

  * 유효하지 않은 user\_id로 요청함



