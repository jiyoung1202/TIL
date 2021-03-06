##  Section 4. 비대칭키 암호

- 비대칭키 암호

  - 키 배송 문제

    - 대칭키 암호를 사용하려고 하면키 배송문제가 발생

    - 키 보내지 않으면 수산한 밥은 암호문 복호화 불가

    - 키 배송 문제 해결 위한 방법

      1) 키 사전공유에 의한 해결

      2) 키 배포 센터에 의한 해결(온라인 키 분배)

      3) Diffie-Hellman 키 교환에 의한 해결

      4) 공개키 암호에 의한 해결

  - 키 사전 공유에 의한 해결

    - 키 관리 기관(TA, Trusted Authrotiy)이 사전에 임의의 두 사용자에게 비밀 경로를 통하여 임의 키를 선택하여 전달하는 방법
    - 이 경우, TA와 네트워크 상의 모든 사용자 사이에 안전한 통로가 있어야함. 
    - 사용자들은 많은 키를 관리해야함
      

  - 키배포 센터에 의한 해결(온라인 키 분배)

    - 암호 통신이 필요해질 때마다 통신용 키를 키배포 센터(KDC, Key distribution center)라는 신뢰받는 제 3자에 의뢰해서 개인과 키 배포센터 사이에서만 키를 사저에 공유하는 것.

    - 키배포 센터에 의한 키배송 플로우
      1) 앨리스가 키배포 센터에 밥과 통신하고 싶다고 요청

      2) 키 배포 센터는 의사난수 생성기를 사용하여 세션키 생성. 이것은 앨리스와 밥과의 이번 통신만을 위한 일시적 키이다.
      3) 키배포 센터는 데이터베이스에서 앨리스의 키(KA)와 밥의 키(KB)를 꺼냄
      4) 키배포 센터는 앨리스의 키를 사용하여 세션키를 암호화 해서 앨리스에게 보냄
      5) 키배포 센터는 밥의 키를 사용하여 세션키를 암호화 해서 밥에게 보냄게 보냄

      6) 앨리스는 키배포 센터에서 온 세션키(앨리스의 키로 암호화되어 있음) 를 복호화해서 세션키를 얻는다.
      7) 앨리스는 세션키를 사용하여 밥에게 보낼 메일을 암호화 해서 밥에게 보낸다.
      8) 밥은 키 배포 센터에서 온 세션키를 복호화 해서 세션키를 얻음
      9) 밥은 세션키를 사용하여 앨리스에게 온 암호문을 복호화 한다.
      10) 앨리스와 밥은 세션키 삭제함

  - Diffie-Hellman 키 교환에 의한 해결

    - KDC 없이 대칭 세션키를 생성하는 것.
    - 대칭키를 만들기 전에, 두개의 수 p와 q를 선택해야함. p는 매우 큰 소수. 300자리가 넘는 십진수(1024비트)
    - 모듈러 계산 
      

  - 공개키 암호에 의한 해결 

    - 공개키 암호에서는 암호화키와 복화키가 분리되어있음.
    - 공개키와 개인키를 각각 별개로 만들수는 없다. 

