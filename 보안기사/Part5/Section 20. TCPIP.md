## Section 20. TCP/IP

- ARP 요청
  
  - 특정 IP 주소에 대한 물리 주소를 요구
  
- ICMPv4(Internet Control Message Protocol version 4)
  - 호스트가 다른 라우터나 다른 호스트가 동작하고 있는지 알 필요가 있을때 사용
  - 크게 ''오류보고 메세지''와 ''질의 메세지''가 있다.
  - 오류보고 메세지 : 라우터(목적지)나 호스트가 IP 패킷을 처리하는 도중에 탐지하는 문제를 보고한다. 질의 메세지는 쌍으로 생성되는데 호스트나 네트워크 관리자가 라우터나 다른 호스트로부터 특정 정보를 획득하기 위해서 사용
  
- IPv6
  - 기존 IPv4의 32비트 주소길이를 4배 확장한 128비트 주소길이를 사용.
  - IPv4는 4부분 IPv6는 8부분 16진수
  - IPv6로 변환 하기 위해서 이중스택을 채택하면, 둘다 동시에 지원하는 것을 뜻한다.
  
- TCP
  - 3-way Handshakeing
    - SYN --> SYN + ACK --> ACK (연결설정)
    
    - FIN --> FIN +ACK --> ACK(연결종료)
    
      
  
- 잘알려진 포트는 클라이언트 측이 아니라 서버 측 응용에 주로 배정

- 포트 번호 : 0번 ~65535

  - 0~1023 : 잘알려진 포트(서버측 응용)
  - 49152~65535 : 임시포트 (클라이언트 사용 후 반납)

- IPv4 주소

  - 클래스 A

    "0"이 첫번째 비트인 IP 주소

  - 클래스 B

    "10"이 첫번째 두 비트인 IP주소

  - 클래스 C

    "110"이 첫번째 세 비트인 IP 주소

  - 클래스 D

    "1110"이 처음 네비트인 IP주소

  - 클래스 E

    "1111"이 처음 네 비트인 IP주소 - 추후 사용 위해 예약됨



- BlackNurse 공격

  - ICMP 프로토콜에 대한 Dos 공격

  - 목적지 도달 불가(Destination Unreachable - ICMP Type 3)공격

  - CPU를 High load 시키는 것.

    

- 프로토콜 세부기능

  - ICMP Ping : 네트워크 장치의 동적 상황 검사
  - ICMP Redirection Message : Routing Table 변경 요청
  - ICMP Echo Request : IP 통신위한 집단 데이터 전송
  - IGMP : Multi-Casting 제어, 그룹 탈퇴 및 추가/삭제 등을 동적으로 수행하기 위한 프로토콜로 사용



- ICMP 메세지 종류

  1) 오류보고 메세지

  - 목적지 도달 불가 메세지(Destination Unreachable Message) - 3 Type

    : 패킷이 중도에 폐기 될떄 사용되는 메세지

  - 시간초과 메세지(Time Exceeded Message)

    : 패킷이 목적지에 전달되기 전에 시간 초과로 폐기되는 경우

  - 파라미터 문제 메세지(Parameter Problem Message)

    : 헤더 부분에 문제가 발생한 경우에 사용되는 메세지

  - 근원지 억제 메세지(Source Quench)

    : 패킷 흐름을 위해 사용되는 메세지

  - 재지정 메세지(Redirection Message) - 5 Type

    : 동일 네트워크의 다른 라우터로 라우팅하는 것이 더 효율적이라고 판단되면 라우팅 경로를 변경하도록 ICMP 재지정 메세지를 호스트로 전송

  2) ICMP 쿼리(Query) 메시지

  - 에코 요청과 응답 메세지(Echo Request and Reply)

    : 두 호스트 사이에 통신이 가능한지 검사할 떄 사용되는 메시지

    Echo Request - 8 Type

    Echo Reply - 0 Type

  - 타임스탬프 요청과 응답 메시지(Timestamp Request and Reply)

    : 패킷 전송 시간 측정 메세지

  - 주소 마스크 요청과 응답 메시지(Address Mask Request and Reply)

    : 호스트가 서브넷 마스크 값을 얻을 때 사용하는 메시지

  - 라우터 요청과 광고 메시지(Router Solicitation and Advertisement)

    : 호스트가 네트워크 정보를 알고 싶을 때 사용하는 메시지

  

- ICMP 메세지 특징
  - 127.0.0.0 이나 0.0.0.0과 같은 특별한 주소를 가진 데이터 그램에 대해서는 오류 메세지 생성 되지 않음
  - ICMP오류 메시지에 대해서는 ICMP 오류 메시지가 생성되지 않는다
  - ICMP 오류 메시지를 전달하는 데이터 그램에 대해서는 ICMP 오류메시지가 생성되지 않는다. 
  - 처음 단편이 아닌 단편화된 데이터 그램에 대해서는 ICMP 오류 메세지가 생성되지 않는다. 
- TCP/IP 특징
  - 전 세계 IP Address 관리하는 곳은 IANA
  - 주소 클래스는 네트워크 ID와 호스트 ID로 구성되어 있음
  - 애니캐스트(Anycast) 다중 송신자와 그룹내에서 가장 가까운 곳에 있는 수신자 사이의 통신을 말한다.
- 절반폐쇄(4-way Handshake)
  - FIN(x,y)
  - ACK(y,x+1)
  - FIN(z,x+1)
  - ACK(x+1,z+1)