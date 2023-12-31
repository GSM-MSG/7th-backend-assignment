## RESTful API란
* 두 컴퓨터 시스템이 인터넷을 통해 정보를 안전하게 교환하기 위해 사용하는 인터페이스

* RESTful API는 안전하고 신뢰할 수 있고 효율적인 소프트웨어 통신 표준을 따르므로 이러한 정보 교환을 지원한다.
---
## REST란

* Representational State Transfer(REST)는 API 작동 방식에 대한 조건을 부과하는 소프트웨어 아키텍처

* REST 기반 아키텍처를 사용하여 대규모의 고성능 통신을 안정적으로 지원할 수 있다.

* 쉽세 구현하고 수정할 수 있어 모든 API 시스템을 파악하고 여러 플랫폼에서 사용할 수 있다.

* API 개발자는 여러 아키텍처를 사용해서 API를 설계할 수 있는데 REST 아키텍처 스타일을 따르는 API를 REST API라 한다. REST 아키텍처를 구현하는 웹 서비스를 RESTful 웹 서비스라고 한다.

### REST 아키텍처 스타일

* 균일한 인터페이스

* 무상태

* 계층화 시스템

* 캐시 가능성

* 온디맨드 코드

---
## RESTful API의 장점

* 확장성
    > 모든 기능은 성능을 저하시키는 통신 병목 현상을 일으키지 않으면서 확장성을 지원한다.

* 유연성
    > 애플리케이션 함수를 계층화하는 기능은 유연성을 더욱 향상시킨다.

* 독립성
    > API 설계에 영향을 주지 않고 다양한 프로그래밍 언어로 클라이언트 및 서버 애플리케이션을 모두 작성 할 수 있다.
---
## RESTful API 작동 방법

1. 클라이언트가 서버에 요청을 전송한다. 클라이언트가 API 문서에 따라 서버가 이해하는 방식으로 요청 형식을 지정한다.

2. 서버가 클라이언트를 인증하고 해당 요청을 수행할 수 있는 권한이 클라이언트에 있는지 확인다.

3. 서버가 요청을 수신하고 내부적으로 처리한다.

4. 서버가 클라이언트에 응답을 반환한다. 응답에 요청이 성공했는지 여부를 클라이언트에 알려주는 정보가 포함된다. 응답에는 클라이언트가 요청한 모든 정보도 포함된다.
---
## RESTful API 클라이언트 요청

* 고유 리소스 식별자
    > 서버는 고유한 리소스 식별자로 각 리소스를 식별한다. REST 서비스의 경우 서버는 일반적으로 URL을 사용하여 리소스 식별을 수행한다.
* 메서드
    > 개발자는 HTTP를 사용해서 RESTful API를 구현한다. HTTP 메서드는 리소스에 수행해야 하는 작업을 서버에 알려준다. 
    * GET
        > 클라이언트는 GET을 사용하여 서버의 지정된 URL에 있는 리소스에 액세스한다. GET 요청을 캐싱하고 RESTful API 요청에 파라미터를 넣어 전송하여 전송 전에 데이터를 필터링하도록 서버에 지시할 수 있다.
    * POST
        > 클라이언트는 POST를 사용하여 서버에 데이터를 전송한다. 요청과 함께 데이터 표현이 포함된다. 
    * PUT
        > 클라이언트는 PUT을 사용해서 서버의 기존 리소스를 업데이트한다.

    * DELETE
        > 클라이언트는 DELETE 요청을 사용하여 리소스를 제거한다. DELETE 요청은 서버 상태를 변경할 수 있다.
    
* PATCH
    > RESTful API를 사용할 때 **UPDATE**하는 부분에서 **PUT** or **PATCH**를 사용한다.
    * PUT : 자워 `전체` 교체(자원의 모든 필드 필요)

    * PATCH : 자원의 `부분` 교체(자원의 일부 필드 필요)

    * 차이점
        > UPDATE할 때 `PATCH`을 사용하기 위해서는 **자원 내의 `일부 필드`**만 있어도 된다.


* HTTP 헤더
    > 요청 헤더는 클라이언트와 서버 간에 교환되는 메타데이터이다.
    * 데이터
        > REST API 요청에는 POST, PUT 및 기타 HTTP 메서드가 성공적으로 작동하기 위한 데이터가 포함될 수 있다.
    * 파라미터
        > RESTful API 요청에는 수행해야 할 작업에 대한 자세한 정보를 서버에 제공하는 파라미터가 포함될 수 있다.
    
    ### 파라미터 유형
    * URL 세부정보를 지정하는 경로 파라미터

    * 리소스에 대한 추가 정보를 요청하는 쿼리 파라미터

    * 클라이언트를 빠르게 인증하는 쿠키 파라미터
    