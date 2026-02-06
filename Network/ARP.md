# ARP Packet

ARP Header   
type = 0806이면 ARP헤더로 구성되어 있다.

---

### ARP Request

3계층 프로토콜   
Mac Address 를 알아내는 프로토콜   

Operation = 1

DATA
- 송신지 Mac
- 송신지 IP
- [수신지 Mac] - 빈칸(0x000000000000)
- 수신지 IP
 
Destination: ff:ff:ff:ff:ff:ff - Broadcast통신

---

ARP reply

0806 arp
Operation = 2 이면 reply

 DATA
- [송신지 Mac] - 채워줌
- 송신지 IP
- 수신지 Mac
- 수신지 IP


## ARP 통신예시

   
전제조건:
- 192.168.1.10 -> 192.168.1.20 - 내부망통신
- 1.30과 1.10은 통신이력이 있음 => 1.30의 ARP Cache에 1.10의 IP와 MAC이 있음   

ARP Cache Table 확인   
ARP Request 수신 MAC 주소를 Broadcasting으로 전송
1.30의 ARP Cache Table의 1.10 aging time이 끝나기전 전송받음
agaiung time 갱신후 IP는 다르므로 Reply는 나가지 않음

전제조건:
- 192.168.1.10 -> 192.168.1.20
- 1.30과 1.10은 통신이력이 없음

1.30이 1.10의 데이터를 받은 후 ARP Cache Table에 없으므로 폐기
aging time 갱신안하고, IP도 다르므로 Reply는 나가지 않음

1.20은 ARP Cache Table에 1.10의 Mac Address를 신규 등록하고 Reply를 보낸다.

Reply Unicast통신

1.10은 Reply를 받고 APR Cache Table에 1.30의 정보를 등록

---
Reply의 MAC주소를 속여 다른 곳과 통신하게 만드는 공격이 오기도 함

Mac 주소는 가끔 변경을 한다.   
LAN카드를 부팅하면 신호가 나감