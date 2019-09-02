# Restful API

### REST

REST는 representational state transfer의 약자로서 자원을 이름으로 구분하여 해당 자원의 상태를 주고 받는 것을 의미한다. 여기서 얘기하는 자원은 해당 소프트웨어가 관리하는 모든 것을 뜻하며 자원을 표현하기 위해 DB의 특성을 고려해 짓는다. 상태는 데이터가 요청된 시점에서 자원의 상태를 전달하고 이는 주로 JSON 혹은 XML의 형식을 따른다.

모든 자원이 서버에 존재하는 고유한 ID인 HTTP URI (Uniform Resource Identifier)를 통해 자원을 명시하고 HTTP method (POST, GET, PUT, DELETE)를 통해 자원을 처리한다.

REST가 필요한 이유은 애플리케이션 분리 및 통합, 다양한 클라이언트의 등장, 모바일 기기 통신 때문이다.

장점

- HTTP 프로토콜의 인프라를 그대로 사용하므로 별도의 인프라 구축이 필요없다.
- HTTP 프로토콜을 따르는 모든 플렛폼에서 사용이 가능하다.
- 여러가지 서비스 디자인에서 생길 수 있는 문제를 최소화한다.
- 서버와 클라이언트의 역할을 명확하게 분리한다.

단점

- 표준이 존재하지 않는다.
- 사용할 수 있는 메소드가 4가지 밖에 없다.
- 구형 브라우저에서 지원 안 할 수 있다.

### RESTful API

REST 기반으로 서비스 API 구현한 것이다. 사내 시스템들도 REST 기반으로 시스템을 분산해 확장성과 재사용성을 높여 유지보수 및 운용을 편리하게 하고 HTTP를 지원하는 프로그램 언어로 클라이언트, 서버를 구현할 수 있다.

이를 설계하기 위해서 지켜야 되는 규칙들이 있다.

1. URI 정보의 자원을 표현해야 한다.
2. 자원과 관련된 메소드들은 HTTP 메소드의 GET, PUT, POST, DELETE 등이 있다.
    - URI에 HTTP 메소드가 들어가면 안 된다.