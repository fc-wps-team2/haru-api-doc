# 로그아웃 {#로그아웃}

Logout

**URL :**`/users/logout`

**Method :**`POST`

**URL example :**`https://<domain name>/api/users/logout`

**Running URL :**`http://haru-eb.ap-northeast-2.elasticbeanstalk.com/logout/`

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

* HTTP Status : 401 - Unauthorized

  * 유효하지 않은 Token으로 요청함



