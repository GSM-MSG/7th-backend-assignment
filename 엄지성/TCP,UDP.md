## TCP 와 UDP

* TCP와 UDP는 OSI 표준모델과 TCP/IP 모델의 **전송계층**에서 사용되는 프로토콜

* 전송계층은 송신자와 수신자를 연결하는 통신 서비스를 제공하고 IP에 의해 전달되는 패킷의 오류를 검사하며 재전송 요구 제어등을 담당하는 계층

* 정확성을 추구할지 신속성을 추구할지를 구분한다.
---
## TCP

* 데이터를 중요하게 생각하여 확실히 주고받고 싶을 때는 'TCP'를 사용한다.

* TCP는 통신할 컴퓨터끼리 서로 확인 메세지를 보내면서 데이터를 주고받음으로써 통신의 신뢰성을 높인다.

* 웹이나 메일, 파일 공유 등과 같이 데이터를 누락시키고 싶지 않은 서비스는 TCP를 사용한다.

### TCP 3-way Handshake란

* TCP는 장치들 사이에 논리적인 접속을 성립하기 위해서 3-way handshake

* TCP/IP프로토콜을 이용해서 통신을 하는 응용프로그램이 디에터를 전송하기 전에 먼저
    * Client > Server:TCP SYN
    * Server > Client:TCP SYN ACK
    * Client > Server:TCP ACK
* 이런 절차는 TCP 접속을 성공적으로 성립하기 위해 반드시 필요!

### TCP의 3-way Handshaking 역할

* 양쪽 모두 데이터를 전송할 준비가 되었다는 것을 보장, 실제로 데이터 전달이 시작하기 전에 한쪽이 다른쪽이 준비되었다는 것을 알도록한다.

### 사용 예시

1. HTTP Web: 웹 브라우저

2. FTP(File transfer): 파일 전송

3. Telnet(remote login): 원격 로그인

---
## UDP

* 데이터의 신뢰성은 제쳐두고 어쨌든 빨리 보내고 싶은 때는 'UDP'를 사용한다.

* UDP는 데이터를 보내면 그것으로 끝이므로 신뢰성은 없지만 확인 응답과 같은 절차를 생력할 수 있어 통신의 신속성을 높인다.

* VoIP와 같은 시간동기가 필요한 특히 속도를 필요로 하는 서비스들이 UDP를 사용한다.

### 사용 예시

1. Streaming media

2. teleconferencing

3. DNS(Domain Name System)