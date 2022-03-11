# Socket
- 스프링 공식 문서 https://docs.spring.io/spring-framework/docs/5.2.6.RELEASE/spring-framework-reference/web.html#websocket

## 파악할 점: 왜 소켓 요청은 스프링 시큐리티를 거치지 않는가

## WebSocket
### 정의
- 하나의 TCP 접속에 full-duplex 통신 채널을 제공하는 컴퓨터 통신 프로토콜이다. 

### 특징
- full-duplex: 두 대의 단말기가 데이터를 송수신하기 위해 동시에 각각 독립된 회선을 사용하는 통신 방식
- two-way communication channel

### 연결 = handshake 
- 클라이언트가 HTTP GET request를 보냄. Upgrade header를 가짐. 
- 서버는 101 Switching Protocols을 결과로 보냄
- HandshakeInterceptor를 사용해서 컨트롤할 수 있다.


![](https://i.imgur.com/FeiyKkF.png)


### connect 요청
#### 1. info
http://localhost:8094/ws-stomp/info
- The SockJS client begins by sending GET /info to obtain basic information from the server. After that, it must decide what transport to use. If possible, WebSocket is used. If not, in most browsers, there is at least one HTTP streaming option. If not, then HTTP (long) polling is used.

#### 2. ws:// 
(http://localhost:8094/ws-stomp/939/5hifpyxw/websocket)
ws://localhost:8094/ws-stomp/557/plkr2cyl/websocket
- 웹소켓은 HTTP를 기반으로 하지만 HTTP 프로토콜과는 전혀 다른 프로토콜이다. HTTP를 기반으로 한다는 것의 의미는 웹소켓 연결을 맺는 과정에 HTTP가 개입한다는 의미다. Handshake 과정이 성공적으로 끝나면, HTTP를 웹소켓 프로토콜로 바꾸는 protocol switching과정을 진행한다. 이 과정이 끝나면 HTTP 대신 ws와 wss프로토콜이흐르게 된다.
- 웹소켓을 호출할 때는 "ws://"를 사용한다. 

### STOMP 프로토콜 동작 과정 

![](https://i.imgur.com/6jOSnl7.png)



