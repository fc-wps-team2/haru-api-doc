# 글 삭제 {#글-삭제}

Delete Post

**URL :**`/posts/{post_id}`

**Method :**`DELETE`

**URL example :**`https://<domain name>/api/v1/posts/{post_id}`

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

* HTTP Status : 204 - No Content

  * 글 삭제 성공

* HTTP Status : 400 - Bad Request

  * 유효하지 않은 user\_id로 요청함

* HTTP Status : 401 - Unauthorized

  * 유효하지 않은 Token으로 요청함



