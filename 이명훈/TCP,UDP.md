# 과제

* TCP
* UDP

<br>

*TCP /UDP 모두 패킷을 한 컴퓨터에서 다른 컴퓨터로 전달해주는 IP 프로토콜을 기반으로 구현되어있다*

## TCP(Transmission Control Protocol)

* TCP란?
    * **TCP**는 신뢰성보다 연속성이 있는 전송이 중요할 때 사용하는 프로토콜이다
    * 네트워크에 연결된 컴퓨터에서 실행되는 프로그램 간의 데이터를 안정적으로, 순서대로, 에러없이 교환하게 해준다
    
* 연결형 서비스
    * TCP는 연결혈 서비스로 가상 회선 방식을 제공한다

<br>


## UDP(User Datagram Protocol)

 * UDP란?
    * 여기서 D의 Datagram은 독립적인 관계를 지니는 패킷을 뜻한다 -> 즉, 각각의 패킷이 독립적이기 때문에 패킷마다  서로 다른 경로로 독립적으로 처리하게 된다

* 비연결형 서비스
    * UDP는 비연결형 서비스이다 -> 때문에 정보를 주고받을 때 TCP와 같은 연결절차를 밟지않는다
    * 그렇기 때문에 TCP 보다 속도가 빠른 것이 특징이다

* * *

## 관련 사례
* TCP
   * 웹(HTTP/HTTPS)
   * 메일(SMTP)
   * 파일전송(FTP/SFTP)
   * 터미널접속(Telnet/SSH)
* 특징
   * 연결형 서비스
   * 신뢰성 통신
 
* UDP
   * 실시간 스트리밍(Datagram)
   * 음성(VolP)
   * 파일전송(TFTP)
   * 시스템관리(SNMP)
* 특징
   * 비연결형 서비스
   * 비신뢰성 통신
