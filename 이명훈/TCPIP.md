# 과제

* TCP/IP

<br>

## TCP/IP

* TCP/IP란?
    * TCP/IP는 OSI 7계층 중에서 3,4계층을 다루는 프로토콜이다
    * TCP/IP는 패킷 통신 방식의 인터넷 프로토콜인 IP와 전송 프로토콜인 TCP로 이루어져 있다. IP는 패킷 전달 여부를 보증하지 않고, 패킷을 보낸 순서와 받는 순서가 다를 수 있다. TCP는 IP 위에서 동작하는 프로토콜로, 데이터의 전달을 보증하고 보낸 순서대로 받게 해 준다
    * HTTP, FTP, SMTP 등 TCP를 기반으로 한 많은 수의 애플리케이션 프로토콜들이 IP 위헤서 동작하기 때문에, 묶어서 TCP/IP로 부르기도 한다

    ***즉, TCP/IP를 말한다는 것은 송신자가 수신자에게 IP주소를 사용하여 데이터를 전달하고 그 데이터가 제대로 갔는지, 너무 빠르지는 않는지, 제대로 받았다고, 연략은 오는지에 대한 이야기를 하는 것이다***

* Transport Layer(4 Layer)
    * 송신자와 수신자의 논리적 연결을 담당하는 부분으로, 신뢰성 있는 연결을 유지할 수 있도록 도와준다. 즉, 사용자 간의 연결을 생성하고 데이터를 얼마나 보냈ㄴ즌지 얼마나 받았는지, 제대로 받았는지 등을 확인한다. TCP와 UDP가 대표적이다

* Network Layer(3 Layer)
    * IP이 활용되는 부분으로, 한 사용자가 다른 사용자로 가고자 할 경우, 목적지를 찾아준다. 이를 Routing 이라고 하며 대역이 다른 IP들이 목적지를 향해 제대로 찾아갈 수 있도록 돕는 역할을 한다

* * *

## 3-Way Handshake란
* TCP/IP 프로토콜을 이용해서 통신을 하는 응용프로그램이 데이터를 전송하기 전에 먼저 정확한 전송을 보장하기 위해 상대방 컴퓨터와 사전에 세션을 수립하는 과정을 말한다
