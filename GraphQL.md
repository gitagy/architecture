
# GraphQL
> GraphQL is an API.

## GraphQL 과 REST APIs
 * https://medium.com/chute-engineering/graphql-in-the-age-of-rest-apis-b10f2bf09bba#.tfhd9p82n

## SOAP 이 REST 로 대체된 것으로 생각해라
 * 업계에서 일반적으로 대체된다면 오래 걸리지 않겠나? 10년?
 * 동시 지원도 할거고...

## Why is it better?

### 서버의 단방향 응답구조를 개선하여 클라이언트에게 유연성을 부여

### 클라이언트의 단편화된 요청 구문(REST API)을 다중화 시키고 커뮤니케이션 표준화를 꽤 한다.
 * React 와 Angular 에서 REST API 를 어떻게 사용하길래 이런 요구가 있는지 이해가 필요
   * REST API : 글 내용을 가져온다. 글 코멘트를 가져온다. 코멘트의 작성자 정보를 가져온다.
   * GraphQL : 글 내용과, 글 코멘트 그리고 코멘트 작성자 정보를 Query 로 정의해 가져온다. (exposed schme base)

### 왜 JSON Schema 가 아닌가?
 * 대안으로 쓰기에 표준화가 부족하다.
 * GraphQL, JSON-LD, JSON Schema http://react-etc.net/entry/graphql-json-ld-and-json-schema-formats-explained

## GraphQL 과 REST 함께 쓰기
 * 클라이언트 <-단일요청-> GraphQL Server <-다중요청가능-> REST Server
   * 서버는 훨씬 나은 대역폭이 있으므로 서버에서의 다중처리는 문제가 없다.

## Relay
 `Client(Relay <-> graphql-rest) <-> REST Server`
 * React 를 위한 GraphQL 클라이언트 라이브러리
 * GraphQL 서버에서 데이터 가져오기를 추상화하는 플러그 형 전송 계층
 * 서버가 원격에서 실행될 필요가 없고, 클라이언트의 요소로써 패키지 된다.
