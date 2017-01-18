
# Message Protocol
 `mqtt < amqp < wamp`

## Compare
 * http://wamp-proto.org/compared/

## MQTT (pub/sub)
 * AMQP 보다 단순하고 집중적인 디자인 원칙을 가진다. (light weight)
 * pub/sub 지원에 대기열(queue)는 없다
 * 제한된 장치 및 낮은 밴드폭 대상
   * 전화연결 등 high latency 에 적합
   * 머신 to 머신, IoT 등에 사용
 * 3가지 서비스 품질
   * fire-and-forget / unreliable
   * at least once (might be sent more than one time)
   * exactly one

## AMQP (pub/sub, [rpc], [websocket])
 * RabbitMQ: The Polyglot Broker
 * reliable queuing
 * topic-based pub/sub
 * flexible routing
 * transaction ?
 
## WAMP (pub/sub, rpc, websocket)
 * 무엇인가?
   * http://wamp-proto.org/why/
   * http://www.slideshare.net/RyanEdge/wamp-47586205
   * Model
     * Caller-Callee (Client-Server)
       * Dealer
     * PubSub
     * Router 는 브로커와 딜러의 조합
 * RPC 와 PubSub 이 하나의 프로토콜로...
   * 액션 실행(커맨드) = RPC
   * 알림(변경수신) - PubSub
 * 시나리오
   * 클라이언트
     * OnTicketCreated 구독
     * createTicket 실행
    * 서버
      * createTicket 수행
      * OnTicketCreated 토픽 발행
   * 여러 클라이언트가 OnTicketCreated 를 구독할 수 있다.

### solution
 * https://github.com/Vinelab/minion
 * http://autobahn.ws/js/tutorial.html
 * http://autobahn.ws/js/#features
 