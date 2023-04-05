### TCP 
- 인터넷상에서 데이터를 메세지의 형태로 보내기 위해 IP와 함께 사용하는 프로토콜을 말한다.
- TCP는 애플리케이션에게 신뢰적이고 연결지향성 서비스를 제공한다.
- 서버와 클라이언트간에 데이터를 신뢰성 있게 전달하기 위해 만들어진 프로토콜이다.
- TCP는 장치들 사이에 논리적인 접속을 성립하기 위해서 **3-way Handshake**를 사용한다.

# 3-Way Handshake란?
- TCP/IP 프로토콜을 이용해서 통신을 하는 응용프로그램이 데이터를 전송하기 전에 먼저 정확한 전송을 보장하기 위해 **상대방 컴퓨터와 사전에 세션을 수립하는 과정**
- TCP 통신을 이용하여 데이터를 전송하기 위해 네트워크 연결을 설정(Connection Establish) 하는 과정
- 양쪽 모두 데이터를 전송할 준비가 되었다는 것을 보장하고, 실제로 데이터 전달이 시작하기 전에 한 쪽이 다른 쪽이 준비되었다는 것을 알 수 있도록 한다.
- 즉, TCP/IP 프로토콜을 이용해서 통신을 하는 응용 프로그램이 데이터를 전송하기 전에 먼저 정확한 전송을 보장하기 위해 상대방 컴퓨터와 사전에 세션을 수립하는 과정을 의미한다.
  
### State 정보
- CLOSED: 포트가 닫힌 상태
- LISTEN: 포트가 열린 상태로 연결 요청 대기 중
- SYN_RECV: SYNC 요청을 받고 상대방의 응답을 기다리는 중
- ESTABLISHED: 포트 연결 상태
- TIME-WAIT: Server로부터 FIN을 수신하더라도 일정시간(default: 240초)동안 세션을 남겨놓고 잉여 패킷을 기다리는 과정을말한다.

### 동작 방식
- SYN(Synchronization) : 연결요청, 세션을 설정하는데 사용되며 초기에 시퀀스 번호를 보냄
- ACK(Acknowledgement) : 보낸 시퀀스 번호에 TCP 계층에서의 길이 또는 양을 더한 것과 같은 값을 ACK에 포함하여 전송 
   - 동기화 요청에 대한 답변 : Client의 Sequence Number+1을 하여 ACK로 돌려줍니다.

#### Step1 [Client -> SYN -> Server]
- Client가 Server에게 접속을 요청하는 SYN플래그를 보낸다.

#### Step2. [Server -> SYN + ACK -> Client ]
- Server는 Listen상태에서 SYN이 들어온 것을 확인하고 SYN_RECV상태로 바뀌어 SYN + ACK플래그를 Client에게 전송한다. 그 후 Server는 다시 ACK 플래그를 받기 위해 대기상태로 변경된다.

#### Step3. [Client -> ACK -> Server]
- SYN + ACK 상태를 확인한 Client는 서버에게 ACK를 보내고 연결 성립(Established)이 된다. 

 