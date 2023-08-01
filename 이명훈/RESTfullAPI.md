# 과제

* RESTful API

<br>

## RESTful API

* REST API란
    * 월드 와이드 웨(www)과 같은 분산 하이퍼미디어 시스템을 위한 소프트웨어 개발 아키텍쳐의 한 형식
    * REST는 기본적으로 웹의 기존 기술과 HTTP프로토콜을 그대로 할용하기 때문에 웹의 장접을 최대한 활용할 수 있는 아키텍쳐 스타일이다

* REST란?
    * HTTP URL를 통해 자원을 명시하고, HTTP Method(Post, Get, Put, DELETE)를 통해 해당
    * 자원에 대한 CRUD OPERATION을 적용하는 것을 의미한다
    -CRUD OPERATION -> 즉, REST는 자원 기반 구조(ROA) 설계의 중심에 Resource가 있고, HRRP Method를 통해 Resource를 처리하도록 설계된 아키텍쳐를 의미한다, 웹의 모든 자원의 고유한 ID인 HTTP URL를 부여한다

* RESTful API란
    * HTTP와 URL 기반으롤 자원에 접근할 수 있도록 제공하는 애플리케이션 개발 인터페이스이다
    * REST API를 제공하는 웹 서비스를 RESTful하다고 할 수 있다
    * RESTful은 REST를 REST 답게 쓰기 위한 방법으로, 누군가가 공식적으로 발표한 것은 아니다

* RESRful API 개발 원칙
1. 자원은 식별할 수 있어야한다 / URL만으로 내가 어떤 자원을 제어하려고 하는지 알 수 있어야한다
2. 행위는 명시적이어야 한다
3. 자기 서술적이어야 한다 / 데이터 처리를 위한 정보를 얻기 위해서, 데이터 원본을 읽어야 한다면 자기 서술적이라고 할 수 있다
4. HATEOS 클라이언트 요청에 대해 응답을 할 때, 추가적인 정보를 제공하는 링크를 포함할 수 있어야 한다