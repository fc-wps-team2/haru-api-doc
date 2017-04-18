# 로그아웃

Logout

**URL :** `/logout/`

**Method :** `POST`

**URL example :** `https://<domain name>/logout/`

**Running URL :**

`http://haru-eb.ap-northeast-2.elasticbeanstalk.com/logout/`

`https://haru.ycsinabro.com/logout/`

## Request

### Headers

| key           | value                     |
| ------------- | ------------------------- |
| Authorization | Token `<token key value>` |

example :

| key           | value                                            |
| ------------- | ------------------------------------------------ |
| Authorization | `Token a35b9eb7e90d9ecdb5567183fb13f6b813cf2547` |

### Body

`None`

## Responses

-   HTTP Status : 200 - OK

        {
            "detail": "Log-Out Success"
        }

-   HTTP Status : 401 - Unauthorized

    -   Headers 에 Token 값을 포함하여 요청하지 않았을 경우, key 이름 또는 값 형식이 잘못되었을 경우

            {
                "detail": "Authentication credentials were not provided."
            }

    -   유효하지 않은 Token 값으로 요청

            {
                "detail": "Invalid token."
            }
