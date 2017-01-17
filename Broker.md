
# Broker vs. Brokerless
* http://zeromq.org/whitepapers:brokerless

## Broker

### 조합
 * 단일 브로커 (클러스터링)
 * 멀티 브로커 + 서비스 디스커버리

### pros
 * 발신 후 라이프가 종료 되어도 무관하다.
 * 응용프로그램이 종료되어도 메시지는 브로커가 처리 한다.

### cons
 * request/response 같이 사용할 경우 network hops 이 증가 한다. (1 req/res = 2 network hops)

### solution
 * RabbitMQ(The Polyglot Broker) - pub/sub, rpc (amqp)

## Brokerless

### 조합
 * p2p + 서비스 디스커버리

### pros
 * network hops 감소로 performance 향상

### cons
 * directory service (zookeeper?) 가 반드시 필요하다.

### solution
 * ZeroMQ - pub/sub, rpc (zerorpc를 통해서...)
