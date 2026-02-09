# TCP Header

TCP의 헤더는 기본 20 바이트이며 옵션까지 최대 60바이트를 채울 수 있다.

- Source port address - 16bits
- Destination port address - 16bits
  - TCP헤더의 목적지의 port번호가 _SAP(Service Access Point)_ 이다.
- Sequence number - 32bits
  - SN은 이전에 사용된 AN을 사용한다.
- Acknowledgement number - 32bits
  - AN은 이전에 사용된 SN + DataSize가 와야 한다.
- HLEN - 4bits
- Reserved - 6bits
- flag - 6bits
  - urg
    - tcp의 우선순위가 바뀜을 표시
  - ack
    - syn의 확인응답
  - psh
  - rst
  - syn
  - fin
- window size - 16bits
  - 여유 데이터 사이즈를 보냄으로 **흐름제어**
- Checksum - 16bits
- Urgent pointer - 16bits
- Options & padding


# UDP Header 

UDP헤더는 8바이트 고정이다.

- Source port number - 16bits
- Destination port number - 16bits
- Total Length - 16bits
  - TL - 8bytes(Header) = DataSize
- Checksum - 16bits 

# IP Header

IP헤더

- VER
- HLEN
- Servie type
- Total Length
- Identification
- flag
  - reserved
  - Don't Fragment
  - More Fragment
- Fragmentation offset
- Time To Live
- Protocol
- Header Checksum
  - 다른 Checksum과 달리 헤더만 오류검출
- Source IP Address
- Destination IP Address