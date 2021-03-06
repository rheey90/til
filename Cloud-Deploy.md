# Cloud Deploy

웹 앱을 다 만들고 사용자들이 사용할 수 있도록 배포를 해야 한다. 먼저 다양한 컴퓨터 환경에서 웹 앱이 작동할 수 있도록 팀원 간 충돌 없이 각자의 코드가 각자의 환경에서 잘 작동하는지 확인하고 프로젝트를 요청한 클라이언트의 요구들이 충족 되었는지 클라이언트와 상의하여 실제로 웹 앱이나 서비스를 사용자들 대상으로 배포하게 된다.

배포를 할 때 사용자들이 웹 앱을 사용할 수 있도록 본인의 컴퓨터를 서버로 만들어서 실행할 수 있지만 외부인에게 컴퓨터가 그대로 유출 될 수 있고 서버를 끄게 되면 앱 자체를 못 쓰게 됨으로 여러가지 문제를 야기할 수 있다. 그 대안으로 클라우드를 통해 사용자들에게 배포할 수 있는 방법이 있다. 클라우드 서버 서비스를 제공하는 업체는 대표적으로 아마존, 마이크로소프트 등이 있는데 여기선 아마존이 제공하는 Amazon Web Service (AWS)를 예로 쓸 것이다.

### 클라이언트 배포

먼저 사용자 측에 클라이언트를 배포하기 위해서 사용자들이 웹 앱이나 서비스를 이용하는데 필수적인 파일들을 선정하여 build란 폴더에 담아 사용자가 한 번에 가져갈 수 있도록 포장을 한다. Build를 배포하기 위해서 아마존에서 제공하는 Amazon S3 클라우드를 사용할 수 있다. Amazon S3는 간단한 웹 서비스 인터페이스를 가지고 있으며 웹 어디에서나 데이터를 저장하고 가져올 수 있는 기능을 제공한다. 그럼 Amazon S3가 어떤 종류의 저장소를 가지고 있는지 그리고 어떤 장점들을 지니고 있을까?

Amazon S3는 일반 목적, 비주기적 접근, 아카이브 등의 세 가지 종류의 저장소를 제공한다. 데이터의 생애주기를 관리하기 위해서 Amazon S3는 수정 가능한 생애주기 정책들을 가지고 있다. Amazon S3 사용자들은 생애주기 정책을 통하여 코드를 수정할 필요없이 데이터를 자동적으로 목적에 알맞는 저장소에 옮길 수 있다. 데이터 접속 권한을 통제하기 위해 Amazon S3는 여러 종류의 접근 권한, 통제, 암호화 옵션들을 제공한다.

Amazon S3의 장점들은 다음과 같다. Amazon S3는 데이터를 담을 버킷을 제공하는데 이의 용량은 거의 무제한이다. 각 객체마다 5TB란 어마어마한 데이터를 저장할 수 있게 해준다. 그리고 저장된 데이터를 수정 및 다운로드 권한을 자유롭게 설정할 수 있고 REST와 SOAP 인터페이스를 사용하기 때문에 어느 인터넷 개발 툴킷과 작업이 용이하다. 그러므로 위에서 언급한 포장 된 build 파일들을 Amazon S3가 제공하는 버킷에 담아 사용자들이 다운로드 받을 수 있다.

### 서버 배포

서버 앱을 배포하기 위해서 Amazon EC2란 서비스를 통해 node app에 접속해서 API를 가져갈 수 있다. Amazon EC2는 AWS 클라우드 인프라에서 앱을 구동하기 위해 사용자를 돕는 가상 서버를 운영한다. Amazon EC2를 사용하여 CPU, 메모리, 저장소, 네트워킹 등을 다양한 설정을 가진 인스턴스를 사용할 수 있다. 인스턴스 유형을 설정한 후 서버를 배포할 수 있는데 Amazon EC2는 연산, 메모리, 저장소 등이 최적화가 뛰어나 용이하다. 그러므로 안정적으로 서버를 배포 및 수정을 할 수 있고 고유한 IP 주소를 제공 해줘 인스턴스를 지속적으로 돌리고 보안이 우수하다는 장점을 지니고 있다. 또한 Amazon EC2는 elastic IP를 제공해 주는데 이는 동적 클라우드 컴퓨팅을 위해 만들어졌고 주소를 계정의 다른 인스턴스에 신속하게 다시 매핑하여 인스턴스나 소프트웨어의 오류를 덮을 수 있다.

### 데이터베이스 관리

아마존은 데이터베이스 관리 솔루션으로 Amazon RDS란 서비스를 제공한다. 이는 사용자가 선호하는 데이터베이스 엔진을 고를 수 있도록 다양한 엔진을 보유하고 있고 사용자의 니즈에 따라 최적화된 인스턴스 유형을 제공한다. 이는 Amazon EC2와 마찬가지로 인스턴스의 유형은 CPU, 메모리, 스토리지 및 네트워킹 용량 등의 다양한 조합으로 구성되며 적절한 리소스 조합을 선택할 수 있는 유연성을 제공한다.