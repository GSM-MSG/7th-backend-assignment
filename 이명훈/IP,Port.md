# 과제
   
* IP
* Port

<br>

## IP(Internet Protocol)

* IP

    * 컴퓨터를찾을 때 필요한 주소 (=컴퓨터 주소, 집주소와 비슷)
    * 컴퓨터 간의 네트워킹를 가능하게 하는 통신 규약
    * 데이터 통신을 위해서는 IP 주소가 필요함 (데이터 통신 = 편지를 주고 받는 것과 비슷)
    * 예를 들어 유튜브를 본다고 하면, 유튜브 서버도 IP 주소가 있어야 하고, 내 컴퓨터에도 IP 주소가 있어야한다
    * IP 주소는 컴퓨터가 ㅔ트워크에 연결이 될때, 그때 정해짐
    * 예를 들어 카페에 가서 공유기 비밀변호 입력해서 와이파이 련결 -> 와이파이 고유기는 내 컴퓨터에 IP를 할당해줌
    * IPv4 : IPv4주소는 32비트 길이의 식별자로 0.0.0.0 ~ 255.255.255.255까지의 숫자의 조합으로 이루어지며 총 네구간으로 나눠져있으며 최대 12자리의 번호로 이루어져 있다. IPv4를 통해 최대 약 43억개의 서로 다른 주소를 부여할 수 있다. 하지만 전세계 공용으로 사용되며 인터넷 사용자수가 급증하면서 Pv4주소가 고갈될 문제에 처해있다
    * IPv6 : IPv6주소는 기존의 IPv4주소체계를 128비트 크기로 확장한 차세대 인터넷 프로토콜 주소이다. IPv6주소의 경우 일반적으로 16비트 단위로 나누어지며 각 16비트 블록은 다시 4자리 16진수로 변환되고 콜론으로 구분되어 진다
    * 개인적으로 사용할 경우 IP 주소는 유동적으로 할당되는 것이 일반적이지마, 서버의 경우는 고정해두지 않으면 사용자가 접속할 수  없으므로 고정해야함

<br>

* Port
    * 컴퓨터가 각종 신호, 정보 등을 주고 받을 수 있도록 해주는 통신 통로 (=컴퓨터의 도로)
    * 여러 네트워크 활동 (ex. 업로드, 다운로드 등)을 할 때 사용하는 관문 같은 역할
    * 컴퓨터 안에서 프로그램을 찾기 위한 수단, 즉 각 프로세스가 위치한 방 번호라고 생각하면 됨
    * 16비트로 된 숫자
    * 포트 번호 구분
        1. 잘 알려진 포트(well-known port) : 국제 도메인 관리기구에서 통제
        <예시> -> HTTP : 80 // HTTPS : 443
        2. 등록된 포트 (registered port) : 국제 도메인 관리기구에 등록
        3. 동적 포트 (dyamic port) : 임시 포트들, 어떤 프로세스들에게 임의로 사용 가능
            -IP + 포트 번호 -> 소켓
            -IP 주소가 집 주소와 비슷한 개념이라면, 포트 번호는 방 번호와 비슷한 개념
