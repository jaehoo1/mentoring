UDP란 무엇일까?

다들 한번쯤 들어봤을법한 주제인데 TCP는 신뢰성 위주의 프로토콜 이었다면, UDP는 속도 위주의 통신 프로토콜이다.

TCP와 비교를 하였을 때 신뢰성이 낮으며 비 연결성이라는 특징을 가지고 있으며, 순서화 되지 않은 Datagram 서비스를 제공하고 있다.

TCP의 신뢰성 기반의 통신과는 다르게 UDP는 다양한 제한이 많이 없는데,

- 확인응답
- 순서제어
- 흐름제어
- 오류제어

위 4개의 기능이 존재하지 않는다고 봐도 무방하다.

이러한 UDP는 대신 실시간 응용 및 멀티캐스팅이 가능하여 스트리밍 서비스, VoIP, mVoIP의 분야에서 사용이 되고 있는데 이러한 서비스들은 속도가 중요하기 때문에 TCP통신을 사용하면 매우 비효율적이다.

이 외에도 TFTP, SNMP, DHCP, NFS, DNS, RIP, NTP, RTP등은 UDP 위에서 동작되는 다양한 프로토콜 혹은 응용분야이다.