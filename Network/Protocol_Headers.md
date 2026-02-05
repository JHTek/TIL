# TCP Header

TCP의 헤더는 기본 20 바이트이며 옵션까지 최대 60바이트를 채울 수 있다.

- Source port address - 16bits
- Destination port address - 16bits
- Sequence number - 32bits
- Acknowledgement number - 32bits
- HLEN - 4bits
- Reserved - 6bits
- flag - 6bits
  - urg
  - ack
  - psh
  - rst
  - syn
  - fin
- window size - 16bits
- Checksum - 16bits
- Urgent pointer - 16bits
- Options & padding


# UDP Header 

UDP헤더는 8바이트 고정이다.

- Source port number - 16bits
- Destination port number - 16bits
- Total Length - 16bits
- Checksum - 16bits 

# IP Header