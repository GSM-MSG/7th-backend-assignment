# 과제

* URI
* URL

<br>

## URI / URL
   
*결론은 URI는 URL의 의미를 품고있다*

* URI이란?
    * URI는 자원이 실제로 존재하는 위치를 가리킨다

* URL이란?
    * URL는 자원의 위치뿐만 아니라 자원에 대한 고유 식별자로서 URL을 의미를 포함한다
    
* 예시
    1. http://torang.co.kr/index
        -위의 예시에서는 torang.co.kr에서 index라는 경로를 나타내고 있다
        -서버에서는 해당 라우팅에 대한 알맞은 자원을 전송해줄 것이며 이는 자원의 실제 위치이므로 URL이다

    2. http://torang.co.kr/user/107
        -위의 예시에서는 torang.co.kr.dptj 107의 ID값을 가지고있는 자원을 식별하고있다. 따라서 http://torang.co.kr/user/까지는 자원의 실제 위치이기 때문에 URI임과 동시에 URL이며 끝의 /107 부분은 식별자 이므로 http://torang.co.kr/user/107은 URL(http://torang.co.kr/user/)을 포함한 URI라고 볼 수 있다

    3. http://torang.co.kr/user?id=107
        -위의 예시에서 마찬가지로 http://torang.co.kr/user 까지는 자원의 실제 위치를 나타내기 때문에 URL 이라고 할 수 있으며, 뒤의 쿼리스트링 식별자(?id=107)를 포함하여 URI라고 볼 수 있다
