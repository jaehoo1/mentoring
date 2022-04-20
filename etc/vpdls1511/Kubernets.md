# Kubernetes

MSA관련해서 공부를 하다보니 한번쯤 들어본 Kubernetes,이는 무엇일까

딱 한마디로 정리를 하자면, 분산된 시스템(애플리케이션 컨테이너)를 탄력적으로 실행하기 위한 프레임워크라고 할 수 있을것 같다.

왜냐하면 프로덕션 환경에서 애플리케이션을 실행하는 컨테이너를 관리하고, 가동이 중지된 시간이 없는지 확인을 해야한다. 이 때 만약 한 컨테이너가 다운이 된다면 이 컨테이너를 다시 시작해야 하는데, 이럴때 도움을 주는것이 쿠버네티스 이다.

## 특징

### 서비스 디스커버리와 로드 밸런싱

DNS이름을 사용하거나 자체 IP 주소를 사용하여 컨테이너를 찾아낼 수 있으며, 이 컨테이너들의 네트워크 트래픽을 파악하여 적절하게 분배해줄 수 있다.

### 스토리지 오케스트레이션

로컬 스토리지, 공용 클라우드 공급자 등 원하는 저장소 시스템을 자동으로 탑재가 가능하다.

### 자동화된 상태 확인과 셀프 힐링

배포된 애플리케이션의 구성 요소들과 노드들을 지속적으로 모니터링 하며, 어느 한 컨테이너에 문재발생 혹은 노드단에서 장애가 발생할 경우 자동으로 해당 애플리케이션 컨테이너를 문제가 없는 다른 노드로 스케줄링 해주거나, 다시 구동시킨다. 이 때 컨테이너는 특성상 재구동이 빨라 운영자의 모니터링 없이도 장애에 자동으로 대응할 수 있다.

여기에는 `롤아웃과 롤백,` `빈 패킹`, `복구`의 작업이 들어가게 된다.

`롤 아웃과 롤백`은 배포된 컨테이너의 현재 상태를 원하는 상태로 설정한 기간에 따라 변경할 수 있으며
`빈 패킹`은 각 컨테이너를 노드에 맞추어 리소스(CPU, RAM)를 잘 사용할 수 있도록 해준다.
마지막으로 `복구`는 셀프힐링과 같은 역할을 한다.

### 시크릿과 구성 관리

OAuth 토큰, 암호, SSH키 와 같은 중요한 정보를 저장하고 관리할 수 있다.