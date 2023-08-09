# 과제

* Controller
* Service
* Repository

<br>

## Controller란?

* Controller는 MVC에서 C에 해당 하며 주로 사용자의 요청을 처리한 후 지정된 뷰에 모델 객체를 넘겨주는 역할을 한다
* 즉, 사용자의 요청이 진입하는 지점이며 요청에 따라 어떤 처리를 할지 결정을 Service에 넘겨준다 / 그후 Service에서 실질적으로 처리한 내용을 View에게 넘겨준다

### Controller를 사용하는 이유

* 대규모 서비스중 A서비스, B서비스, C서비스 등등이 있다고 하면, 이 ㅁ낳은 종류의 서비스를 한 클래스를 만들어서 꽉꽉 몰아 처리할 게 아니라 COntroller라는 중간 제어자를 만들어서 A서비스에 대한것은 A-Controller가 맡고 B서비스는 B-Controller 이런식으로 역할에 따라 설계를 하고 코딩을하면 개발비용이나 유지보수비용이 대폭 줄어들기 때문에 Controller를 사용한다고 한다

### Spring에서의 Controller사용법

* 스프링에서의 컨트롤러를 지정해주기 위한 어노태이션은 @Controller와 @RestController가 있다

    1. @Controller(Spring MVC Controller)
    * 전통적인 Spring MVC의 컨트롤러인 @Controller는 주로 View를 반환하기 위해 사용한다 / 하지만 @ResponseBOdy 어노테이션과 같이 사용하면 RestController와 똑같은 기능을 수행할 수 있다
    ```
    @Controller
    public class Controllerprac {
        @GetMapping("/home") // home으로 Get요청이 들어오면
        public String homepage(){
            return "home.html"; // home.html생성
        }
    }
    ```

    <br>

    2. @RestController(Spring Restful Controller)Permalink
    * RestController는 Controller에서 @ResponseBody 어노테이션이 붙은 효과를 지니게 된다 / 즉, 주용도는 JSON/XML 형태로 객체 데이터 반환을 목적으로 한다
    ```
    @RestController // JSON으로 데이터를 주고받음을 선언한다
    public class ProductRestController{

        private final ProductService productService;
        private final ProductRepository productRepository

        // 등록된 전체 상품 목록 조회
        @GetMaping("/api/products")
        public List<Product> getProducts() {
            return productRepository.findAll();
        }
    }
    ```

<br>


## Service란?

1. Client가 Request를 보낸다
2. Requrest URL에 알맞은 Controller가 수신 받는다
3. Controller는 넘어온 요청을 처리하기 위해 Service를 호출한다
4. Service는 알맞을 정보를 가공하여 Controller에게 데이터를 넘긴다
5. Controller는 Service의 결과물을 Client에게 전달해준다

* Service가 알맞은 정보를 가공하는 과정을 '비즈니스 로직을 수행한다'라고 한다
* Service가 비즈니스 로직을 수행하고 데이터베이스에 접근하는 DAO를 이용해서 결과값을 받아온다

* 예시코드
```
@Service // 1
@RequiredArgsConstructor
public class BoardService {
    private final BoardRepository boardRepository; // 2

        @Transactional
        public BoardResponseDto createPost(BoardRequestsDto requestsDto) {
            Board board = new Board(requedstsDto);
            boardRepository.save(board); // 3
            return newBoardResponseDto(board);
        }
}
```
* 1 : **@Service**는 Service로 지정해주는 어노테이션이다
* 2 : Service와 인접한 계층은 Repository이므로, **BoardRepository** 객체를 통해 데이터를 데이터베이스에 저장하거나, 테이터베이스로부터 데이터를 가져온다 
    * boardRepository 객체의 **save** 함수를 호출해 board 객체 데이터를 데이터베이스에 저장하도록 한다
<br>

## Reposity란?

* Entity에 의해 생성된 데이터베이스에 접근하는 메소드들을 사용하기 위한 인터페이시이다
* @Entity라는 어노테이션으로 데이터베이스 구조를 만들었다면 여기에 CRUD를 해야하는데 이것을 어떻게 할 것인지 정의해주는 계층이라고 생각하면 편하다