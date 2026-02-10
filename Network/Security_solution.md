# 보안솔루션

## 방화벽

**IP** 와 **Port** 번호를 기반으로 rule set에 따라 패킷 필터링

외부사용자가 내부에 접근하는 것을 막음   
또한 내부사용자의 접근도 제어 가능

### 방화벽(Firewall) 한계
**Human Error** 
- 내부 네트워크에 존재하는 악의적인 공격
- 방화벽을 경유하지 않는 공격
  - ex) 내부 노트북을 외부에 가져감
- 방화벽 방어규칙에 포함되지 않는 공격
  
---
- 데이터에 실려있는 악성코드나 바이러스
  - 7계층 공격
- DoS와DDoS 공격

악성 코드 탐지 한계를 극복하기 위해 나온 시스템이 _IDS_

## IDS
침입탐지시스템(Intrusion Detection System)   
공격을 탐지하고 관리자에게 공격알림을 통해 공격에 대처 할 수 있게 해주는 보안시스템   
악성 코드 탐지

### HIDS
특정 컴퓨터에 IDS를 설치해 공격자를 탐지

호스트의 자원 사용 실태, 로그등을 분석하여 침입 여부 탐지

### NIDS
망(Zone) 내에서 이상한 패킷을 찾아냄   
Signature를 파악해 log를 남기거나 관리자에게 넘김   
스위치의 미러링포트를 이용하거나 TAP 장비를 통해 패킷 복사   
오픈소스NIDS : Snort

### IDS 탐지 방법

#### 오용탐지(Misuse Detection)
시그니처 기반의 탐지

- 오탐률(false positive)이 낮음   
- 미탐률(false negative)이 높음
  - 새로운 공격(Zero-Day Attack)에 탐지에 약함
#### 이상탐지(Anomaly Detection)
행동 기반의 탐지   
정상범위(normal)를 벗어나는 데이터를 
탐지   

- 미탐률(false negative)이 낮음   
- 오탐률(false positive)이 높음
  - 임계치 설정이 어려움
  
### 침입 탐지 시스템 한계

- 실시간공격을 막을 수 있으나 약하다.   
- 단편화(fragmentation), 난독화, 암호화와 같은 기술은 감지하기 어려움
## IPS

침입방지시스템(Intrusion Prevention System) 

방화벽(차단 O 감지 X) + IDS(차단 X 감지 O) 

이상행위탐지(anomaly detection)를 통해 알려지지 않은 공격 패턴에 대응   

**능동형**보안솔루션
- IDS : 탐지 후 사후에 조치를 취하는기술
- IPS : 예방적이고 사전에 조치를 취하는기술

현대 방화벽은 IPS급의 성능을 포함한다.

## WAF
Web Application Firewall(WAF)

**웹 컨텐츠(HTTP/HTTPS)** 를 분석하여 공격을 탐지및차단

## NAC
```
<<점검항목>>
    ❶ 정상적인장치/사용자인증확인
    ❷ 안티바이러스설치여부점검
    ❸ 보안패치설치여부점검
```

## VPN

암호화를 사용해 공중망을 사설망처럼 쓸 수 있게 함      
**VPN** = 캡슐화기술 = 터널기술

IPsec, SSL/TLS/DTLS을 사용하여 인터넷 망에서 암호화

## UTM

소규모 망에서 값 싸게 다양한 보안기능을 사용가능