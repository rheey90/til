# Two week project progress report

로그인과 로그아웃 기능을 구현하기 위해서 기존에는 세션을 사용하였다. 포스트맨에서 테스트를 했을 때는 세션 하나만 생성 되었지만 클라이언트와 연결 했을 때 세션이 다중으로 생성되어 이를 해결하고자 노력했으나 며칠 간 붙잡아도 결국 해내지 못 했다. 이에 대한 대안으로써 passport와 jwt 모듈을 사용했다. 다행히 passport와 jwt 사용에 대해 자세히 나온 블로그가 있어 코드를 작성하는데 큰 어려움은 없었다. passport는 authenticate 하는데 쓰이고 jwt는 토큰을 생성하는 역할을 하는데 jwt에서 토큰을 만들어주면 로그인할 때 passport는 이를 verify하여 authentification을 준다. 다만, 한 가지 좀 복잡했던 부분은 authenticate하는 미들웨어를 작성하는 것이었는데 우리 프로젝트 상황에 맞게 변형하다 보니 시간이 걸리게 됐다. 내일이 프로젝트 마지막 날인데 클라이언트와 토큰 부분을 맞추고 S3 사진이 클라이언트에 렌더가 된다면 무사히 마칠 것 같다.