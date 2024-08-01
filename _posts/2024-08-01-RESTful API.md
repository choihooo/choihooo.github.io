---
title: RESTful API
date: 2024-08-01 18:03:15+0900
categories: [Dev, Network]
tags: [rest, restful]
---



# `CRUD`
클라이언트가 서버에게 보내는 요청은 크게 4가지로 이루어진다 → CRUD


- c는 create의 약자로 데이터를 서버에 올리는 요청을 한다.
- r은 read의 약자로 서버에서 데이터를 불러오는 요청을 한다.
- u는 update의 약자로 서버의 데이터를 바꾸는 요청을 한다.
- d는 delete의 약자로 서베의 데이터를 지우는 요청을 한다.


데이터를 다룰 때 큰 틀에서 보면 대부분의 요청이 이 4가지 요청에 속한다.


모든 데이터는 CRUD 관점에서 바라봐야하며 CRUD 특정 기능이 없는 기획이라면 그 의도가 명확해야 한다.


### CRUD의 요청 주소

CRUD 요청은 각각의 주소를 가진다.

도메인/create

도메인/read

도메인/update

도메인/delete

이러면 하나의 데이터 별로 주소가 4개씩 생기기 때문에 주소가 너무 많아진다.

간단하게 알아보자면 밑에 느낌으로 주소가 4개 생기는 느낌이다.

```java
요청(도메인/create)
요청(도메인/read)
요청(도메인/update)
요청(도메인/delete)
```

## RESTful API

위의 문제를 해결하기 위해 좀 더 체계적으로 API를 관리하는 체계의 명칭이 RESTful API이다.

### 동작 방식

요청을 보낼 때 어떤 요청을 보냈는지 파악할 수 있는 라벨을 붙여서 함께 전송한다.

<aside>
💡 변수 → 파라미터, 라벨 → 메소드

</aside>

create → POST

read → GET

update → PUT(전체) & PATCH(일부)

delete → DELETE

간단하게 생각해보자면

```java
요청.post(도메인)
요청.get(도메인)
요청.put(도메인)
요청.patch(도메인)
요청.delete(도메인)
```

이런식으로 하나의 도메인의 post, get 과 같은 라벨을 달아 요청을 보내 처리한다.

이렇게 되면 위의 RESTful 전에 방식보다 관리해야하는 도메인은 줄게된다.

## HTTP 상태 코드

200번대 코드 → 잘된 요청

400번대 코드 → 클라이언트의 요청에 문제가 있는 경우

500번대 코드 → 서버에 문제가 있는 경우

https://developer.mozilla.org/ko/docs/Web/HTTP/Status